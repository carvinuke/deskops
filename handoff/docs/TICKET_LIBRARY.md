# Starter Ticket Library — DeskOps Lab

Implement at least the ten cases below as real scenarios. Additional cases can be procedural or randomized only after these deterministic cases work. The **ticket must respond to persistent environment state**, not a one-off button click. IDs and all people/addresses below are fictional.

## Shared seed environment

**Organization:** Northstar Office Group. Domain: `northstar.local`. Mail domain: `northstar.example`.

Seed people:
- **Maya Chen** (`mchen`, Finance) — `maya.chen@northstar.example`, workstation `NS-FIN-014`, groups `Domain Users`, `Finance-Share`.
- **Evan Brooks** (`ebrooks`, Sales) — `evan.brooks@northstar.example`, workstation `NS-SALES-008`, groups `Domain Users`, `Sales-Share`.
- **Priya Shah** (`pshah`, Human Resources) — `priya.shah@northstar.example`, workstation `NS-HR-003`, groups `Domain Users`, `HR-Share`.
- **Leo Martinez** (`lmartinez`, Support) — `leo.martinez@northstar.example`, workstation `NS-SUP-002`, groups `Domain Users`, `Support-Share`.
- **Jordan Price** (`jprice`, Operations) — `jordan.price@northstar.example`, workstation `NS-OPS-021`, groups `Domain Users`, `Operations-Share`.
- **Avery Wilson** (`awilson`, Executive Office) — `avery.wilson@northstar.example`, workstation `NS-EXEC-001`, groups `Domain Users`, `Executive-Share`.

Seed infrastructure: MetroFiber ISP (up), Edge Router `10.0.0.1`, Main Firewall `10.0.0.254`, Floor 1 Switch `10.0.1.1`, Floor 2 Switch `10.0.2.1`, Floor 3 Switch `10.0.3.1`, Lobby Wi-Fi AP `10.0.10.1`, Cafe Wi-Fi AP `10.0.10.2`. Servers: `DC01`, `DC02`, `FILE01`, `MAIL01`, `PRINT01`. Devices may map to one or more tickets; an action on a shared entity should affect every case that depends on it.

## Scenario 1 — Account locked after vacation

- **Reference:** `INC-1042`
- **Priority/category:** High / Access
- **Requester/asset:** Maya Chen / `NS-FIN-014`
- **Description:** “Hi, I’m back from vacation and my account says it’s locked. I can’t open the finance share and payroll is due this afternoon. My colleague can still open it.”
- **Impact:** One Finance employee is blocked from payroll work; other staff can access the share.
- **Already tried:** “Restarted the laptop twice. Same message.”
- **Seed state:** `mchen.locked = true`; account enabled; password not expired; membership correct.
- **Required tool:** Directory → search `mchen` → Authentication.
- **Objectives:** Correct user is unlocked. No need to reset password unless the player does so, but that extra action is harmless.
- **Wrong-action feedback:** resetting the password alone leaves the account locked; tell player explicitly.
- **Hint ladder:** (1) “Because a colleague can reach the share, start with Maya’s account rather than the network.” (2) “Search for Maya in Directory and inspect Authentication.” (3) “Unlock `mchen`.”
- **Model answer:** Verified the requester’s account, cleared the lockout in Directory, asked the requester to sign in again and confirmed Finance share access.
- **Points:** High +22.

## Scenario 2 — Password expired and account also locked

- **Reference:** `INC-1043`
- **Priority/category:** High / Access
- **Requester/asset:** Evan Brooks / `NS-SALES-008`
- **Description:** “I can’t get into my laptop or Sales Hub this morning. Yesterday it kept telling me to change my password, and now it says the account is locked.”
- **Impact:** Sales rep cannot access pipeline notes before a customer meeting.
- **Already tried:** “Tried the old password a bunch of times.”
- **Seed state:** `ebrooks.locked = true`; `ebrooks.passwordExpired = true`.
- **Objectives:** Unlock the account, reset the password, set “must change at next sign-in”, and record a successful sign-in check.
- **Important rule:** resetting a password does not clear `locked`; both objectives must be satisfied.
- **Hint ladder:** locked and expired are separate flags; check Authentication first; unlock, then reset password and require a change at sign-in.
- **Model answer:** Checked the account state, unlocked the user, reset the expired password, required a change at the next sign-in and verified access.
- **Points:** High +22.

## Scenario 3 — Finance share access denied

