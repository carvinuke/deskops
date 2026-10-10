# DeskOps Lab — Game Design & Functional Specification

## 1. Product definition

**Genre:** single-player, browser-based IT help-desk troubleshooting simulation.

**Audience:** people learning entry-level IT support, PC troubleshooting, identity administration, network triage and ticket documentation.

**Premise:** The player is a technician on the service desk at Northstar Office Group, a fictional company of roughly 500 employees. Requests arrive as tickets. The player must diagnose and fix them using a set of connected simulated tools, then document and close the case.

**Core fantasy:** “I am on shift, surrounded by believable admin consoles, and I can reason through the same sort of problems a real first-line tech would see.” It should reward diagnosing the root cause, reading the evidence, taking the lowest-risk correct action and documenting the resolution.

**Not a real remote-access product:** every directory account, email, server, desktop and command is fictional local game state. No genuine account is accessed and no real command is executed.

## 2. Runtime contract (critical)

The user wants to commit or upload `index.html` to GitHub, download it, open it and play. Assume **local-file execution** (`file:///.../index.html`), not only `http://localhost`.

- One self-contained HTML document; embed CSS, JavaScript, data and SVG icons.
- No login/signup; no account, password, email verification or cloud profile.
- No backend, remote API, analytics, cookies for tracking or external dependency.
- No remote fonts/images/CDN. Use system fonts and inline SVG/CSS art.
- No `fetch()` of JSON files or ES module imports. Some browsers block them for local files.
- Use `localStorage` in a try/catch. If it fails, run in memory and show a small non-blocking note that progress may not persist.
- Add “Export save” and “Import save” as optional quality-of-life actions only if implemented safely with file input/Blob; these are not required for the MVP. Do not require them to play.
- Include “Reset progress” in a profile/settings menu; confirm first.
- No registration wall or tier limits. Everything necessary for the game is unlocked.

## 3. Visual system

The referenced in-game experience is light, quiet, and compact. It uses thin separators, small uppercase metadata and a blue accent rather than a colorful dashboard. The reference also uses larger, geometric all-caps ticket titles. Capture the *design language* but use original styling and assets.

### Suggested token system

- Page background: `#F6F8FA` or `#F7F8FA`
- Surfaces: `#FFFFFF`
- Main text: `#20252B`
- Secondary text: `#66717D`
- Muted metadata: `#8B96A2`
- Borders: `#DFE4E8`
- Active/primary blue: `#0098D7` (hover slightly deeper)
- Pale blue background: `#EDF8FE`
- Critical: `#D92D35`; High: `#E66B2B`; Medium: `#C68718`; Low: `#9C8B35`
- Success: `#25845D`; warning: `#B87519`; disabled: `#A6AFB7`
- Border radius: 4–8px; prefer small radii over pill-shaped everything.
- Shadows: rare and subtle, mainly for popovers/dialogs.
- Typeface: system stack (`system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif`). Monospace for IDs, IPs, log lines and terminal output.

Color carries semantic meaning. Priority needs both the word and a colored marker. For ordinary rows, use neutral colors. Avoid the reference site's login-screen purple gradient altogether because this offline game opens directly into the dashboard.

### Typography and density

- Page / console heading: 18–22px, medium weight.
- Ticket title: 22–28px, bold or geometric uppercase treatment on desktop; normal title case is fine on narrow screens.
- Section label: 10–12px, uppercase, letter spacing around 0.10em.
- Table content: 12–14px on desktop, readable 14px on mobile.
- Supporting prose: 13–15px, line-height 1.45–1.6.
- Maintain compact rows, but don't make body copy tiny. Density should resemble an admin tool rather than a marketing homepage.

### Shell and navigation

1. A 52–60px top bar, white with a bottom border.
2. Left: original DeskOps Lab logo (simple inline glyph, e.g. two stacked windows) and “DeskOps Lab”.
3. Main navigation on desktop: **Dashboard**, **Tools**, **Calls** (optional), **Voicemails** (optional), and a compact **Shift Guide** control. Dashboard should always be easy to return to.
4. Right: Company Chat, activity/score, local profile menu with display name and Settings / Past Tickets / Achievements / Reset Progress.
5. Do not use a full-height sidebar. Tools opens as a categorized popover/drawer from the top bar. Selected tools occupy the main content area. Keep a clear Back to Dashboard control inside every tool.
6. Show a tiny connection/state note like “LOCAL LAB · ALL SYSTEMS SIMULATED” in the profile/settings area, not a scary alert.

### Main dashboard layout

At 1366px wide: 24px outside gutters, centered content max-width ~1220px. A header row greets the local technician and shows the current shift/points. Main section labelled “Ticket Queue”. Primary queue card occupies most of the width. Secondary compact panels can show “My Queue”, “Recent activity” and “Systems overview” if space allows. Do not bury the queue below marketing copy.

