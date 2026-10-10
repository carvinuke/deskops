# DeskOps Lab — build plan

## Context
The uploaded handoff (`DeskOps_Lab_Claude_Handoff.zip`) specifies **DeskOps Lab**: an offline IT help-desk simulator in a single `index.html`. The player picks a ticket, claims it, diagnoses and fixes it in simulated admin consoles, verifies, closes, gets a score and reviews the work. The repo `carvinuke/deskops` is empty. Weekly usage is nearly gone, so **today** we only save the handoff and this plan to GitHub (this container gets wiped before Sunday). **Sunday** we build the game, P0 first.

Sources of truth, committed under `handoff/`: `CLAUDE_BUILD_PROMPT.md` (P0/P1/P2), `docs/GAME_DESIGN_SPEC.md` (screens, scoring, state, acceptance §10), `docs/TICKET_LIBRARY.md` (the 10 cases), `docs/IMPLEMENTATION_PLAN.md` (QA checklist) and `references/*.png` (layout targets; open them with Read before writing CSS).

Spec conflicts, resolved:
- **Ticket numbers:** TICKET_LIBRARY wins (INC-1042…1051). After 1045, the IMPLEMENTATION_PLAN checklist is off by one and leaves out the Wi-Fi case. The dashboard mockup uses a third numbering.
- **Seed clash:** 1042 needs Maya locked with correct groups, but 1044 needs her signed in and missing `Finance-Share`. Similarly, 1043 has Evan locked while 1051 has him working from home. Fix: a ticket can declare `after` + `arrive(s)`. **1044 arrives once 1042 is closed or escalated**, and its `arrive` removes Finance-Share. **1051 arrives after 1043.** So 8 tickets at start, 10 in total.

## Today (right after approval): no game code
1. `git symbolic-ref HEAD refs/heads/main`, `git commit --allow-empty -m "Initial commit"`, `git push -u origin main`.
2. `git checkout -b claude/weekly-usage-plan-t6vsgx`.
3. Unzip into a fresh scratchpad dir and copy `deskops-simulator-claude-handoff/` to `handoff/`. Copy this plan to `PLAN.md`.
4. Commit, then `git push -u origin claude/weekly-usage-plan-t6vsgx`. Open a **draft PR into main** and subscribe to it. No timed check-ins (saves usage). Stop.

## Sunday: build
Spec rules:
- One `index.html` with all CSS, JS, SVG and data inline.
- No fetch, modules, CDN, web fonts, login or network. It must work from `file://`.
- `localStorage` inside try/catch, falling back to memory with a small banner.
- Original branding (DeskOps Lab, Northstar Office Group, `northstar.local`, `@northstar.example`). No copied text or assets.
- Light, quiet, blue-accent UI using the spec §3 tokens.

**After every milestone: commit, push and tick its box below.** If usage runs out mid-build, the next session resumes from these boxes and `git log`.

### Architecture (one file, split into marked sections)
Write a skeleton first, then fill each section with Edits of at most ~400 lines. Expect ~3k lines in total.
```
<style>  tokens · base · topbar · dashboard · ticket · tools · consoles · desktop · dialogs · responsive · reduced-motion
<body>   <header id=topbar>  <main id=app>  <dialog id=dlg>  <div id=toasts aria-live=polite>
<script> 1 SEED · 2 STATE/SAVE · 3 ENV mutators · 4 SCENARIOS · 5 LIFECYCLE/SCORING · 6 VIEWS · 7 EVENTS · 8 SELFTEST
```
- **State:** one JSON-safe root object, `S = {v:1, profile, settings, users, net:{devices,servers}, workstations, mail:{mailboxes,messages,quarantine,rules}, assets, tickets:{ref:{status,assignee,hints,notes,penalties,log}}, log, ui}`. Static ticket text, hints, model answers and objectives live in a `TICKETS` const in code. Only fields that change are saved, so fixing ticket text never breaks a save.
- **Seed and save:** `seed()` is deterministic (no randomness). `load()` validates `v` and the shape; a corrupt or unknown save becomes a fresh seed plus a toast. `save()` runs after every mutation.
- **Testable logic:** ENV mutators and scenario checks take `s` as a parameter (no DOM, no globals), so `selfTest()` can run them on a fresh `seed()`. The UI calls them through a single `act(tool, entity, action, fn)`. It mutates the state, logs `{time, tool, entity, action, ticket}`, applies penalty rules, saves and re-renders. No console keeps its own copy of the state.
- **Computed on the fly, never stored:**
  - "resolved" = assigned and its check is complete
  - a workstation is online = powered, its floor switch is up, and it is in the office or remote-connected
  - a mailbox can receive mail = usage under 98% of quota
  - dashboard and overview counts