- **Reference:** `INC-1044`
- **Priority/category:** Medium / Access
- **Requester/asset:** Maya Chen / `NS-FIN-014`
- **Description:** “My login works, but I get Access Denied when I open `\\FILE01\Finance`. My teammate can still open the same folder.”
- **Impact:** One user is blocked from a critical departmental share; authentication is healthy.
- **Already tried:** “Restarted File Explorer and signed out/in once.”
- **Seed state:** Maya's `Finance-Share` membership removed, account otherwise healthy.
- **Required tools:** Directory → Groups; optional Remote Desktop → File Explorer to verify.
- **Objectives:** Add `mchen` to `Finance-Share`, then sign-in refresh/re-authentication is acknowledged (a “sign out and back in” check or explicit verify action).
- **Wrong action:** resetting password does not fix permissions.
- **Hint ladder:** the login succeeds; compare authorization/group membership; add Finance-Share and refresh the session.
- **Model answer:** Confirmed identity, restored required group membership, refreshed the session, and verified the share opens.
- **Points:** Medium +15.

## Scenario 4 — Entire third floor lost network

- **Reference:** `INC-1045`
- **Priority/category:** Critical / Network
- **Requester/asset:** Multiple users / Floor 3 network
- **Description:** “Nobody on the third floor can reach the internet or shared drives. Floors one and two are fine. It started about five minutes ago.”
- **Impact:** Multi-user business interruption isolated to Floor 3.
- **Already tried:** “Users have reconnected to Wi-Fi and restarted PCs. No change.”
- **Seed state:** Floor 3 Switch `10.0.3.1` down; ISP/router/firewall and other switches healthy.
- **Required tool:** Server Room → Overview/Topology/Devices.
- **Objectives:** Locate the Floor 3 switch as the narrowest failed shared component; power on/reboot it; confirm status online and that affected subnet is restored.
- **Wrong action:** checking ISP is harmless but should indicate ISP online; rebooting the whole network is discouraged and triggers a small explained penalty.
- **Hint ladder:** impact is a floor, while other floors work; trace topology to the Floor 3 branch; restore Floor 3 Switch.
- **Model answer:** Compared the outage scope with the topology, identified the failed Floor 3 switch, restored it and confirmed the affected segment returned online.
- **Points:** Critical +30.

## Scenario 5 — One user's Wi-Fi drops

- **Reference:** `INC-1046`
- **Priority/category:** Medium / Network
- **Requester/asset:** Jordan Price / `NS-OPS-021`
- **Description:** “My Wi-Fi keeps disconnecting during calls. People sitting around me seem fine, and the rest of the office is working.”
- **Impact:** One user experiences intermittent connectivity; shared network devices are healthy.
- **Already tried:** “Forgot the Wi-Fi network and rejoined.”
- **Seed state:** All infrastructure online; workstation Wi-Fi profile has an invalid saved profile.
- **Required tool:** Remote Desktop → Settings/Network (or simulated VPN/Wi-Fi panel).
- **Objectives:** Inspect local connection/profile, remove the broken saved profile, reconnect to `Northstar-Staff`, verify connected and ping gateway succeeds in simulated output.
- **Wrong action:** restarting the core router causes an unnecessary outage; give feedback/penalty.
- **Hint ladder:** a single device while nearby colleagues work points to the workstation; inspect its saved Wi-Fi profile; recreate it and test connectivity.
- **Model answer:** Verified the wider network was healthy, recreated the affected workstation's Wi-Fi profile, reconnected and verified gateway reachability.
- **Points:** Medium +15.

## Scenario 6 — Legitimate email quarantined

- **Reference:** `INC-1047`
- **Priority/category:** High / Software (Email)
- **Requester/asset:** Priya Shah / mailbox `priya.shah@northstar.example`
- **Description:** “A supplier sent today’s onboarding spreadsheet, but it never arrived. They say they got no bounce. I checked Junk and it isn’t there.”
- **Impact:** HR onboarding delayed.
- **Already tried:** “Checked Junk and asked the supplier to resend once.”
- **Seed state:** a safe legitimate message is quarantined by a too-strict filter rule; sender, recipient and subject are pre-seeded.
- **Required tools:** Mail Admin → Message Trace, then Mail Security → Quarantine.
- **Objectives:** Message Trace shows `Quarantined`; player finds the matching message in Mail Security and releases it; status becomes Delivered; verify requester can see it.
- **Wrong action:** changing mailbox password does not help.
- **Hint ladder:** check the trace to find where the message stopped; Quarantined means it is in the filter; release the matching legitimate message.
- **Model answer:** Traced the message, confirmed the filtering service quarantined it, released the verified legitimate item and confirmed delivery.
- **Points:** High +22.

## Scenario 7 — Mailbox over quota

- **Reference:** `INC-1048`
- **Priority/category:** Medium / Software (Email)
- **Requester/asset:** Avery Wilson / mailbox `avery.wilson@northstar.example`
- **Description:** “People get a bounce when they email me, with a mailbox full message. I can still sign in to webmail and read old messages.”
- **Impact:** Executive Office cannot receive new messages.
- **Already tried:** “Signed out of webmail and tried again.”
- **Seed state:** mailbox storage 99% of 5 GB; send/receive blocked; archive disabled.
- **Required tool:** Mail Admin → Mailbox Admin.
- **Objectives:** Inspect storage/status, enable archive or apply the allowed safe quota remedy, ensure mailbox state becomes able to receive mail, verify by simulation.
- **Wrong action:** resetting the user account password is unrelated.
- **Hint ladder:** sign-in still works; this is mailbox delivery, not identity; inspect mailbox storage and quota.
- **Model answer:** Checked mailbox properties, found quota enforcement, enabled the approved archive/space remedy and confirmed delivery recovered.
- **Points:** Medium +15.