Queue list rows contain:
- Ticket reference (`INC-1042`, monospace or compact small text)
- User-written issue title
- Requester name and department underneath
- Priority word/marker at the far right
- Optional category/age, but only if the row remains readable
- Whole row clickable, with hover/focus state

Sort unresolved tickets by priority then age (Critical → High → Medium → Low; oldest within a tier). Assigned tickets appear in “My Queue” above the unclaimed queue. A ticket moves after claim and returns after unclaim. Empty state should say that all available incidents are cleared and offer “Review Past Tickets” / “Load next shift” if there is another batch.

### Ticket detail layout

At the top show back navigation, reference number, priority and a title. The title is visually prominent. Place an Options menu at the upper-right. Below show an Assignee row with avatar circle, state and **Assign to me** / **Return to queue** control.

Use sections or columns:
- **Requester**: name, department, location, extension, email.
- **Description**: the user's words, often naturally written.
- **Business impact**: why it matters (one user vs a department vs company-wide).
- **Already tried**: troubleshooting that has already happened.
- **Affected asset**: hostname, device tag, service or mailbox.
- **Activity / work notes**: system events and technician notes.
- **Required outcome** / “Check fix”: a discreet state indicator, not a spoiler. Only reveal a full solution through the Hint flow.

Primary actions: Assign; open Tools; Hint (optional); Check Fix; Escalate; Close Ticket. Keep primary actions in consistent locations. Disable resolution/closing for unassigned tickets except if you explicitly implement a deliberate “close unassigned” penalty rule. Tool selection can support a split-screen mode: on desktop, ticket context remains in a left column and the selected console occupies the right. On narrower displays show “Ticket” and “Tool” tabs or stack them vertically. It must never truncate fields off-screen.

### Tools panel

Use four labelled groups as the reference does:

**Infrastructure**
- Directory
- Server Room
- Remote Desktop
- Computer Deployment
- PC Shelf

**Email**
- Mail Admin
- Mail Security

**Knowledge**
- Documentation

**Management**
- Asset Management
- Ship Manager

Each item has an original line icon, name, one-line purpose and a clear hover/focus state. Some P1 tools can display a complete simple working view rather than a dead button, but P0 tools must be genuinely functional.

## 4. Ticket lifecycle

Ticket statuses: `open`, `assigned`, `resolved`, `closed`, `escalated`. `resolved` means the checker detects that the environment satisfies the ticket's objectives; `closed` means the player has recorded the resolution and committed closure. An escalated ticket is routed out of normal work and stored in history. Avoid ambiguous overlapping labels.

### Happy path

1. Open dashboard; choose a ticket.
2. Inspect the evidence; assign it to the current local technician.
3. Enter relevant console(s) via Tools. The tool is pre-populated with fictional data and knows the current ticket context only for gentle navigation hints, not for auto-solving.
4. Search/open the relevant account, device, mailbox or service.
5. Perform valid simulated actions. Store state changes centrally.
6. Return to the ticket or remain in split view. Select “Check Fix”. The game evaluates scenario-specific predicates, lists completed requirements, and gives a neutral next-step nudge for missing requirements.
7. Once complete, show “Solution complete” plus “Review your work”.
8. Select “Close Ticket”. A dialog asks for optional resolution notes (max 600 chars), previews score and shows any completion warning. On a complete ticket confirm closure and award points.
9. Add the final action to history and retain the ticket with its model answer for review.

### Incorrect closure

If incomplete, the dialog must state “This ticket still appears unresolved” and list at most three evidence-based blockers, e.g. “Account is still locked” / “Mail remains quarantined”. The button reads “Close Anyway” and clearly displays the penalty before the player commits. Never silently close a broken case. A cancel button preserves state.

### Unclaim, abandon, escalate

- Unclaim returns the ticket to the shared queue; retain action log but clear assignee.
- Abandon / report-broken: optional. If implemented, show confirmation and record reason; never lose work silently.
- Escalation is appropriate for suspicious compromise or work that needs a higher-privilege owner. Routine escalation loses a few points; a true security case earns a modest bonus and is marked “Routed to Security”. Escalation must not be required to earn full score on an ordinary fix.

## 5. Scoring system

Use a transparent and consistent scoring model with short feedback explaining each adjustment. Suggested defaults:

- Low: +10
- Medium: +15
- High: +22
- Critical: +30
- Clean resolution-note bonus: +0 to +3, based on reasonable minimum completeness, not prose AI evaluation.
- Correct security escalation: +12.
- Wrong routine escalation: −8.
- Close unresolved: −10 for Low/Medium, −15 for High, −20 for Critical.
- Destructive / irrelevant action: −2 to −6 only when it has a clear simulated consequence and the UI explains it.
- Hints: zero penalty.
- Do not punish harmless navigation or read-only investigations.