- **Rendering:** template strings plus `esc()`. `render()` rebuilds `#app`, then restores focus and caret through `data-key`.
- **Events:** one delegated `click` handler (`[data-act]` → `ACT[name](dataset)`), one `input` handler, and Enter/Space on `[role=button]`.
- **Use the platform:** `<dialog>.showModal()` for every dialog (focus trap and Esc for free). The Popover API (`popover` attribute) for the Tools, Options and profile menus (click-outside and Esc for free). Close-notes drafts live in `S.ui.drafts`, so Esc never loses them.

### Seed data (TICKET_LIBRARY "Shared seed environment", plus these)
- **People, groups and workstations:** exactly as listed.
  - Floors: Maya F2 (ext 4421), Priya F1, Jordan F1, Leo F2, Avery F2.
  - Evan's `NS-SALES-008` is remote (at home) with VPN profile `Northstar-Legacy`.
  - Two Floor-3 machines with no tickets, so the 1045 outage visibly takes hosts offline in Remote Desktop.
- **Infrastructure:** as listed, plus printers `PRN-F1-01` and `PRN-F2-01`. The `PRINT01` spooler is Stopped, so that server shows Degraded (4/5 healthy).
- **Mail:**
  - Priya's legitimate supplier message (Quarantined) and one phishing item.
  - The trace also holds Delivered, Failed (Avery's bounce) and Pending messages.
  - Avery's mailbox is at 4.95/5 GB with archive off.
  - Leo has a rule forwarding all mail to `external-archive@outside.example`, plus one harmless rule.
- **10 knowledge base articles:** lockout, password reset, share access, floor outage triage, Wi-Fi profile, mail quarantine, mailbox quota, suspicious inbox rule, print spooler, VPN profile.

### Scenarios
Each objective is `{ok: s => bool, done, todo}`. The `todo` text doubles as the blocker line in the close dialog. Verify flags (sign-in test, ping, re-run trace, test page, test mail, share/VPN check) reset if their entity changes again, so an out-of-date check never counts.

| Ticket | Complete when | Wrong action |
|---|---|---|
| 1042 Maya locked · High | `mchen` unlocked + enabled | password reset on a locked user → "still locked" (general Directory rule) |
| 1043 Evan locked+expired · High | unlocked · password reset · must-change set · Test sign-in passed afterwards | — |
| 1044 Maya share · Med (after 1042) | in `Finance-Share` · "Ask user to sign out & back in" done after the change | password reset: "doesn't change permissions" |
| 1045 Floor 3 down · Crit | Floor 3 Switch online | reboot Edge Router/Firewall −4 |
| 1046 Jordan Wi-Fi · Med | broken profile forgotten · on `Northstar-Staff` · `ping 10.0.0.1` OK after reconnecting | reboot Edge Router −4 |
| 1047 Priya quarantine · High | supplier mail released · trace re-run shows Delivered | release the phishing item −6 |
| 1048 Avery quota · Med | can receive (archive on or quota 10 GB) · test message delivered | — |
| 1049 Leo rule · Crit · security | rule inspected · rule not deleted · escalated to Security with notes | delete rule (warned first) −4, no bonus |
| 1050 PRINT01 · High | spooler running (restart service or reboot server) · test page printed | printer reboot: reason explained, no fix |
| 1051 Evan VPN · High (after 1043) | profile `Northstar-Staff` · connected · internal share or ping verified | — |

Penalties: each ticket lists `penalties: {actionKey: [pts, why]}`. `act()` records the penalty on every **assigned** ticket that lists that key, once per key.

### Scoring (spec §5)
- Base points: Low 10, Medium 15, High 22, Critical 30.
- Notes bonus, 0–3 points: 40+ characters, names the user or asset, says verified/confirmed/tested.
- Subtract any penalties.
- Escalation: to Security on the security case +12; any other escalation −8.
- Closing an unresolved ticket: −10 for Low/Medium, −15 for High, −20 for Critical.
- Each ticket's total is clamped to −20…+42. Hints are free.

The close dialog shows a preview; Past Tickets shows the breakdown.

### Screens (P0)
- **Top bar:** glyph + "DeskOps Lab", Dashboard, Tools (4 groups), Shift Guide, points, and a profile menu (name, hints toggle, split toggle, Past Tickets, Reset progress with confirm, "LOCAL LAB · ALL SYSTEMS SIMULATED"). First run shows "Welcome to your first shift" → Start shift.
- **Dashboard:** greeting and points, My Queue, Ticket Queue (priority word + color, then oldest first), Systems overview, Recent activity. Empty state links to Past Tickets.
- **Ticket page:** layout per `mock-ticket-detail.png`.
  - Assign/Return. Options menu: Escalate to Security, Return to queue. Open Tools.
  - Hint: one at a time, then the model answer.
  - Check Fix: done and remaining items plus a nudge; a "Solution complete" banner when finished.
  - Close: notes up to 600 characters, at most 3 blockers, penalty preview, "Close Anyway". Cancel changes nothing.
  - Work notes and the action log.
  - Close and Escalate require the ticket to be assigned.
- **Split view** when a tool is opened from a ticket: ticket column next to the console at ≥1100px; "Ticket | Tool" tabs below that width.
- **Directory:** search by name, username or email. Tabs: Profile, Groups, Licenses, Devices, Authentication, Mailbox. Actions:
  - Unlock/Lock, Enable/Disable
  - Reset password (lab temp password; must-change on by default)
  - Reset MFA (with confirm), Send code, Test sign-in
  - Add/remove group, Ask to sign out & back in
- **Server Room:** every action takes effect immediately (no timers).
  - Overview
  - Topology: inline SVG, fixed positions, nodes clickable and focusable, status shown in words
  - Devices: Check ISP, Reboot, Power on/off
  - Servers: CPU/memory bars, View services, Restart service, Reboot, Send test page
- **Remote Desktop:**
  - Picker searchable by hostname, tag or owner. Offline rows say why.
  - Lab-credential screen with no password field.
  - Desktop: session bar (host + owner), maximize, Disconnect, taskbar clock.
  - Four apps:
    - Network & Wi-Fi settings
    - VPN Client
    - File Explorer
    - Terminal: only `help ipconfig ping nslookup whoami hostname gpupdate sfc cls`, with scripted output based on state and no eval. Anything else gets "Command not recognized in this lab".
- **Mail Admin:**
  - Message Trace: sender, recipient, status and time filters.
  - Mailbox Admin: usage bar, archive, quota, retention, Send test message.
  - Inbox Rules: warning on external forwarding, View details, Delete (with a warning).
- **Mail Security:** quarantine search; Release / Keep blocked / Report to Security. Releasing the phishing item asks for confirmation and shows the consequence.
- **Documentation:** live, case-insensitive search. Each article shows steps, tool tags and related tickets.
- **Asset Management:** the only P1 tool, so that the P0 "Management" group isn't empty. Searchable register; state and location can be edited; changes persist.
- **Past Tickets:** outcome, points breakdown, time, notes, action log, model answer.

**Not built Sunday:** listed in the README and kept out of the menus, so there are no dead buttons.
- Computer Deployment, PC Shelf, Ship Manager
- Company Chat and the extra desktop apps
- Achievements, shift toasts, calls/voicemail
- Export/import save

### Milestones
- [ ] **M1 Shell:** skeleton, tokens/CSS, top bar, Tools popover, router, dialog/toast helpers, seed + save/load/reset + storage fallback, first run, dashboard.
- [ ] **M2 Game logic:**
  - all ENV mutators, the scenario registry and the arrival chain
  - penalties and scoring
  - ticket page with claim, hints, Check Fix, close and escalate
  - Past Tickets and `selfTest()`
- [ ] **M3 Directory + Server Room** (1042–1045 and 1050 playable).
- [ ] **M4 Mail Admin + Mail Security + Documentation** (1047–1049).
- [ ] **M5 Remote Desktop + Asset Management** (1044 verify, 1046, 1051).
- [ ] **M6 Polish + QA:**
  - split view/tabs; layouts at 1366, 1024 and 390 px
  - focus/Esc and reduced motion
  - README: how to run, how to reset, checks done, unfinished items
  - update the PR description

### Verification
- **`selfTest()`** in the file (run it via `index.html#selftest` or the console). For each ticket, starting from a fresh `seed()` plus its `arrive`:
  - not complete at seed
  - apply the model fix through the ENV mutators
  - now complete
  
  It also covers the spec's negative cases: 1042 password reset only, 1043 one step = partial, 1044 password reset, 1049 delete only, 1050 printer reboot.
- **Playwright** (global `playwright@1.56.1`, Chromium in `/opt/pw-browsers`; run `NODE_PATH=$(npm root -g) node <scratchpad>/smoke.js`):
  1. Open `file:///home/user/deskops/index.html`. Fail on any request that isn't `file:` and on any console error.
  2. Run `selfTest()`.
  3. Play 1042 through the UI: claim → Directory → unlock → Check Fix → close → check points and Past Tickets.
  4. Try closing an unresolved ticket, then Cancel.
  5. Reload: progress is kept.
  6. Corrupt the save: the game recovers.
  7. Make `localStorage` throw: still playable, with the banner.
  8. Reset: back to a clean seed.
  9. Take screenshots at 1366×768, 1024×768 and 390×844, and look at them.
- Walk through spec §10 and the IMPLEMENTATION_PLAN checklist (with the corrected INC numbers) and record the results in the README.
