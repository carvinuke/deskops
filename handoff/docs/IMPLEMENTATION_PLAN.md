# Implementation Plan & QA Checklist

## Build order

### Milestone 1 — frame and persistence

- One `index.html`; inline CSS/JS/data.
- Dashboard shell, top bar, page routing, common button/field/dialog/toast components.
- Root state; load/save/reset with localStorage try/catch.
- Use no external dependencies and do not fetch data.
- Set and verify `document` UI is rendered from `file://` without a web server.

### Milestone 2 — ticket lifecycle

- Seed environment, 10 starter tickets and deterministic IDs.
- Ticket detail, claim/unclaim, action history and active-ticket context.
- Per-ticket objective checker and partial-progress state.
- Hint ladder with reveal index.
- Close modal, resolution notes, confirm penalty before unresolved close, score update, Past Tickets.
- Build unit-like scenario checks as normal functions and manually run all ten ticket cases.

### Milestone 3 — core tools

- Directory + search/profile/actions.
- Server Room + Overview/Topology/Devices/Servers, using the same central entity state.
- Remote Desktop picker + simulated desktop + core apps.
- Mail Admin and Mail Security.
- Documentation search.
- Ensure tool updates change ticket status without reload; ensure leaving/reopening a tool preserves state.

### Milestone 4 — visual polish and secondary features

- Match the visual reference proportions, whitespace, thin borders and compact typography.
- Keyboard focus, Escape, click-outside popovers, mobile tabs/stacked panes.
- Past Tickets answer view; settings, name, hints toggle and reset.
- P1 tools if time; no dummy links or inactive controls.

### Milestone 5 — offline release QA

Test with browser devtools network disabled and by opening from a local file path. The app should have zero network attempts. Validate on desktop and narrow viewport. Refresh after performing mutations to check persistence. Corrupt saved JSON manually to test graceful recovery. Check each ticket from clean seed state before attempting another case.

## Manual test plan

### Startup and offline

- [ ] File opens directly from `index.html`; no server required.
- [ ] No login or any credential prompt at startup.
- [ ] No external requests, CDN, fonts, imported scripts or image loads.
- [ ] A first-run message can be dismissed into the real dashboard.
- [ ] If localStorage is blocked, play remains possible and a clear message is shown.

### Queue and lifecycle

- [ ] Queue shows critical/high/medium/low in correct order and a priority word.
- [ ] Ticket references and requesters are visible; selecting a row opens details.
- [ ] Claim moves the ticket to My Queue; unclaim returns it.
- [ ] Relevant tool changes update the checker when clicked; no reload is needed.
- [ ] Hints reveal one step at a time and do not alter score.
- [ ] Complete ticket shows resolved banner; unresolved close previews exact penalty.
- [ ] Canceling close does not mutate status or score.
- [ ] Closing adds the ticket to Past Tickets with model answer and action history.

### Ticket scenarios

- [ ] INC-1042: unlock Maya; reset-only action is not accepted as the fix.
- [ ] INC-1043: unlock and reset Evan; one step by itself is partial only.
- [ ] INC-1044: group membership changes access; password reset does not.
- [ ] INC-1045: Floor 3 switch restores the floor and is shown healthy.
- [ ] INC-1046: trace leads to the matching quarantine item; release changes status to Delivered.
- [ ] INC-1047: mailbox quota is inspected and safely corrected.
- [ ] INC-1048: suspicious rule is routed to Security; destructive routine deletion is not rewarded.
- [ ] INC-1049: print server / spooler fix beats rebooting an individual printer.
- [ ] INC-1050: VPN profile fix restores remote access.

### Persistence and safety

- [ ] Points/history persist after refresh and browser restart.
- [ ] Environment mutations persist; user can't accidentally reset by changing screens.
- [ ] Reset is confirmation-gated and clears all game progress.
- [ ] No command entered in simulated Terminal is executed by the host OS.
- [ ] No genuine email, user account, network, file system or remote machine is accessed.

### Layout and accessibility

- [ ] 1366×768, 1024px and mobile/narrow layouts remain usable.
- [ ] Wide layout supports split view; narrow layout uses tabs/stack.
- [ ] All action buttons have visible labels or accessible names.
- [ ] Dialogs and menus work using keyboard; Escape closes menus without losing draft text.
- [ ] Focus ring visible; priority and online/offline are not color-only.
- [ ] No dead controls, dead links, placeholder content or fatal console errors.

## Common failure modes to avoid

- Building a lovely static screenshot that does not respond to clicks.
- Using a remote CDN icon library / Google Font that breaks offline use.
- Splitting data into JSON files and loading via fetch; this can fail from `file://`.
- Making each tool maintain duplicate disconnected state (e.g. Directory shows unlocked while ticket still thinks locked).
- Checking only whether any action occurred instead of checking the correct user, entity and state.
- Allowing “close” to erase incomplete work without telling the player.
- Calling real terminal commands or attempting to reach the host machine.
- Generating random initial states that make a ticket unsolvable or non-reproducible.