Cap a ticket's score delta within a sensible range (for example −20 to +42). Show points before closure and after closure. Lifetime points, tickets resolved and streak (optional) can be stored locally. Avoid daily quotas or paywalls.

## 6. Core consoles — behavior specification

### 6.1 Directory

Purpose: diagnose identity/access tickets. Layout: search bar + scrollable user list (left), tabs/navigation (middle or top), record details (right). It must search display name, username and email. Use fictional accounts across departments.

Tabs: Profile, Groups, Licenses, Devices, Authentication, Mailbox. Minimum useful behavior:
- Authentication summary: Enabled / Disabled, Locked / Unlocked, Password expired / current, MFA enrolled / not enrolled, last sign-in.
- Actions: Reset password (creates an in-game temporary password and can set “must change at next sign-in”), Unlock/Lock account, Enable/Disable account, Reset MFA (require a confirmation/identity warning), Send simulated verification code.
- Groups: view membership and add/remove from provided fictional groups. Group changes must affect mapped-drive/access cases.
- Devices: list assigned hostnames and status.
- Mailbox: mailbox enabled state, quota used, forwarding/inbox-rule hint (the suspicious rule detail belongs in Mail Admin).

Use a confirm dialog for sensitive state changes and create a concise audit-log entry. Resetting the password does not automatically unlock the account. Re-enabling a deliberately disabled compromised account should not be rewarded as a “fix”. Account identity must match the ticket's target username/employee ID.

### 6.2 Server Room

Four tabs: Overview, Topology, Devices, Servers. Overview shows:
- ISP online/offline and latency
- Network load status
- Online/total device count
- Healthy/total server count
- Device status list and server CPU/memory bars

Topology is a readable node diagram such as Internet → ISP → Edge Router → Firewall → floor switches / servers / Wi-Fi APs. Keep node positions stable; use inline SVG and accessible labels. State colors: blue/green-like accent for online, muted red/slate for down, pale accent for rebooting.

Devices table: name, IP, location, uptime, status and action menu. The ISP has a “Check ISP status” action rather than a power switch. Other devices can be rebooted or powered on/off according to state. Simulate a brief restart with an obvious but non-blocking status transition; simplest fully deterministic option is to mark it healthy immediately with a “Restarted” activity entry. Servers table includes role and small CPU/memory bars. A ticket about a whole floor should be tied to a shared device; a one-machine case should not reward randomly rebooting network infrastructure.

### 6.3 Remote Desktop

Picker searches by hostname, asset tag or owner. Selecting a machine and choosing Connect opens a simulated connection/credentials interstitial. Credentials are fictional: a toggle may reveal a canned hint used for the lab. Never store or request a real password. Offline/broken machines should clearly explain why remote connection cannot start.

Inside the desktop, show wallpaper, desktop shortcuts, taskbar/clock, hostname + owner session bar, fullscreen-like maximize button and Disconnect. Windows are fake app panels that open inside the desktop frame. Required useful apps:
- File Explorer (drive mapping and shared-drive access state)
- Mail (inbox, trace/rule-related symptoms if needed)
- VPN Client (connection/disconnection status, profile choice)
- Chat (a few canned employee messages and confirmation replies)
- System Update (pending/restart state)
- Settings (display, network and printer configuration)
- Web Browser (simulation-only page list, proxy symptoms)
- Terminal (safe simulated command console for `ipconfig`, `ping`, `nslookup`, `whoami`, `gpupdate` or `sfc /scannow`, returning scripted output only)

The terminal must not pass input to the host OS, `eval`, `Function`, a shell, or network. Use a command allowlist plus ticket-specific scripted output. Unknown commands return “Command not recognized in this lab”.

### 6.4 Mail Admin

Tabs: Message Trace, Mailbox Admin, Inbox Rules. Message trace can filter by recipient/sender, time window and message status; results show timestamp, sender, recipient, subject and status. Mailbox Admin shows enabled state, quota/usage, archive and retention. Inbox Rules lists rule name, condition and action. A suspicious “all incoming mail → forward outside org” rule should visibly carry a warning and a direction to escalate to Security.

### 6.5 Mail Security

Show searchable quarantine items, sender, recipient, subject, date and reason/score. Releasing a quarantined legitimate message changes it to Delivered and resolves matching cases. A malware/phishing item should offer “Keep blocked” / “Escalate to Security”; releasing it is a risky wrong action with an explained consequence.

### 6.6 Documentation / Knowledge Base

Local searchable knowledge articles with title, category, concise step-by-step instructions, relevant tool tags and related tickets. Search should be case-insensitive and filter as the player types. Start with articles for account lockouts, password resets, VPN, Wi-Fi, mapped drives, printers, mail quarantine, mailbox quota and suspicious inbox rules. Hints are separate: show one clue per click, never reveal all at once, no score penalty.

