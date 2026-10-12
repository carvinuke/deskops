# DeskOps Lab

An offline IT service-desk training game. You're a first-line technician at the fictional Northstar Office Group: pick a ticket, claim it, investigate in simulated admin consoles, fix the right thing, verify it, then close or escalate it and get scored.

Everything is fictional and local. No account, server, mailbox or command is real, and the page makes no network requests.

## Run it

Download `index.html` and double-click it. That's the whole game: no install, no build step, no server, no internet, no login. It runs from a `file://` path.

New here? Read [docs/HOW_TO_PLAY.md](docs/HOW_TO_PLAY.md) for the core loop, scoring, ranks, shifts, a tour of the tools and keyboard tips.

## Progress and reset

Progress (points, tickets, notes, chat, and every change you make to the simulated environment) is saved in your browser's local storage on that computer, under the key `deskops-lab-v3`. Saves from older versions are ignored, so you start a fresh shift.

- **Reset:** click your name (top right), select **Reset progress…** and confirm.
- **Storage blocked:** the game still runs and shows a banner saying progress lasts only until the tab closes.
- **Corrupted save:** detected on load. The game starts a fresh shift and tells you.

## What's in it

- **31 tickets over three shifts.** Shift 1 (10 tickets): lockouts, an expired password, share permissions, a floor outage, Wi-Fi, quarantined mail, a full mailbox, a malicious forwarding rule, a crashed print spooler and a VPN profile. Shift 2 (10): hardware swaps, new starters, a remote laptop replacement, a full disk, displays, a social-engineering voicemail, a weak charger, a full DHCP scope, a new phone and shared-mailbox access. Shift 3 (11): joiner, name change, leaver, MFA reset, a returner, a vishing call, a DNS outage, a provider outage, a full file server, a file restore and reported phishing.
- **Ticket intake like a real desk:** a queue sorted by priority, plus requests that arrive as Company Chat messages or voicemails and must be logged first. Some tickets only appear after another is finished.
- **Ten consoles:** Directory, Server Room, Remote Desktop, Computer Deployment, PC Shelf, Mail Admin, Mail Security, Documentation, Asset Management and Ship Manager. Every action in them is real within the simulation, and tickets are checked against that shared state.
- **Company Chat and Voicemails:** 16 fictional staff at the start (more join as tickets arrive), with presence, scripted replies, ticket quick actions (ask to confirm the fix, ask for approval) and an #office-announcements channel. Voicemails are transcripts with caller ID, and you can log, save, forward or delete them.
- **Documentation:**
  - 37 runbooks, one per procedure the tickets use, each with purpose, prerequisites, steps, verification and when to escalate.
  - A solution guide for every ticket: symptoms to notice, diagnosis, click-by-click steps, how to verify, common mistakes, a real-world note, the hint ladder, scoring with every penalty, and an ideal resolution note.
  - Guides for tickets you haven't closed sit behind a "Reveal full solution" gate. Revealing one is free.
- **Help when stuck:** Check fix lists what's done and what's missing, and a free three-step hint ladder ends in the model answer and a link to the guide.
- **Scoring:**
  - Low 10, Medium 15, High 22 and Critical 30 points, up to +3 for useful notes, and +12 for a correct security escalation.
  - Penalties for closing unresolved tickets, risky changes and needless escalations.
  - Each ticket is capped at −20…+42, and a perfect run scores 742.
- **Ranks and achievements:** Trainee, Bronze (40), Silver (100), Gold (180) and Platinum (280), plus five achievements.
- **Past tickets:** your score breakdown, notes, the model answer and the action log for every finished ticket.

## Documentation files

- [docs/HOW_TO_PLAY.md](docs/HOW_TO_PLAY.md): how the game works. No spoilers.
- [docs/SOLUTIONS.md](docs/SOLUTIONS.md) **(spoilers)** has, for every ticket:
  - an index table: ref, title, priority, category, tools and shift;
  - the full guide, required outcome, wrong actions and their penalties, hint ladder, model answer and ideal note.

  It ends with all 37 runbooks. It is generated from the ticket and runbook data in `index.html`, so it matches the game; regenerate it rather than editing it by hand.

## Checks performed

- **Self-test:** `index.html#selftest` runs every scenario from a fresh state through the same functions the consoles use, and all 278 checks pass. They cover:
  - wrong paths: a password reset alone doesn't unlock, rebooting a printer doesn't fix the spooler, and deleting the suspicious rule isn't rewarded;
  - scoring rules, and a model fix plus at least one tempting wrong action for every shift 2–3 ticket;
  - the consoles, chat replies, voicemails, shifts, ranks and save schema;
  - the documentation: every ticket has a full guide whose ideal note earns the full notes bonus and at least one runbook, and every runbook has all five sections.
- **Headless Chromium, from `file://`:** every non-file request and console error counts as a failure, and none occurred. The run covers:
  - the first-run welcome and queue order;
  - claiming and closing tickets, including the unresolved-close penalty;
  - Server Room topology, Remote Desktop, reload persistence, a corrupt save and blocked storage;
  - every console, Company Chat and Voicemails;
  - Documentation: runbooks, filters, the spoiler gate, links between guides and runbooks, and opening a ticket from its guide;
  - screenshots at 1366, 1024 and 390 px wide, with no sideways scrolling at 390 px.
- **Play-throughs:** every ticket has been played in the browser to a clean resolution with no penalties. The 10 shift 1 guides and six of the shift 2–3 guides were followed click by click and reached the best possible score.

## Not built, and known limits

- Only tested in Chromium. The Tools menu and Escape-to-close-chat rely on the Popover API, so check older Firefox and Safari versions.
- Voicemails are transcripts only: no audio and no live calls.
- Chat replies are scripted. Typing to a requester gets a reply based on the ticket's state, but confirmations that a ticket requires only come from the quick-action buttons.
- The 31 tickets are fixed and play out the same way every time. There's no random or procedurally generated content and no shifts beyond three.
- PCs only use DC01 for DNS, so when DC01's DNS stops, name lookups fail even though DC02 is running. `nslookup <name> dc02` is the only way to query DC02.
- No save export or import. Progress lives in one browser on one computer.
- Phone-width (390 px) layouts are checked automatically for sideways scrolling, but most shift 2 and 3 screens haven't been reviewed by eye at that width.
