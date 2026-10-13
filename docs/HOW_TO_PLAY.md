# How to play DeskOps Lab

You're a first-line technician on the service desk at Northstar Office Group, a fictional company. Tickets come in; you pick one, investigate it in simulated admin consoles, fix the right thing, prove it's fixed, and close it with notes. Every account, PC, server and mailbox is simulated inside the page, so nothing you do touches a real system.

To start, open `index.html` in a browser (double-clicking it is fine, even offline). Enter a display name in the welcome dialog and select **Start shift**.

## The core loop

1. **Pick a ticket.** The dashboard shows **My Queue** (tickets assigned to you) and the **Incidents** queue, Critical first. **Incoming contacts** lists chat messages and voicemails that haven't been logged yet: open them, then select **Log as ticket**.
2. **Assign it to yourself.** Open the ticket and select **Assign to me**. You can only close or escalate tickets you own.
3. **Read the evidence.** The ticket page shows who reported it, their department and contact, the affected asset, the issue in their words, what they already tried and the business impact. Scope matters: one user, one floor, or everyone?
4. **Investigate.** Select **Open Tools** and pick a console. With **Split screen view** on, the ticket stays beside the console so you can check requirements as you work.
5. **Fix it.** Make the change in the right console. Every action is written to the ticket's activity log. Risky actions ask for confirmation, and a wrong action shows a warning toast with the points it will cost at close.
6. **Check fix.** Lists which requirements are met and what's still missing. It updates live and costs nothing.
7. **Confirm with the requester.** Many tickets offer a Company Chat quick action such as "Ask to confirm the fix". Typing something like "can you try now?" to the requester gets a reply based on whether every requirement is met yet.
8. **Close or escalate.** Select **Close ticket** and write short resolution notes, or **Escalate to Security** for a suspected compromise or social-engineering attempt (the evidence box needs at least 15 characters). The dialog previews your points before you confirm.
9. **Review.** **Past tickets** shows your score breakdown, your notes, the model answer, the action log and a link to the ticket's solution guide.

## Scoring