### 6.7 Secondary consoles

If built, each must work locally:
- **Computer Deployment:** choose a stock build profile, assign user/location, run a staged provisioning sequence, then add an asset to inventory.
- **PC Shelf:** available, reserved, deployed and retired devices; reserving/removing stock affects deployment tickets.
- **Asset Management:** searchable asset register with owner, tag, serial, warranty, location and state; changes persist.
- **Ship Manager:** create a shipment for a replacement device, choose dispatch/return label and track status. Keep it a lightweight scenario, not a logistics spreadsheet.

### 6.8 Company Chat

A local simulated coworker chat. Seed relevant requesters and teams. Some ticket conditions require asking a user to test the fix or reply “It works now”. Message content and user replies are deterministic, driven by actions. Do not implement real chat/networking.

## 7. Responsive behavior and accessibility

- 1366×768 is the primary design target; 1024px must remain functional; mobile should switch from split panes to tabs/stacked panels.
- Queue cards and tool forms reflow; tables may horizontally scroll within their panel, not the whole page.
- Popovers/dialogs stay within viewport and close on Escape; click outside may close menus, but don't lose unsaved resolution notes.
- Every icon-only button has an accessible name/title. Use native button, input, select, textarea and dialog-like semantics where practical.
- Full keyboard operation, visible `:focus-visible`, adequate contrast, labels connected to controls, and no color-only state communication.
- Respect `prefers-reduced-motion`; keep transitions quick (120–180ms) and optional.
- Toasts must not be the only evidence of success; update the relevant row/status inline too.

## 8. State, data and persistence

Use one root state object rather than mutating HTML ad hoc. Example conceptual state:

```js
{
  schemaVersion: 1,
  profile: { displayName: "Technician", points: 0, resolvedCount: 0 },
  settings: { theme: "light", hintsEnabled: true, splitScreen: true, soundEnabled: false },
  currentView: "dashboard",
  activeTicketId: null,
  users: [...], devices: [...], servers: [...], mailboxes: [...], messages: [...], assets: [...],
  tickets: [...], history: [...], actionLog: [...], achievements: []
}
```

The data structures can differ, but define clear central actions such as `claimTicket`, `performToolAction`, `checkTicketResolution`, `closeTicket`, `escalateTicket`, `saveGame`, `loadGame`, `resetGame` and `renderApp`. Use unique IDs. Never have each tool keep a separate truth about the same account/device/mailbox.

Suggested ticket fields: `id`, `reference`, `title`, `requesterId`, `department`, `location`, `extension`, `priority`, `category`, `status`, `assignee`, `description`, `businessImpact`, `alreadyTried`, `assetId`, `relatedEntities`, `objectives`, `hints`, `modelAnswer`, `basePoints`, `actions`, `createdAt`. Objectives should be predicates over state, e.g. account is unlocked and password reset flag is set. Serialize data without functions; keep a scenario-rule registry in code keyed by ticket ID/category.

On save/load, validate the schema version and recover from corrupt JSON with a safe defaults path and a small message. Never crash the game just because localStorage contains invalid data. Do not store real secrets.

## 9. Writing, tone and microcopy

Professional and concise. Ticket descriptions sound like employees, not puzzle riddles. Example: “Hi, I’m back from vacation and my account says it’s locked. I can’t open the finance share and payroll is due this afternoon. My colleague can still open it.” The evidence should be enough to reason through the case, but players should still need to inspect a tool.

Use specific feedback: “Account unlocked. The password is still expired.” Avoid generic “Wrong answer!” or exaggerated game language. Provide useful partial-success text when a correct first step leaves a second objective outstanding.

## 10. Acceptance test (must pass)

1. Save only `index.html`; open it from a local file path while offline. Game loads without a server.
2. There is no login/signup or required network request.
3. Open the dashboard, open a ticket, claim it, go to Directory, search for the named employee, unlock their account, and verify that the ticket becomes partially or fully complete as expected.
4. Show that resetting a password alone does not unlock a locked user; correct sequencing matters.
5. Fix a network ticket by inspecting Server Room and correcting the actual failed device, not by random actions.
6. Release a legitimate quarantined mail item in Mail Security and verify the mail ticket.
7. On a suspicious forwarding-rule case, escalating is rewarded and deleting the rule as a routine task is not presented as safe.
8. Try closing an unresolved ticket: a penalty is shown before confirmation, and Cancel leaves the ticket unchanged.
9. Close a completed case, see points update, then find it in Past Tickets with model answer/action log.
10. Refresh the page; points, tickets and environment changes persist.
11. Reset progress; confirmation is required and reset actually restores a clean initial state.
12. Use keyboard focus and Escape to operate menus/dialogs; verify layout at desktop and mobile sizes.
13. Check that no button is dead, there is no placeholder/lorem ipsum, and the console has no avoidable runtime error.
