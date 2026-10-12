# DeskOps Lab

An offline IT service-desk training game. You're a first-line technician at the fictional Northstar Office Group: pick a ticket, claim it, diagnose it in simulated admin consoles, fix it, verify, close it and get scored.

Everything is fictional and local. No account, server, mailbox or command is real, and the page makes no network requests.

## Play

Download `index.html` and double-click it. That's the whole game: no install, no server, no internet, no login. It works from a `file://` path in current Chrome, Edge, Firefox and Safari.

## Progress and reset

Progress (points, tickets, history, chat and every change you make to the simulated environment) is saved in your browser's local storage on that machine, under `deskops-lab-v2`. Saves from version 1 are ignored, so you start a fresh shift.

- **Reset:** click your name (top right) › **Reset progress…** and confirm.
- If the browser blocks local storage, the game still runs and shows a banner saying progress lasts only until the tab closes.
- A corrupted save is detected on load; the game starts a fresh shift and tells you.

## What's in it

- **10 tickets** (INC-1042 to INC-1051): account lockout, expired password, missing group membership, floor-wide outage, broken Wi-Fi profile, quarantined mail, full mailbox, suspicious forwarding rule (escalate to Security), stuck print spooler, stale VPN profile. INC-1044 and INC-1051 arrive after INC-1042 and INC-1043 are closed.
- **Dark, queue-first interface:** My Queue and the Incidents queue on the home screen, an intake-style ticket page with an "I don't know how to fix this" hint ladder, a split-screen toggle, and a Tools menu in a centred modal.
- **Consoles:** Directory, Server Room (overview, clickable topology, devices, servers), Remote Desktop (Wi-Fi settings, VPN client, File Explorer, a terminal with an allowlist of simulated commands), Computer Deployment, PC Shelf, Mail Admin, Mail Security, Documentation, Asset Management, Ship Manager. Deployment, PC Shelf and Ship Manager are read-only inventory views for now.
- **Company Chat:** a side panel with 12 fictional Northstar staff (search, Recent / Contacts / Pinned, presence dots). Replies are scripted: a requester tells you whether their problem is still happening.
- **Voicemails:** transcripts of calls to the desk that match tickets in the queue.
- **Rank and achievements:** Trainee, Bronze (40), Silver (100), Gold (180), Platinum (280), plus five achievements worked out from your shift.
- **Ticket checks** read the shared environment state, so a ticket is only complete when the right entity is actually fixed and verified. **Check fix** lists what's done and what's missing; **hints** are free.
- **Scoring:** Low 10, Medium 15, High 22, Critical 30, up to +3 for useful notes, +12 for a correct security escalation; penalties for closing unresolved tickets, risky changes and needless escalations. Each ticket is capped at −20…+42.

## Checks performed

- `index.html#selftest` runs every scenario from a fresh state through the same functions the consoles use, including the wrong paths (password reset alone doesn't unlock, rebooting a printer doesn't fix the spooler, deleting the suspicious rule isn't rewarded) and the scoring rules. All 42 checks pass, including the chat replies, voicemails, rank thresholds and save schema.
- Headless Chromium, opened from `file://`, with every non-file request and console error treated as a failure (none occurred):
  - first-run welcome, queue order (Critical first), claim/unclaim
  - closing unresolved shows the penalty and Cancel changes nothing
  - INC-1042 end to end in split view: Directory › unlock › Check fix › close with notes (+25) › Past Tickets
  - INC-1044 arrives after INC-1042 closes
  - Server Room topology: rebooting the edge router asks for confirmation and applies the penalty; powering on the Floor 3 switch fixes INC-1045
  - Remote Desktop on NS-OPS-021: forget the broken Wi-Fi profile, reconnect, `ping 10.0.0.1`
  - reload keeps points and environment changes; a corrupted save recovers; blocked storage shows the banner
  - split-screen toggle, hint ladder, Tools modal opening Ship Manager, PC Shelf and Computer Deployment, marking a voicemail as listened, and a Company Chat conversation with a scripted reply
  - screenshots at 1366×768, 1024×768 and 390×844 (no horizontal scroll at 390)

## Not built yet

Actions in Computer Deployment, PC Shelf and Ship Manager, chat replies tailored to each ticket, the extra desktop apps (mail, chat, browser, system update), live calls and save export/import.
