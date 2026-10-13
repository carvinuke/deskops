# DeskOps Lab

An offline IT service-desk training game. You're a first-line technician at the fictional Northstar Office Group: pick a ticket, claim it, investigate in simulated admin consoles, fix the right thing, verify it, then close or escalate it and get scored.

Everything is fictional and local. No account, server, mailbox or command is real, and the page makes no network requests.

## Run it

Download `index.html` and double-click it. That's the whole game: no install, no build step, no server, no internet, no login. It runs from a `file://` path.

New here? Read [docs/HOW_TO_PLAY.md](docs/HOW_TO_PLAY.md) for the core loop, scoring, ranks, shifts, a tour of the tools and keyboard tips.

## Progress and reset

Progress (points, tickets, notes, chat, and every change you make to the simulated environment) is saved in your browser's local storage on that computer, under the key `deskops-lab-v3`. Saves from older versions are ignored, so you start a fresh shift. A `v3` save made before a ticket existed keeps its progress: the new ticket is added in its "not arrived" state when the save loads.

- **Reset:** click your name (top right), select **Reset progress…** and confirm.
- **Skip to the boss (dev shortcut):** on the dashboard, type `iamimpatient` anywhere outside a text box. On a phone, type it into any text box instead, such as the Company Chat search. After you confirm, every unfinished shift 1–3 ticket is closed as if solved perfectly, the boss stage starts and Avery Farmwell's ticket (INC-1073) opens.
- **Storage blocked:** the game still runs and shows a banner saying progress lasts only until the tab closes.
- **Corrupted save:** detected on load. The game starts a fresh shift and tells you.

## What's in it

- **32 tickets: three shifts and a boss stage.** Shift 1 (10 tickets): lockouts, an expired password, share permissions, a floor outage, Wi-Fi, quarantined mail, a full mailbox, a malicious forwarding rule, a crashed print spooler and a VPN profile. Shift 2 (10): hardware swaps, new starters, a remote laptop replacement, a full disk, displays, a social-engineering voicemail, a weak charger, a full DHCP scope, a new phone and shared-mailbox access. Shift 3 (11): joiner, name change, leaver, MFA reset, a returner, a vishing call, a DNS outage, a provider outage, a full file server, a file restore and reported phishing. The boss stage (1): see below.
- **A final boss.** INC-1073 unlocks only after every shift 3 ticket is closed or escalated, with its own briefing, and is marked BOSS in the queue and on the ticket page. The requester, Avery Farmwell (they/them), has security and IT certifications and has already ruled out every user-side fix, so the ticket is built to be the hardest in the game while staying fair: every cause can be proved from the consoles, and every fix Avery already tried really doesn't work. It has several layers that appear one at a time, red herrings that the evidence refutes, a requester you can question in Company Chat, an in-game clock that matters, actions that can't be undone, a five-step hint ladder with no model answer, +60 points (capped at −30…+70), a +5 Flawless bonus, a Diamond rank at 760 points and two achievements.
- **Ticket intake like a real desk:** a queue sorted by priority, plus requests that arrive as Company Chat messages or voicemails and must be logged first. Some tickets only appear after another is finished.
- **Ten consoles:** Directory, Server Room, Remote Desktop, Computer Deployment, PC Shelf, Mail Admin, Mail Security, Documentation, Asset Management and Ship Manager. Every action in them is real within the simulation, and tickets are checked against that shared state.
- **Company Chat and Voicemails:** 16 fictional staff at the start (more join as tickets arrive), with presence, scripted replies, ticket quick actions (ask to confirm the fix, ask for approval) and an #office-announcements channel. Voicemails are transcripts with caller ID, and you can log, save, forward or delete them.
- **Documentation:**
  - 38 runbooks, one per procedure the tickets use, each with purpose, prerequisites, steps, verification and when to escalate.
  - A solution guide for every ticket: symptoms to notice, diagnosis, click-by-click steps, how to verify, common mistakes, a real-world note, the hint ladder, scoring with every penalty, and an ideal resolution note.
  - Guides for tickets you haven't closed sit behind a "Reveal full solution" gate. Revealing one is free.
