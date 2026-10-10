# PRIMARY PROMPT FOR CLAUDE — BUILD DESKOPS LAB

You are an experienced frontend game developer. Build **DeskOps Lab**, a complete, playable, high-polish, offline IT service-desk simulator. Use the accompanying `docs/GAME_DESIGN_SPEC.md`, `docs/TICKET_LIBRARY.md`, `docs/IMPLEMENTATION_PLAN.md`, screenshots and local SVG mockups as the source of truth.

The player should feel like a first-line IT support technician working through realistic tickets with an interconnected set of simulated admin consoles. The core loop is: **choose a ticket → claim it → diagnose with the correct console(s) → perform the correct fix → verify → write resolution notes → close ticket → receive score and review feedback.** This loop is based on the flow documented by the reference site, but the final game must have original branding, original microcopy and its own visuals.

## Required delivery

Return a **single self-contained `index.html`**. Embed all HTML, CSS, JavaScript, SVG icons and ticket/object data into the file. It must work if a user downloads it from GitHub and double-clicks it from Windows Explorer/macOS Finder, with no server, no build tooling, no sign-in and no internet. Do not reference remote fonts, remote images, CDNs, APIs, analytics or external libraries. Do not use `fetch()` for data files or JavaScript module imports. Use CSS, inline SVG and vanilla JavaScript. Save progress in localStorage with a safe fallback if storage is blocked.

Also explain briefly how to run it and how to reset saved progress. Do not return only a plan, pseudocode, mockup or a partial skeleton: implement the playable game.

## Priorities

### P0 — mandatory, fully functional

1. Dashboard with ordered incident queue, priority, requester, category, ticket reference, and My Queue section.
2. Open a ticket; claim/unclaim it; show full description, impact, troubleshooting already tried, requester details, device/asset, status, assignee and resolution requirements.
3. Working Tools menu grouped into Infrastructure, Email, Knowledge and Management.
4. A Directory console with search and user profile tabs; at least account state, lockout, password-expired, group membership, mailbox/device facts, and functional simulated reset/unlock/enable/MFA/group actions.
5. A Server Room console with status overview, device/server tables, topology view and contextual simulated reboot/power/ISP actions.
6. A Remote Desktop console with machine search, simulated connect flow, desktop/taskbar and at least four app panels; the remote environment can drive ticket progress.
7. Mail Admin and Mail Security consoles sufficient to diagnose and fix failed, pending, quarantined and delivered mail cases.
8. Documentation / Knowledge Base that is searchable and contains hints/articles for the seeded tickets.
9. Ticket resolution model: completion is determined by scenario state flags/actions, not by the player clicking a magical “Solved” button. A “Check fix”/verification control can explain remaining requirements.
10. Close-ticket dialog with resolution notes, completion warning and point preview. Correctly completed ticket awards points; incorrect close warns about penalty and requires explicit confirmation.
11. Ticket history / Past Tickets with outcome, action log, time/score and model answer.
12. Hints available one step at a time; hints must not reduce score.
13. Local persistent profile, points, settings, ticket states and history; no identity/login needed. Use an editable local display name if desired.
14. Reset progress action with a confirmation dialog.
15. Keyboard-operable controls, clear focus states, responsive layout and no fatal console errors.

### P1 — implement if possible after P0 is stable

- Computer Deployment workflow and PC Shelf inventory.
- Asset Management and Ship Manager.
- Company Chat for post-fix employee confirmations.
- A small simulated workstation set of apps (File Explorer, Mail, VPN, Chat, Settings, System Update, Browser and a simulated Terminal).
- Achievements and compact local analytics.
- A lightweight “shift briefing” / new-ticket toast that does not block the player.

### P2 — optional polish only after the game works

- Text-only simulated phone call / voicemail ticket intake, audio only if generated with Web Audio and completely optional.
- Difficulty ramp, daily shift challenge and optional keyboard shortcuts.
- Additional ticket packs and more detailed desktop windows.

Do not let optional features delay the core ticket lifecycle or break direct-file offline execution.

## UX and design direction

Use a restrained, professional, light-theme operations UI: white surfaces, pale gray page background, hairline gray borders, deep gray text, and a clear cyan/blue accent for interactive and active states. Recommended tokens are documented in the spec. Use small, tracked uppercase labels for metadata and section headings, clean system fonts, compact tables and clear spacing. Screenshots show a deliberately quiet UI: color should communicate priority or state, not decorate every component. Use red for Critical, orange for High, amber for Medium and muted yellow for Low; always show the priority word as well as its color.

Top bar rather than a permanent left sidebar. Keep the player’s core context visible. The Tools popover/panel groups consoles into four categories. A ticket can stay visible beside a tool in split-screen mode on wide screens; on narrow screens use tabs or a stacked view. The interface should feel like a plausible work application, not a game HUD full of gradients, giant cards, animations or emojis.

Start directly at the dashboard. Do not create a login screen. First run can show a compact one-time “Welcome to your first shift” explainer with a “Start shift” button, but this must enter the real game and never ask for an account.

Use custom inline SVG icons or simple CSS symbols. No copied brand marks or third-party assets. Create a fictional firm, people, device hostnames, domain and email addresses (for example `northstar.local` and `@northstar.example`).

## Gameplay integrity

- Ticket completion must use a per-ticket objective checker. Example: an “account locked” case requires the correct user to be unlocked; changing another user does nothing to the ticket.
- Read-only investigations should produce findings; mutating actions change the simulated environment.
- Some cases require multiple steps: unlock then reset password; find a quarantined email in Mail Security and release it; verify a device is online after a reboot; distinguish a single-user problem from a shared network outage.
- Provide contextual feedback when a player makes a wrong or risky change, but avoid arbitrary gotchas.
- Security-sensitive cases should teach safe choices. A suspicious inbox-forwarding rule should be escalated, not silently deleted as if it were routine housekeeping.
- Tool state and ticket state must be shared. Fixing a setting in Directory or Server Room should be reflected when the player revisits the tool and when they verify the ticket.
- All “terminal” commands are fictional/simulated strings interpreted locally by the game. Never invoke real shell commands, OS APIs, devices or network endpoints.

## Final quality bar

The app should look complete at 1366×768 and remain usable at 1024px and mobile widths. Buttons must all do something real; no dead controls or lorem ipsum. At minimum, implement and test all cases in `docs/TICKET_LIBRARY.md`. Avoid one giant unreadable function: keep state, rendering, scenario checks, tool actions, scoring, storage and modal handling in small named functions inside the one HTML file. Add comments at the important architectural boundaries.

At the end, include a compact test checklist with the exact manual checks you performed. Be honest about any unfinished P1/P2 feature.