## Scenario 8 — Suspicious inbox forwarding rule

- **Reference:** `INC-1049`
- **Priority/category:** Critical / Security
- **Requester/asset:** Leo Martinez / mailbox `leo.martinez@northstar.example`
- **Description:** “A coworker says some replies to my password-reset emails are disappearing. I found a forwarding address I don’t recognize in my mailbox settings.”
- **Impact:** Possible account compromise and data exfiltration.
- **Already tried:** “I did not create any new rules.”
- **Seed state:** suspicious inbox rule applies to all incoming messages and forwards a copy to `external-archive@outside.example`.
- **Required tools:** Mail Admin → Inbox Rules; ticket Options → Escalate to Security. Optional Mail Security investigation panel.
- **Objectives:** Inspect rule and recognize it as suspicious, escalate ticket to Security, record evidence in work notes. Do not delete the rule as the only action; the safe simulation should mark Security as owner of disabling/remediating it.
- **Scoring:** Correct escalation +12 or critical-case credit; routine closure without escalation remains unresolved and warns player.
- **Hint ladder:** a rule that forwards everything externally is a security concern; preserve evidence and do not treat it like housekeeping; escalate to Security.
- **Model answer:** Inspected the rule, documented the external forwarding evidence, avoided destroying evidence and escalated to Security for containment.
- **Points:** Critical +30 plus correct escalation bonus if desired; cap total as defined in main scoring rules.

## Scenario 9 — Printer queue stuck for everyone

- **Reference:** `INC-1050`
- **Priority/category:** High / Server
- **Requester/asset:** Multiple users / `PRINT01`
- **Description:** “Everyone in the office gets ‘Printing’ forever, and nothing is coming out of the shared printers. The printers themselves are powered on.”
- **Impact:** Company-wide printing unavailable; all printer models affected.
- **Already tried:** “Power-cycled one printer; it did not help.”
- **Seed state:** `PRINT01` spooler/service unhealthy; network and individual printers online.
- **Required tool:** Server Room → Servers (PRINT01), or Remote Desktop → simulated Services panel.
- **Objectives:** Read service status; restart print spooler or the relevant service on `PRINT01`; confirm service healthy and a test job finishes.
- **Wrong action:** restarting an individual printer does not resolve the shared service.
- **Hint ladder:** every printer at once means a shared dependency; inspect the print server; restore the spooler and test a job.
- **Model answer:** Identified the shared print server rather than a single printer, restarted the failed spooler service and confirmed a test job completed.
- **Points:** High +22.

## Scenario 10 — VPN cannot connect from home

- **Reference:** `INC-1051`
- **Priority/category:** High / Network
- **Requester/asset:** Evan Brooks / `NS-SALES-008`
- **Description:** “I’m at home and the VPN says my connection profile is invalid. The internet works and I can browse normal websites, but I can’t reach the company drive.”
- **Impact:** Remote worker cannot access internal resources.
- **Already tried:** “Restarted the laptop and checked the home router.”
- **Seed state:** internet connected; VPN client has obsolete `Northstar-Legacy` profile; current profile is `Northstar-Staff`.
- **Required tool:** Remote Desktop → VPN Client.
- **Objectives:** inspect profile, switch to `Northstar-Staff`, connect VPN, verify internal gateway reachability / mapped drive.
- **Wrong action:** reset account password without evidence; does not change the VPN profile.
- **Hint ladder:** public internet works; fault is the tunnel/client profile; select the current Northstar-Staff profile and verify tunnel.
- **Model answer:** Confirmed ordinary internet connectivity, replaced the obsolete VPN profile with the current profile, connected and verified internal access.
- **Points:** High +22.

## Cross-ticket engine rules

1. A single underlying entity can support multiple cases; changing it should update all dependent cases (e.g. a recovered shared switch clears the infrastructure state for the floor outage).
2. Avoid impossible ticket states: all “correct” fixes must be available in the seeded environment with no hidden real-time dependency.
3. Every mutation produces a local action-log entry with time, tool, entity and action. The log powers ticket work notes and Past Tickets review.
4. A user-targeted fix must confirm identity before mutation. Similar names should not create ambiguity in the first ten tickets; introduce lookalikes later as a training challenge.
5. `Check Fix` returns a structured result: all completed objective names, remaining objective names and an overall `complete` boolean. Do not expose `modelAnswer` until the hint flow is fully exhausted or ticket is closed.
