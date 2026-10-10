# DeskOps Simulator — Claude Handoff Pack

**Purpose:** Build a polished, single-file, offline help-desk simulation game using the public ServiceDesk Simulator experience as a functional reference.

## Read in this order

1. `CLAUDE_BUILD_PROMPT.md` — paste this whole document into Claude as the primary task.
2. `docs/GAME_DESIGN_SPEC.md` — required behavior, screens, rules, visual direction, save system and edge cases.
3. `docs/TICKET_LIBRARY.md` — sample cases and exact resolution logic. Use these as the first testable scenario set.
4. `docs/IMPLEMENTATION_PLAN.md` — recommended build sequence and acceptance checklist.
5. `docs/REFERENCE_SOURCES.md` — direct links to publicly viewable reference screenshots and what to study in each.
6. Open the local original SVG mockups in `references/` for a quick picture of the intended layout. `references/reference-gallery.html` also links to source screenshots online.

## Non-negotiable delivery requirements

- The player starts directly in the game. **No login, signup, email, password, cloud account, paid tier, backend, analytics, external API, or network dependency.**
- Final playable deliverable is **one `index.html` file** with HTML, CSS, JavaScript, icon SVGs and game data embedded in that file.
- It must work after a user downloads the file from GitHub and double-clicks `index.html`, including from a `file://` URL and without internet.
- No build step, package installation, local server, CDN, external fonts, fetch/import of JSON, service worker, or required sibling file.
- Local save is optional-but-preferred and must use `localStorage` safely. The game must still run if storage is unavailable.
- Do not copy ServiceDesk Simulator branding, logos, exact prose, or its screenshot files into the playable product. Use the screenshots only as design/interaction references. Create original fictional company names, UI copy, icons and CSS/SVG visuals.

## Suggested fictional identity

**DeskOps Lab** — an original IT support training sandbox for a fictional company, Northstar Office Group. Neutral, practical, modern enterprise UI. Avoid purple login screen styling: there is no login screen. The in-game consoles should use a light, understated, blue-accented operations-dashboard look.

## What “done” means

A player can open the file, pick a ticket, claim it, inspect the scenario, use simulated tools to find and fix the cause, verify completion, close the ticket, earn points, review past work, refresh/close/reopen the browser and keep their progress. The page must never pretend to run real system commands or connect to real devices; all tools are safe simulations.