| Outcome | Points |
|---|---|
| Resolve a Critical ticket | +30 |
| Resolve a High ticket | +22 |
| Resolve a Medium ticket | +15 |
| Resolve a Low ticket | +10 |
| Resolve the final boss (INC-1073) | +60 |
| Flawless boss: resolved with no penalties, without revealing its solution guide first | +5 |
| Correctly escalate a security ticket to Security | +12 on top |
| Resolution notes of 40 or more characters | +1 |
| Notes that name the user, host, service or other ticket keyword | +1 |
| Notes that say how you verified ("verified", "confirmed", "tested") | +1 |
| Close a ticket that isn't resolved | −20 (Critical), −15 (High), −10 (Medium, Low), −30 (boss) |
| Escalate a routine ticket to Security | The same as closing it unresolved: −20, −15 or −10, and −30 for the boss |
| Escalate a security ticket before its case is ready (evidence not gathered, or something changed that shouldn't have) | −20 (Critical), −15 (High), −10 (Medium, Low) instead of the resolve points |
| A ticket-specific wrong action (rebooting the core router for one user, releasing phishing, deleting evidence, sending passwords to the wrong place…) | −2 to −8 each |

- Wrong-action penalties are recorded when you make the mistake and charged once, when the ticket is closed or escalated. They count as soon as the ticket has arrived (even before you assign it or after you return it to the queue), and one action is charged to one ticket.
- The game has its own clock: each shift starts at 09:40 on its day (Monday Oct 12, 2026 for shift 1) and every action takes a minute, so timestamps never depend on your real time of day.
- Each ticket's total is capped between −20 and +42. The boss is capped between −30 and +70.
- Hints and the solution guides are free. The one exception: revealing the boss's guide before you finish it forfeits the +5 Flawless boss bonus.
- A perfect run through all three shifts scores 742 points, and a flawless boss adds 68 (810 in total).

A good note has three parts: the cause, the action, and the verification. For example: *"Cause: mchen locked out after vacation. Action: unlocked the account in Directory. Verified: sign-in test passed and Maya confirmed in chat."*

## Ranks and achievements

| Rank | Points |
|---|---|
| Trainee | 0 |
| Bronze | 40 |
| Silver | 100 |
| Gold | 180 |
| Platinum | 280 |
| Diamond | 760 |

Diamond is above the 742 points a perfect run through shifts 1–3 can score, so it takes a boss win.

Your rank shows under your name in the top bar. **Achievements** (the trophy icon) shows the rank ladder and seven achievements, worked out from your results: First fix, By the book (a ticket resolved with no penalties), Paper trail (full notes bonus), Security minded (a compromise routed to Security with the evidence intact), Inbox zero (every shift 1–3 ticket cleared), Boss defeated (INC-1073 resolved) and Flawless boss (the boss resolved with no penalties, without revealing its guide first).

## Shifts

| Shift | Tickets | Theme |
|---|---|---|
| 1 · Monday morning | 10 | Lockouts, a floor outage, Wi-Fi, mail delivery, printing and VPN |
| 2 · Tuesday | 10 | Hardware: dead PCs, new starters, remote replacements, displays, chargers, DHCP, phones, mailbox access |
| 3 · Wednesday | 11 | Identity and infrastructure: joiners, leavers, name changes, MFA, DNS, a provider outage, storage, file restores, phishing |
| Boss stage · Thursday | 1 | The final boss: one requester who has already tried everything |

- When every ticket on the shift is closed or escalated, the dashboard offers **Start next shift** with a briefing. **Shift briefing** on the dashboard shows the current one again.
- Some tickets only arrive after another is finished, because the second problem only shows once the first is fixed.
- Some tickets arrive as a Company Chat message or a voicemail rather than in the queue. Read who sent it and from which number or account before you trust it.

## The boss stage

Until shift 3 is cleared, the dashboard shows a locked **Final boss** card. When every shift 3 ticket is closed or escalated, the dashboard offers **Start the boss stage** and a briefing. The boss is one ticket, marked **BOSS** in the queue and on the ticket page, from a very technical requester who has already tried every fix a user can try.

- It has layers. Check fix only lists the requirements you can see so far, plus "More requirements appear as you dig." Fixing one layer is what shows you the next, usually as an update from the requester in Company Chat.
- The world keeps moving. Every action takes a minute of in-game time, and some things happen on a schedule, so watch the clock in the Remote Desktop taskbar and the timestamps in the logs.
- Talk to the requester. Type to them in Company Chat: they answer what they've already checked, and they can give you exact times and error codes. Their measurements are reliable; their conclusions are hypotheses.
- Some actions can't be undone, and the order you do things in matters. Wrong actions here cost up to −8 each.
- The hint ladder has five hints and no model answer. The solution guide stays behind its spoiler gate, and revealing it before you finish forfeits the Flawless boss bonus.

## Tools tour

Open them from **Tools** in the top bar or **Open Tools** on a ticket.

| Tool | What it's for |
|---|---|
| **Directory** | Users (profile, email addresses, groups, licences, devices, authentication, sessions, mailbox), HR **Starters** and **Leavers** records, **Licence pools**, Create user, Verify identity, unlock, enable, password and MFA resets, sign-in tests |
| **Server Room** | Overview, clickable **Topology**, Devices, Servers and their services, **DHCP** scopes and leases, **Storage** volumes, **Shadow copies** with previous versions and the file audit, **Events & tasks**, and the ISP circuit (check status, log a fault) |
| **Remote Desktop** | Connect to a user's PC: Network & Wi-Fi, VPN Client, File Explorer, Terminal, Settings (Display, Storage, Power & battery, About), System Update, Device Manager, Office Suite (including local data files), Task Scheduler, Restart |
| **Computer Deployment** | Image a shelf device with a role image, assign it and run the five-stage deployment; image catalogue and deployed fleet |
| **PC Shelf** | Spare devices (reserve, wipe, mark faulty, retire) and accessories you can issue to a device |
| **Mail Admin** | Message trace, mailboxes (quota, archive, conversion to shared, permissions, automatic replies, forwarding, test messages, mailbox audit log), shared mailboxes, distribution lists, mobile devices, inbox rules |
| **Mail Security** | Quarantine, reported messages (analyse, report, purge, block) and blocked senders |
| **Documentation** | **Runbooks** for every procedure (purpose, prerequisites, steps, verification, when to escalate) and a **Solution guide** for every ticket |
| **Asset Management** | Hardware register: owner, location, state, warranty, health, lock, wipe, return to shelf, accessories, history, and company mobiles |
| **Ship Manager** | Ship devices to people, create return labels, advance tracking and mark deliveries |

Also in the top bar:

- **Company Chat:** message any member of staff, use ticket quick actions, and post to #office-announcements during outages.
- **Voicemails:** transcripts with caller ID. You can Log as ticket, Save to the ticket, Forward to Security or Delete.
- **Past tickets** and **Achievements.**
- **Your name:** opens the profile menu. From there you can change your display name, show or hide hint buttons, keep the ticket beside tools (split view), or Reset progress….

## When you're stuck

1. **Check fix** tells you what's still missing.
2. **I don't know how to fix this** on the ticket opens a three-step hint ladder, then the model answer. Hints are free.
3. **Documentation › Runbooks** explains each procedure without naming the answer.
4. **Documentation › Solution guides** has the full walkthrough for every ticket: symptoms, diagnosis, click-by-click steps, how to verify, common mistakes, the scoring and an ideal note. Guides for tickets you haven't closed sit behind **Reveal full solution**; revealing one is free. The hint card also links to the ticket's guide.

The same guides are in [`SOLUTIONS.md`](SOLUTIONS.md), which contains spoilers.

## Keyboard tips

- **Tab / Shift+Tab** move through every control; **Enter** or **Space** activates buttons, including the boxes in Server Room › Topology.
- **Escape** closes dialogs and menus, closes Company Chat, and restores a maximized Remote Desktop window.
- **Enter** in the Remote Desktop terminal runs the command. Type `help` for the list: `ipconfig [/all|/renew|/flushdns]`, `ping <host>`, `nslookup <host> [server]`, `tracert <host>`, `whoami`, `hostname`, `quser`, `schtasks` (with `/query /v`, `/change /tn <task> /disable` or `/enable`, `/run /tn <task>` and `/delete /tn <task> /f`), `cmdkey /list`, `cmdkey /delete:<target>`, `logoff`, `shutdown /r`, `gpupdate /force`, `sfc /scannow` and `cls`.
- **Enter** in the work-note box adds the note; **Enter** in Company Chat sends the message.
- Search boxes filter as you type. Focus stays where it was when the screen redraws.

## Progress

Progress is saved in your browser on this computer, and nothing is sent anywhere. To start over, open the menu under your name and select **Reset progress…**. If the browser blocks storage, the game still runs, and a banner warns that progress lasts only until you close the tab.