- **Help when stuck:** Check fix lists what's done and what's missing, and a free three-step hint ladder ends in the model answer and a link to the guide.
- **Scoring:**
  - Low 10, Medium 15, High 22, Critical 30 and the boss 60 points, up to +3 for useful notes, +12 for a correct security escalation and +5 for a flawless boss.
  - Penalties for closing unresolved tickets, risky changes and needless escalations. A needless escalation costs the same as closing the ticket unresolved.
  - Each ticket is capped at −20…+42 (the boss at −30…+70). A perfect run through shifts 1–3 scores 742, and 810 with a flawless boss.
- **Ranks and achievements:** Trainee, Bronze (40), Silver (100), Gold (180), Platinum (280) and Diamond (760, which needs the boss), plus seven achievements.
- **Past tickets:** your score breakdown, notes, the model answer and the action log for every finished ticket.

## Documentation files

- [docs/HOW_TO_PLAY.md](docs/HOW_TO_PLAY.md): how the game works. No spoilers.
- [docs/SOLUTIONS.md](docs/SOLUTIONS.md) **(spoilers)** has, for every ticket:
  - an index table: ref, title, priority, category, tools and shift;
  - the full guide, required outcome, wrong actions and their penalties, hint ladder, model answer and ideal note.

  It ends with all 38 runbooks. It is generated from the ticket and runbook data in `index.html`, so it matches the game; regenerate it rather than editing it by hand.

## Checks performed

- **Self-test:** `index.html#selftest` runs every scenario from a fresh state through the same functions the consoles use, and all 369 checks pass. They cover:
  - wrong paths: a password reset alone doesn't unlock, rebooting a printer doesn't fix the spooler, and deleting the suspicious rule isn't rewarded;
  - scoring rules, and a model fix plus at least one tempting wrong action for every shift 2–3 ticket;
  - the consoles, chat replies, voicemails, shifts, ranks and save schema;
  - the documentation: every ticket has a full guide whose ideal note earns the full notes bonus and at least one runbook, and every runbook has all five sections;
  - the boss: it stays locked until shift 3 is cleared, it isn't complete when it arrives, every fix the requester already tried and every red herring leaves it unsolved, each layer advances only with its real fix, the risky actions carry penalties, old saves keep their progress, and the model solution completes it for 68 points. The boss tests start from a worst-case world in which shifts 1–3 were cleared without fixing anything.
- **Headless Chromium, from `file://`:** every non-file request and console error counts as a failure, and none occurred. The run covers:
  - the first-run welcome and queue order;
  - claiming and closing tickets, including the unresolved-close penalty;
  - Server Room topology, Remote Desktop, reload persistence, a corrupt save and blocked storage;
  - every console, Company Chat and Voicemails;
  - Documentation: runbooks, filters, the spoiler gate, links between guides and runbooks, and opening a ticket from its guide;
  - screenshots at 1366, 1024 and 390 px wide, with no sideways scrolling at 390 px;
  - the boss: the locked teaser, an old save loading with the boss added, the briefing, the BOSS queue row and ticket, and every new boss panel at all three widths.
- **Play-throughs:** every ticket has been played in the browser to a clean resolution with no penalties. The 10 shift 1 guides, six of the shift 2–3 guides and the boss guide were followed click by click and reached the best possible score (the boss: 68, ending at 810 points and Diamond). The boss has not had a blind playtest yet, so its difficulty is untested.

## Not built, and known limits

- Only tested in Chromium. The Tools menu and Escape-to-close-chat rely on the Popover API, so check older Firefox and Safari versions.
- Voicemails are transcripts only: no audio and no live calls.
- Chat replies are scripted. Typing to a requester gets a reply based on the ticket's state, but confirmations that a ticket requires only come from the quick-action buttons.
- The 32 tickets are fixed and play out the same way every time. There's no random or procedurally generated content and nothing after the boss stage.
- The boss's in-game clock only moves when you act (one minute per action), so waiting means acting or asking the requester to watch the next scheduled run.
- PCs only use DC01 for DNS, so when DC01's DNS stops, name lookups fail even though DC02 is running. `nslookup <name> dc02` is the only way to query DC02.
- No save export or import. Progress lives in one browser on one computer.
- Phone-width (390 px) layouts are checked automatically for sideways scrolling, but most shift 2 and 3 screens haven't been reviewed by eye at that width.
