# DeskOps Lab · Solution guides and runbooks

> **Spoilers.** Every ticket’s full solution is below. The same guides are in the game under **Tools › Documentation › Solution guides**, where tickets you haven’t closed stay behind a “Reveal full solution” gate. Reading a guide is free: it never changes your score.

This file is generated from the ticket and runbook data in `index.html`, so it always matches the game. Don’t edit it by hand.

31 tickets across 3 shifts, and 37 runbooks.

## Contents

- [How scoring works](#how-scoring-works)
- [Ticket index](#ticket-index)
- [Shift 1 · Monday morning](#shift-1)
- [Shift 2 · Tuesday](#shift-2)
- [Shift 3 · Wednesday](#shift-3)
- [Runbooks](#runbooks)

## How scoring works

| Outcome | Points |
|---|---|
| Resolve a Critical / High / Medium / Low ticket | +30 / +22 / +15 / +10 |
| Correct escalation of a security ticket to Security | +12 |
| Resolution notes: 40+ characters, a ticket keyword, and “verified”, “confirmed” or “tested” | +1 each, up to +3 |
| Close a ticket that isn’t resolved | −20 (Critical), −15 (High), −10 (Medium, Low) |
| Escalate a routine ticket to Security | −8 |
| Escalate a security ticket before its case is ready | −20 (Critical), −15 (High), −10 (Medium, Low) |
| Ticket-specific wrong actions (listed per ticket) | −2 to −6 each, charged once at close (they count from the moment the ticket arrives) |
| Cap per ticket | −20 … +42 |

Hints and these guides are free.

## Ticket index

| Ref | Title | Priority | Category | Tools | Shift |
|---|---|---|---|---|---|
| [INC-1042](#inc-1042) | Account locked after returning from vacation | High | Access / Account lockout | Directory, Company Chat | 1 |
| [INC-1043](#inc-1043) | Locked out after the password expired | High | Access / Password | Directory | 1 |
| [INC-1044](#inc-1044) | Finance share says Access Denied | Medium | Access / Permissions | Directory, Remote Desktop | 1 |
| [INC-1045](#inc-1045) | Nobody on the third floor can reach the network | Critical | Network / Outage | Server Room, Remote Desktop | 1 |
| [INC-1046](#inc-1046) | Wi-Fi keeps dropping during calls | Medium | Network / Wi-Fi | Remote Desktop, Voicemails | 1 |
| [INC-1047](#inc-1047) | Supplier email is missing from the inbox | High | Email / Delivery | Mail Admin, Mail Security | 1 |
| [INC-1048](#inc-1048) | Mailbox is full and new mail bounces | Medium | Email / Mailbox | Mail Admin | 1 |
| [INC-1049](#inc-1049) | Unknown forwarding address in my mailbox | Critical | Security / Mailbox | Mail Admin | 1 |
| [INC-1050](#inc-1050) | Shared printers are stuck on “Printing” | High | Server / Printing | Server Room, Voicemails | 1 |
| [INC-1051](#inc-1051) | VPN profile invalid when working from home | High | Network / VPN | Remote Desktop | 1 |
| [INC-1052](#inc-1052) | Dispatch desk PC is dead: no lights, no fans | Critical | Hardware / Desktop failure | Remote Desktop, Computer Deployment, PC Shelf, Asset Management, Company Chat | 2 |
| [INC-1053](#inc-1053) | New Finance starter on Monday: laptop build and handover | Medium | Hardware / New starter | Directory, Computer Deployment, PC Shelf, Asset Management, Company Chat | 2 |
| [INC-1054](#inc-1054) | Remote worker dropped laptop, screen shattered | High | Hardware / Remote replacement | Directory, Remote Desktop, Computer Deployment, PC Shelf, Asset Management, Ship Manager, Company Chat, Voicemails | 2 |
| [INC-1055](#inc-1055) | Laptop crawling, “restart to update” every afternoon | Medium | Hardware / Performance & updates | Remote Desktop, Company Chat | 2 |
| [INC-1056](#inc-1056) | Second monitor says “No signal” after a boardroom presentation | Low | Hardware / Peripherals & display | Remote Desktop, Company Chat | 2 |
| [INC-1057](#inc-1057) | Voicemail: “Avery Wilson” wants a laptop couriered to a hotel today | Critical | Security / Social engineering (device) | Directory, Asset Management, Company Chat, Voicemails | 2 |
| [INC-1058](#inc-1058) | Laptop battery drains while plugged in | Low | Hardware / Power & accessories | Remote Desktop, PC Shelf, Asset Management, Company Chat | 2 |
| [INC-1064](#inc-1064) | Access to the Sales Orders inbox while covering | Low | Email / Shared mailbox access | Directory, Mail Admin, Company Chat | 2 |
| [INC-1067](#inc-1067) | New laptop on Floor 2 says “No internet” | Medium | Network / DHCP | Server Room, Remote Desktop, Company Chat | 2 |
| [INC-1071](#inc-1071) | New phone won’t sync company email | Low | Email / Mobile access | Mail Admin, Company Chat | 2 |
| [INC-1059](#inc-1059) | New starter tomorrow: Sales account, laptop and licences | High | Identity / Joiner | Directory, Computer Deployment, Documentation, Company Chat | 3 |
| [INC-1060](#inc-1060) | Name changed after marriage but email still shows old name | Low | Identity / Profile change | Directory, Mail Admin, Documentation, Company Chat | 3 |
| [INC-1061](#inc-1061) | Leaver offboarding: Operations coordinator finished Friday | High | Identity / Leaver | Directory, Mail Admin, Asset Management | 3 |
| [INC-1062](#inc-1062) | Voicemail: lost phone, can’t approve sign-ins | High | Security / MFA reset | Directory, Asset Management, Company Chat, Voicemails | 3 |
| [INC-1063](#inc-1063) | Back from parental leave: account disabled | Medium | Access / Return from leave | Directory, Remote Desktop | 3 |
| [INC-1065](#inc-1065) | Voicemail: urgent password reset for the Chief of Staff | Critical | Security / Social engineering | Directory, Company Chat, Voicemails | 3 |
| [INC-1066](#inc-1066) | Intranet and shared drives “can’t be found” for everyone | Critical | Network / Name resolution | Server Room, Remote Desktop | 3 |
| [INC-1068](#inc-1068) | Websites and card machines down, but shared drives still open | Critical | Network / ISP | Server Room, Remote Desktop, Company Chat, Voicemails | 3 |
| [INC-1069](#inc-1069) | “Not enough space” when saving to any shared drive | High | Server / Storage | Server Room, Remote Desktop | 3 |
| [INC-1070](#inc-1070) | Starters spreadsheet vanished from the HR drive | Medium | Server / File restore | Server Room, Remote Desktop, Company Chat | 3 |
| [INC-1072](#inc-1072) | Reported email: “Mailbox storage limit reached, revalidate within 24 hours” | High | Security / Phishing | Mail Admin, Mail Security, Company Chat | 3 |

<a id="shift-1"></a>

## Shift 1 · Monday morning

A busy Monday: lockouts after the weekend, a floor outage and printing problems. Work critical tickets first. Your team lead Dana Okafor has left you a message in Company Chat.

<a id="inc-1042"></a>

### INC-1042 · Account locked after returning from vacation

**Priority:** High (22 points) · **Category:** Access / Account lockout · **Arrives:** at the start of shift 1 · **Finish with:** Close ticket · **Best score:** +25

**Tools:** Directory, Company Chat  
**Runbooks:** [Unlocking a locked account](#kb1)

**The ticket**

> Hi, I’m back from vacation and my account says it’s locked. I can’t open the Finance share and payroll is due this afternoon. My colleague can still open it.
>
> *Business impact:* One Finance employee is blocked from payroll work. Other staff can still reach the share.
>
> *Already tried:* Restarted the laptop twice. Same message.

#### Symptoms to notice

- Maya is back from vacation and the message says “locked”. That word points at her account, not the network or the share.
- A colleague can still open \\\\FILE01\\Finance, so FILE01, the share and the network are all working.
- Directory › Maya Chen › Authentication: Account Enabled, Lockout Locked, Password Current, MFA Enrolled.
- Last sign-in Sep 26, 17:42: nothing since she went away, so the lockout came from failed attempts, not from a working session.
- Restarting the laptop twice didn’t help: a lockout is held on the domain controller, not on the PC.

#### Diagnosis

One user, one account, a clear error message and healthy colleagues: this is an authentication problem on a single account. Read every flag on the Authentication tab before changing anything, because locked, disabled, expired and MFA are separate states with separate fixes. Only Lockout is wrong here, so the whole fix is Unlock account. A password reset wouldn’t clear the lockout (the game tells you so) and would make Maya learn a new password for no reason.

#### Perfect steps

1. Open INC-1042 from the Incidents queue and select Assign to me.
2. Select Open Tools › Directory. Type “maya” in the search box and select Maya Chen (mchen · Finance). The Authentication tab opens.
3. Read every row: Account Enabled, Lockout Locked, Password Current, MFA Enrolled, Last sign-in Sep 26, 17:42.
4. Good practice: select Verify identity…, choose “Callback to number on record” and select Run check before you change her account.
5. Select Unlock account. The flash reads “Maya Chen’s account is unlocked.” and Lockout changes to Not locked.
6. Select Test sign-in. Expect “Sign-in test passed for mchen.”
7. Optional: open Company Chat › Maya Chen, type “Can you try signing in now?” and press Enter. Maya replies that it’s working.
8. Select Check fix (in the ticket column, or after Back to INC-1042). “Maya’s account is unlocked” turns green.
9. Select Close ticket, write a resolution note and select Close ticket in the dialog.

#### Verify

- Directory › Maya Chen › Authentication: Lockout Not locked, Account Enabled, Last sign-in test Passed.
- Check fix: 1 of 1 requirement met, and the ticket chip reads Resolved.
- Optional: Remote Desktop › NS-FIN-014 › File Explorer › Open on F: (\\\\FILE01\\Finance) reads “Opened \\\\FILE01\\Finance.”

#### Required outcome (what Check fix tests)

- Maya’s account is unlocked

#### Common mistakes

- Resetting the password instead of unlocking. The reset succeeds, but the flash warns that a password reset doesn’t clear a lockout.
- Investigating FILE01 or the network although a colleague can open the same share.
- Selecting Disable account: that is a different state and stops her signing in at all.
- Closing before Check fix is green: closing an unresolved High ticket costs 15 points.

#### Wrong actions and penalties

No ticket-specific penalties.

Closing it unresolved costs −15. Escalating it to Security costs −8.

#### Hint ladder

1. Because a colleague can reach the share, start with Maya’s account rather than the network.
2. Search for Maya in Directory and open the Authentication tab.
3. Unlock mchen.

#### Model answer

Verified the requester’s account, cleared the lockout in Directory, asked the requester to sign in again and confirmed Finance share access.

#### Ideal resolution note

> Cause: mchen locked out after vacation (last sign-in Sep 26); password current and account enabled. Action: verified Maya by callback to the number on record, then Directory › Authentication › Unlock account. No password reset needed. Verified: sign-in test passed and Maya confirmed in chat that she can sign in.

Earns +3 of 3 for notes. Keywords: `mchen`, `maya`, `ns-fin-014`.

#### In the real world

Lockouts after a holiday are among the most common service-desk calls. The usual cause is a device still trying an old or mistyped password (a phone mail app, or a mapped drive with saved credentials), which trips the lockout threshold. Real desks verify the caller before unlocking, and if the lockout comes back they look up the lockout source in the domain controller logs and fix that device.

<a id="inc-1043"></a>

### INC-1043 · Locked out after the password expired

**Priority:** High (22 points) · **Category:** Access / Password · **Arrives:** at the start of shift 1 · **Finish with:** Close ticket · **Best score:** +25

**Tools:** Directory  
**Runbooks:** [Unlocking a locked account](#kb1), [Resetting a password safely](#kb2)

**The ticket**

> I can’t get into my laptop or Sales Hub this morning. Yesterday it kept telling me to change my password, and now it says the account is locked.
>
> *Business impact:* A sales rep can’t reach pipeline notes before a customer meeting.
>
> *Already tried:* Tried the old password a bunch of times.

#### Symptoms to notice

- “Yesterday it kept telling me to change my password”: the password expired overnight.
- “Now it says the account is locked”: trying the old password again and again tripped the lockout.
- Directory › Evan Brooks › Authentication: Lockout Locked and Password Expired. Two separate flags.
- He can’t reach Sales Hub either: every app signs in with the same account, so this isn’t an app fault.
- Last sign-in Yesterday 17:55 from his laptop, before the password expired.

#### Diagnosis

Two faults on one account, and each needs its own fix. Unlock clears the lockout but leaves the password expired; a password reset clears the expiry but not the lockout. The ticket is only done when both are fixed, the temporary password must be changed at the next sign-in (so only Evan ends up knowing it), and a sign-in test proves the account works. Run the test last, because every unlock or reset clears the previous test result.

#### Perfect steps

1. Open INC-1043 and select Assign to me.
2. Open Tools › Directory, search “evan” and select Evan Brooks. On Authentication read Lockout Locked and Password Expired.
3. Select Verify identity…, choose “Callback to number on record” and select Run check. Identity check now reads Callback to number on record.
4. Select Unlock account. The flash adds “The password is still expired.”
5. Select Reset password…. Keep “User must change password at next sign-in” ticked, leave “Deliver the temporary password” on “Read to user on a verified call” and select Reset password.
6. Select Test sign-in. Expect “Sign-in test passed for ebrooks. They’ll be asked to choose a new password.”
7. Select Check fix: all four requirements are green.
8. Select Close ticket, write a resolution note and select Close ticket in the dialog.

#### Verify

- Authentication: Lockout Not locked; Password Current with the chip “Must change at next sign-in” and “reset 1× today · sent via Read to user on a verified call”; Last sign-in test Passed.
- Check fix: 4 of 4 requirements met.

#### Required outcome (what Check fix tests)

- Evan’s account is unlocked
- Expired password was reset
- Must change password at next sign-in
- Sign-in test passed after the fix

#### Common mistakes

- Fixing only one of the two flags. Unlock alone, or a reset alone, still leaves Evan unable to sign in.
- Unticking “User must change password at next sign-in”: the desk would then know his working password.
- Running Test sign-in before the last change. Any unlock or reset clears the result, so test last.
- Sending the temporary password by chat or to a personal email address instead of reading it to him on a verified call.
- Resetting before verifying: the reset dialog warns that the caller hasn’t been verified.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Sent the temporary password by chat or to a personal email address | −3 |

Closing it unresolved costs −15. Escalating it to Security costs −8.

#### Hint ladder

1. Locked and expired are two separate problems on the same account.
2. Open Evan’s Authentication tab in Directory and read every flag.
3. Unlock ebrooks, reset the password with “must change at next sign-in”, then run a sign-in test.

#### Model answer

Checked the account state, unlocked the user, reset the expired password, required a change at the next sign-in and verified access with a sign-in test.

#### Ideal resolution note

> Cause: ebrooks password expired overnight; repeated attempts with the old password locked the account. Action: verified Evan by callback to the number on record, unlocked the account and reset the password (must change at next sign-in), temporary password read to him on the verified call. Verified: Test sign-in passed and he is prompted to set a new password.

Earns +3 of 3 for notes. Keywords: `ebrooks`, `evan`, `ns-sales-008`.

#### In the real world

Expired-then-locked is a classic chain: the expiry prompt gets ignored, the user keeps typing the old password and the lockout policy trips. Remote staff hit it more often because a laptop that can’t reach a domain controller can’t change its password before it expires. Many desks offer self-service password reset with MFA so this call never reaches a technician.

<a id="inc-1044"></a>

### INC-1044 · Finance share says Access Denied

**Priority:** Medium (15 points) · **Category:** Access / Permissions · **Arrives:** after INC-1042 is closed or escalated · **Finish with:** Close ticket · **Best score:** +18

**Tools:** Directory, Remote Desktop  
**Runbooks:** [Share access denied: group membership](#kb3)

**The ticket**

> My login works now, but I get Access Denied when I open \\\\FILE01\\Finance. My teammate can still open the same folder.
>
> *Business impact:* One user is blocked from a critical departmental share. Sign-in is healthy.
>
> *Already tried:* Restarted File Explorer and signed out and in once.

#### Symptoms to notice

- “My login works now”: authentication is healthy. Directory › Maya Chen › Authentication confirms Enabled and Not locked.
- Access Denied on \\\\FILE01\\Finance while a teammate opens it: the share and FILE01 are up, so the problem is Maya’s permissions.
- Directory › Maya Chen › Groups: only Domain Users. Finance-Share, the group the Finance share requires, is missing.
- Signing out and in once didn’t help because she wasn’t in the group yet: group membership is read at sign-in.

#### Diagnosis

Authentication answers “who are you?”; authorization answers “what may you open?”. Maya’s sign-in works, so stop looking at passwords. The Finance share is granted through the Finance-Share group and Maya isn’t in it any more. Add the one missing group and nothing else. A Windows session reads group membership when the user signs in, so the change only takes effect after she signs out and back in.

#### Perfect steps

1. INC-1044 arrives after you close INC-1042. Open it and select Assign to me.
2. Open Tools › Directory, search “maya” and select Maya Chen. On Authentication confirm Enabled and Not locked. Don’t reset or unlock anything.
3. Open the Groups tab: only Domain Users is listed.
4. Optional evidence: Tools › Remote Desktop › NS-FIN-014 › Connect › File Explorer › Open on F: (\\\\FILE01\\Finance) reads “Access is denied.”
5. Back in Directory › Maya Chen › Groups, choose Finance-Share in “Add to group” and select Add. A warning reads “Group changes apply after Maya signs in again.”
6. Select “Ask user to sign out & back in” in that warning. The flash reads “Maya signed out and back in. Group changes now apply to the session.”
7. Verify: Remote Desktop › NS-FIN-014 › File Explorer › Open on F: now reads “Opened \\\\FILE01\\Finance.”
8. Select Check fix (2 of 2), write a resolution note and select Close ticket.

#### Verify

- Directory › Maya Chen › Groups lists Domain Users and Finance-Share, and the “Group changes apply after Maya signs in again” warning has gone.
- File Explorer on NS-FIN-014 opens \\\\FILE01\\Finance and lists Payroll\_Oct.xlsx.
- Check fix: 2 of 2 requirements met.

#### Required outcome (what Check fix tests)

- Maya is a member of Finance-Share
- Group change applied to Maya’s session

#### Common mistakes

- Resetting the password or unlocking again: sign-in already works.
- Adding the group but not refreshing the session. Check fix keeps “Maya’s session hasn’t picked up the group change”.
- Adding extra groups such as Executive-Share or HR-Share “to be safe”, which breaks least privilege.
- Restarting the PC or File Explorer and expecting the change to apply without a fresh sign-in.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Added Maya to share groups her Finance role doesn’t need (least privilege) | −3 |

Closing it unresolved costs −10. Escalating it to Security costs −8.

#### Hint ladder

1. The login works, so this is about authorization, not authentication.
2. Compare Maya’s group membership in Directory with what the Finance share needs.
3. Add mchen to Finance-Share, then have her sign out and back in so the change applies.

#### Model answer

Confirmed identity, restored the missing Finance-Share group membership, had the user refresh her session and verified the share opens.

#### Ideal resolution note

> Cause: mchen authenticates fine but was missing Finance-Share, the group \\\\FILE01\\Finance requires. Action: added mchen to Finance-Share only (no other groups) and had her sign out and back in to refresh her token. Verified: \\\\FILE01\\Finance opens from NS-FIN-014 in File Explorer.

Earns +3 of 3 for notes. Keywords: `mchen`, `maya`, `finance-share`.

#### In the real world

Access is almost always granted to groups rather than to people, so a “suddenly denied” ticket usually means a group membership changed, often during an access review or a clean-up script. Windows reads group membership into the user’s sign-in token, which is why every group change ends with “sign out and back in”. Check with the manager before adding a group that the person’s role doesn’t already include.

<a id="inc-1045"></a>

### INC-1045 · Nobody on the third floor can reach the network

**Priority:** Critical (30 points) · **Category:** Network / Outage · **Arrives:** at the start of shift 1 · **Finish with:** Close ticket · **Best score:** +33

**Tools:** Server Room, Remote Desktop  
**Runbooks:** [Triaging a floor-wide outage](#kb4)

**The ticket**

> Nobody on the third floor can reach the internet or shared drives. Floors one and two are fine. It started about five minutes ago.
>
> *Business impact:* Multi-user business interruption, isolated to Floor 3.
>
> *Already tried:* Users reconnected to Wi-Fi and restarted PCs. No change.

#### Symptoms to notice

- Everyone on Floor 3 is down while Floors 1 and 2 work: the scope is one floor, not the whole office.
- It started for the whole floor at once, about five minutes ago: one shared device failed, not dozens of PCs.
- Dashboard › Service health: Floor switches 2/3 online.
- Server Room › Overview: Devices 9 / 10, Network load “Segment down”, and Device status lists Floor 3 Switch (Server Room B · 10.0.3.1) offline.
- Server Room › Topology: the Floor 3 Switch box is red with a dashed link; Edge Router, Main Firewall and the other switches are green.
- Remote Desktop lists the Floor 3 hot desks NS-MKT-011 and NS-MKT-012 as Offline: “Unreachable: Floor 3 Switch is down”.

#### Diagnosis

Work outward from the impact. Floors 1 and 2 work, and every floor shares the internet link, the edge router and the firewall, so those must be fine. The narrowest component that only Floor 3 depends on is the Floor 3 switch, and the topology shows it offline. Restore that one device. Rebooting the edge router or the firewall “just in case” would drop every floor and fix nothing.

#### Perfect steps

1. Open INC-1045 (Critical, top of the queue) and select Assign to me.
2. Open Tools › Server Room. On Overview read Devices 9 / 10 and find Floor 3 Switch · offline under Device status.
3. Open the Topology tab. Follow the path Internet › MetroFiber ISP › Edge Router › Main Firewall: all online. Only the Floor 3 Switch box is red.
4. Select the Floor 3 Switch box. Its panel shows 10.0.3.1, Server Room B, offline, and a Power on button.
5. Select Power on. The flash reads “Floor 3 Switch powered on and reports Online.”
6. Optional: Tools › Remote Desktop now lists NS-MKT-011 and NS-MKT-012 as Online.
7. Select Check fix, write a resolution note and select Close ticket.

#### Verify

- Topology: every box is green, and the dashboard shows Floor switches 3/3 online.
- Remote Desktop: the Floor 3 hosts show Online · On the office network.
- Check fix: Floor 3 Switch is back online.

#### Required outcome (what Check fix tests)

- Floor 3 Switch is back online

#### Common mistakes

- Rebooting or powering off the Edge Router or Main Firewall: every floor drops, and each one costs 4 points.
- Treating it as a Wi-Fi or PC fault and restarting users’ machines one by one.
- Powering off a working floor switch while “testing”: that floor loses its network too.
- Closing without noting why the switch went down, so nobody follows up on its power.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Rebooted the edge router — every floor dropped briefly | −4 |
| Powered off the edge router — every floor lost access | −4 |
| Rebooted the main firewall — every floor dropped briefly | −4 |
| Powered off the firewall — every floor lost access | −4 |
| Powered off the healthy Floor 1 switch — the whole floor lost its network | −3 |
| Powered off the healthy Floor 2 switch — the whole floor lost its network | −3 |

Closing it unresolved costs −20. Escalating it to Security costs −8.

#### Hint ladder

1. The impact is one floor while the others work. Look for the narrowest shared component.
2. In Server Room, trace the topology down to the Floor 3 branch.
3. Restore the Floor 3 Switch (10.0.3.1).

#### Model answer

Compared the outage scope with the topology, identified the failed Floor 3 switch, restored it and confirmed the segment came back online.

#### Ideal resolution note

> Cause: Floor 3 Switch (10.0.3.1, Server Room B) was offline; Floors 1–2, the edge router and the firewall were healthy, so the outage was isolated to that switch. Action: powered on the Floor 3 switch in Server Room › Topology without touching the core devices. Verified: switch reports Online and Floor 3 hosts are reachable again. Follow-up: Facilities to check the switch power.

Earns +3 of 3 for notes. Keywords: `floor 3`, `switch`, `10.0.3.1`.

#### In the real world

Scope is the fastest diagnostic tool on a service desk. One user usually means their device; one floor means that floor’s switch, its uplink or its power; the whole office means the core or the provider. Floor switches often drop because a power supply or UPS failed, so after restoring one, raise a follow-up with Facilities or the network team to find the root cause.

<a id="inc-1046"></a>

### INC-1046 · Wi-Fi keeps dropping during calls

**Priority:** Medium (15 points) · **Category:** Network / Wi-Fi · **Arrives:** at the start of shift 1 · **Finish with:** Close ticket · **Best score:** +18

**Tools:** Remote Desktop, Voicemails  
**Runbooks:** [Fixing a broken Wi-Fi profile](#kb5)

**The ticket**

> My Wi-Fi keeps disconnecting during calls. People sitting around me seem fine, and the rest of the office is working.
>
> *Business impact:* One user has intermittent connectivity. Shared network devices are healthy.
>
> *Already tried:* Forgot the Wi-Fi network from the taskbar and rejoined.

#### Symptoms to notice

- One laptop drops while the people sitting next to Jordan are fine, so the access points and the network are healthy.
- Jordan’s 08:44 voicemail says the same: it’s just his laptop.
- Remote Desktop › NS-OPS-021: the session bar reads “Wi-Fi disconnected”.
- Network & Wi-Fi › Saved networks: Northstar-Staff shows “Can’t connect: saved security settings don’t match the network”.
- Forgetting from the taskbar and rejoining didn’t help: the broken saved profile is still on the laptop.

#### Diagnosis

When one device fails and its neighbours work, look at that device. The laptop holds a saved Northstar-Staff profile whose security settings no longer match the network, so every connection attempt fails authentication. Remove the bad profile, join Northstar-Staff again so a fresh profile is created, and prove the route to the gateway with a ping. The guest network isn’t a fix: it gives internet only and no access to company drives.

#### Perfect steps

1. Open INC-1046 and select Assign to me. Optional: Voicemails › Jordan Price › Mark as listened, then Save to INC-1046.
2. Open Tools › Remote Desktop, search “NS-OPS-021”, select Connect, then Connect in the dialog. The session bar reads Wi-Fi disconnected.
3. Open Network & Wi-Fi. Under Saved networks, Northstar-Staff shows “Can’t connect: saved security settings don’t match the network”.
4. Select Forget on the Northstar-Staff row. It moves to Available networks.
5. Under Available networks select Connect on Northstar-Staff (not Northstar-Guest). Expect “NS-OPS-021 connected to Northstar-Staff.”
6. Open Terminal, type ping 10.0.0.1 and press Enter. Expect three replies and “Received = 3”.
7. Optional: run ipconfig to see the 10.0.1.x address and Default Gateway 10.0.0.1.
8. Select Check fix (3 of 3), write a resolution note and select Close ticket.

#### Verify

- Network & Wi-Fi: Status connected to Northstar-Staff · On the office network.
- Terminal: ping 10.0.0.1 gets 3 replies (0% loss).
- Check fix: broken profile removed, connected to Northstar-Staff, internal connectivity tested.

#### Required outcome (what Check fix tests)

- Broken saved Wi-Fi profile removed
- Connected to Northstar-Staff
- Internal connectivity tested

#### Common mistakes

- Rebooting or powering off the Edge Router for one person’s Wi-Fi: every floor drops, and it costs 4 points.
- Selecting Connect on the broken profile again: authentication fails every time.
- Connecting to Northstar-Guest: it has internet only, so Jordan loses his shared drives.
- Skipping the ping: “connected” only proves the radio link, not a working route.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Rebooted the edge router for a single-user Wi-Fi problem | −4 |
| Powered off the edge router for a single-user Wi-Fi problem | −4 |

Closing it unresolved costs −10. Escalating it to Security costs −8.

#### Hint ladder

1. One device fails while nearby colleagues work: look at the workstation, not the network.
2. Remote into NS-OPS-021 and inspect its saved Wi-Fi profiles.
3. Forget the broken Northstar-Staff profile, reconnect, then ping the gateway (10.0.0.1) from Terminal.

#### Model answer

Verified the wider network was healthy, removed the corrupt saved Wi-Fi profile on the workstation, reconnected to Northstar-Staff and confirmed gateway reachability.

#### Ideal resolution note

> Cause: NS-OPS-021 (jprice) had a corrupt saved Northstar-Staff profile failing authentication; nearby users and the network were healthy. Action: removed the broken profile in Remote Desktop › Network & Wi-Fi and reconnected to Northstar-Staff. Verified: ping 10.0.0.1 from the laptop got 3 of 3 replies.

Earns +3 of 3 for notes. Keywords: `jprice`, `jordan`, `ns-ops-021`, `wi-fi`, `wifi`.

#### In the real world

Corrupt or outdated saved Wi-Fi profiles are common after a network changes its security settings or certificate. Forgetting the network from the taskbar doesn’t always remove a profile that was pushed by policy, so desks remove it remotely (for example with netsh wlan delete profile). If several laptops of the same model start dropping at once, suspect a Wi-Fi driver update instead.

<a id="inc-1047"></a>

### INC-1047 · Supplier email is missing from the inbox

**Priority:** High (22 points) · **Category:** Email / Delivery · **Arrives:** at the start of shift 1 · **Finish with:** Close ticket · **Best score:** +25

**Tools:** Mail Admin, Mail Security  
**Runbooks:** [Finding and releasing quarantined mail](#kb6), [Following a message with Message trace](#kb37)

**The ticket**

> A supplier sent today’s onboarding spreadsheet, but it never arrived. They say they got no bounce. I checked Junk and it isn’t there.
>
> *Business impact:* HR onboarding for Monday’s starters is delayed.
>
> *Already tried:* Checked Junk and asked the supplier to resend once.

#### Symptoms to notice

- No bounce for the supplier and nothing in Junk: the message was accepted, then held somewhere before the inbox.
- Mail Admin › Message trace for “priya.shah”: “Onboarding pack – October starters (spreadsheet)” from BrightPath Staffing at 09:02, status Quarantined, “Held by the content filter: strict attachment policy”.
- The same trace shows a second Quarantined message to Priya, “Action required: verify your payroll account” from secure-docs@paylink-verify.example, held as phishing.
- Mail Security › Quarantine: the BrightPath item’s reason is Strict attachment policy (score 5.1); the payroll message is Phishing: credential-harvest link (score 9.6).

#### Diagnosis

A missing message with no bounce is a tracing job, not a mailbox job. Message trace shows exactly where it stopped: the content filter quarantined it under a strict attachment policy. The sender is a known staffing supplier, the subject is what Priya expects and the score is low, so it’s a false positive and safe to release. The other message held for Priya is real phishing and must stay blocked. Release only the one you checked, then trace again to prove it was delivered.

#### Perfect steps

1. Open INC-1047 and select Assign to me.
2. Open Tools › Mail Admin. On Message trace, type “priya.shah” in “Sender, recipient or display name” and select Search.
3. Find the BrightPath Staffing row (09:02, “Onboarding pack – October starters (spreadsheet)”): Quarantined, held by the strict attachment policy.
4. Open Tools › Mail Security › Quarantine. Check sender, recipient, subject and reason on each row.
5. On the BrightPath row (Strict attachment policy, score 5.1) select Release. Expect “Released … Delivered to priya.shah@northstar.example.”
6. Leave the paylink-verify.example row held, or select Report to Security on it. Never select Release on a phishing item.
7. Back in Mail Admin › Message trace, select Search again. The BrightPath row now reads Delivered, “Released from quarantine and delivered to inbox”.
8. Select Check fix (2 of 2), write a resolution note and select Close ticket.

#### Verify

- Message trace for priya.shah: the BrightPath message shows Delivered.
- Mail Security › Quarantine: BrightPath shows Released · Delivered; the payroll phishing message is still held, or Blocked · Reported.
- Check fix: supplier message released and delivery confirmed in Message trace.

#### Required outcome (what Check fix tests)

- Supplier message released
- Delivery confirmed in Message trace

#### Common mistakes

- Releasing the “verify your payroll account” message: it’s credential phishing, the release dialog warns you, and it costs 6 points.
- Releasing without running the trace again: Check fix wants delivery confirmed in Message trace.
- Asking the supplier to resend again: the new copy would be held by the same policy.
- Releasing every quarantined item for the user “to be safe”.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Released a phishing message into a user’s inbox | −6 |

Closing it unresolved costs −15. Escalating it to Security costs −8.

#### Hint ladder

1. No bounce and not in Junk: find out where the message stopped.
2. Run Mail Admin › Message trace for Priya’s address. “Quarantined” means the filter is holding it.
3. Release the matching legitimate message in Mail Security, then re-run the trace to confirm delivery.

#### Model answer

Traced the message, confirmed the filtering service quarantined it, released the verified legitimate item and confirmed delivery in Message trace.

#### Ideal resolution note

> Cause: BrightPath Staffing onboarding spreadsheet (09:02) to pshah was quarantined by the strict attachment policy (score 5.1), a false positive. Action: checked sender and subject, released only that message in Mail Security; the payroll phishing message stays blocked. Verified: Message trace shows the BrightPath message Delivered.

Earns +3 of 3 for notes. Keywords: `pshah`, `priya`, `quarantine`, `brightpath`.

#### In the real world

Quarantine false positives are normal: strict attachment policies catch spreadsheets with macros or unusual file types from senders the filter hasn’t seen before. Real desks check the sender domain, the headers and whether the user expects the message before releasing, and ask Security to tune the policy or allow-list a supplier if it keeps happening. Phishing is never released, even when the user insists.

<a id="inc-1048"></a>

### INC-1048 · Mailbox is full and new mail bounces

**Priority:** Medium (15 points) · **Category:** Email / Mailbox · **Arrives:** at the start of shift 1 · **Finish with:** Close ticket · **Best score:** +18

**Tools:** Mail Admin  
**Runbooks:** [Mailbox over quota](#kb7), [Following a message with Message trace](#kb37)

**The ticket**

> People get a bounce when they email me, with a “mailbox full” message. I can still sign in to webmail and read old messages.
>
> *Business impact:* The Executive Office can’t receive new messages.
>
> *Already tried:* Signed out of webmail and tried again.

#### Symptoms to notice

- Senders get a “mailbox full” bounce but Avery can sign in and read old mail: identity is fine, delivery isn’t.
- Mail Admin › Message trace for “avery.wilson”: “Board pack draft v3” and “Itinerary update – Thursday” Failed with 550 5.2.2 Recipient mailbox full.
- Mail Admin › Mailboxes › avery.wilson@northstar.example: Storage 4.95 GB of 5 GB (99%), Delivery “Blocked: quota exceeded”, Online archive Not enabled, Retention policy Executive (7 years).
- Server Room › Servers › MAIL01 › Event log: warning 4010, “Delivery to avery.wilson@northstar.example failed: mailbox full.”

#### Diagnosis

The mailbox has reached its 5 GB quota, so the mail server rejects new messages. There are two approved remedies: enable the online archive (older items move out and the mailbox drops to about 2.2 GB), or raise the quota to the 10 GB approved for executives. The archive is the better first choice because it keeps the 7-year retention policy and leaves room to grow. Deleting an executive’s mail is never the fix. Finish with a test message, because a storage number alone doesn’t prove delivery.

#### Perfect steps

1. Open INC-1048 and select Assign to me.
2. Open Tools › Mail Admin › Message trace, type “avery.wilson” and select Search. Note the two Failed messages with 550 5.2.2 Recipient mailbox full.
3. Open the Mailboxes tab. It opens on avery.wilson@northstar.example (otherwise choose it in the Mailbox list). Read Storage 4.95 GB of 5 GB and Delivery Blocked: quota exceeded.
4. Select Enable online archive. Expect “Online archive enabled. Older items moved, mailbox now at 2.23 GB of 5 GB.”
5. Alternative: choose “10 GB (approved for executives)” in the Quota list and select Apply quota.
6. Leave “Send test to” on avery.wilson@northstar.example and select Send test message. Expect “Test message to avery.wilson@northstar.example delivered to Avery Wilson’s mailbox.”
7. Select Check fix (2 of 2), write a resolution note and select Close ticket.

#### Verify

- Mailboxes › avery.wilson@northstar.example: Delivery Receiving, Online archive Enabled, “Last test delivered”.
- Check fix: the mailbox has room to receive mail and a test message was delivered.

#### Required outcome (what Check fix tests)

- Mailbox has room to receive mail
- Test message delivered

#### Common mistakes

- Resetting Avery’s password or checking MFA: sign-in works, so it’s a storage problem.
- Choosing the 50 GB quota: that size is for shared mailboxes, not an approved executive remedy.
- Fixing storage but never sending a test message, so delivery isn’t proven.
- Asking the Chief of Staff to delete mail that sits under a 7-year retention policy.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Gave an executive mailbox the 50 GB shared-mailbox quota, which isn’t an approved remedy | −2 |

Closing it unresolved costs −10. Escalating it to Security costs −8.

#### Hint ladder

1. Sign-in still works, so this is mailbox delivery, not identity.
2. Open Avery’s mailbox in Mail Admin › Mailboxes and look at storage.
3. Enable the online archive (or raise the quota to the approved 10 GB), then send a test message.

#### Model answer

Checked mailbox properties, found quota enforcement blocking delivery, enabled the approved archive remedy and confirmed delivery with a test message.

#### Ideal resolution note

> Cause: awilson mailbox at 4.95 of 5 GB, so new mail bounced with 550 5.2.2 (board pack, itinerary). Action: enabled the online archive (approved remedy, 7-year retention kept); mailbox now at 2.23 GB. Verified: test message delivered. Asked Avery to have the board office resend the board pack.

Earns +3 of 3 for notes. Keywords: `awilson`, `avery`, `quota`, `archive`.

#### In the real world

Mailbox-full bounces (550 5.2.2) are common for executives who keep everything. An online archive moves older mail to a separate archive mailbox that is still searchable from the mail client, which suits retention policies far better than deleting. The server doesn’t retry a hard 5.x.x failure, so tell the user that anyone whose message bounced has to send it again.

<a id="inc-1049"></a>

### INC-1049 · Unknown forwarding address in my mailbox

**Priority:** Critical (30 points) · **Category:** Security / Mailbox · **Arrives:** at the start of shift 1 · **Finish with:** Escalate to Security · **Best score:** +42

**Tools:** Mail Admin  
**Runbooks:** [Suspicious inbox forwarding rules](#kb8), [Escalating to Security with evidence](#kb34)

**The ticket**

> A coworker says some replies to my password-reset emails are disappearing. I found a forwarding address I don’t recognize in my mailbox settings.
>
> *Business impact:* Possible account compromise and data exfiltration.
>
> *Already tried:* I did not create any new rules.

#### Symptoms to notice

- Replies to Leo’s password-reset emails are disappearing, and he found a forwarding address he didn’t create.
- Mail Admin › Inbox rules (mailbox leo.martinez@northstar.example): a rule named “.” on All incoming messages, tagged “Forwards outside org”.
- View details: Action “Forward a copy to external-archive@outside.example, mark as read”; Created “Oct 9, 02:14 from an unrecognized web session”.
- Message trace for “leo.martinez”: the 09:10 “Rota for next week” was “Delivered to inbox (copy forwarded by rule to external-archive@outside.example)”.
- Directory › Leo Martinez › Mailbox warns “1 inbox rule forwards mail outside the organization”.

#### Diagnosis

A rule with a near-invisible name (a single dot), created at 02:14 from an unknown web session, that silently forwards everything outside the company and marks it as read is a textbook sign of a compromised mailbox. Attackers use rules like this to keep reading mail, including password resets, even after the password changes. This isn’t housekeeping: the rule, its creation time and the session behind it are evidence Security needs to scope the breach. Inspect it, write it down, change nothing, and escalate. Security takes ownership and contains the account.

#### Perfect steps

1. Open INC-1049 (Critical) and select Assign to me.
2. Open Tools › Mail Admin › Inbox rules. The Mailbox list opens on leo.martinez@northstar.example.
3. On the rule named “.” (Forwards outside org) select View details. Note Applies to: All incoming messages; Action: forward a copy to external-archive@outside.example and mark as read; Created: Oct 9, 02:14 from an unrecognized web session.
4. Don’t select Delete. If you open the delete dialog by mistake, select Cancel.
5. Optional evidence: Message trace for “leo.martinez” shows the 09:10 message copied to external-archive@outside.example.
6. Optional: add a work note on the ticket with the rule details, so the evidence is on record.
7. Select Escalate to Security (Resolution card, or Options ···). Under “Evidence for Security” write the rule name, target address, creation time and source, and that nothing was deleted (at least 15 characters).
8. Select Escalate. The ticket moves to Past tickets as Routed to Security.

#### Verify

- Before escalating, Check fix shows 2 of 3: rule inspected and rule preserved. The third, Routed to Security, completes when you escalate.
- The escalation dialog’s preview includes “Correct security escalation +12”.
- Past tickets: outcome Routed to Security. Inbox rules still lists the rule, now marked as disabled by Security with evidence preserved.

#### Required outcome (what Check fix tests)

- Forwarding rule inspected
- Rule preserved as evidence
- Routed to Security

#### Common mistakes

- Deleting the rule: it destroys evidence and costs 4 points (the dialog warns you first).
- Closing instead of escalating: “Not yet routed to Security” stays unmet and it scores as closed unresolved (−20).
- Treating it as routine and only resetting Leo’s password: the forwarding rule keeps working after a reset.
- Escalating with a vague note. Security needs the rule, the address and the timestamps.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Deleted the suspicious rule and destroyed evidence | −4 |

Closing it unresolved costs −20.

#### Hint ladder

1. A rule that forwards everything outside the company is a security concern.
2. Inspect Leo’s inbox rules in Mail Admin. Preserve the evidence: this is not housekeeping.
3. Escalate the ticket to Security with the rule details in your notes.

#### Model answer

Inspected the inbox rule, documented the external forwarding evidence, avoided destroying it and escalated to Security for containment.

#### Ideal resolution note

> Evidence: lmartinez inbox rule “.” forwards all incoming mail to external-archive@outside.example and marks it read; created Oct 9 02:14 from an unrecognized web session. Message trace confirms copies were forwarded (09:10 rota). Rule inspected and preserved, nothing deleted. Escalated to Security to contain the suspected compromise.

Earns +3 of 3 for notes. Keywords: `lmartinez`, `leo`, `external-archive`, `outside.example`, `forward`.

#### In the real world

Malicious forwarding rules are one of the most common steps attackers take after compromising a mailbox (business email compromise). They name rules “.” or similar to hide them and forward to free external mailboxes. A real Security team revokes sessions, resets the password and MFA, exports the rule and sign-in logs, looks for other affected mailboxes and checks what was sent out. The desk’s job is to spot it, preserve it and hand over quickly.

<a id="inc-1050"></a>

### INC-1050 · Shared printers are stuck on “Printing”

**Priority:** High (22 points) · **Category:** Server / Printing · **Arrives:** at the start of shift 1 · **Finish with:** Close ticket · **Best score:** +25

**Tools:** Server Room, Voicemails  
**Runbooks:** [Print jobs stuck for everyone](#kb9)

**The ticket**

> Everyone in the office gets “Printing” forever, and nothing is coming out of the shared printers. The printers themselves are powered on.
>
> *Business impact:* Company-wide printing is unavailable. All printer models are affected.
>
> *Already tried:* Power-cycled one printer. It didn’t help.

#### Symptoms to notice

- Every printer in the office is stuck on “Printing”, across all models: one shared component, not a printer fault.
- Power-cycling a printer didn’t help, as Tomasz’s 08:22 voicemail also says.
- Dashboard › Service health: Printing Degraded.
- Server Room › Servers: PRINT01 (Print Server, 10.0.0.30) is Degraded. Its Services show Print Spooler stopped and Print Web Portal running.
- PRINT01 › Event log & scheduled tasks: error 7031 at 08:19, “The Print Spooler service terminated unexpectedly. 0 recovery actions configured.”

#### Diagnosis

Every print job goes through the Print Spooler service on PRINT01, which crashed at 08:19 and had no automatic restart configured. With the spooler down, jobs pile up in the queues and every printer looks busy. Restarting printers doesn’t help because nothing is being sent to them. Start the one stopped service instead of rebooting the whole server, then send a test page to prove jobs are flowing again.

#### Perfect steps

1. Open INC-1050 and select Assign to me. Optional: Voicemails › Tomasz Nowak (08:22) › Mark as listened, then Save to INC-1050.
2. Open Tools › Server Room › Servers. PRINT01 shows Degraded.
3. Select Services on the PRINT01 row: Print Spooler is stopped.
4. Optional: select “Event log & scheduled tasks” and read event 7031 at 08:19, then go back to the Servers tab (PRINT01’s services stay open).
5. Select Start next to Print Spooler. Expect “Print Spooler restarted on PRINT01 and is Running.”
6. Select Send test page on the PRINT01 row. Expect “Test page printed on PRN-F1-01.”
7. Select Check fix (2 of 2), write a resolution note and select Close ticket.

#### Verify

- Server Room › Servers: PRINT01 Healthy, Print Spooler running.
- Send test page reports “Test page printed on PRN-F1-01.”
- Dashboard › Service health: Printing Healthy.

#### Required outcome (what Check fix tests)

- Print Spooler running on PRINT01
- Test page printed

#### Common mistakes

- Rebooting printers one by one in Server Room › Devices: the flash says jobs are still waiting in the PRINT01 queue.
- Sending the test page before starting the spooler: it sticks in the queue and doesn’t count.
- Rebooting the whole PRINT01 server when one service needs starting. It works, but it also drops the Print Web Portal, takes longer and costs 3 points.
- Closing without a test page.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Rebooted the whole print server for one stopped service: the Print Web Portal dropped for everyone | −3 |

Closing it unresolved costs −15. Escalating it to Security costs −8.

#### Hint ladder

1. Every printer at once means a shared dependency.
2. Inspect the print server in Server Room › Servers.
3. Restart the Print Spooler on PRINT01, then send a test page.

#### Model answer

Identified the shared print server rather than a single printer, restarted the stopped spooler service and confirmed a test page printed.

#### Ideal resolution note

> Cause: Print Spooler on PRINT01 crashed at 08:19 (event 7031, no recovery actions), so every queue stalled office-wide. Action: started the Print Spooler service on PRINT01 (no server reboot, no printer reboots). Verified: test page printed on PRN-F1-01. Follow-up: set spooler recovery to restart automatically.

Earns +3 of 3 for notes. Keywords: `print01`, `spooler`.

#### In the real world

A crashed print spooler is a classic Windows print-server failure, often caused by a faulty printer driver or a corrupt job. Restarting the service fixes it for now. The follow-up is to set the service to restart automatically after a failure, and to find the job or driver that crashed it (event 7031 and the spooler logs) so it doesn’t happen again tomorrow.

<a id="inc-1051"></a>

### INC-1051 · VPN profile invalid when working from home

**Priority:** High (22 points) · **Category:** Network / VPN · **Arrives:** after INC-1043 is closed or escalated · **Finish with:** Close ticket · **Best score:** +25

**Tools:** Remote Desktop  
**Runbooks:** [VPN profile invalid](#kb10)

**The ticket**

> I’m at home and the VPN says my connection profile is invalid. The internet works and I can browse normal websites, but I can’t reach the company drive.
>
> *Business impact:* A remote worker can’t reach internal resources.
>
> *Already tried:* Restarted the laptop and checked the home router.

#### Symptoms to notice

- Evan is at home and normal websites work, so his home internet and Wi-Fi are fine.
- The VPN says the connection profile is invalid, and the company drive can’t be reached: the tunnel isn’t coming up.
- Remote Desktop › NS-SALES-008: the session bar reads “Off-site — VPN not connected”.
- VPN Client: Connection profile Northstar-Legacy, Status Disconnected. Connect fails with “profile invalid. Gateway vpn-legacy.northstar.example has been retired.”
- File Explorer › Open on S: (\\\\FILE01\\Sales): “The network path … wasn’t found. Connect the VPN first.”

#### Diagnosis

Internet works and only internal resources fail, so the problem is the tunnel into the company, not his router. The VPN client still uses the Northstar-Legacy profile, which points at a retired gateway, so it can never connect. Switch to the current Northstar-Staff profile, connect, and prove internal access by opening his Sales drive or pinging FILE01. INC-1051 only arrives once INC-1043 is closed, because Evan needs a working account first.

#### Perfect steps

1. INC-1051 arrives after you close INC-1043. Open it and select Assign to me.
2. Open Tools › Remote Desktop, search “NS-SALES-008”, select Connect, then Connect in the dialog. The session bar reads Off-site — VPN not connected.
3. Open VPN Client. Connection profile shows Northstar-Legacy.
4. Optional: select Connect to see the failure, “Connection failed: profile invalid. Gateway vpn-legacy.northstar.example has been retired.”
5. Choose Northstar-Staff in the Connection profile list. The flash reads “VPN profile set to Northstar-Staff.”
6. Select Connect. Expect “VPN connected with Northstar-Staff. Internal address 10.8.0.14.”
7. Open File Explorer and select Open on S: (\\\\FILE01\\Sales). Expect “Opened \\\\FILE01\\Sales.” Alternatively open Terminal and run ping file01.
8. Select Check fix (3 of 3), write a resolution note and select Close ticket.

#### Verify

- VPN Client: Status Connected; the session bar reads Connected over VPN.
- File Explorer opens \\\\FILE01\\Sales and lists Pipeline\_Q4.xlsx, Pricing\_2026.pdf and Client\_Notes.
- Check fix: current profile selected, VPN connected, internal access verified.

#### Required outcome (what Check fix tests)

- Current VPN profile selected
- VPN connected
- Internal access verified

#### Common mistakes

- Troubleshooting Evan’s home router or Wi-Fi when ordinary websites work.
- Connecting the Legacy profile again and again: its gateway has been retired.
- Stopping at “Connected” without opening a drive or pinging an internal server.
- Leaving INC-1043 unresolved: a locked or expired account can’t open the share even with the VPN up.

#### Wrong actions and penalties

No ticket-specific penalties.

Closing it unresolved costs −15. Escalating it to Security costs −8.

#### Hint ladder

1. Public internet works, so the fault is in the tunnel or client profile.
2. Remote into NS-SALES-008 and open the VPN Client.
3. Select the current Northstar-Staff profile, connect, and verify by opening the S: drive or pinging FILE01.

#### Model answer

Confirmed ordinary internet worked, replaced the obsolete VPN profile with the current one, connected and verified internal access.

#### Ideal resolution note

> Cause: NS-SALES-008 (ebrooks, working from home) still used the Northstar-Legacy VPN profile, whose gateway was retired; home internet was fine. Action: switched the VPN client to Northstar-Staff and connected (10.8.0.14). Verified: \\\\FILE01\\Sales opens over the VPN from his laptop.

Earns +3 of 3 for notes. Keywords: `ebrooks`, `evan`, `vpn`, `northstar-staff`, `ns-sales-008`.

#### In the real world

When a VPN gateway is retired, clients that still hold the old profile fail with “profile invalid”. Well-run desks push the new profile through device management before switching the old gateway off, and chase the laptops that haven’t checked in, because remote machines miss updates. Always verify with an internal resource: many VPN clients show “connected” before routes and DNS are actually working.

<a id="shift-2"></a>

## Shift 2 · Tuesday

Hardware day: new starters, replacements and shipments, a new laptop and a new phone that won’t connect, and a mailbox access request. Expect requests by chat and voicemail as well as the queue.

<a id="inc-1052"></a>

### INC-1052 · Dispatch desk PC is dead: no lights, no fans

**Priority:** Critical (30 points) · **Category:** Hardware / Desktop failure · **Arrives:** at the start of shift 2 · **Finish with:** Close ticket · **Best score:** +33

**Tools:** Remote Desktop, Computer Deployment, PC Shelf, Asset Management, Company Chat  
**Runbooks:** [Deploying a computer from the PC Shelf](#kb12), [Dead PC: swap or repair?](#kb17)

**The ticket**

> My desk PC is completely dead this morning. I press the power button and nothing happens: no lights, no fan noise, nothing. The courier dispatch board runs on that machine and drivers start calling in for their routes at 9.
>
> *Business impact:* The only dispatch desk is down, so route allocation for the whole courier fleet stops at 09:00. No other users are affected.
>
> *Already tried:* Tried a different wall socket and pushed the power cable back in. The monitor turns on fine on its own.

#### Symptoms to notice

- No lights and no fans. A PC that has only hung still shows a power light, so this points to the power supply or board, not Windows.
- The monitor works on the same socket, so the wall power is fine.
- Asset Management › NS-OPS-030 › Health: Off / unreachable, no heartbeat, last event Oct 11, 22:47 during the Facilities building power test (FAC-7781).
- Asset Management › Details: warranty 2026-03-31, marked Expired, so there’s no vendor repair route.
- Details › User data: folders are redirected to \\\\FILE01\\Operations\\Profiles\\tnowak, so nothing is lost with the unit.
- PC Shelf: NSA-S201 is a Desk 24 that is Not wiped (returned by a leaver). NSA-S202 is a Desk 24 that is Wiped, with certificate WC-5521. Only NSA-S202 is clean.

#### Diagnosis

Scope first: one machine and one user, so it isn’t the network or a server. A desktop with no power at all, right after a building power event, points to a failed power supply or motherboard. The evidence that matters is the asset record: no heartbeat, out of warranty, data stored on the server. For a critical desk with a deadline, swap the machine rather than repair it. Pick a spare that is available, wiped and not reserved (NSA-S202). Then close the loop on the old asset so the inventory is correct and the disk goes through certified disposal.

#### Perfect steps

1. Open INC-1052 and select Assign to me.
2. Open Tools › Asset Management, search “NS-OPS-030” and select Open. On the Health tab note “Off / unreachable” and the last event at 22:47.
3. On the Details tab note Warranty 2026-03-31 (Expired) and User data “Folders redirected to \\\\FILE01\\Operations\\Profiles\\tnowak”.
4. Optional evidence: Tools › Remote Desktop shows NS-OPS-030 Offline (“Powered off / not reachable”) and the Connect button is disabled.
5. Open Tools › PC Shelf › Devices. Compare NSA-S201 (Not wiped, returned by a leaver) with NSA-S202 (Wiped Oct 3). Choose NSA-S202.
6. Open Tools › Computer Deployment. Set Device: NSA-S202, Build profile / image: Standard Office · Northstar Standard 24.2, Assign to: Tomasz Nowak (tnowak), Location: Floor 1. Select Run deployment and check all five stages pass.
7. Back in Asset Management, find NS-OPS-030 in the list and set its State dropdown to “Retired, awaiting disposal”. The owner clears automatically.
8. Open Company Chat › Tomasz Nowak and select the quick action “INC-1052 · Ask to confirm the fix”. Tomasz confirms the dispatch board works.
9. Select Check fix (all requirements green), write a resolution note and select Close ticket.

#### Verify

- Asset Management: the new NS-OPS-1xx host (tag NSA-S202) shows owner Tomasz Nowak, state In use, location Floor 1.
- Asset Management: NS-OPS-030 shows Retired, awaiting disposal, with no owner.
- PC Shelf: NSA-S201 is still Available and Not wiped. It wasn’t deployed.
- Company Chat: Tomasz confirms the dispatch board is running.

#### Required outcome (what Check fix tests)

- Clean Desk 24 spare deployed to Tomasz on Floor 1
- Dead unit NS-OPS-030 retired and queued for secure disposal
- The unwiped spare NSA-S201 wasn’t handed to anyone
- Tomasz confirmed the dispatch board works on the new PC

#### Common mistakes

- Grabbing the first desktop on the shelf (NSA-S201) without reading its wipe status.
- Marking the dead PC Disposed straight away, which skips certified disk destruction.
- Setting it to In repair for an out-of-warranty unit and leaving the desk down.
- Taking a laptop that is reserved for a new starter.
- Closing without the user’s confirmation.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Deployed an unwiped device: a leaver’s data went to a new person | −5 |
| Marked the dead PC Disposed, skipping the secure disk wipe and disposal certificate | −3 |

Closing it unresolved costs −20. Escalating it to Security costs −8.

#### Hint ladder

1. The monitor powers on but the PC shows no lights at all. Check Asset Management for when the PC last reported in, and look at its warranty.
2. NS-OPS-030 lost power in last night’s building power test and is out of warranty. Tomasz’s files live on FILE01, so a clean spare is enough. In PC Shelf, read each desktop’s wipe status.
3. Deploy NSA-S202 (Northstar Standard 24.2) to Tomasz on Floor 1, set NS-OPS-030 to “Retired, awaiting disposal”, then ask Tomasz in Company Chat to confirm the dispatch board works.

#### Model answer

Confirmed the PC had no power and no heartbeat since the building power test. It is out of warranty and the user’s folders are redirected to FILE01. Deployed clean spare NSA-S202 (Northstar Standard 24.2) to tnowak on Floor 1 and retired NS-OPS-030 to awaiting secure disposal. Didn’t use NSA-S201 because it hasn’t been wiped. Tomasz confirmed in chat that the dispatch board is working.

#### Ideal resolution note

> Cause: NS-OPS-030 has no power after building power test FAC-7781. No heartbeat since 22:47, out of warranty (2026-03-31), user folders redirected to FILE01. Action: deployed clean spare NSA-S202 (Northstar Standard 24.2, wipe cert WC-5521) to tnowak on Floor 1. Set NS-OPS-030 to Retired, awaiting disposal. Didn’t use NSA-S201 (not wiped). Verified: Tomasz confirmed in chat that the dispatch board is working.

Earns +3 of 3 for notes. Keywords: `ns-ops-030`, `nsa-s202`, `retired`, `warranty`, `spare`.

#### In the real world

Most service desks keep a small pool of “hot spares” for critical desks, because swapping is faster than diagnosing a dead power supply while the business waits. The swap is only safe if user data lives on the server, and only clean if every spare has a wipe certificate. Retired disks go to a certified disposal vendor; you never just bin them.

<a id="inc-1053"></a>

### INC-1053 · New Finance starter on Monday: laptop build and handover

**Priority:** Medium (15 points) · **Category:** Hardware / New starter · **Arrives:** at the start of shift 2 · **Finish with:** Close ticket · **Best score:** +18

**Tools:** Directory, Computer Deployment, PC Shelf, Asset Management, Company Chat  
**Runbooks:** [Share access denied: group membership](#kb3), [Deploying a computer from the PC Shelf](#kb12), [New starter: account, access and day-one handover](#kb31)

**The ticket**

> We’ve got Nadia Rahman starting in Finance on Monday as an analyst. Can you get her laptop ready so she can sit down and start on month-end straight away? She’ll need the same setup as the rest of the team, including the payroll software.
>
> *Business impact:* A new starter can’t work on day one, and month-end close is one analyst short.
>
> *Already tried:* HR says they’ve created her account.

#### Symptoms to notice

- The ticket says “same setup as the team, including the payroll software”, so a generic build won’t do.
- Directory › Nadia Rahman › Profile: Role template “Finance Analyst: image Northstar Finance 24.2, groups Finance-Share”, start date Mon Oct 19.
- Directory › Groups: only Domain Users, even though HR “created her account”.
- PC Shelf: NSA-S120 is Reserved for Nadia Rahman (HR-2290) but carries the Northstar Standard 24.2 image.
- Computer Deployment › Image catalogue: only Northstar Finance 24.2 includes Ledgerline Accounts and Payroll Desktop.

#### Diagnosis

A new-starter ticket is really a checklist against a source of truth: here, the role template in Directory. Compare what exists (an account with Domain Users only, a laptop with the Standard image) against what the template says (Finance image, Finance-Share). The gaps are the work. Two traps: giving extra access to save a future ticket, and handing credentials to someone other than the starter.

#### Perfect steps

1. Open INC-1053 and select Assign to me.
2. Open Tools › Directory, search “nadia”, select Nadia Rahman. On Profile read the Role template line. On Groups note only Domain Users.
3. Open Tools › PC Shelf › Devices: confirm NSA-S120 is Reserved for Nadia Rahman and shows Northstar Standard 24.2.
4. Open Tools › Computer Deployment. Set Device: NSA-S120, Build profile / image: Finance · Northstar Finance 24.2, Assign to: Nadia Rahman (nrahman), Location: Floor 2. Select Run deployment. There is no reservation warning because the assignee matches.
5. Back in Directory › Nadia Rahman › Groups, choose Finance-Share in “Add to group” and select Add. Add nothing else.
6. Optional: Tools › Asset Management shows the new NS-FIN-1xx host (tag NSA-S120) owned by Nadia Rahman with image Northstar Finance 24.2.
7. Open Company Chat › Maya Chen and select “INC-1053 · Agree an in-person handover (ID check, then password)”. Maya agrees to bring Nadia down at 09:00.
8. Select Check fix, write a resolution note and select Close ticket.

#### Verify

- Asset Management: the NSA-S120 host is owned by Nadia Rahman, In use, image Northstar Finance 24.2.
- Directory › Nadia Rahman › Groups lists exactly Domain Users and Finance-Share.
- Company Chat: Maya agrees to the in-person handover. No password appears in the thread.

#### Required outcome (what Check fix tests)

- Reserved laptop NSA-S120 built with Northstar Finance 24.2 for Nadia
- Nadia is in Finance-Share
- Nadia has no access beyond her role template
- Handover agreed with Maya: ID check and password in person

#### Common mistakes

- Deploying the reserved laptop with the Standard image it already has.
- Taking a different spare and breaking the reservation.
- Adding extra share groups “just in case”.
- Sending the temporary password to the manager to pass on.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Gave a new starter access beyond her role template (least privilege) | −3 |
| Sent a credential to a third party over chat. Temporary passwords go to the starter in person after an ID check | −4 |

Closing it unresolved costs −10. Escalating it to Security costs −8.

#### Hint ladder

1. Don’t guess the build. Directory › Nadia’s Profile shows her role template, and PC Shelf shows a laptop reserved for her.
2. The reserved laptop only has the Standard image. Finance staff need Northstar Finance 24.2 (Ledgerline and Payroll Desktop), and the role template lists exactly one group.
3. Deploy NSA-S120 with Northstar Finance 24.2 to Nadia on Floor 2, add Finance-Share in Directory, then agree an in-person handover with Maya in Company Chat. Never send Maya the password.

#### Model answer

Built reserved laptop NSA-S120 with Northstar Finance 24.2 (includes Ledgerline and Payroll Desktop) and assigned it to nrahman on Floor 2. Added Finance-Share as her role template requires, and nothing more. Agreed with Maya that Nadia gets her temporary password in person after an ID check on Monday, so no credentials went over chat.

#### Ideal resolution note

> New starter nrahman (Finance Analyst, starts Oct 19). Role template: Northstar Finance 24.2 + Finance-Share. Deployed reserved NSA-S120 (HR-2290) with Northstar Finance 24.2 (Ledgerline + Payroll Desktop) to nrahman on Floor 2. Added Finance-Share only. Handover agreed with Maya Chen: ID check and temporary password in person Monday 09:00 (must change at first sign-in). No credentials sent over chat. Verified: Asset Management shows the NSA-S120 host In use for nrahman with Northstar Finance 24.2.

Earns +3 of 3 for notes. Keywords: `nrahman`, `nadia`, `nsa-s120`, `finance-share`, `role template`.

#### In the real world

Joiner builds are driven by role templates (“birthright” access) so every analyst gets the same thing and audits stay simple. Day-one credentials are a classic leak: good desks hand them over in person, or through a self-service activation link, after an ID check. They don’t go to the manager.

<a id="inc-1054"></a>

### INC-1054 · Remote worker dropped laptop, screen shattered

**Priority:** High (22 points) · **Category:** Hardware / Remote replacement · **Arrives:** as a voicemail (log it as a ticket first) · **Finish with:** Close ticket · **Best score:** +25

**Tools:** Directory, Remote Desktop, Computer Deployment, PC Shelf, Asset Management, Ship Manager, Company Chat, Voicemails  
**Runbooks:** [Deploying a computer from the PC Shelf](#kb12), [Replacing a remote worker’s laptop](#kb13), [Logging chat messages and voicemails as tickets](#kb35)

**The ticket**

> I knocked my laptop off the kitchen counter and the screen’s shattered. I can see a bit in one corner but that’s it. I’m working from home all week with customer calls booked, so can you send me something? I moved at the start of the month, but HR should have my new address.
>
> *Business impact:* A remote account manager can’t work or join customer calls for the rest of the week.
>
> *Already tried:* Restarted it. The screen is still cracked and mostly black.

#### Symptoms to notice

- Voicemail: physical damage (a drop), she works remotely, and “I moved at the start of the month”.
- Remote Desktop › NS-SALES-019 connects, so the operating system is fine. Device Manager › Monitors shows the internal display panel in Error (Code 43).
- Asset Management › NS-SALES-019 › Details: warranty 2027-06-30 and Accidental damage cover: Yes.
- Directory › Clara Keller › Profile: Home address Flat 3, 22 Lantern Row, updated Oct 1 (HR).
- Ship Manager: choosing “Saved address book” gives 7 Quarry Bend, and a warning says the saved entry differs from Directory.

#### Diagnosis

Separate hardware from software first. A working remote session plus a Code 43 error on the panel proves the operating system is healthy and the screen is broken, so no remote fix exists. Uninstalling the driver and scanning again brings the same error back. For a remote user with customer calls booked, the answer is to ship a replacement and recover the broken unit. Covered damage means it goes for repair, not disposal. The real trap is logistics: the courier tool’s address book is out of date, and the authoritative address is HR’s record in Directory, which matches what she said.

#### Perfect steps

1. Open Voicemails, read Clara’s message and select Log as ticket. Open INC-1054 and select Assign to me.
2. Open Tools › Remote Desktop, search “NS-SALES-019”, Connect, open Device Manager: note “Northbook 14 internal display panel · Error (Code 43)”.
3. Open Tools › Asset Management, search “NS-SALES-019”, Open › Details: note warranty 2027-06-30 and Accidental damage cover: Yes.
4. Open Tools › Directory, search “clara”, Profile: note the home address and “Updated Oct 1 (HR)”.
5. Open Tools › PC Shelf: pick an Available, Wiped Northbook 14 laptop that isn’t reserved (for example NSA-S121).
6. Open Tools › Computer Deployment. Device: that spare, Build profile / image: Sales Mobile · Northstar Sales 24.2, Assign to: Clara Keller (ckeller), Location: Remote (home). Select Run deployment and note the new NS-SALES-1xx host name.
7. Open Tools › Ship Manager. Type: Outbound to a person, Item: the new NS-SALES-1xx host, Recipient: Clara Keller, Address from: Directory (HR record), Service: Next day. Select Create shipment.
8. Still in Ship Manager: Type: Return label (person sends to IT), Item: NS-SALES-019, Recipient: Clara Keller, Address from: Directory (HR record). Select Create return label. NS-SALES-019 becomes Return in transit.
9. On the outbound shipment row select Mark delivered (simulates the courier).
10. Open Company Chat › Clara Keller and select “INC-1054 · Ask to confirm the fix”. Clara confirms sign-in and the CRM.
11. Select Check fix, write a resolution note and select Close ticket.

#### Verify

- Ship Manager: the outbound shipment to 22 Lantern Row shows Delivered, and the return for NS-SALES-019 shows Label created.
- Asset Management: the new host is owned by Clara Keller and In use. NS-SALES-019 is Return in transit.
- Company Chat: Clara confirms sign-in and the CRM.

#### Required outcome (what Check fix tests)

- A replacement laptop with the Sales image is assigned to Clara
- Replacement delivered to her current (Directory) address
- Return label issued for the broken NS-SALES-019
- Clara confirmed she received it and can sign in

#### Common mistakes

- Accepting the saved address book entry without cross-checking HR.
- Shipping a device that hasn’t been deployed or assigned to her.
- Retiring a laptop that is covered for repair.
- Forgetting the return label, which leaves a “ghost” asset with the user.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Shipped to the saved address book entry: Clara moved out of 7 Quarry Bend | −4 |
| Scrapped a laptop with accidental-damage cover until 2027-06-30. Return it for repair | −2 |

Closing it unresolved costs −15. Escalating it to Security costs −8.

#### Hint ladder

1. Is this software or hardware? Remote Desktop still connects to NS-SALES-019. What does Device Manager say about the internal display?
2. The panel is physically broken, and Asset Management shows accidental-damage cover. She needs a replacement now and a repair return. She also said she moved, so compare the addresses before you ship.
3. Deploy a spare laptop with Northstar Sales 24.2 to Clara (Remote (home)), ship it with the Directory (HR record) address, create a return label for NS-SALES-019, mark the shipment delivered, then confirm with Clara in Company Chat.

#### Model answer

Remote session showed Code 43 on the internal panel, so it’s physical damage. NS-SALES-019 has accidental-damage cover until 2027-06-30. Deployed a spare Northbook 14 with Northstar Sales 24.2 to ckeller and shipped it next day to her Directory address (updated by HR Oct 1), not the stale saved address. Issued a return label for NS-SALES-019 for warranty repair. Clara confirmed delivery and sign-in.

#### Ideal resolution note

> Cause: physical panel damage (drop). Code 43 on the internal display; the OS is fine over Remote Desktop. NS-SALES-019 has accidental-damage cover until 2027-06-30. Action: deployed a spare Northbook 14 with Northstar Sales 24.2 to ckeller and shipped it next day to her Directory address (Flat 3, 22 Lantern Row, updated Oct 1). Didn’t use the stale saved address 7 Quarry Bend. Return label created for NS-SALES-019 (warranty repair), state Return in transit. Verified: delivered, and Clara confirmed sign-in and the CRM in chat.

Earns +3 of 3 for notes. Keywords: `ckeller`, `clara`, `ns-sales-019`, `lantern row`, `return label`, `code 43`.

#### In the real world

Remote swaps are where asset tracking breaks down. Every outbound device should have a matching return, and the shipping address should come from HR, not the courier tool’s history. Next-day signed-for delivery protects the company if a box goes missing.

<a id="inc-1055"></a>

### INC-1055 · Laptop crawling, “restart to update” every afternoon

**Priority:** Medium (15 points) · **Category:** Hardware / Performance & updates · **Arrives:** at the start of shift 2 · **Finish with:** Close ticket · **Best score:** +18

**Tools:** Remote Desktop, Company Chat  
**Runbooks:** [Updates fail and the PC is slow (full disk)](#kb18)

**The ticket**

> My laptop has been really slow for about a week. Every afternoon it tells me it needs to restart to finish updates, and after the restart the same message is back. Opening the HR system takes ages now.
>
> *Business impact:* One HR user is slowed down and their laptop is missing this month’s security update.
>
> *Already tried:* Restarted it most days and closed browser tabs.

#### Symptoms to notice

- The “restart to update” prompt comes back after every restart, so an install is failing, not just waiting.
- Slow for about a week: something has been building up, not a sudden fault.
- System Update: Status Failed, last error 0x80070070 “not enough free space (needs 20 GB)”, free disk space 1 GB.
- Settings › Storage: 1 GB free of 256 GB. Temporary files 12 GB, Update cache 12 GB, Recycle Bin 18 GB, Downloads 24 GB, Documents 61 GB (Protected).

#### Diagnosis

Read the failure code instead of restarting again. 0x80070070 means the disk is full. A nearly full system drive also explains the slowness: there is no room for the page file and the disk is constantly busy. One root cause gives two symptoms. The order matters: free space safely first (system-generated temporary files, the update cache and the Recycle Bin, never the user’s files), then retry the update, then restart, then check both the free space and the update status.

#### Perfect steps

1. Open INC-1055 and select Assign to me.
2. Open Tools › Remote Desktop, search “NS-HR-003”, Connect. Open System Update: read Status Failed and the 0x80070070 error, and note “updates need 20 GB”.
3. Open Settings › Storage: read the category list. Documents is Protected; Downloads belongs to Priya.
4. Select Clean up on Temporary files, then Clean up on Update cache. Free space rises to 25 GB.
5. Select Empty Recycle Bin. Free space rises to 43 GB.
6. Open System Update and select Retry install. Status becomes “Restart required”.
7. Select Restart now (or ⏻ Restart on the taskbar) and confirm. System Update now shows Up to date.
8. Open Settings › Storage again and confirm at least 20 GB is free.
9. Open Company Chat › Priya Shah and select “INC-1055 · Ask to confirm the fix”. Priya confirms it is fast again.
10. Select Check fix, write a resolution note and select Close ticket.

#### Verify

- Settings › Storage shows 43 GB free, with Documents still 61 GB and Downloads still 24 GB.
- System Update shows Up to date with nothing pending, and updates aren’t paused.
- Company Chat: Priya confirms the laptop is responsive.

#### Required outcome (what Check fix tests)

- At least 20 GB free on C:
- Priya’s own files untouched (or removed with her agreement)
- October cumulative update installed and the laptop restarted
- Priya confirmed the laptop is responsive

#### Common mistakes

- Restarting again without reading the update error.
- Removing Downloads without asking Priya first.
- Pausing updates to stop the prompt.
- Forgetting the restart, which leaves the update half-installed.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Deleted the user’s downloads without asking her first | −3 |
| Paused security updates on an HR laptop to hide the symptom | −2 |

Closing it unresolved costs −10. Escalating it to Security costs −8.

#### Hint ladder

1. “Restart to update” coming back after every restart means the update isn’t installing. Find out why in System Update.
2. The error is 0x80070070: not enough disk space. Settings › Storage shows what is using C: and which items are safe to remove.
3. Clean up Temporary files and the Update cache, empty the Recycle Bin, select Retry install, restart, then ask Priya in Company Chat.

#### Model answer

System Update showed the October cumulative update failing with 0x80070070 (C: had 1 GB free, 20 GB needed), which caused both the restart loop and the slowness. Freed 42 GB by cleaning temporary files and the update cache (24 GB) and emptying the Recycle Bin (18 GB). Documents and Downloads were left alone. Retried the update, restarted, and confirmed it is up to date with 43 GB free. Priya confirmed the laptop is fast again.

#### Ideal resolution note

> Cause: C: full (1 GB free), so KB-NS-26104 kept failing with 0x80070070 and the laptop was paging heavily. Action: cleaned temporary files and the update cache (24 GB), emptied the Recycle Bin (18 GB), retried the update, restarted. Documents and Downloads untouched. Verified: 43 GB free, System Update shows Up to date, Priya confirmed performance in chat.

Earns +3 of 3 for notes. Keywords: `ns-hr-003`, `0x80070070`, `kb-ns-26104`, `disk space`, `update`.

#### In the real world

Full system drives are one of the most common causes of “slow PC” tickets and failed patching. Built-in clean-up of update caches and temporary files is safe. User folders are not, especially where records must be kept. Patch-compliance reports usually flag these machines before users do.

<a id="inc-1056"></a>

### INC-1056 · Second monitor says “No signal” after a boardroom presentation

**Priority:** Low (10 points) · **Category:** Hardware / Peripherals & display · **Arrives:** as a Company Chat message (log it as a ticket first) · **Finish with:** Close ticket · **Best score:** +13

**Tools:** Remote Desktop, Company Chat  
**Runbooks:** [Second screen shows “No signal”](#kb19), [Logging chat messages and voicemails as tickets](#kb35)

**The ticket**

> My second screen has said “No signal” since this morning. The laptop screen is fine. I presented in the boardroom yesterday afternoon, if that matters. I normally drag the queue onto the big screen.
>
> *Business impact:* One user is working on a single screen. Slower, but not blocked.
>
> *Already tried:* Unplugged and replugged the dock cable and pressed the monitor’s power button.

#### Symptoms to notice

- “No signal” on the monitor means it isn’t receiving a picture. That can be a cable or a setting.
- “Presented in the boardroom yesterday”: presenting often changes the display mode.
- Device Manager: Northstar USB-C Dock DK-2 Working (firmware current), NSM-27 monitor Working. The laptop can see it.
- Settings › Display: 2 displays detected, 1 active, mode “Show only on 1”.

#### Diagnosis

Work up the stack. Physical: the dock and monitor are detected, so the cable and dock are fine. Driver: working. Configuration: one of two detected displays is active, and the mode is “Show only on 1”. That matches the timeline (a projector session yesterday). “Detected but not active” is the key evidence that rules out replacing hardware.

#### Perfect steps

1. Open the chat from Ines (dashboard › Incoming contacts › Open chat) and select Log as INC-1056. Open the ticket and select Assign to me.
2. Open Tools › Remote Desktop, search “NS-SUP-007”, Connect, open Device Manager: confirm the dock and the NSM-27 monitor are Working.
3. Open Settings › Display: note “2 displays detected · 1 active” and Multiple displays “Show only on 1”.
4. In Multiple displays choose “Extend these displays”, then select Keep changes in the confirmation box.
5. Check Settings › Display again: 2 displays detected · 2 active.
6. Open Company Chat › Ines Duarte and select “INC-1056 · Ask to confirm the fix”. Ines confirms.
7. Select Check fix, write a resolution note and select Close ticket.

#### Verify

- Settings › Display: Extend these displays, 2 of 2 displays active.
- Device Manager: every device Working (no driver removed).
- Company Chat: Ines confirms she can drag the queue across.

#### Required outcome (what Check fix tests)

- Both screens active in Extend mode
- No unnecessary hardware sent
- Ines confirmed she can drag windows to the second screen

#### Common mistakes

- Ordering a monitor or dock because it says “No signal”.
- Uninstalling display drivers before checking the settings.
- Choosing Duplicate, which lights up the screen but not the way she works.
- Not asking what changed recently (the boardroom presentation).

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Shipped hardware when Device Manager showed the monitor connected | −2 |
| Issued a new monitor for a display-settings fault | −2 |
| Issued a new dock for a display-settings fault | −2 |

Closing it unresolved costs −10. Escalating it to Security costs −8.

#### Hint ladder

1. She presented yesterday. Something may have changed on the laptop then, not on the monitor. First check whether the laptop can see the monitor at all.
2. Device Manager lists the dock and the NSM-27 as working, and Settings › Display shows 2 detected but 1 active. Look at the Multiple displays setting.
3. Settings › Display › Multiple displays: choose “Extend these displays”, select Keep changes, then confirm with Ines in Company Chat.

#### Model answer

Device Manager showed the dock and the NSM-27 monitor working, so the hardware was fine. The display mode had been left on “Show only on 1” after yesterday’s boardroom presentation. Set Multiple displays to Extend and kept the change. Two displays are now active and Ines confirmed she can drag the queue onto the second screen. No hardware ordered.

#### Ideal resolution note

> Cause: display mode left on “Show only on 1” after a boardroom presentation. Dock DK-2 working (firmware current), NSM-27 detected but not active. Action: Settings › Display › Multiple displays set to Extend these displays and kept. Verified: 2 active displays; Ines confirmed in chat she can drag windows to the second screen. No hardware ordered.

Earns +3 of 3 for notes. Keywords: `ns-sup-007`, `extend`, `display`, `show only on 1`, `presentation`.

#### In the real world

Projection settings (Win+P) stick after meetings and cause a steady stream of “monitor broken” tickets. Asking what changed recently, then checking whether the operating system can detect the device, solves most peripheral calls without a desk visit.

<a id="inc-1057"></a>

### INC-1057 · Voicemail: “Avery Wilson” wants a laptop couriered to a hotel today

**Priority:** Critical (30 points) · **Category:** Security / Social engineering (device) · **Arrives:** as a voicemail (log it as a ticket first) · **Finish with:** Escalate to Security · **Best score:** +42

**Tools:** Directory, Asset Management, Company Chat, Voicemails  
**Runbooks:** [Verifying a caller’s identity](#kb14), [Urgent requests to send devices or passwords somewhere new](#kb21), [Escalating to Security with evidence](#kb34), [Logging chat messages and voicemails as tickets](#kb35)

**The ticket**

> Hi, this is Avery Wilson, Chief of Staff. My laptop was stolen from my car at the airport. I need a replacement couriered today to the Corvane Hotel, 88 Wharf Street, room 1214. I’m presenting to the board tomorrow. Please also reset my password and text the new one to this number, 555-0187. Thanks.
>
> *Business impact:* If the request is fake, an executive’s device and credentials would go to an attacker. If it’s real, an executive is without a device.
>
> *Already tried:* Voicemail only. No portal ticket and no call from the extension on file.

#### Symptoms to notice

- Urgency, authority (Chief of Staff, board meeting) and a new delivery channel (a hotel, a password by text) together: classic pretexting.
- Caller ID +1 555-0187 is external and doesn’t match the mobile on Avery’s record (+1 555-0110).
- Directory › Avery Wilson › Authentication: last sign-in “Today 08:02 · NS-EXEC-001 (Floor 2, wired)”.
- Asset Management › NS-EXEC-001 › Health: Heartbeat Live, network Floor 2 Switch. The “stolen” laptop is in the building.
- The request skips the normal process: no portal ticket, and it asks for a password over text message.

#### Diagnosis

The question isn’t how to replace a laptop. It’s whether the request is genuine. Never use contact details the requester supplies; check against what you already hold. Live data contradicts the story (the “stolen” laptop is online on Floor 2), and the real person, reached through a trusted internal channel, denies calling. That makes this an attempted social-engineering attack. The safe action is to change nothing (any change, even a protective wipe, causes harm here), keep the details and hand off to Security.

#### Perfect steps

1. Open Voicemails, read the message and caller ID, and select Log as ticket. Open INC-1057 and select Assign to me.
2. Open Tools › Directory, search “avery”, select Avery Wilson. On Profile compare Mobile (+1 555-0110) with the caller ID (+1 555-0187). On Authentication note the last sign-in at 08:02 from NS-EXEC-001.
3. Open Tools › Asset Management, search “NS-EXEC-001”, Open › Health: Heartbeat Live, network Floor 2 Switch.
4. Open Company Chat › Avery Wilson and select “INC-1057 · Ask Avery if she called about a stolen laptop”. She didn’t call and still has her laptop.
5. Don’t create a shipment, reset the password or MFA, or lock or wipe the laptop.
6. Optional: on the voicemail select Save to INC-1057 and Forward to Security.
7. Select Escalate to Security and write the evidence: caller number, time 08:51, the hotel address and the password-by-text request, and the facts that contradict the claim.

#### Verify

- Company Chat shows Avery’s denial.
- Ship Manager has no shipment for Avery Wilson.
- Directory: Avery is Enabled, MFA Enrolled, no password reset today. Asset Management: NS-EXEC-001 is In use, not locked or wiped.
- The ticket status is Escalated.

#### Required outcome (what Check fix tests)

- Claim checked with the real Avery through Company Chat
- Nothing shipped on the strength of the voicemail
- Avery’s account and laptop left untouched
- Routed to Security

#### Common mistakes

- Calling back the number the caller left instead of using a trusted channel.
- Wiping or locking the laptop “to be safe”, which disrupts the real executive.
- Resetting the password because the caller is senior and in a hurry.
- Closing the ticket instead of reporting the attempt to Security.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Sent an executive laptop to an unverified address from a voicemail | −6 |
| Reset an executive’s password for an unverified caller | −5 |
| Removed an executive’s MFA for an unverified caller | −5 |
| Wiped the real executive’s working laptop on a fake theft report | −6 |
| Locked out the real user on an unverified claim | −3 |
| Marked a laptop that is online on Floor 2 as stolen | −3 |

Closing it unresolved costs −20.

#### Hint ladder

1. Before acting on an urgent request to send a device or credentials somewhere new, check the story against what your systems already show.
2. The callback number isn’t on Avery’s record, Directory shows she signed in at 08:02 from NS-EXEC-001, and Asset Management shows that laptop online and wired on Floor 2. Contact Avery through a trusted channel.
3. Ask Avery in Company Chat, record the evidence in your notes, change nothing, and escalate to Security.

#### Model answer

The voicemail came from an unregistered external number and asked to ship to a hotel and text a password, both strong signs of pretexting. Directory shows Avery signed in today from NS-EXEC-001, and Asset Management shows that laptop online on the Floor 2 switch. Avery confirmed in Company Chat that she made no call and still has her laptop. Made no changes: no shipment, no password reset, no lock or wipe. Escalated to Security with the caller number, time and requested address.

#### Ideal resolution note

> Suspected social engineering. Voicemail 08:51 from external number +1 555-0187 (not on file; Avery’s mobile is +1 555-0110) claimed NS-EXEC-001 was stolen and asked to courier a replacement to the Corvane Hotel, 88 Wharf St, room 1214, and to text a new password. Evidence against: Directory shows awilson signed in 08:02 from NS-EXEC-001; Asset Management shows NS-EXEC-001 live on the Floor 2 switch. Avery confirmed in Company Chat she didn’t call and has her laptop. No changes made (no shipment, reset, lock or wipe). Escalated to Security with the caller details.

Earns +3 of 3 for notes. Keywords: `awilson`, `avery`, `555-0187`, `corvane`, `ns-exec-001`, `pretext`, `social engineering`.

#### In the real world

Help-desk pretexting, impersonating a senior person to get a password reset or a device, is behind several well-known breaches. Strong desks require a call back to the number on file, or a verified internal channel, for any credential or device request, however senior or urgent the caller sounds. They report every attempt, because one targeted call often means others.

<a id="inc-1058"></a>

### INC-1058 · Laptop battery drains while plugged in

**Priority:** Low (10 points) · **Category:** Hardware / Power & accessories · **Arrives:** as a Company Chat message (log it as a ticket first) · **Finish with:** Close ticket · **Best score:** +13

**Tools:** Remote Desktop, PC Shelf, Asset Management, Company Chat  
**Runbooks:** [Laptop not charging while plugged in](#kb20), [Logging chat messages and voicemails as tickets](#kb35)

**The ticket**

> My laptop battery keeps going down even though it’s plugged in. It’s at 18% now. It’s plugged in to the charger at my desk, and the light on the cable is on.
>
> *Business impact:* One user will lose their laptop within the hour unless charging is fixed. Nothing else is affected.
>
> *Already tried:* Tried a different wall socket.

#### Symptoms to notice

- “The light on the cable is on”: power is arriving, so the question is how much.
- Settings › Power & battery: Status Not charging, power adapter 45 W USB-C with the warning “Below the 65 W this laptop needs”. Battery health 91%, 212 cycles.
- Device Manager › Batteries: USB-C Power Delivery, source a 45 W third-party adapter.
- Asset Management › NS-OPS-026 › Accessories: CHG-65W-118 reported missing Oct 6.

#### Diagnosis

Split the power path into charger, port, battery and operating system. The battery is healthy (91%, low cycle count) and the operating system clearly reports the adapter’s wattage, which is below what this model needs. Every USB-C charger fits, so people grab whatever is on the desk. The asset record explains why: his own charger went missing. The cheapest correct fix is the accessory, recorded against the asset so the inventory stays accurate.

#### Perfect steps

1. Open the chat from Daniel (dashboard › Incoming contacts › Open chat) and select Log as INC-1058. Open the ticket and select Assign to me.
2. Open Tools › Remote Desktop, search “NS-OPS-026”, Connect, open Settings › Power & battery: read Not charging, 45 W adapter, health 91%, 212 cycles.
3. Open Device Manager › Batteries: USB-C Power Delivery source is a 45 W third-party adapter.
4. Open Tools › Asset Management, search “NS-OPS-026”, Open › Accessories: note CHG-65W-118 reported missing Oct 6.
5. Open Tools › PC Shelf › Accessories. On USB-C charger 65 W choose NS-OPS-026 · Daniel Asante and select Issue. Stock drops by one and the asset lists the charger.
6. Open Company Chat › Daniel Asante and select “INC-1058 · Ask Daniel to swap to the issued charger”. He swaps it.
7. Back in Remote Desktop › Settings › Power & battery: Status Charging, power adapter 65 W.
8. In Company Chat select “INC-1058 · Ask to confirm the fix”. Daniel confirms the percentage is going up.
9. Select Check fix, write a resolution note and select Close ticket.

#### Verify

- Power & battery shows Charging on a 65 W adapter.
- Asset Management › NS-OPS-026 › Accessories lists USB-C charger 65 W. The replacement battery is still on the shelf.
- Company Chat: Daniel confirms it’s charging.

#### Required outcome (what Check fix tests)

- A 65 W charger issued and recorded against NS-OPS-026
- Laptop is charging at 65 W
- Laptop and battery kept in service (the battery is healthy)
- Daniel confirmed the battery is charging

#### Common mistakes

- Replacing the battery or the whole laptop without reading the battery health.
- Issuing the 45 W charger, which is no better than the one he has.
- Not recording the issued accessory against the asset.
- Using Battery saver as a “fix”.

#### Wrong actions and penalties

No ticket-specific penalties.

Closing it unresolved costs −10. Escalating it to Security costs −8.

#### Hint ladder

1. “Plugged in but draining” can be the battery, the laptop or the charger. Remote Desktop › Settings › Power & battery tells you which.
2. The laptop reports a 45 W adapter, and a Northbook 14 needs 65 W. Battery health is 91%. Asset Management › Accessories shows his issued charger went missing on Oct 6.
3. Issue a USB-C charger 65 W from PC Shelf › Accessories to NS-OPS-026, ask Daniel in Company Chat to swap chargers, check Power & battery shows Charging, then get his confirmation.

#### Model answer

Power & battery showed “Not charging” on a 45 W adapter, below the 65 W a Northbook 14 needs. Daniel was using a third-party charger because his issued 65 W charger (CHG-65W-118) went missing on Oct 6. Battery health is 91%, so no battery or laptop swap was needed. Issued a 65 W charger from stock against NS-OPS-026, Daniel swapped it in, and Power & battery now shows Charging at 65 W. Daniel confirmed.

#### Ideal resolution note

> Cause: under-powered 45 W third-party USB-C charger (a Northbook 14 needs 65 W). Issued charger CHG-65W-118 reported missing Oct 6. Battery health 91%, 212 cycles, no fault. Action: issued a USB-C charger 65 W from stock against NS-OPS-026 for dasante and asked him to swap. Verified: Power & battery shows Charging at 65 W; Daniel confirmed in chat.

Earns +3 of 3 for notes. Keywords: `dasante`, `daniel`, `ns-ops-026`, `65 w`, `45 w`, `charger`.

#### In the real world

Under-powered USB-C chargers are a common modern cause of “battery won’t charge” tickets: the plug fits and the light comes on, but the wattage is too low. Tracking chargers and docks as accessories against the laptop saves money and finds the ones that walk off to meeting rooms.

<a id="inc-1064"></a>

### INC-1064 · Access to the Sales Orders inbox while covering

**Priority:** Low (10 points) · **Category:** Email / Shared mailbox access · **Arrives:** at the start of shift 2 · **Finish with:** Close ticket · **Best score:** +13

**Tools:** Directory, Mail Admin, Company Chat  
**Runbooks:** [Shared mailbox access requests](#kb25)

**The ticket**

> Hi, could I get access to the Sales Orders inbox (sales-orders@)? I’m covering for Nina next week while she’s off and need to keep on top of incoming orders. My manager Dana said it’s fine. Thanks!
>
> *Business impact:* Low: the cover starts next week. Order mail is customer-facing.
>
> *Already tried:* Tried adding the mailbox in Outlook myself. It said I don’t have permission.

#### Symptoms to notice

- The requester cites approval from his line manager, who doesn’t own the mailbox.
- Mail Admin › Shared mailboxes › Sales Orders lists an Owner (Rosa Delgado) and an access policy that asks for her written approval.
- The cover is temporary (next week), so the access should be time-boxed.
- Order confirmations go to customers, so Send As matters.

#### Diagnosis

Nothing is broken; the job is to apply access control correctly. Mail Admin › Shared mailboxes › Sales Orders shows the owner is Rosa Delgado and the policy needs her written approval. A line manager vouching for an employee is not the same as the data owner authorising access to their data. Get the approval in Company Chat, where it is written and attributable, and grant only what was approved: Full Access (read and manage), no Send As, ending on the approved date. Then verify from the user’s side.

#### Perfect steps

1. Open INC-1064 and select Assign to me.
2. Open Tools › Mail Admin › Shared mailboxes and select Open on Sales Orders. Note Owner: Rosa Delgado, the access policy, and the current permissions (Nina: Full Access + Send As; Rosa: Full Access).
3. Optional: Tools › Directory › Evan Brooks › Profile shows Manager: Dana Okafor, who isn’t the owner.
4. Open Company Chat › Rosa Delgado and select “INC-1064 · Ask Rosa to approve Evan’s access to Sales Orders”. Rosa approves read and manage only, until Fri Oct 23, and no Send As.
5. Back in Mail Admin › Shared mailboxes › Sales Orders › Permissions: choose Evan Brooks, Full Access, expiry “Fri Oct 23”, and select Grant. The row shows Owner approved. Don’t add Send As.
6. Under Test access as…, choose Evan Brooks and select Test access. Expect “ebrooks can open sales-orders@northstar.example”.
7. Open Company Chat › Evan Brooks and select “INC-1064 · Ask to confirm the fix”. Evan confirms the mailbox appears in Outlook.
8. Select Check fix, write a note that quotes Rosa’s approval, and select Close ticket.

#### Verify

- Sales Orders › Permissions shows Evan Brooks: Full Access, expires 2026-10-23, Owner approved, and no Send As row.
- Test access shows Evan Brooks: Can open.
- Company Chat holds Rosa’s approval text and Evan’s confirmation.

#### Required outcome (what Check fix tests)

- Written approval recorded from the mailbox owner, Rosa Delgado
- Evan has Full Access to Sales Orders, granted after Rosa approved
- No Send As, matching the approved scope
- Access set to expire on Fri Oct 23
- Access tested as Evan and confirmed by him

#### Common mistakes

- Accepting “my manager said it’s OK” as approval.
- Ticking Send As because it is next to Full Access.
- Granting open-ended access for a one-week cover.
- Not recording the approval in the ticket notes, which leaves nothing for an audit.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Granted access to Sales Orders before the owner approved: Dana isn’t the owner | −3 |
| Gave Evan Send As on Sales Orders, which Rosa didn’t approve | −2 |

Closing it unresolved costs −10. Escalating it to Security costs −8.

#### Hint ladder

1. Open Sales Orders in Mail Admin › Shared mailboxes and read its owner and access policy before you grant anything.
2. “My manager said it’s fine” isn’t the approval the policy asks for. Ask the owner in Company Chat and note exactly what she approves.
3. Get Rosa’s approval in Company Chat, grant Full Access only (no Send As) with expiry Fri Oct 23, then Test access as Evan and ask him to confirm.

#### Model answer

The Sales Orders policy requires written approval from the owner, Rosa Delgado. Evan’s line manager Dana deferred to Rosa. Rosa approved Full Access (read and manage) until Fri Oct 23 and explicitly declined Send As. Granted Evan Full Access only, expiring 2026-10-23, tested access as Evan, and he confirmed the mailbox appears in Outlook.

#### Ideal resolution note

> Request for Sales Orders (sales-orders@) access to cover for Nina next week. Policy requires owner approval; the owner is Rosa Delgado (Dana, Evan’s manager, deferred to Rosa). Rosa approved in Company Chat: “read and manage only, until Fri Oct 23. No Send As.” Granted Evan Full Access expiring 2026-10-23, no Send As. Tested access as Evan (can open); Evan confirmed in chat.

Earns +3 of 3 for notes. Keywords: `sales-orders`, `rdelgado`, `rosa`, `full access`, `send as`, `oct 23`.

#### In the real world

Shared mailbox access is a frequent audit finding because grants are rarely removed. Recording the owner’s approval and setting an expiry keeps permissions from piling up. Send As matters because messages appear to come from the team or company and can be used for fraud.

<a id="inc-1067"></a>

### INC-1067 · New laptop on Floor 2 says “No internet”

**Priority:** Medium (15 points) · **Category:** Network / DHCP · **Arrives:** as a Company Chat message (log it as a ticket first) · **Finish with:** Close ticket · **Best score:** +18

**Tools:** Server Room, Remote Desktop, Company Chat  
**Runbooks:** [DHCP scope full (169.254 address)](#kb30), [Logging chat messages and voicemails as tickets](#kb35)

**The ticket**

> Hi! It’s my first day. My new laptop is connected to Northstar-Staff but the icon says “No internet” and Outlook won’t load. Maya’s laptop right next to me works fine. Is something wrong with my account?
>
> *Business impact:* A new starter can’t work on her first day. Any other new device on Floor 2 will fail the same way.
>
> *Already tried:* Turned Wi-Fi off and on, restarted the laptop and signed in again.

#### Symptoms to notice

- Only a brand-new device fails. The colleague at the next desk works, so the floor network is fine.
- “No internet” while connected to the right Wi-Fi means the link works but IP configuration failed.
- The requester suspects her account, but she signed in with cached credentials. Don’t chase the account.

#### Diagnosis

A Windows device that gets no DHCP answer gives itself a 169.254.x.x (APIPA) address. When you see one, stop looking at accounts and Wi-Fi profiles and look at DHCP. The DHCP Server service is running (restarting it changes nothing), so ask whether it has an address to give. The Floor 2 scope is small (50 addresses) and shows 50 / 50 in use. Its lease list explains why: 31 EVT-WS devices from a one-day workshop still hold addresses because the lease lasts 8 days. Existing colleagues keep working because they already hold leases; only new devices are refused. The safe fix removes only the stale leases, and a shorter lease stops it happening again. Wiping every lease, or widening the range carelessly, creates conflicts.

#### Perfect steps

1. Open the chat from Lucia (dashboard › Incoming contacts › Open chat) and select Log as INC-1067. Open the ticket and select Assign to me.
2. Open Tools › Remote Desktop, search “NS-FIN-031” and select Connect, then Connect in the dialog. The status bar reads “Self-assigned 169.254 address (no DHCP lease)”.
3. Open Terminal and run ipconfig. Note the 169.254.x.x (Autoconfiguration) address and the empty Default Gateway.
4. Run ping 10.0.0.1. It fails with “General failure”, which confirms there’s no usable address.
5. Open Tools › Server Room › Servers, select Services on DC01: DHCP Server is Running. Select “Event log & scheduled tasks” and read event 1020: the Floor 2 scope is 100% full.
6. Open the DHCP tab. Floor 2 shows 50 / 50 in use, lease 8 days. Select View leases: 31 EVT-WS-xx leases last seen yesterday at 17:05, Inactive.
7. Select Delete inactive leases (not Delete all leases). Floor 2 now shows 19 / 50 in use.
8. In the lease duration list choose 8 hours and select Set lease duration.
9. Leave the range alone. If you ever widen it, use “100 addresses (.100–.199)”, never the .20–.219 range that covers the printer at 10.0.2.50.
10. Back in Remote Desktop › NS-FIN-031 › Terminal, run ipconfig /renew. It returns a 10.0.2.1xx address with gateway 10.0.0.1.
11. Run ping 10.0.0.1 and expect replies. This sets the connectivity requirement.
12. Optional: tell Lucia in Company Chat that she’s connected. Select Check fix, write notes and select Close ticket.

#### Verify

- Server Room › DHCP › Floor 2 shows free addresses (for example 20 / 50 in use) and a lease of 8 hours.
- ipconfig on NS-FIN-031 shows a 10.0.2.x address and gateway 10.0.0.1.
- ping 10.0.0.1 replies from NS-FIN-031.
- All four requirements are ticked.

#### Required outcome (what Check fix tests)

- Floor 2 scope has free addresses and doesn’t overlap fixed devices
- Floor 2 lease time is a day or less
- NS-FIN-031 has a 10.0.2.x lease
- Connectivity tested from NS-FIN-031

#### Common mistakes

- Resetting the new starter’s password or checking her groups: an identity rabbit hole.
- Deleting every lease, which knocks 19 working people off the network.
- Widening the range into the fixed-address block where printers and switches live.
- Fixing the scope but not renewing on the laptop. A 169.254 address doesn’t heal instantly.
- Not shortening the lease, so the next event fills the scope again.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Deleted every Floor 2 lease: 19 working colleagues dropped off and had to renew | −4 |
| Widened the Floor 2 scope over fixed addresses: PRN-F2-01 (10.0.2.50) now clashes | −4 |
| Rebooted the Floor 2 switch: the whole floor dropped and the scope was still full | −3 |
| Powered off the Floor 2 switch: the whole floor dropped and the scope was still full | −3 |

Closing it unresolved costs −10. Escalating it to Security costs −8.

#### Hint ladder

1. Her account isn’t the problem. A device that can’t get an address can’t reach anything. Check what address the laptop has.
2. Remote into NS-FIN-031 and run ipconfig. A 169.254.x.x address means DHCP gave it nothing. Then look at the Floor 2 scope in Server Room › DHCP.
3. Delete only the inactive EVT-WS leases from yesterday’s workshop, set the lease duration to 8 hours, then run ipconfig /renew and ping 10.0.0.1 on NS-FIN-031.

#### Model answer

The account was fine; the device was the issue. NS-FIN-031 had a 169.254 self-assigned address, so DHCP wasn’t answering it. DC01 event 1020 showed the Floor 2 scope 100% full: 31 of its 50 leases belonged to EVT-WS guest devices from yesterday’s partner workshop, held by an 8-day lease. Deleted only the inactive leases, cut the lease to 8 hours, renewed the lease on NS-FIN-031 (now 10.0.2.1xx) and confirmed the gateway replies. Told Lucia she’s set.

#### Ideal resolution note

> NS-FIN-031 (new starter lferreira) had a 169.254 APIPA address, so DHCP wasn’t answering. DC01 DHCP Server was running, but event 1020 showed the Floor 2 scope (10.0.2.100–149) 100% full: 31 of 50 leases were EVT-WS guest devices from yesterday’s workshop, kept by an 8-day lease. Deleted only the inactive leases (19 / 50 in use) and set the lease to 8 hours. Verified: ipconfig /renew gave 10.0.2.1xx and ping 10.0.0.1 replies. Recommend a guest network for future events.

Earns +3 of 3 for notes. Keywords: `ns-fin-031`, `169.254`, `apipa`, `evt-ws`, `lease`, `dhcp`.

#### In the real world

Guest and event devices belong on a guest network with its own short-lease scope, never the staff scope. Set DHCP alerts at about 80% use, and keep fixed devices (printers, switches, access points) in an excluded range or reservation so a range change can’t collide with them.

<a id="inc-1071"></a>

### INC-1071 · New phone won’t sync company email

**Priority:** Low (10 points) · **Category:** Email / Mobile access · **Arrives:** as a Company Chat message (log it as a ticket first) · **Finish with:** Close ticket · **Best score:** +13

**Tools:** Mail Admin, Company Chat  
**Runbooks:** [Approving a new phone for company mail](#kb29), [Logging chat messages and voicemails as tickets](#kb35)

**The ticket**

> Hey, I got my new phone yesterday. The mail app says “Your administrator must approve this device before it can sync,” and the calendar is empty too. I’m out at a client from 2pm, so it’d be great to have it working before then.
>
> *Business impact:* One user has no mobile email or calendar on the road. Desktop email works.
>
> *Already tried:* Removed and re-added the account in the phone’s mail app twice.

#### Symptoms to notice

- The error names the cause: admin approval (quarantine), not a password or server problem.
- There are two waiting requests with the same Device ID but different apps.
- The old phone is still listed as Allowed, which is a lingering access path.

#### Diagnosis

The mobile access policy quarantines new devices until IT approves them. The question isn’t whether to approve, but what exactly to approve. Two requests share one Device ID, so they’re the same phone using two different apps. Policy allows only Northstar Mail; MailSync Pro would put the user’s credentials in someone else’s cloud. Before approving anything, prove the phone is Talia’s by matching the Device ID she reads off her own handset. While you’re there, clean up the old phone. It was traded in, so remove the partnership instead of sending a full wipe to hardware nobody here controls. Finish by confirming sync works.

#### Perfect steps

1. Open the chat from Talia (dashboard › Incoming contacts › Open chat) and select Log as INC-1071. Open the ticket and select Assign to me.
2. Open Tools › Mail Admin › Mobile devices. Read Talia Reyes’s three rows: Aster X5 · Northstar Mail 6.1 (Quarantined, NSD-7Q4K-A7F3), Aster X5 · MailSync Pro 3.4 (Quarantined, same ID, “Not on the approved list”), Aster X2 · Northstar Mail 5.8 (Allowed, last sync Oct 10).
3. Open Company Chat › Talia Reyes and select “INC-1071 · Ask Talia for the new phone’s Device ID”. She reads NSD-7Q4K-A7F3 and mentions trying MailSync first.
4. In Mail Admin › Mobile devices select Approve on the Northstar Mail 6.1 row.
5. Select Block on the MailSync Pro 3.4 row.
6. In Company Chat select “INC-1071 · Ask Talia what happened to her old phone”. She traded it in and the shop reset it.
7. Select Remove partnership on the Aster X2 row. Don’t use Remote wipe.
8. Select Test sync on the Northstar Mail 6.1 row. Expect “sync test passed”.
9. In Company Chat select “INC-1071 · Ask to confirm the fix”. Talia confirms mail and calendar.
10. Select Check fix, write notes and select Close ticket.

#### Verify

- Northstar Mail 6.1 shows Allowed with “test OK”.
- MailSync Pro 3.4 shows Blocked and the Aster X2 shows Removed.
- Talia confirms in Company Chat that mail and calendar arrived.
- All five requirements are ticked.

#### Required outcome (what Check fix tests)

- Device ID confirmed with Talia
- New phone’s Northstar Mail access approved
- Unapproved MailSync Pro access blocked
- Old phone’s mail access removed
- Sync tested and Talia confirmed mail and calendar arrived

#### Common mistakes

- Approving both waiting requests to “make it work”.
- Turning off quarantine for everyone to fix one user.
- Approving without checking the Device ID with the user.
- Full-wiping a traded-in phone, which may now belong to someone else.
- Leaving the old phone’s partnership active.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Approved MailSync Pro: it isn’t on the approved list and stores the password in a third-party cloud | −4 |
| Approved a phone before checking its Device ID with Talia | −2 |
| Sent a full wipe to a traded-in phone that now belongs to someone else | −3 |
| Turned off mobile quarantine for every user to fix one phone | −5 |

Closing it unresolved costs −10. Escalating it to Security costs −8.

#### Hint ladder

1. The message says exactly where to look: someone has to approve the device. Check which devices are waiting.
2. Mail Admin › Mobile devices: compare the app and Device ID of each of Talia’s rows, and ask Talia for her Device ID in Company Chat.
3. Approve the Northstar Mail request with Device ID NSD-7Q4K-A7F3, block the MailSync Pro one, remove the old Aster X2 partnership, then Test sync and ask Talia to check.

#### Model answer

Mail Admin showed two quarantined requests from Talia’s new phone with the same Device ID (NSD-7Q4K-A7F3). One used Northstar Mail, the approved app; the other used MailSync Pro, which isn’t approved and relays mail through a vendor cloud. Confirmed the Device ID with Talia in chat, approved the Northstar Mail partnership, blocked MailSync Pro and asked her to uninstall it. She confirmed the old Aster X2 was traded in, so I removed its mail partnership (no full wipe on a phone we no longer control). Test sync passed and Talia confirmed mail and calendar arrived.

#### Ideal resolution note

> Talia’s new Aster X5 (Device ID NSD-7Q4K-A7F3, confirmed by Talia in chat) had two quarantined requests: Northstar Mail (approved app) and MailSync Pro (not approved, third-party cloud relay). Approved Northstar Mail, blocked MailSync Pro and asked her to uninstall it. Old Aster X2 (NSD-2M9P-41C0) was traded in, so I removed the partnership (no full wipe). Verified: test sync passed and Talia confirmed mail and calendar in chat.

Earns +3 of 3 for notes. Keywords: `treyes`, `talia`, `nsd-7q4k-a7f3`, `mailsync`, `quarantine`, `partnership`.

#### In the real world

Mobile quarantine and approved-app lists are a standard data-protection control in mail systems and MDM. When someone gets a new phone, retire the old partnership in the same visit. Use an account-only (selective) wipe for personal or traded devices, and keep the full wipe for company-owned devices that are lost or stolen.

<a id="shift-3"></a>

## Shift 3 · Wednesday

Identity, infrastructure and security: joiners, leavers, returners and name changes, MFA resets, an office-wide DNS failure, a provider outage, a full file server, a lost file, a suspicious phone call and reported phishing.

<a id="inc-1059"></a>

### INC-1059 · New starter tomorrow: Sales account, laptop and licences

**Priority:** High (22 points) · **Category:** Identity / Joiner · **Arrives:** at the start of shift 3 · **Finish with:** Close ticket · **Best score:** +25

**Tools:** Directory, Computer Deployment, Documentation, Company Chat  
**Runbooks:** [Resetting a password safely](#kb2), [Username standard](#kb11), [Deploying a computer from the PC Shelf](#kb12), [New starter: account, access and day-one handover](#kb31), [Licence pools: assigning and reclaiming seats](#kb33)

**The ticket**

> Hi IT, Kofi Mensah starts in Sales tomorrow at 09:00 and nothing is set up yet. Sorry, the starter form got stuck in my drafts. The full details are on starter record HR-2291. He needs to be able to sign in and see the Sales files on day one. Rosa is meeting him at reception.
>
> *Business impact:* A new hire arrives tomorrow morning with no account, mailbox or laptop. The Sales manager has blocked out the morning for onboarding.
>
> *Already tried:* HR filled in starter record HR-2291 (Directory › Starters). Nothing else.

#### Symptoms to notice

- Only a name is given. The ticket never states a username, so you have to work it out from the standard.
- The starter record says access should be “the same as the rest of the Sales team”. That is vague, so compare against a real Sales account instead of guessing.
- The record has a personal email address. It is there to tempt you into sending credentials to it.
- Licence pools › Sales Hub CRM shows exactly 1 free seat.
- The PC Shelf has a faulty laptop (NSA-S305) that can’t be deployed.

#### Diagnosis

This joiner ticket checks whether you follow the identity standard instead of improvising. Searching Directory for “mensah” returns kmensah (Kwame Mensah), disabled since 2025, with a leaver record that says the mailbox is on a 7-year hold. The Username standard (Documentation) says: first initial + surname; if taken, add the middle initial, or with no middle initial the next letter of the first name. Kofi has no middle initial, so the account is komensah. Never reuse the leaver: Kofi would get a former employee’s mailbox, groups and audit trail. “Same as the team” means the minimum set a peer holds: Rosa Delgado, his manager, has Domain Users + Sales-Share. Licences come from the starter record; Office Suite provisions the mailbox. The first-day password goes to the manager through an internal channel, never to a personal mailbox. Verify with a sign-in test, then close the loop with HR, who own the joiner process.

#### Perfect steps

1. Open INC-1059 and select Assign to me.
2. Open Tools › Directory › Starters, select Kofi Mensah (HR-2291) and note dept Sales, title Account Executive, manager Rosa Delgado, floor 1, ext 3113, licences Office Suite + Sales Hub CRM.
3. Open Tools › Documentation, search “username” and read “Username standard”.
4. In Directory › Users search “mensah”: kmensah is Kwame Mensah, Disabled. Directory › Leavers › Kwame Mensah (HR-LVR-0031) says never reuse it. Change nothing.
5. Search “delgado”, select Rosa Delgado › Groups: Domain Users + Sales-Share is the team baseline.
6. Directory › Starters › Kofi Mensah › Create account from this record…. Change Username to komensah (the hint turns green). Keep Department Sales, Manager Rosa Delgado. Tick Sales Hub CRM as well as Office Suite and Endpoint Protection, keep “Add the department share group” ticked, and select Create user.
7. Check komensah › Groups (Domain Users, Sales-Share) and › Licences (Office Suite, Sales Hub CRM assigned; the flash said the mailbox was provisioned).
8. Open Tools › Computer Deployment. Device: an Available, Wiped Northbook 14 (for example NSA-S131), image Sales Mobile · Northstar Sales 24.2, Assign to: Kofi Mensah (komensah), Location: Floor 1. Select Run deployment. Leave the faulty NSA-S305 alone.
9. Directory › komensah › Authentication › Reset password…: keep “User must change password at next sign-in” ticked and set delivery to “Company Chat to their manager”. Select Reset password.
10. Select Test sign-in. Expect “Sign-in test passed for komensah. They’ll be asked to choose a new password.”
11. Open Company Chat › Priya Shah and select “INC-1059 · Ask to confirm the fix”. Priya ticks off HR-2291.
12. Select Check fix, write a resolution note and select Close ticket.

#### Verify

- Directory › komensah › Authentication: Enabled, Not locked, Must change at next sign-in, sent via Company Chat to their manager, last sign-in test Passed.
- Directory › komensah › Groups lists exactly Domain Users and Sales-Share.
- Directory › Licence pools › Sales Hub CRM shows 0 free, with Kofi as a holder.
- Asset Management lists a NS-SALES-1xx laptop owned by Kofi Mensah, In use, image Northstar Sales 24.2.
- Directory › kmensah still shows Disabled · Kwame Mensah.
- Company Chat shows Priya’s confirmation.

#### Required outcome (what Check fix tests)

- Account komensah created for Kofi Mensah in Sales, managed by Rosa Delgado
- The 2025 leaver account kmensah is untouched and disabled
- Groups match the Sales team: Domain Users and Sales-Share
- Office Suite and Sales Hub CRM assigned, mailbox provisioned
- A laptop with Northstar Sales 24.2 is deployed to Kofi
- Temporary password must change at first sign-in and went to his manager
- Sign-in test passed and Priya confirmed the starter is ready

#### Common mistakes

- Typing kmensah without searching first, then “fixing” the conflict by re-enabling the leaver.
- Inventing a username (kmensah2) instead of following the written standard.
- Copying groups from someone in another department, or adding every share “just in case”.
- Sending the password to the personal email because it is the only address on the form.
- Forgetting Sales Hub CRM, or the Office licence, so there is no mailbox on day one.
- Skipping the sign-in test and the confirmation with HR.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Re-enabled a 2025 leaver’s account: Kofi would get a stranger’s mailbox and Operations access | −4 |
| Repurposed a leaver’s account instead of creating a new one | −4 |
| Sent a temporary password to a personal email address, outside the company | −4 |

Closing it unresolved costs −15. Escalating it to Security costs −8.

#### Hint ladder

1. Open the HR starter record first. Then read the Username standard in Documentation before you type anything into Create user.
2. Search Directory for “mensah”: a 2025 leaver already holds kmensah. Follow the standard for the next name, and copy the group set from his manager, Rosa Delgado.
3. Create komensah (Sales, manager Rosa Delgado, Sales-Share). Assign Office Suite and Sales Hub CRM, deploy a laptop with Northstar Sales 24.2, reset the password with must-change sent to his manager, run Test sign-in, then confirm with Priya.

#### Model answer

Processed starter HR-2291 for Kofi Mensah. kmensah belongs to a 2025 leaver on a legal hold, so I left it disabled and created komensah under the Username standard (no middle initial, so the next letter of the first name). Set Sales / Account Executive with manager Rosa Delgado and matched Rosa’s groups (Domain Users, Sales-Share). Assigned Office Suite (which provisioned the mailbox) and the last free Sales Hub CRM seat. Deployed a Northbook 14 with Northstar Sales 24.2. Issued a temporary password that must change at first sign-in and sent it to Rosa through Company Chat, not the personal address on the form. The sign-in test passed and Priya confirmed in chat.

#### Ideal resolution note

> Starter HR-2291 Kofi Mensah (Sales, AE, manager Rosa Delgado, start tomorrow 09:00). kmensah is held by leaver Kwame Mensah (disabled, 7-year hold), so I left it untouched and created komensah under the Username standard. Groups match Rosa: Domain Users, Sales-Share. Licences: Office Suite (mailbox kofi.mensah@northstar.example provisioned) plus Sales Hub CRM (last free seat). Laptop deployed with Northstar Sales 24.2. Temp password must change at first sign-in, sent to Rosa via Company Chat, not the personal address. Sign-in test passed. Priya (HR) confirmed in chat.

Earns +3 of 3 for notes. Keywords: `komensah`, `kofi`, `hr-2291`, `username standard`, `sales-share`, `kmensah`.

#### In the real world

In real joiner/mover/leaver processes, account reuse is one of the most common audit findings. A new hire who shares a surname with a leaver can inherit their mailbox, files and access. Most organisations make usernames permanent and never recycle them. First-day credentials usually go to the line manager, or through a temporary access pass, so they never pass through personal email.

<a id="inc-1060"></a>

### INC-1060 · Name changed after marriage but email still shows old name

**Priority:** Low (10 points) · **Category:** Identity / Profile change · **Arrives:** at the start of shift 3 · **Finish with:** Close ticket · **Best score:** +13

**Tools:** Directory, Mail Admin, Documentation, Company Chat  
**Runbooks:** [Username standard](#kb11), [Name change: display name and email alias](#kb32), [Following a message with Message trace](#kb37)

**The ticket**

> Hi, I got married last month and HR updated my surname to Osei on payroll (HR-CHG-0417), but my email, chat and the address book all still say Hannah Clarke. Could you switch everything over to my new name? Suppliers email me invoices all day, so I really can’t afford to miss anything.
>
> *Business impact:* One user. Cosmetic but visible to suppliers, with a risk to accounts-payable mail flow if it’s done wrong.
>
> *Already tried:* Changed my email signature myself. Nothing else.

#### Symptoms to notice

- HR has already recorded the change (the Pending HR change banner), so the request is legitimate and authorised.
- Message trace for “clarke” shows 6 supplier messages to hannah.clarke@ today. Removing that address would bounce real invoices.
- Her username hclarke is what her laptop NS-FIN-024 and her mapped drives use.

#### Diagnosis

A name change touches three different identifiers: the display name (what people see), the email addresses (where mail goes) and the sign-in name (what devices and apps rely on). Only the first two should change. The message trace shows active external senders, so the old address must stay as an alias or invoices will bounce. The Username standard explains why the username stays: renaming it breaks saved sign-ins, mapped drives and scripts, for a cosmetic gain nobody sees. The HR record is the authority for the new legal name, so no extra approval is needed. Test the risky part, mail to the old address, and confirm the visible part with Hannah.

#### Perfect steps

1. Open INC-1060 and select Assign to me.
2. Open Tools › Directory, search “hannah”, select Hannah Clarke. Profile shows “Pending HR change: HR records this person as Hannah Osei”.
3. Open Tools › Mail Admin › Message trace, type “clarke” and select Search. Note the supplier invoices delivered to hannah.clarke@ today.
4. Optional: Tools › Documentation › “Username standard”.
5. Back in Directory › Hannah Clarke › Profile, select Edit profile…, set Display name to Hannah Osei, leave Username as hclarke, and select Save changes.
6. Open the Email addresses tab, type hannah.osei@northstar.example and select Add address, then select Make primary on it. hannah.clarke@ is kept as an alias. Leave it there.
7. Open Mail Admin › Mailboxes, choose Hannah’s mailbox, set “Send test to” to hannah.clarke@northstar.example and select Send test message. Expect “delivered to Hannah Osei’s mailbox”.
8. Open Company Chat › Hannah Osei and select “INC-1060 · Ask to confirm the fix”. She confirms.
9. Select Check fix, write a resolution note and select Close ticket.

#### Verify

- Directory Profile: Display name Hannah Osei, Username hclarke, Email hannah.osei@northstar.example; Email addresses lists hannah.clarke@ as an alias.
- Mail Admin: the mailbox shows “Alias delivers”.
- Re-run the trace for “clarke”: the supplier mail still shows Delivered (alias).
- Hannah’s confirmation appears in Company Chat.

#### Required outcome (what Check fix tests)

- Display name updated to Hannah Osei
- Primary email is hannah.osei@northstar.example
- Old address kept as an alias so supplier mail still arrives
- Sign-in username left unchanged
- Test mail to the old address delivered to Hannah’s mailbox
- Hannah confirmed the new name looks right

#### Common mistakes

- Renaming the username for consistency. It breaks the profile, drives and sign-in links.
- Removing the old address as housekeeping and silently bouncing supplier invoices.
- Creating a fresh account under the new name.
- Asking for more approval when the HR record already authorises the change. Not an error, but it wastes time.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Renamed the sign-in username: NS-FIN-024 now creates a new empty profile and mapped drives fail | −3 |
| Removed the old address: supplier invoices to hannah.clarke@ now bounce | −3 |
| Created a second identity for Hannah instead of updating her account | −3 |

Closing it unresolved costs −10. Escalating it to Security costs −8.

#### Hint ladder

1. Open Hannah’s Directory profile and read the Pending HR change banner. Then run a Message trace for her old address. Who still sends there?
2. Change what people see (display name and primary address), not what she signs in with. Read the Username standard in Documentation.
3. Edit profile: display name Hannah Osei. Add hannah.osei@northstar.example and make it primary, keep the old address as an alias, send a test to the old address, then ask Hannah to confirm in Company Chat.

#### Model answer

Verified the legal name change against HR record HR-CHG-0417. Changed the display name to Hannah Osei and made hannah.osei@northstar.example the primary address. Kept hannah.clarke@northstar.example as an alias, because today’s trace shows suppliers still invoicing the old address. Left the sign-in username hclarke unchanged so her Windows profile and mapped drives keep working. A test to the old address was delivered to her mailbox, and Hannah confirmed the change in chat.

#### Ideal resolution note

> Name change per HR-CHG-0417: Hannah Clarke to Hannah Osei. Display name updated, primary address now hannah.osei@northstar.example, old hannah.clarke@ kept as an alias (6 supplier invoices to the old address today, per trace). Username hclarke deliberately unchanged to protect the NS-FIN-024 profile and mapped drives. Test to the old address delivered via alias. User confirmed in chat.

Earns +3 of 3 for notes. Keywords: `hclarke`, `hannah`, `osei`, `alias`, `hr-chg-0417`.

#### In the real world

Most organisations treat the sign-in name as permanent and keep previous email addresses as aliases indefinitely, or at least for a year. Legal name changes can be sensitive (marriage, divorce, transition), so handle them promptly and discreetly, and never ask for justification beyond the HR record.

<a id="inc-1061"></a>

### INC-1061 · Leaver offboarding: Operations coordinator finished Friday

**Priority:** High (22 points) · **Category:** Identity / Leaver · **Arrives:** at the start of shift 3 · **Finish with:** Close ticket · **Best score:** +25

**Tools:** Directory, Mail Admin, Asset Management  
**Runbooks:** [Offboarding a leaver](#kb22), [Licence pools: assigning and reclaiming seats](#kb33)

**The ticket**

> Marcus Hale’s last day was Friday and his leaver form is HR-LVR-0088. Please could you close him down? Jordan needs to keep an eye on supplier emails that come to Marcus for a while. Marcus dropped his laptop at reception this morning.
>
> *Business impact:* A departed employee still has working credentials and access to Operations data and supplier contracts.
>
> *Already tried:* HR completed the leaver form. Reception has the laptop.

#### Symptoms to notice

- Last sign-in Today 07:51 from home broadband, after employment ended. Treat this as urgent, not routine.
- Sessions shows two: web mail and a mobile mail app on a personal phone.
- HR’s form says don’t forward and don’t delete, and asks for 2-year retention.
- The mailbox is still a user mailbox, so removing the Office licence first would start a 30-day deletion.

#### Diagnosis

Offboarding comes down to cutting access first, keeping data, then reclaiming resources, all to HR’s written instructions rather than habit. Directory shows Marcus signed in after he left, so the first moves are disable plus session revoke: disabling stops new sign-ins, but existing web and mobile sessions keep working until revoked. The leaver record is the authority: convert to shared (which needs no licence) so Jordan can work the supplier mail, set an auto-reply, and don’t forward, because forwarding hides the mail trail and is against the form. The trap is the order of operations: a user mailbox without an Office licence goes into 30-day deletion, so convert before you reclaim. Deleting the account destroys retained data. Finish by returning the laptop so it gets wiped and reissued, then verify both sides: the leaver is blocked and the manager has access.

#### Perfect steps

1. Open INC-1061 and select Assign to me.
2. Open Tools › Directory › Leavers › Marcus Hale (HR-LVR-0088) and read the HR instructions.
3. Select Open account. On Authentication read the sign-in log: web mail at 07:51 today from home broadband.
4. Select Disable account and confirm.
5. Open the Sessions tab and select Revoke all sessions. Both sessions disappear.
6. Open Groups and select Remove beside Operations-Share. Domain Users stays.
7. Open Tools › Mail Admin › Mailboxes, choose Marcus’s mailbox and select Convert to shared, then Convert.
8. Under Permissions choose Jordan Price, Full Access, expiry “90 days (Jan 10)”, and select Grant. Don’t add Send As.
9. Under Automatic replies choose On, paste HR’s text and select Save. Leave Forwarding empty.
10. Back in Directory › Marcus Hale › Licences, select Remove on Office Suite (Standard), Endpoint Protection and Design Studio. No deletion warning appears because the mailbox is shared.
11. Open Tools › Asset Management, search “NS-OPS-024”, Open › Health › Return to shelf, and confirm. It becomes Returned · Pending wipe with no owner.
12. In Directory › Marcus Hale › Authentication select Test sign-in. “Sign-in test failed: the account is disabled” is the expected result for a leaver.
13. In Mail Admin › Marcus’s mailbox › Test access as…, choose Jordan Price and select Test access. Expect “jprice can open …”.
14. Select Check fix, write a resolution note and select Close ticket.

#### Verify

- Authentication: Disabled, no active sessions, sign-in test failed (blocked as expected).
- Groups: Domain Users only.
- Mailbox: Type Shared, Jordan Price Full Access, automatic replies On, Forwarding None, no deletion warning.
- Licences: none; Licence pools gain the seats back.
- Asset Management: NS-OPS-024 Returned · Pending wipe, unassigned.

#### Required outcome (what Check fix tests)

- Account disabled
- Active web and mobile sessions revoked
- Removed from Operations-Share
- Mailbox converted to shared, Jordan has Full Access, auto-reply on, no forwarding
- Licences reclaimed and the account kept for retention
- Laptop NS-OPS-024 returned to IT for wiping
- Verified: Marcus can’t sign in and Jordan can open the mailbox

#### Common mistakes

- Disabling without revoking sessions, so the leaver keeps reading mail on a phone.
- Deleting the account for tidiness and destroying retained mail.
- Removing licences first and starting a 30-day mailbox deletion.
- Forwarding everything to the manager instead of shared access, against HR’s instruction.
- Forgetting the laptop, which then sits unwiped in a drawer.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Deleted the account and mailbox: HR-LVR-0088 requires 2-year retention and Jordan loses the supplier mail | −6 |

Closing it unresolved costs −15. Escalating it to Security costs −8.

#### Hint ladder

1. Read leaver record HR-LVR-0088 in full: it says what happens to the mailbox, the laptop and the account. Then check Marcus’s sign-in log. When did he last sign in?
2. Order matters. Cut access first (disable and revoke sessions), then convert the mailbox to shared before you remove licences.
3. Disable, revoke sessions, remove Operations-Share. In Mail Admin convert to shared, grant Jordan Full Access and set the auto-reply. Remove the licences, return NS-OPS-024 to the shelf, then run Test sign-in and Test access as Jordan.

#### Model answer

Actioned leaver HR-LVR-0088 for Marcus Hale. He had an active web mail session from home at 07:51 today, after his leaving date, so I disabled the account and revoked both web and mobile sessions first. Removed Operations-Share. Converted the mailbox to shared, granted Jordan Price Full Access for 90 days and set HR’s auto-reply, with no forwarding. Removed the Office, Endpoint and Design licences only after the conversion, so the mailbox is kept, and kept the account for the 2-year retention. Returned laptop NS-OPS-024 (NSA-1024) to the shelf for wiping. Verified the sign-in test is blocked and Jordan can open the shared mailbox.

#### Ideal resolution note

> Leaver HR-LVR-0088 Marcus Hale (Ops). He signed in to web mail at 07:51 today after his Oct 9 leaving date, so I disabled the account and revoked 2 sessions (web mail, mobile mail app). Removed Operations-Share. Mailbox converted to shared, Full Access for Jordan Price (90 days), HR auto-reply on, no forwarding per HR. Licences removed after conversion and returned to the pools. Account kept for the 2-year policy, not deleted. NS-OPS-024 returned to the shelf, pending wipe. Verified: sign-in blocked; Jordan can open the shared mailbox.

Earns +3 of 3 for notes. Keywords: `mhale`, `marcus`, `hr-lvr-0088`, `shared mailbox`, `revoke`, `ns-ops-024`.

#### In the real world

Sign-ins after someone has left are a classic insider-risk signal and a common audit finding. In most cloud suites the sequence is block sign-in, revoke sessions, convert to shared, then remove licences. Shared mailboxes under the size limit need no licence. Keep the disabled account for as long as the retention policy requires.

<a id="inc-1062"></a>

### INC-1062 · Voicemail: lost phone, can’t approve sign-ins

**Priority:** High (22 points) · **Category:** Security / MFA reset · **Arrives:** as a voicemail (log it as a ticket first) · **Finish with:** Close ticket · **Best score:** +25

**Tools:** Directory, Asset Management, Company Chat, Voicemails  
**Runbooks:** [Verifying a caller’s identity](#kb14), [Lost phone and MFA reset](#kb23), [Logging chat messages and voicemails as tickets](#kb35)

**The ticket**

> I lost my phone on the tram last night, so the authenticator app’s gone and I can’t get into anything that asks for approval. Can someone reset my MFA? Call me back on 555-0418. It’s my partner’s phone, mine’s gone.
>
> *Business impact:* An operations lead can’t reach MFA-protected apps. A lost company phone may still have mail synced on it.
>
> *Already tried:* Tried signing in on the web and got stuck at the approval prompt.

#### Symptoms to notice

- A voicemail is not proof of identity. Anyone can say “it’s Jordan”.
- The callback number in the message (555-0418) differs from the mobile on record. The caller explains why, but you still can’t trust it.
- The registered phone is the lost device, so a code sent to it proves nothing and reaches no one.
- A company phone is lost with an active mail session: that is a data exposure, separate from the access problem.

#### Diagnosis

An MFA reset removes a security factor, so it is one of the riskiest service-desk actions and a favourite target of social engineers. The request came through an unauthenticated channel (voicemail) with a new callback number, which is exactly the pattern attackers use. It sounds plausible, and that is the point: plausible is not verified. Directory › Profile lists his mobile and his desk extension x3520. The only trusted channels are ones already on record before the request. The mobile is lost, so the desk extension is the right callback (his manager can’t vouch today). Once identity is confirmed, reset MFA so Jordan re-enrols, and separately contain the lost device: mark it Lost/Stolen and revoke its session so mail stops syncing to a phone on a tram. Verify with Jordan’s own confirmation after he re-enrols.

#### Perfect steps

1. Open Voicemails and read the 07:38 message from Jordan Price. Select Log as ticket, then Save to INC-1062 so the transcript is on the ticket.
2. Open INC-1062 and select Assign to me.
3. Open Tools › Directory, search “jordan”, select Jordan Price. On Profile note the Mobile, Ext. 3520 and Employee ID. The voicemail number doesn’t match.
4. Select Verify identity…, choose “Callback to number on record” and select Run check. The flash confirms Jordan quoted his employee ID.
5. On Authentication select Reset MFA… and confirm.
6. Open Sessions and select Revoke beside NSM-0098 (Pixelon 7a) · Mobile mail app.
7. Open Tools › Asset Management › Mobiles and set the state of NSM-0098 to Lost/Stolen. Optional: Queue remote wipe.
8. Open Company Chat › Jordan Price and select “INC-1062 · Ask to confirm the fix”. Jordan re-enrols and confirms he can sign in.
9. Select Check fix, write a resolution note (include the verification method) and select Close ticket.

#### Verify

- Directory › Authentication: Identity check “Callback to number on record”, MFA Enrolled again after Jordan’s confirmation.
- Sessions: no session from NSM-0098.
- Asset Management › Mobiles: NSM-0098 is Lost/Stolen.
- Company Chat shows Jordan’s confirmation, and the notes record how he was verified.

#### Required outcome (what Check fix tests)

- Identity verified by calling back a number on record
- MFA reset after verification
- Lost phone NSM-0098 marked Lost/Stolen and its session revoked
- Jordan re-enrolled MFA and confirmed he can sign in

#### Common mistakes

- Calling the number from the voicemail and treating whoever answers as verified.
- Resetting MFA first and planning to verify later.
- Sending a code to the lost phone and waiting.
- Fixing access but forgetting that the lost phone still syncs company mail.
- Not recording which verification method was used.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Removed a security factor for a caller who wasn’t verified through a number on record | −5 |

Closing it unresolved costs −15. Escalating it to Security costs −8.

#### Hint ladder

1. A voicemail proves nothing about who called. Compare the callback number with Jordan’s record in Directory before you change his account.
2. A code to the registered phone can’t work: that phone is lost. Use a callback to a number that was already on his record.
3. Verify identity… › Callback to number on record (his desk extension). Then Reset MFA…, set phone NSM-0098 to Lost/Stolen, revoke its session, and ask Jordan in Company Chat to re-enrol and confirm.

#### Model answer

Received a voicemail asking for an MFA reset from an off-record number (555-0418) and didn’t call it. Called Jordan on his desk extension on record (x3520); he gave employee ID E35201, which matches Directory. After verifying, reset his MFA, marked company phone NSM-0098 Lost/Stolen and revoked its mail session. Jordan re-enrolled the authenticator on his replacement phone and confirmed in Company Chat that he can sign in.

#### Ideal resolution note

> Voicemail 07:38 asked for an MFA reset and gave callback 555-0418, which is NOT on record; I didn’t use it. Verified Jordan by calling his desk extension x3520 on record; he gave employee ID E35201, which matches Directory. Then reset MFA. Lost company phone NSM-0098 marked Lost/Stolen and its mail session revoked. Jordan re-enrolled on his replacement phone and confirmed sign-in in chat. Voicemail saved to the ticket.

Earns +3 of 3 for notes. Keywords: `jprice`, `jordan`, `callback`, `nsm-0098`, `mfa`, `e35201`.

#### In the real world

Help-desk MFA resets after a phone call were the way in for several well-known breaches: attackers research the target, then phone the service desk claiming a lost phone. Mature desks require verification through a channel already on record (a call back to a known number, manager confirmation, in-person ID or a video check) and log the method on the ticket.

<a id="inc-1063"></a>

### INC-1063 · Back from parental leave: account disabled

**Priority:** Medium (15 points) · **Category:** Access / Return from leave · **Arrives:** as a Company Chat message (log it as a ticket first) · **Finish with:** Close ticket · **Best score:** +18

**Tools:** Directory, Remote Desktop  
**Runbooks:** [Resetting a password safely](#kb2), [Verifying a caller’s identity](#kb14), [Returning from long leave](#kb24), [Licence pools: assigning and reclaiming seats](#kb33), [Logging chat messages and voicemails as tickets](#kb35)

**The ticket**

> (Company Chat, from Maya Chen’s account) “Hi IT, it’s Leah Fontaine, I’m borrowing Maya’s PC. First day back from parental leave and my laptop says ‘Your account has been disabled’. I’m at my old desk on Floor 2 and my desk phone works. Could you help me get back in today? I have month-end reconciliations waiting.”
>
> *Business impact:* One returning Finance analyst is fully blocked during month-end.
>
> *Already tried:* Tried her password on her laptop and on webmail. Same message both times.

#### Symptoms to notice

- The sender in Company Chat is Maya Chen, not Leah. The person typing is unconfirmed.
- Directory › Leah Fontaine shows an HR note: disabled by the leave workflow LOA-0193, return date today, Office licence released.
- Authentication shows three problems: Disabled, password Expired, and no Office Suite licence.
- Licence pools › Office Suite (Standard) shows 0 free (unless Marcus Hale’s seat from INC-1061 has already gone back to the pool), and one holder is a disabled leaver from July.

#### Diagnosis

The visible symptom (disabled) is only the first of three layers the leave workflow left behind. Fix only the obvious one and the next appears: enable, and sign-in fails on the expired password; fix that, and Excel opens unlicensed. Before touching anything, deal with the channel. A chat from someone else’s account is a classic pretext, so verify Leah through something on her own record: her desk extension works because she says she’s at her desk, and her registered mobile works for a code. The HR leave record authorises re-enabling, so no extra approval is needed. For the licence, the pool is exhausted. Reclaim a seat from a disabled leaver (Tara Morgan, last sign-in Jul 31, mailbox already shared), never from an active colleague. Verify end to end: a sign-in test, then Office reports licensed on her laptop.

#### Perfect steps

1. Open the chat from Maya Chen (dashboard › Incoming contacts › Open chat) and select Log as INC-1063. Optionally reply that you’ll call Leah on her desk line.
2. Open INC-1063 and select Assign to me.
3. Open Tools › Directory, search “leah” and select Leah Fontaine. Read the HR note on Profile, then on Authentication note Disabled, password Expired and the Blocked sign-in at 09:19.
4. Select Verify identity…, choose “Callback to number on record” and select Run check. Leah answers x4418 and quotes E44181.
5. On Authentication select Enable account.
6. Select Reset password…, keep “User must change password at next sign-in” ticked, choose “Read to user on a verified call” and select Reset password.
7. Open the Licences tab: Office Suite (Standard) shows 0 free and Assign is greyed out. Select View licence pools. (If you already released Marcus Hale’s seat in INC-1061, one seat is free and Assign works straight away: you can skip the next step.)
8. In Licence pools › Office Suite (Standard), find Tara Morgan · Disabled · last sign-in Jul 31 and select Remove.
9. Back in Users › Leah Fontaine › Licences, select Assign on Office Suite (Standard).
10. On Authentication select Test sign-in. Expect “Sign-in test passed for lfontaine. They’ll be asked to choose a new password.”
11. Open Tools › Remote Desktop, connect to NS-FIN-027, open Office Suite and select Refresh licence. Expect “Product activated”.
12. Select Check fix, write the note and select Close ticket.

#### Verify

- Directory › Leah Fontaine › Authentication: Enabled, password Current with Must change, sent via “Read to user on a verified call”, identity check Callback to number on record, last sign-in test Passed.
- Licence pools › Office Suite (Standard): Leah is a holder, Tara Morgan isn’t, and every holder still listed is who it was before.
- Remote Desktop › NS-FIN-027 › Office Suite shows Licensed.

#### Required outcome (what Check fix tests)

- Leah verified through a channel on her own record
- Account re-enabled
- Expired password reset, must change at next sign-in, read to Leah on the verified call
- Office Suite seat reclaimed from a leaver and assigned to Leah
- Sign-in test passed and Office shows as licensed on NS-FIN-027

#### Common mistakes

- Trusting the chat because it came from a real internal account. It was the wrong person’s account.
- Fixing “disabled”, closing, and getting a reopen an hour later about the password or Excel.
- Freeing a seat by taking it from an active colleague.
- Creating a new account instead of restoring the old one.
- Sending the temporary password into Maya’s chat or to her manager.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Re-enabled an account on a request from Maya’s chat without confirming who was typing | −3 |
| Reset a password on a request from Maya’s chat without confirming who was typing | −3 |
| Sent Leah’s temporary password somewhere other than the verified call, where Maya or someone else could read it | −2 |
| Took Office Suite from an active colleague: they just lost Word, Excel and Outlook mid-day | −3 |
| Created a second identity: a new account has none of Leah’s mailbox, files or Finance history | −3 |

Closing it unresolved costs −10. Escalating it to Security costs −8.

#### Hint ladder

1. The chat came from Maya’s account. Who are you actually talking to? Then read the HR note on Leah’s Directory record: more than one thing changed while she was away.
2. Verify Leah through her own record (desk extension x4418 or her registered mobile). Then check Licences: if the Office pool is full, look for a seat held by someone who has left.
3. Verify identity… (callback to number on record), Enable account, Reset password… (must change, read to user on the verified call), remove Office Suite from leaver tmorgan in Licence pools and assign it to Leah, Test sign-in, then Remote Desktop › NS-FIN-027 › Office Suite › Refresh licence.

#### Model answer

The request arrived through Maya Chen’s chat account, so I verified Leah by calling her desk extension on record (x4418); she confirmed employee ID E44181. The parental-leave workflow (LOA-0193, return date today) had disabled her account, her password had expired during leave, and her Office licence had been released. Re-enabled the account and read a temporary password to her on the verified call, set to change at next sign-in. The Office Suite pool was full, so I reclaimed the seat still held by leaver Tara Morgan (left Jul 31) and assigned it to Leah. The sign-in test passed and Office shows as licensed on NS-FIN-027 after a licence refresh.

#### Ideal resolution note

> Leah Fontaine back from parental leave (LOA-0193, return today). Request came via Maya Chen’s chat, so I verified Leah by calling her desk x4418 on record (employee ID E44181 matched). Three issues: disabled by the leave workflow, password expired, Office licence released. Re-enabled; temporary password read on the verified call, must change at next sign-in. Office pool at 0 free, so I reclaimed the seat from leaver tmorgan (disabled since Jul 31) and assigned it to Leah. Sign-in test passed; Office licensed on NS-FIN-027 after a refresh.

Earns +3 of 3 for notes. Keywords: `lfontaine`, `leah`, `loa-0193`, `tmorgan`, `callback`, `e44181`.

#### In the real world

Leave workflows often disable accounts and release licences to save cost, and returners then hit several failures in a row. A good technician checks every layer before calling back. Reclaiming licences from leavers is routine cost control, and a pool full of disabled holders is a common audit finding.

<a id="inc-1065"></a>

### INC-1065 · Voicemail: urgent password reset for the Chief of Staff

**Priority:** Critical (30 points) · **Category:** Security / Social engineering · **Arrives:** as a voicemail (log it as a ticket first) · **Finish with:** Escalate to Security · **Best score:** +42

**Tools:** Directory, Company Chat, Voicemails  
**Runbooks:** [Verifying a caller’s identity](#kb14), [Urgent requests to send devices or passwords somewhere new](#kb21), [Escalating to Security with evidence](#kb34), [Logging chat messages and voicemails as tickets](#kb35)

**The ticket**

> Voicemail 07:52: “Hi, it’s Callum, Avery Wilson’s new EA. Avery’s stuck at the airport and locked out, and she’s got the board call at ten. Can you reset her password and text it to me on 555-0193, and switch off the phone approval thing for today? She’s really not happy. I’ll be waiting.”
>
> *Business impact:* If acted on, an attacker could take over an executive account that holds board materials. The pressure and urgency point to social engineering.
>
> *Already tried:* The caller says Avery tried her password “a few times”.

#### Symptoms to notice

- Urgency and authority pressure: an executive, a board call at ten, “she’s really not happy”.
- The caller asks for two things no process allows: a password sent to a third party’s phone, and MFA switched off.
- The callback number isn’t on any record, and nobody called Callum is in Directory.
- The account contradicts the story: not locked, and signed in on-site at 08:40.

#### Diagnosis

Nothing is wrong with Avery’s account. The incident is the call itself. Every element matches a classic help-desk vishing pretext: a high-value target, an intermediary who can’t be verified, time pressure, and requests to send credentials to a new channel and weaken MFA. Directory disproves the story: Avery isn’t locked, last signed in from her office workstation this morning, and has no assistant listed. Even if the story were true, the answer would be the same: credentials only go to the account holder through a verified channel. Confirm with the real person through a channel you already trust (Company Chat shows her online on NS-EXEC-001), change nothing, keep the evidence (recording and number), and hand it to Security, who can check whether other staff were targeted.

#### Perfect steps

1. Open Voicemails and read the 07:52 message. Select Log as ticket. Don’t delete it.
2. Open INC-1065 and select Assign to me.
3. Open Tools › Directory, search “avery” and select Avery Wilson. On Profile note Assistant: — and Mobile +1 555-0110, which doesn’t match the caller’s number.
4. On Authentication note Lockout: Not locked and Last sign-in: Today 08:40 · NS-EXEC-001. Don’t select Reset password… or Reset MFA….
5. Search Directory for “callum”: no accounts match.
6. Open Company Chat › Avery Wilson (Online) and select “INC-1065 · Ask Avery to verify the voicemail request”. She is at her desk, has no assistant called Callum and didn’t ask for this.
7. Back in Voicemails, select Save to INC-1065, then Forward to Security on the 07:52 message.
8. Select Escalate to Security and write the evidence: caller name and number, time, what was asked for, the Directory facts and Avery’s denial. Don’t close it.

#### Verify

- Directory › Avery Wilson › Authentication shows no password reset today and MFA Enrolled.
- The voicemail shows “Saved to ticket” and “Forwarded to Security”, and it isn’t deleted.
- Avery’s denial is in Company Chat.
- The ticket is Escalated, and the notes include +1 555-0193.

#### Required outcome (what Check fix tests)

- Request checked with the real Avery through Company Chat
- Avery’s password and MFA left untouched
- Voicemail saved to the ticket and forwarded to Security
- Escalated to Security

#### Common mistakes

- Resetting “just to be safe” without sending the password. It still disrupts the executive and shows the attacker the desk will act on a call.
- Calling the attacker’s number to verify.
- Deleting the voicemail as obvious spam, which destroys the evidence Security needs.
- Refusing and closing quietly. Security should know, because these campaigns usually target several people.
- Sending Avery a verification code, which looks like the MFA-fatigue prompts attackers use.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Reset an executive’s password for an unverified caller: Avery is on-site and signed in at 08:40 | −6 |
| Removed MFA from an executive account on a caller’s word | −6 |
| Deleted the voicemail: Security needs the number and the recording | −3 |

Closing it unresolved costs −20.

#### Hint ladder

1. Before you touch Avery’s account, look at it. Is she actually locked out? Where did she last sign in? Does she have an assistant on record?
2. Contact Avery through a channel you already trust (Company Chat, where she’s online), not the number in the message.
3. Ask Avery in Company Chat, save the voicemail to the ticket and forward it to Security, then escalate with the caller’s number and claims in your notes. Don’t reset anything.

#### Model answer

An unverified caller (“Callum”, +1 555-0193) left a voicemail asking for Avery Wilson’s password to be reset and texted to him, and for MFA to be switched off. Directory shows Avery isn’t locked, signed in on-site at 08:40 today on NS-EXEC-001, and has no assistant on record; nobody called Callum is in Directory. Avery confirmed in Company Chat that she is at her desk, has no EA called Callum and made no request. Made no changes to her account. Saved the voicemail to the ticket, forwarded it to Security and escalated as a suspected social-engineering attempt.

#### Ideal resolution note

> Suspected social engineering. Voicemail 07:52 from “Callum, Avery’s new EA” (+1 555-0193) asked to reset Avery Wilson’s password, text it to him, and disable MFA before a 10:00 board call. Evidence: Avery not locked; last sign-in today 08:40 on NS-EXEC-001 (on-site); no assistant on record; no “Callum” in Directory. Avery confirmed in Company Chat she is at her desk, has no EA called Callum and made no request. No changes to her account. Voicemail saved to the ticket and forwarded to Security. Escalated to Security for investigation and a staff alert.

Earns +3 of 3 for notes. Keywords: `awilson`, `avery`, `555-0193`, `callum`, `vishing`, `social engineering`.

#### In the real world

Phone-based social engineering of service desks, often against executives and their “assistants”, has led to major breaches. Typical demands are a password reset to a new number and MFA re-registration. Mature service desks never send credentials to anyone but the verified account holder, verify executive requests through a known channel, and report every attempt to Security.

<a id="inc-1066"></a>

### INC-1066 · Intranet and shared drives “can’t be found” for everyone

**Priority:** Critical (30 points) · **Category:** Network / Name resolution · **Arrives:** at the start of shift 3 · **Finish with:** Close ticket · **Best score:** +33

**Tools:** Server Room, Remote Desktop  
**Runbooks:** [DNS outage: names fail, IP addresses work](#kb15)

**The ticket**

> Since about quarter to nine nobody on floors 1 and 2 can open the intranet or any mapped drive. The browser says the site can’t be reached and File Explorer says the network path wasn’t found. Wi-Fi shows connected and the desk phones are fine.
>
> *Business impact:* Office-wide loss of the intranet, mapped drives and web browsing. People already signed in stay signed in, but nobody can reach anything by name.
>
> *Already tried:* Users restarted PCs and reconnected Wi-Fi. One person tried a different browser.

#### Symptoms to notice

- Everything that fails is reached by a name (intranet address, \\\\FILE01 paths, websites).
- Wi-Fi shows connected, which means the link and the IP address are fine.
- Several floors are affected at once, so this is a shared service, not one PC.
- Desk phones still work. They don’t depend on the same name lookups.

#### Diagnosis

First split connectivity from name resolution. If ping 10.0.0.20 replies but ping file01 says “could not find host”, routing, switching and the server are fine and only the name-to-address step is failing. nslookup shows which DNS server the client asks (dc01.northstar.local) and that it times out. Pointing the same query at DC02 (nslookup file01 10.0.0.11) gets an answer, which proves the records are fine and DC01’s DNS service is the single failed part. ipconfig /all shows clients only get 10.0.0.10 as their DNS server, which is why the healthy DC02 doesn’t take over. DC01’s event log (7031, service terminated unexpectedly) confirms it. The fix is starting one service; rebooting the domain controller or touching network gear is far bigger than this needs.

#### Perfect steps

1. Open INC-1066 and select Assign to me. It is Critical and affects several floors.
2. Open Tools › Remote Desktop, search “NS-HR-003” and select Connect, then Connect in the dialog.
3. Open Terminal. Run ping 10.0.0.20 and expect 3 replies: the network path is fine.
4. Run ping file01 and expect “could not find host”: the name step is what fails.
5. Run nslookup file01 and expect “Server: dc01.northstar.local” and “DNS request timed out”.
6. Optional: run nslookup file01 10.0.0.11. DC02 answers, so DC01 is the problem. Run ipconfig /all and note that DNS Servers lists only 10.0.0.10.
7. Open Tools › Server Room › Servers and select Services on DC01. DNS Server shows stopped. Select “Event log & scheduled tasks” and read event 7031 at 08:44.
8. Back on the Servers tab, open DC01’s services again and select Start next to DNS Server. Don’t select Reboot.
9. Return to Remote Desktop › NS-HR-003 › Terminal. Run ipconfig /flushdns (the failed ping cached a negative answer), then nslookup intranet.northstar.local. Expect “Address: 10.0.0.40”. This sets the verification requirement.
10. Optional: File Explorer › H: (\\\\FILE01\\HR) opens again.
11. Select Check fix, write the resolution notes and select Close ticket.

#### Verify

- Server Room › DC01 › Services shows DNS Server running.
- nslookup intranet.northstar.local from an office PC returns 10.0.0.40 from dc01.northstar.local.
- ping file01 replies again.
- Both requirements are ticked.

#### Required outcome (what Check fix tests)

- DNS Server service is running on DC01
- Name resolution verified from an office workstation

#### Common mistakes

- Rebooting DC01. It works, but it takes sign-in down for everyone, and rebooting a domain controller is a change-controlled action.
- Rebooting the edge router or firewall because “the internet is down”. Pings to IP addresses prove the network works.
- Closing after starting the service without testing from a client.
- Forgetting ipconfig /flushdns on a PC that cached the failure, then thinking the fix didn’t work.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Rebooted a domain controller when one stopped service needed starting: nobody could sign in for 6 minutes | −4 |
| Stopped DNS on DC02, the last working DNS server | −5 |
| Rebooted the edge router: pings to IP addresses already proved the network works | −4 |
| Powered off the edge router: pings to IP addresses already proved the network works | −4 |
| Rebooted the firewall: pings to IP addresses already proved the network works | −4 |
| Powered off the firewall: pings to IP addresses already proved the network works | −4 |

Closing it unresolved costs −20. Escalating it to Security costs −8.

#### Hint ladder

1. Look at what fails and what still works. Everything that breaks is reached by name. Try reaching a server by its address instead.
2. Remote into an office PC such as NS-HR-003. In Terminal compare ping file01 with ping 10.0.0.20, then run nslookup file01 and note which server it asks.
3. Server Room › Servers › DC01 › Services: start the DNS Server service. Then on the PC run ipconfig /flushdns and nslookup intranet.northstar.local.

#### Model answer

Every working floor lost everything reached by name. From NS-HR-003, ping 10.0.0.20 worked but ping and nslookup by name timed out against DC01 (10.0.0.10), while nslookup against DC02 (10.0.0.11) answered, which isolated the fault to DC01’s DNS service. DC01’s event log showed the DNS Server service terminated unexpectedly at 08:44 (event 7031). Started the DNS Server service on DC01 with no reboot, flushed the PC’s negative cache, and confirmed nslookup intranet.northstar.local returns 10.0.0.40. Follow-up for Infrastructure: clients only get DC01 as their DNS server, so add DC02 as a secondary.

#### Ideal resolution note

> Scope: floors 1–2 couldn’t reach anything by name. From NS-HR-003, ping 10.0.0.20 worked but ping file01 failed and nslookup timed out against 10.0.0.10 (DC01); nslookup against DC02 (10.0.0.11) answered. DC01 event 7031 at 08:44: DNS Server service terminated unexpectedly. Fix: started DNS Server on DC01 (no reboot). Verified: after ipconfig /flushdns, nslookup intranet.northstar.local returns 10.0.0.40 and ping file01 replies. Follow-up: clients only get 10.0.0.10 for DNS; recommend adding 10.0.0.11 as secondary and a problem record for the crash.

Earns +3 of 3 for notes. Keywords: `dc01`, `dns server`, `7031`, `nslookup`, `10.0.0.10`, `flushdns`.

#### In the real world

“IP addresses work, names don’t” is the classic sign of a DNS failure. In real directory environments, always hand out at least two DNS servers through DHCP (both domain controllers). With a single DNS server, one service crash becomes a site-wide outage. After restoring service, find out why it crashed (event logs, recent patches, disk space) and raise a problem record.

<a id="inc-1068"></a>

### INC-1068 · Websites and card machines down, but shared drives still open

**Priority:** Critical (30 points) · **Category:** Network / ISP · **Arrives:** as a voicemail (log it as a ticket first) · **Finish with:** Close ticket · **Best score:** +33

**Tools:** Server Room, Remote Desktop, Company Chat, Voicemails  
**Runbooks:** [Internet down, internal services fine](#kb26), [Logging chat messages and voicemails as tickets](#kb35)

**The ticket**

> Voicemail, 11:10: “Hi IT, it’s Rosa on reception. Visitors and half the office keep coming to the desk saying websites won’t load, and the café card reader can’t connect either. The shared drives still seem fine. I’ve got a client video call at half eleven. Could someone call me back on 3010? Thanks.”
>
> *Business impact:* Office-wide loss of internet access, external email and card payments. Internal services (drives, intranet, printing) still work.
>
> *Already tried:* Reception restarted the café card reader and her own PC.

#### Symptoms to notice

- Shared drives and the intranet work, so the LAN, DNS and servers are healthy.
- Anything that leaves the building (websites, the card reader, external mail) fails.
- Several unrelated device types fail together, which points to a shared upstream dependency.
- The caller asked for a callback. Communication is part of the fix.

#### Diagnosis

Separate inside from outside. If internal addresses and names work but every external destination fails, the break is at or beyond the edge. tracert makes it visible: the floor switch, firewall (10.0.0.254) and edge router (10.0.0.1) answer, then the MetroFiber hop times out. Our own devices are up and forwarding, so restarting them only adds an internal outage to an external one. Server Room shows the ISP circuit down, and the provider’s status page confirms an area incident. We can’t fix it ourselves. What we own is getting our circuit attached to the provider’s incident (a fault reference), telling staff what works and when they’ll hear next, then verifying and announcing recovery.

#### Perfect steps

1. Open Voicemails, read Rosa’s message and select Log as ticket. Open INC-1068 and select Assign to me.
2. Open Tools › Remote Desktop, connect to NS-HR-003 and open Terminal. ping 10.0.0.1 and ping file01 reply: internal is fine.
3. Run ping web.example (100% loss) and tracert web.example. It passes the floor switch, fw01 and edge01, then times out at the MetroFiber hop.
4. Open Tools › Server Room › Overview: the ISP · MetroFiber tile shows Down; the edge router and firewall are online.
5. Open the Topology tab and select MetroFiber ISP. Select Check provider status and read incident MF-INC-5821 (fibre damage, next update 11:45).
6. Leave the circuit list on MF-PRI-88213 (not the backup) and select Log fault with provider. Note the fault reference.
7. Open Company Chat › office-announcements and select Full status update. Don’t post “Ask everyone to restart”.
8. Optional: message Rosa Lindqvist in Company Chat with the reference and suggest a mobile hotspot for her 11:30 call.
9. Back in Server Room › Topology › MetroFiber ISP, select Check provider status again. The circuit is back online.
10. In Remote Desktop › NS-HR-003 › Terminal run ping web.example and expect replies. This sets the verification requirement.
11. Optional: post Resolved in #office-announcements. Select Check fix, write notes with the provider references and select Close ticket.

#### Verify

- Server Room › Overview: the ISP tile shows Online with latency.
- ping web.example from an office PC gets replies.
- #office-announcements has a full status update posted during the outage.
- All four requirements are ticked.

#### Required outcome (what Check fix tests)

- Provider status checked
- Fault logged with MetroFiber against circuit MF-PRI-88213
- Full status update posted to #office-announcements
- Internet restored and verified from an office PC

#### Common mistakes

- Rebooting the edge router or firewall “just in case”, which knocks out the internal services that still work.
- Sending vague updates (“looking into it”) with no workaround or next-update time, so people keep calling.
- Telling users to restart devices, which is wasted effort during a provider outage.
- Closing the ticket when the fault is logged rather than when service is verified.
- Not recording the provider references, which you need for SLA credits and the post-incident review.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Rebooted the edge router during a provider outage: the internal network that still worked dropped too | −4 |
| Powered off the edge router during a provider outage | −4 |
| Rebooted the firewall during a provider outage: the internal network that still worked dropped too | −4 |
| Powered off the firewall during a provider outage | −4 |
| Told all staff to restart their PCs and routers during a provider outage, which fixes nothing and floods the desk | −2 |

Closing it unresolved costs −20. Escalating it to Security costs −8.

#### Hint ladder

1. Internal things still work and only outside things fail. Find where inside stops and outside starts.
2. From any office PC, ping 10.0.0.1, then ping web.example and run tracert web.example. Then look at the ISP tile in Server Room › Overview.
3. Server Room › Topology › MetroFiber ISP: Check provider status, Log fault with provider on MF-PRI-88213, post the Full status update in #office-announcements, check the provider again, then ping web.example from an office PC.

#### Model answer

Internal services were fine: from NS-HR-003 the gateway and FILE01 replied, but external hosts timed out and tracert died at the MetroFiber hop after our edge router. Server Room showed the MetroFiber circuit down, and the provider status page listed major incident MF-INC-5821 (fibre damage at the Riverside exchange). Logged a fault against circuit MF-PRI-88213, posted a full status update to all staff (impact, workaround, next update) and called Rosa back on 3010. The provider restored the circuit; verified with ping web.example from an office PC and posted the all-clear.

#### Ideal resolution note

> Internal OK (gateway, FILE01, intranet). External failed and tracert web.example stopped at the MetroFiber hop after edge01. Edge and firewall online. Server Room showed circuit MF-PRI-88213 down; provider status page listed major incident MF-INC-5821 (Riverside exchange fibre damage). Logged a fault against MF-PRI-88213. Posted a full status update to #office-announcements and called Rosa back on 3010. Provider restored the circuit; verified with ping web.example from NS-HR-003 and posted the all-clear. Suggest a problem record for a backup circuit.

Earns +3 of 3 for notes. Keywords: `metrofiber`, `mf-pri-88213`, `mf-inc-5821`, `tracert`, `status update`, `provider`.

#### In the real world

For an ISP outage, the service desk’s job is triage, vendor engagement and communication. Keep circuit IDs, provider contacts and SLA terms in the runbook. Good updates say what’s affected, what still works, what to do instead and when the next update is. If the business can’t tolerate this, raise a problem record for a second, diverse circuit or a mobile failover.

<a id="inc-1069"></a>

### INC-1069 · “Not enough space” when saving to any shared drive

**Priority:** High (22 points) · **Category:** Server / Storage · **Arrives:** at the start of shift 3 · **Finish with:** Close ticket · **Best score:** +25

**Tools:** Server Room, Remote Desktop  
**Runbooks:** [File server volume full](#kb27)

**The ticket**

> Since this morning people in Finance, HR and Operations get “There is not enough space on the disk” when they save anything to the shared drives. Opening files is fine, and saving to the desktop works.
>
> *Business impact:* Nobody can save to any department share. Month-end Finance work and HR onboarding are blocked.
>
> *Already tried:* Users deleted a few old files from their own folders, which made no difference.

#### Symptoms to notice

- Every department share fails the same way. They all live on one server, FILE01.
- Reading works and writing fails: the classic sign of a full volume.
- The error is about disk space, not permissions, so don’t touch group membership.
- Users deleting their own small files didn’t help, so the big consumer is elsewhere.

#### Diagnosis

The volume is full, but the real question is why it filled up. The folder breakdown shows the business shares are normal sizes while the scanner drop folder (Scans) holds hundreds of GB, almost all older than 30 days. The scheduled task that should purge it has been disabled since a maintenance window: that is the root cause. Shadow copies are another big item, but they are restore points; deleting them trades a little space for your ability to recover files, which the next ticket needs. The safe, targeted action follows the folder’s own retention rule (older than 30 days). Re-enabling the task stops it happening again. Verify by writing a file.

#### Perfect steps

1. Open INC-1069 and select Assign to me.
2. Open Tools › Server Room › Servers and select Services on FILE01: both services are running, so this isn’t a service outage.
3. Open the Storage tab (server FILE01). D: Shares shows a red bar with 1 GB free and no unallocated space.
4. Read the folder list: Scans is by far the biggest, and nearly all of it is older than 30 days. Shadow copies are listed separately.
5. Open Events & tasks and choose FILE01 in the Server list. Read event 2013 at 08:06, and note that “Purge Scans older than 30 days” is Disabled since the Sep 14 maintenance window.
6. Back on Storage, select Purge older than 30 days on the Scans row. Don’t use Delete entire folder or Delete all shadow copies.
7. On Events & tasks, select Enable on “Purge Scans older than 30 days”.
8. On Storage, select Test write on D:. Expect “Test file written to D: and removed”.
9. Optional: Remote Desktop › any office PC › File Explorer › Save a test file on a share.
10. Select Check fix, write notes (cause, action, verification, follow-up) and select Close ticket.

#### Verify

- Storage › D: is about 62% used with a normal bar, and the last test write is OK.
- Shadow copies still lists all three restore points.
- The Scans clean-up task shows Enabled.
- All four requirements are ticked.

#### Required outcome (what Check fix tests)

- FILE01 D: is below 90% used
- Shadow-copy restore points preserved
- Scans clean-up task enabled again
- Test write to D: succeeded

#### Common mistakes

- Deleting all shadow copies because it’s a big, easy number. You lose every restore point and break the next restore request.
- Deleting the whole Scans folder, including today’s unprocessed invoices.
- Rebooting FILE01: it frees nothing and disconnects everyone.
- Freeing space but not re-enabling the task, so the same ticket comes back in a few weeks.
- Asking users to clean their own folders. The problem isn’t user data.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Deleted every file-server restore point to free space | −5 |
| Deleted a whole folder on the file server, including recent files, instead of purging old ones | −3 |
| Rebooted FILE01: everyone lost their open files and no space was freed | −3 |

Closing it unresolved costs −15. Escalating it to Security costs −8.

#### Hint ladder

1. Every share at once means the shared server, not individual folders. Find out what is using the space.
2. Server Room › Storage › FILE01: look at D:’s folder breakdown, then at FILE01’s scheduled tasks under Events & tasks.
3. Purge only Scans files older than 30 days, enable the “Purge Scans older than 30 days” task again, keep the shadow copies, then select Test write on D:.

#### Model answer

Every department share lives on FILE01 D:, which had 1 GB free (event 2013 at 08:06). The folder breakdown showed D:\\Scans had ballooned because its nightly clean-up task was disabled during the Sep 14 maintenance window and never re-enabled. Purged only Scans files older than 30 days, keeping recent scans and every shadow-copy restore point, and re-enabled the clean-up task. D: is now about 62% used and a test write succeeded. Follow-up: an 85% capacity alert and a post-maintenance checklist for re-enabling tasks.

#### Ideal resolution note

> FILE01 D: had 1 GB free (event 2013 08:06), so writes to every share failed. Cause: D:\\Scans had grown because “Purge Scans older than 30 days” was disabled during the Sep 14 maintenance window. Purged Scans files older than 30 days only; recent scans and all shadow-copy restore points kept. Re-enabled the clean-up task. D: now about 62% used. Verified with a test write to D:. Follow-up: 85% capacity alert and a post-maintenance task checklist.

Earns +3 of 3 for notes. Keywords: `file01`, `scans`, `2013`, `purge`, `shadow`, `clean-up task`.

#### In the real world

Monitor volumes with alerts at 80–85%, not at 100%. After any maintenance window, use a checklist to re-enable tasks that were paused. Shadow-copy storage is part of your recovery plan, so cap it with a maximum size instead of deleting it in an emergency, and escalate to Infrastructure if the cleaned volume keeps growing.

<a id="inc-1070"></a>

### INC-1070 · Starters spreadsheet vanished from the HR drive

**Priority:** Medium (15 points) · **Category:** Server / File restore · **Arrives:** after INC-1069 is closed or escalated · **Finish with:** Close ticket · **Best score:** +18

**Tools:** Server Room, Remote Desktop, Company Chat  
**Runbooks:** [Restoring a deleted file from a share](#kb28)

**The ticket**

> I was tidying the H: drive this morning and I think I deleted the October starters spreadsheet by mistake. It’s not in my Recycle Bin. I need the version with yesterday’s changes: I added three new people at about 6pm.
>
> *Business impact:* HR can’t confirm next week’s starters’ equipment and accounts. One file is affected; the rest of the share is fine.
>
> *Already tried:* Checked the Recycle Bin and searched H: for the file name.

#### Symptoms to notice

- The file was on a network drive (H: is \\\\FILE01\\HR), and the Recycle Bin only covers local disks.
- The user gives a timing requirement (edits at about 6pm yesterday). That decides which version is right.
- Only one file is affected. Everything else on the share is current and must stay that way.

#### Diagnosis

First confirm what happened. The audit trail shows a user delete at 09:14, not corruption, ransomware or a permissions change, so a point-in-time restore is the right tool. Choose the version carefully: you want the newest snapshot taken after the last good edit and before the deletion. The Oct 12 07:00 snapshot holds the file as last saved at 18:07 yesterday, which includes the evening changes; the Oct 11 12:00 snapshot predates them. Restore the single item. Reverting the whole share would throw away everyone else’s work since 07:00. Only the requester can confirm the content is right, so close the loop with her.

#### Perfect steps

1. Open INC-1070 and select Assign to me.
2. Open Tools › Server Room › Shadow copies. In File audit, find “Oct 12 09:14 · pshah · Deleted · \\\\FILE01\\HR\\Starters\_October.xlsx”.
3. Set Share to HR and select Starters\_October.xlsx (marked deleted).
4. Compare the versions: sc3 (snapshot Oct 12 07:00) was modified Oct 11 18:07 with 27 starters; sc2 (snapshot Oct 11 12:00) was modified 11:20 with 24.
5. On the sc3 row select Restore to original location. Don’t use Revert entire share.
6. Optional: Remote Desktop › NS-HR-003 › File Explorer › H: lists Starters\_October.xlsx again.
7. Open Company Chat › Priya Shah and select “INC-1070 · Ask to confirm the fix”. She confirms 27 starters, including last night’s three.
8. Select Check fix, write notes with the audit evidence and the version used, and select Close ticket.

#### Verify

- The file shows as restored in Shadow copies, and File Explorer › H: lists it.
- The restore came from sc3 (modified Oct 11 18:07).
- Priya’s chat reply confirms the three evening additions.
- All four requirements are ticked.

#### Required outcome (what Check fix tests)

- Starters\_October.xlsx is back on the HR share
- Restored version includes last night’s changes
- The rest of the HR share left untouched
- Priya confirmed the file is correct

#### Common mistakes

- Picking a version by the snapshot label instead of reading the modified time.
- Reverting the whole share, which silently destroys other people’s work.
- Skipping the audit log and assuming permissions changed.
- Closing without the requester checking the content. Only she knows the three new names.
- Deleting shadow copies in INC-1069, which leaves only the slower nightly backup.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Rolled back the entire HR share to recover one file: everyone’s changes since the snapshot are gone | −6 |

Closing it unresolved costs −10. Escalating it to Security costs −8.

#### Hint ladder

1. Deleting from a network drive skips the Recycle Bin. Look for another copy of the file on the server.
2. Server Room › Shadow copies › File audit shows exactly what was deleted and when. Then open the previous versions of that file on the HR share.
3. Restore only the file, from the version modified Oct 11 18:07 (snapshot Oct 12 07:00), to its original location. Then ask Priya in Company Chat to check it.

#### Model answer

FILE01’s audit log showed pshah deleted \\\\FILE01\\HR\\Starters\_October.xlsx at 09:14 from her PC; network-share deletes don’t go to the Recycle Bin. Priya needed yesterday’s 6pm edits, so I picked the newest snapshot taken before the deletion (sc3, Oct 12 07:00, file modified Oct 11 18:07, 27 rows). I restored only that file to its original location and left the rest of the share alone. Priya confirmed in chat that all 27 starters, including last night’s three, are there.

#### Ideal resolution note

> FILE01 audit: pshah deleted \\\\FILE01\\HR\\Starters\_October.xlsx at 09:14 (network delete, no Recycle Bin). Previous versions: snapshot sc3 (Oct 12 07:00) holds the file modified Oct 11 18:07 (27 rows), which includes the evening edits. Restored that single file to its original location; no share-wide revert, so other HR files are untouched. Verified: Priya confirmed in chat that all 27 starters, including last night’s three, are present.

Earns +3 of 3 for notes. Keywords: `starters_october`, `sc3`, `18:07`, `previous versions`, `audit`, `pshah`.

#### In the real world

Shadow copies (Previous Versions) are the fastest restore for file servers, but they aren’t a backup: they live on the same volume. Keep real backups too, and teach users that deletions on network drives skip the Recycle Bin. When choosing a version, always read the file’s modified time, not just the snapshot label.

<a id="inc-1072"></a>

### INC-1072 · Reported email: “Mailbox storage limit reached, revalidate within 24 hours”

**Priority:** High (22 points) · **Category:** Security / Phishing · **Arrives:** at the start of shift 3 · **Finish with:** Close ticket · **Best score:** +25

**Tools:** Mail Admin, Mail Security, Company Chat  
**Runbooks:** [Reported phishing: analyse, purge, block](#kb16), [Following a message with Message trace](#kb37)

**The ticket**

> I used the Report button on this one. It says it’s from the IT Service Desk and that my mailbox will be suspended unless I revalidate today. The link looks odd, and IT never emails like this. I didn’t click anything. I think Maya got it too.
>
> *Business impact:* A credential-phishing message is sitting in several staff inboxes. One click could compromise an account.
>
> *Already tried:* Reported it with the Report button. Didn’t click the link or reply.

#### Symptoms to notice

- The display name claims to be IT, but the domain is northstar-helpdesk.example, not northstar.example.
- Urgency and threat (“suspended within 24 hours”) are classic pressure tactics.
- The reporter says colleagues got it too, so it’s wider than one mailbox.
- She didn’t click. Confirm with the link-protection data anyway, and check everyone else.

#### Diagnosis

Treat the email as evidence. Read the headers, not the rendered message: SPF fail, no DKIM, an outside Reply-To and a 2-day-old lookalike domain make it phishing beyond doubt. Then size the blast radius: a Message trace for the sender shows 6 recipients. Next decide between containing it and escalating. Link protection shows 0 clicks, so no credentials were entered and this stays a Tier 1 containment task. Report the sample first so Security has the evidence and indicators. Then remove every copy with a recoverable (soft) purge, block the sender to stop follow-up waves, and prove removal with a fresh trace.

#### Perfect steps

1. Open INC-1072 and select Assign to me.
2. Open Tools › Mail Security › Reported messages. On Gemma Whitfield’s report select Analyze. Don’t select Open link.
3. Read the verdict: lookalike domain registered 2 days ago, SPF fail, DKIM none, Reply-To helpdesk.verify@outlook-mail.example, 0 clicks.
4. Open Tools › Mail Admin › Message trace, type “northstar-helpdesk” and select Search: 6 Delivered copies at 09:31–09:32.
5. Back in Mail Security › Reported messages select Report to Security.
6. Select Search & purge…. Scope: “Every copy, all recipients (6 found)”, Mode: “Soft delete (recoverable by admins)”, then Purge. Expect 6 messages removed.
7. Select Block sender on the same row, or on the Blocked senders tab block @northstar-helpdesk.example for the whole domain. Never block northstar.example.
8. In Mail Admin › Message trace, search “northstar-helpdesk” again. All 6 show Purged. This sets the verification requirement.
9. Optional: thank Gemma in Company Chat and remind her to call the desk if she ever does click.
10. Select Check fix, write notes with the indicators (domain, SPF, link, recipients, clicks) and select Close ticket.

#### Verify

- Message trace for the sender shows 6 of 6 Purged.
- Mail Security › Blocked senders lists the northstar-helpdesk.example sender or domain.
- Gemma’s report shows Purged and Sent to Security.
- All five requirements are ticked.

#### Required outcome (what Check fix tests)

- Message headers and link analysed
- Sample reported to Security
- Removed from all 6 inboxes
- Sender blocked
- Removal verified in Message trace

#### Common mistakes

- Opening the link “to see what it does”. Never do this, even from IT.
- Deleting only the reporter’s copy and forgetting the other five recipients.
- Hard-deleting, which leaves Security no recoverable sample.
- Blocking the wrong domain (our own northstar.example).
- Escalating a 0-click campaign that the runbook says Tier 1 contains, or the reverse: not escalating when someone did click.

#### Wrong actions and penalties

| Wrong action | Points |
|---|---|
| Opened a phishing link from an admin workstation | −6 |
| Hard-deleted the phishing copies before Security finished, leaving no recoverable evidence | −3 |
| Blocked the company’s own mail domain | −4 |

Closing it unresolved costs −15. Escalating it to Security costs −8.

#### Hint ladder

1. The display name says IT, but check what the message really is: the sender domain, the authentication results and where the link goes.
2. Mail Security › Reported messages › Analyze. Then run a Message trace for the sender to see who else received it.
3. Report the sample to Security, Search & purge every copy (soft delete), block the sender, then trace the sender again to confirm every copy shows Purged.

#### Model answer

Analysed Gemma’s report without opening the link. The sender domain northstar-helpdesk.example is a 2-day-old lookalike, SPF fails, there’s no DKIM, and the Reply-To is an outside address; the link goes to a fake sign-in page. Message trace showed 6 recipients at 09:31–09:32, all delivered (filter score 4.1). Link protection recorded 0 clicks, so no account compromise is indicated. Submitted the sample to Security, soft-purged all 6 copies, blocked the sender and confirmed in Message trace that every copy shows Purged. Thanked Gemma for reporting it.

#### Ideal resolution note

> User-reported phishing (rp2, gwhitfield). Lookalike sender it-servicedesk@northstar-helpdesk.example (domain 2 days old), SPF fail, no DKIM, Reply-To helpdesk.verify@outlook-mail.example, link to a fake sign-in page. Did not open the link. Trace: 6 recipients 09:31–09:32 (gwhitfield, mchen, pshah, jprice, ebrooks, awilson), filter score 4.1. Link protection: 0 clicks. Reported the sample to Security, soft-purged 6/6, blocked the sender. Verified: trace shows every copy Purged. Thanked Gemma.

Earns +3 of 3 for notes. Keywords: `northstar-helpdesk`, `spf`, `purge`, `0 clicks`, `phishing`, `rp2`.

#### In the real world

The user-reported phishing playbook is: analyse safely (headers and URL reputation, never click), scope it (search by sender, subject and URL), check for clicks or credential entry, preserve and report, purge everywhere, block the indicators, and thank the reporter. Thanking people keeps reporting rates high. If anyone clicked or entered credentials, treat it as a possible compromise: escalate to Security, reset the password, revoke sessions and review inbox rules.

## Runbooks

One runbook per procedure the tickets use. In the game: **Tools › Documentation › Runbooks**.

- [Unlocking a locked account](#kb1) (Identity)
- [Resetting a password safely](#kb2) (Identity)
- [Share access denied: group membership](#kb3) (Identity)
- [Triaging a floor-wide outage](#kb4) (Network)
- [Fixing a broken Wi-Fi profile](#kb5) (Network)
- [Finding and releasing quarantined mail](#kb6) (Email)
- [Mailbox over quota](#kb7) (Email)
- [Suspicious inbox forwarding rules](#kb8) (Security)
- [Print jobs stuck for everyone](#kb9) (Server)
- [VPN profile invalid](#kb10) (Network)
- [Username standard](#kb11) (Identity)
- [Deploying a computer from the PC Shelf](#kb12) (Hardware)
- [Replacing a remote worker’s laptop](#kb13) (Hardware)
- [Verifying a caller’s identity](#kb14) (Identity)
- [DNS outage: names fail, IP addresses work](#kb15) (Server)
- [Reported phishing: analyse, purge, block](#kb16) (Security)
- [Dead PC: swap or repair?](#kb17) (Hardware)
- [Updates fail and the PC is slow (full disk)](#kb18) (Hardware)
- [Second screen shows “No signal”](#kb19) (Hardware)
- [Laptop not charging while plugged in](#kb20) (Hardware)
- [Urgent requests to send devices or passwords somewhere new](#kb21) (Security)
- [Offboarding a leaver](#kb22) (Identity)
- [Lost phone and MFA reset](#kb23) (Identity)
- [Returning from long leave](#kb24) (Identity)
- [Shared mailbox access requests](#kb25) (Email)
- [Internet down, internal services fine](#kb26) (Network)
- [File server volume full](#kb27) (Server)
- [Restoring a deleted file from a share](#kb28) (Server)
- [Approving a new phone for company mail](#kb29) (Email)
- [DHCP scope full (169.254 address)](#kb30) (Network)
- [New starter: account, access and day-one handover](#kb31) (Identity)
- [Name change: display name and email alias](#kb32) (Identity)
- [Licence pools: assigning and reclaiming seats](#kb33) (Identity)
- [Escalating to Security with evidence](#kb34) (Service desk)
- [Logging chat messages and voicemails as tickets](#kb35) (Service desk)
- [Verifying, documenting and closing a ticket](#kb36) (Service desk)
- [Following a message with Message trace](#kb37) (Email)

<a id="kb1"></a>

### Unlocking a locked account

*Identity* · **Tools:** Directory · **Used in:** [INC-1042](#inc-1042), [INC-1043](#inc-1043)

**Purpose.** Restore sign-in for someone whose account locked after too many failed password attempts, without changing anything else on the account.

**Before you start**

- The ticket is assigned to you.
- You can confirm the caller is the account owner (Verify identity…).

**Steps**

1. Open Tools › Directory, search by name, username or email, and select the person.
2. On Authentication read every row: Account, Lockout, Password, MFA, Last sign-in. Locked, disabled, expired and MFA are separate problems with separate fixes.
3. Select Verify identity… and use “Callback to number on record” or “Code to registered mobile”.
4. Select Unlock account. Don’t reset the password unless it has also expired: a reset doesn’t clear a lockout.
5. If Password also reads Expired, continue with “Resetting a password safely”.
6. Select Test sign-in last, after every other change, because each change clears the previous result.

**Verify**

- Lockout reads Not locked and Last sign-in test reads Passed.
- The user confirms in Company Chat that they can sign in.

**Escalate when**

- The account locks again within minutes: a device or script is still using an old password. Ask the identity team to trace the lockout source.
- The sign-in log shows failures from devices or places the user doesn’t recognise: treat it as an attack and escalate to Security.

<a id="kb2"></a>

### Resetting a password safely

*Identity* · **Tools:** Directory · **Used in:** [INC-1043](#inc-1043), [INC-1059](#inc-1059), [INC-1063](#inc-1063)

**Purpose.** Issue a temporary password when a password has expired or been forgotten, so that only the user ends up knowing the new one.

**Before you start**

- The caller is verified: Identity check shows a trusted method (callback to a number on record, or a code to the registered mobile).
- The account is enabled, or HR has confirmed the person is back and you have enabled it.

**Steps**

1. Directory › person › Authentication: confirm Password reads Expired, or that the user has forgotten it.
2. Select Reset password…. If the dialog warns “This caller hasn’t been verified yet”, select Cancel and verify first.
3. Keep “User must change password at next sign-in” ticked.
4. Under “Deliver the temporary password” keep “Read to user on a verified call” unless the ticket’s process says otherwise. A starter whose manager is meeting them can use “Company Chat to their manager” (INC-1059). Never use “Personal email on file”.
5. Select Reset password. If Lockout still reads Locked, select Unlock account too.
6. Select Test sign-in.

**Verify**

- Password reads Current with the chip “Must change at next sign-in”, and the reset line names the delivery route.
- Test sign-in passes with “They’ll be asked to choose a new password.”

**Escalate when**

- You can’t verify the caller through any number or code on record: don’t reset. Ask their manager to raise it, or escalate to Security if the caller pushes.
- Several resets on the same account in one day, or someone requesting a reset on an executive’s behalf: escalate to Security.

<a id="kb3"></a>

### Share access denied: group membership

*Identity* · **Tools:** Directory, Remote Desktop · **Used in:** [INC-1044](#inc-1044), [INC-1053](#inc-1053)

**Purpose.** Give someone access to a shared drive through the group the share trusts, granting no more than their role needs.

**Before you start**

- Sign-in works (Authentication shows Enabled and Not locked).
- You know which group the share needs, and the access matches the person’s role or role template.

**Steps**

1. Directory › person › Groups: compare their groups with the group the share needs (for example Finance-Share for \\\\FILE01\\Finance).
2. Choose the missing group in “Add to group” and select Add. Add only that group.
3. A warning reads “Group changes apply after … signs in again”. Select “Ask user to sign out & back in”.
4. Verify from the user’s PC: Remote Desktop › Connect › File Explorer › Open on the share’s drive letter.

**Verify**

- The warning has gone and File Explorer reads “Opened \\\\FILE01\\…”.

**Escalate when**

- The person needs a group their role doesn’t include: get the data owner’s or manager’s approval in writing first.
- The share fails for everyone in the group: it’s a server problem (see “File server volume full”, or check FILE01’s services).

<a id="kb4"></a>

### Triaging a floor-wide outage

*Network* · **Tools:** Server Room, Remote Desktop · **Used in:** [INC-1045](#inc-1045)

**Purpose.** Find and restore the one shared network device behind an outage that affects a single floor.

**Before you start**

- You know the scope: which floors or groups of people are affected and which still work.

**Steps**

1. Scope first: one user, one floor, or the whole office?
2. Open Tools › Server Room › Overview and read Devices and Device status.
3. Open Topology and follow the path from Internet › MetroFiber ISP › Edge Router › Main Firewall down to the affected floor.
4. If the other floors work, the ISP, edge router and firewall are fine. Don’t reboot or power them off.
5. Select the narrowest failed device (usually that floor’s switch) and select Power on, or Reboot if it’s online but misbehaving.
6. Confirm hosts on that floor are reachable again in Remote Desktop.

**Verify**

- Topology shows every box green and the dashboard reads Floor switches 3/3 online.
- Hosts on the floor show Online in Remote Desktop.

**Escalate when**

- The device won’t come back, or drops again: send it to the network team or Facilities (power, UPS, hardware).
- More than one floor or the core is down: treat it as a major incident and tell the service desk manager.

<a id="kb5"></a>

### Fixing a broken Wi-Fi profile

*Network* · **Tools:** Remote Desktop · **Used in:** [INC-1046](#inc-1046)

**Purpose.** Get one laptop back on the staff Wi-Fi when its saved network profile is corrupt.

**Before you start**

- Other people in the same area are connected, so the access points are healthy.
- The laptop appears in Remote Desktop.

**Steps**

1. Open Tools › Remote Desktop, search the hostname, select Connect and confirm.
2. Open Network & Wi-Fi and read Saved networks. A profile reading “Can’t connect: saved security settings don’t match the network” is broken.
3. Select Forget on that profile.
4. Under Available networks select Connect on Northstar-Staff. Northstar-Guest gives internet only, with no access to company drives.
5. Open Terminal and run ping 10.0.0.1.

**Verify**

- Status reads connected to Northstar-Staff · On the office network.
- ping 10.0.0.1 returns 3 replies.

**Escalate when**

- Several laptops drop at once, or the profile breaks again after a fresh connect: suspect the access points or a driver and pass it to the network team.

<a id="kb6"></a>

### Finding and releasing quarantined mail

*Email* · **Tools:** Mail Admin, Mail Security · **Used in:** [INC-1047](#inc-1047)

**Purpose.** Find an expected message that never arrived, and release it only if it is legitimate.

**Before you start**

- You know the recipient and roughly when the message was sent.

**Steps**

1. Open Tools › Mail Admin › Message trace, type the recipient (for example priya.shah) and select Search.
2. Status Quarantined means the content filter is holding the message. Read the reason under the subject.
3. Open Tools › Mail Security › Quarantine. Check the sender, recipient, subject, reason and score on every row.
4. Select Release only on legitimate business mail the user expects (a low-scoring policy hold from a known supplier).
5. Phishing or malware stays held: select Keep blocked or Report to Security, never Release.
6. Run the Message trace search again.

**Verify**

- The trace shows the message as Delivered (“Released from quarantine and delivered to inbox”).

**Escalate when**

- The user insists on a message scored as phishing: don’t release it; send it to Security.
- The same supplier is held repeatedly: ask Security to review the policy or allow-list the sender.

<a id="kb7"></a>

### Mailbox over quota

*Email* · **Tools:** Mail Admin · **Used in:** [INC-1048](#inc-1048)

**Purpose.** Restore mail delivery to a mailbox that has reached its storage quota, using an approved remedy.

**Before you start**

- Sign-in to webmail works (so it isn’t an identity problem).
- You know the mailbox’s retention policy.

**Steps**

1. Mail Admin › Message trace for the address: bounces read 550 5.2.2 Recipient mailbox full.
2. Open Mail Admin › Mailboxes and choose the mailbox. Read Storage, Delivery and Online archive.
3. Preferred: select Enable online archive. Older items move out and the mailbox drops to under half its size.
4. Alternative for executives: choose “10 GB (approved for executives)” in Quota and select Apply quota. 50 GB is for shared mailboxes only.
5. Under “Send test to” keep the primary address and select Send test message.
6. Tell the user that senders whose mail bounced need to send it again.

**Verify**

- Delivery reads Receiving and “Last test delivered” appears.

**Escalate when**

- The archive is already enabled and the mailbox is still full at 10 GB: raise it with the messaging team rather than deleting mail under retention.

<a id="kb8"></a>

### Suspicious inbox forwarding rules

*Security* · **Tools:** Mail Admin, Directory · **Used in:** [INC-1049](#inc-1049)

**Purpose.** Recognise a forwarding rule that points to a mailbox compromise and preserve it for Security.

**Before you start**

- The ticket mentions disappearing mail, unknown forwarding, or Directory › Mailbox warns that a rule forwards outside the organization.

**Steps**

1. Open Tools › Mail Admin › Inbox rules and choose the mailbox.
2. A rule tagged “Forwards outside org” is a compromise indicator, especially with a hidden name such as “.”.
3. Select View details and note the name, condition, action, target address and Created time and source.
4. Optional: Message trace for the user shows copies forwarded by the rule.
5. Don’t select Delete: the rule is evidence, and deleting it doesn’t remove the attacker’s access.
6. Follow “Escalating to Security with evidence”.

**Verify**

- The rule still exists, inspected, and the ticket is escalated with the details in the evidence box.

**Escalate when**

- Always: any rule forwarding outside the company that the user didn’t create goes to Security.

<a id="kb9"></a>

### Print jobs stuck for everyone

*Server* · **Tools:** Server Room · **Used in:** [INC-1050](#inc-1050)

**Purpose.** Restore office-wide printing when every queue is stuck.

**Before you start**

- The fault affects every printer or model, not a single device.

**Steps**

1. Open Tools › Server Room › Servers. A Degraded print server points to a stopped service.
2. Select Services on PRINT01 and read each service.
3. Optional: select “Event log & scheduled tasks” and read the error (7031 means the service crashed).
4. Select Start next to Print Spooler. Avoid a full server Reboot when one service is down.
5. Select Send test page on the PRINT01 row.

**Verify**

- PRINT01 reads Healthy and the test page prints.
- Dashboard › Service health shows Printing Healthy.

**Escalate when**

- The spooler stops again soon after starting: a bad driver or job is crashing it. Send it to the server team with the event IDs.

<a id="kb10"></a>

### VPN profile invalid

*Network* · **Tools:** Remote Desktop · **Used in:** [INC-1051](#inc-1051)

**Purpose.** Reconnect a remote worker whose VPN client still uses a retired profile.

**Before you start**

- The user’s ordinary internet works.
- Their account can sign in (an expired or locked account fails even with the VPN up).

**Steps**

1. Remote Desktop › Connect to the laptop. The session bar reads “Off-site — VPN not connected”.
2. Open VPN Client. Northstar-Legacy points to a retired gateway.
3. Choose Northstar-Staff in Connection profile, then select Connect.
4. Open File Explorer and Open a mapped drive, or run ping file01 in Terminal.

**Verify**

- VPN Client reads Connected and the drive opens (“Opened \\\\FILE01\\…”).

**Escalate when**

- Northstar-Staff also fails for several remote users: the VPN gateway is down; tell the network team.

<a id="kb11"></a>

### Username standard

*Identity* · **Tools:** Directory, Documentation · **Used in:** [INC-1059](#inc-1059), [INC-1060](#inc-1060)

**Purpose.** Give every person one predictable, permanent username and keep sign-ins stable through name changes.

**Before you start**

- You have the person’s legal first and last name from HR.

**Steps**

1. Usernames are the first initial plus the surname, lowercase, with no spaces or accents: Maya Chen becomes mchen.
2. If that username is taken, add the middle initial (mjchen). If there is no middle initial, add the next letter of the first name (machen).
3. Never reuse a leaver’s username, even if the account is disabled or in the recycle bin.
4. The email address is first.last@northstar.example and is generated from the display name when the account is created.
5. Don’t rename a username for a name change. Change the display name, add the new email address as an alias, make it primary and keep the old one.

**Verify**

- Create user shows the username hint in green (“… is available”).

**Escalate when**

- Two people would end up with the same username and display name: ask HR how they want them told apart before creating the account.

<a id="kb12"></a>

### Deploying a computer from the PC Shelf

*Hardware* · **Tools:** PC Shelf, Computer Deployment, Asset Management · **Used in:** [INC-1052](#inc-1052), [INC-1053](#inc-1053), [INC-1054](#inc-1054), [INC-1059](#inc-1059)

**Purpose.** Build and hand over a clean, correctly imaged device to the right person.

**Before you start**

- You know who it’s for, their role (which decides the image) and where they sit or work.
- A domain controller is running (domain join needs one).

**Steps**

1. Open Tools › PC Shelf › Devices. Pick an Available device that reads Wiped. A Reserved device belongs to someone else’s request unless it’s reserved for this person.
2. Never deploy a device that reads Not wiped: wipe it first (Wipe) or pick another.
3. Open Tools › Computer Deployment. Set Device, Build profile / image (matching the role: Finance, Sales Mobile, Standard Office…), Assign to and Location.
4. If a “Check before deploying” warning appears, stop and read it. “Deploy anyway” is almost never right.
5. Select Run deployment and read the five stages: image, domain join, apps, encryption, hand-over.
6. Open Asset Management to see the new host record (owner, image, location, state In use).
7. Deal with the old device: Return to shelf, retire it, or send a return label if the person is remote.

**Verify**

- Last job shows five green stages.
- Asset Management shows the new host owned by the right person with the right image.

**Escalate when**

- A stage fails (for example domain join because a domain controller is down): fix that first or pass it to the server team.
- No suitable clean spare is available: tell the manager and order one; don’t take a reserved device.

<a id="kb13"></a>

### Replacing a remote worker’s laptop

*Hardware* · **Tools:** Remote Desktop, Asset Management, Directory, Ship Manager, Company Chat · **Used in:** [INC-1054](#inc-1054)

**Purpose.** Get a working replacement to someone working from home, ship to the right address and recover the damaged device for repair.

**Before you start**

- You’ve confirmed it’s a hardware fault (Device Manager shows Error with a code that a driver reinstall won’t clear).
- You know the warranty and accidental-damage cover from Asset Management › Details.

**Steps**

1. Remote Desktop › Device Manager: note the failing device and its code (for example Code 43 on the internal display).
2. Asset Management › Open › Details: warranty and Accidental damage cover decide repair rather than scrap.
3. Directory › person › Profile: read the home address and when HR last updated it.
4. Deploy a spare with the person’s role image and Location Remote (home) (see “Deploying a computer from the PC Shelf”).
5. Ship Manager: Type Outbound to a person, Item the new host, Recipient the person, Address from Directory (HR record). If the preview warns that the saved address book differs, trust Directory. Select Create shipment.
6. Ship Manager: Type Return label (person sends to IT), Item the damaged host, Address from Directory (HR record), then Create return label.
7. When the courier delivers, select Mark delivered on the outbound row.
8. Company Chat: ask the person to confirm they can sign in and work.

**Verify**

- The outbound shipment reads Delivered to the Directory address.
- The old device reads Return in transit; the user confirms in chat.

**Escalate when**

- The address in Directory looks wrong or outdated: confirm with HR before shipping.
- The damage isn’t covered: ask the manager to approve the replacement cost.

<a id="kb14"></a>

### Verifying a caller’s identity

*Identity* · **Tools:** Directory · **Used in:** [INC-1057](#inc-1057), [INC-1062](#inc-1062), [INC-1063](#inc-1063), [INC-1065](#inc-1065)

**Purpose.** Make sure the person asking for a change to an account really is the account owner.

**Before you start**

- You have the account open in Directory, with the person’s Mobile, extension and Employee ID visible on Profile.

**Steps**

1. Never reset a password or MFA, enable an account, or ship a device for an unverified caller.
2. Select Verify identity… on Profile or Authentication.
3. Preferred: “Callback to number on record” (the desk extension or mobile already in Directory) or “Code to registered mobile”.
4. “Callback to number the caller gave” proves nothing: an attacker can give their own number.
5. A code to a phone the caller says is lost won’t work. Use a callback to another number on record.
6. “Manager attestation” is acceptable only when the manager confirms through a channel you trust, such as Company Chat.
7. A message typed from someone else’s account (a colleague’s chat) proves nothing about the person it’s about.
8. Write the verification method in the ticket notes.

**Verify**

- Identity check reads Verified with the method you used.

**Escalate when**

- The caller can’t be verified but pushes for urgency, uses an executive’s name, or offers a new phone number or address: change nothing and escalate to Security.

<a id="kb15"></a>

### DNS outage: names fail, IP addresses work

*Server* · **Tools:** Remote Desktop, Server Room · **Used in:** [INC-1066](#inc-1066)

**Purpose.** Restore name resolution when people can’t reach servers by name even though the network is up.

**Before you start**

- A user PC on the office network to test from (Remote Desktop).

**Steps**

1. From the PC’s Terminal run ping 10.0.0.20 (works) and ping file01 (“could not find host”). Names failing while IPs work means DNS.
2. Run nslookup file01: “DNS request timed out” from dc01.northstar.local points at DC01.
3. Optional: nslookup file01 10.0.0.11 answers from DC02; ipconfig /all shows DNS Servers lists only 10.0.0.10, which is why PCs don’t fail over.
4. Open Tools › Server Room › Servers › Services on DC01: DNS Server reads stopped. Read the event (7031) under “Event log & scheduled tasks”.
5. Select Start next to DNS Server. Don’t Reboot a domain controller for one stopped service, and never stop DNS on DC02.
6. On the PC run ipconfig /flushdns to clear the cached failure, then nslookup intranet.northstar.local.

**Verify**

- nslookup returns an Address (10.0.0.40 for the intranet) from DC01.
- Mapped drives open again in File Explorer.

**Escalate when**

- DNS Server stops again after starting: send it to the server team with the event ID.
- Both DCs fail to answer: major incident; tell the service desk manager.

<a id="kb16"></a>

### Reported phishing: analyse, purge, block

*Security* · **Tools:** Mail Security, Mail Admin · **Used in:** [INC-1072](#inc-1072)

**Purpose.** Contain a phishing campaign that staff have reported, without destroying the evidence.

**Before you start**

- A message is listed under Mail Security › Reported messages.

**Steps**

1. Never select Open link on a reported message. Select Analyze and read the verdict (domain age, SPF, DKIM, reply-to, clicks).
2. Mail Admin › Message trace: search the sender domain to see every recipient of the campaign.
3. Mail Security › Reported messages: select Report to Security so they have the headers and indicators.
4. Select Search & purge…, Scope “Every copy, all recipients”, Mode “Soft delete (recoverable by admins)”, then Purge.
5. Select Block sender, or block the whole lookalike domain on Blocked senders (@domain.example). Never block northstar.example.
6. Trace the sender again.

**Verify**

- Every copy shows Purged in Message trace, and the sender or domain is on Blocked senders.

**Escalate when**

- Anyone clicked the link or entered credentials (the verdict shows clicks): escalate to Security immediately and reset that user’s password with them.
- A legitimate newsletter was reported: tell the user it’s safe instead of purging it.

<a id="kb17"></a>

### Dead PC: swap or repair?

*Hardware* · **Tools:** Asset Management, PC Shelf, Computer Deployment, Company Chat · **Used in:** [INC-1052](#inc-1052)

**Purpose.** Decide quickly between repairing and replacing a PC that won’t power on, and keep the asset register accurate.

**Before you start**

- The user has tried another socket, and the monitor works (so building power is fine).

**Steps**

1. Asset Management › Open › Health: Power, Heartbeat and the Last event show when it died and why.
2. Details: the warranty and User data (where the user’s files live). If folders are redirected to a server, a swap loses nothing.
3. Out of warranty or business-critical: deploy a clean spare (Available and Wiped) rather than wait for a repair.
4. Set the dead unit’s State to “Retired, awaiting disposal” so the disk goes through certified destruction. The owner clears automatically.
5. Never set it straight to Disposed, and never set an out-of-warranty unit to In repair while the desk is down.
6. Company Chat: ask the user to confirm they can work on the new PC.

**Verify**

- New host In use for the user; old unit Retired, awaiting disposal with no owner.

**Escalate when**

- User data is stored locally on the dead PC: send the disk to the hardware team for recovery before retiring it.

<a id="kb18"></a>

### Updates fail and the PC is slow (full disk)

*Hardware* · **Tools:** Remote Desktop, Company Chat · **Used in:** [INC-1055](#inc-1055)

**Purpose.** Free enough disk space for updates to install, without touching the user’s own files.

**Before you start**

- Remote Desktop session to the PC; the user knows you are working on it.

**Steps**

1. Remote Desktop › System Update: read Status and Last error. 0x80070070 means not enough free space; the line shows how much updates need.
2. Settings › Storage shows what uses the disk. Documents is Protected.
3. Select Clean up on Temporary files and Update cache, and Empty Recycle Bin.
4. Ask the user in Company Chat before selecting “Remove downloads older than 30 days”: downloads are theirs.
5. System Update › Retry install, then Restart now once the user has saved their work.
6. Never select Pause updates for 7 days to hide the prompt.

**Verify**

- System Update reads Up to date and Storage shows at least the space updates need.

**Escalate when**

- Space is still short after safe clean-up: the disk is too small for the role. Raise a hardware request rather than deleting user data.

<a id="kb19"></a>

### Second screen shows “No signal”

*Hardware* · **Tools:** Remote Desktop, Company Chat · **Used in:** [INC-1056](#inc-1056)

**Purpose.** Bring back an external monitor when the hardware is fine but Windows isn’t using it.

**Before you start**

- The user can tell you what changed (a presentation, a projector, a new dock).

**Steps**

1. Remote Desktop › Device Manager: if the dock and monitor read Working, the hardware is fine.
2. Settings › Display: compare “displays detected” with “active”.
3. In Multiple displays choose “Extend these displays” (Duplicate mirrors the screen, which isn’t what most people want at a desk).
4. Select Keep changes before the 15-second timer reverts it.
5. Ask the user in Company Chat to confirm both screens work.

**Verify**

- Settings › Display reads 2 displays detected · 2 active.

**Escalate when**

- Device Manager shows the monitor or dock with an error that a rescan doesn’t clear: then it’s hardware, so issue a replacement.

<a id="kb20"></a>

### Laptop not charging while plugged in

*Hardware* · **Tools:** Remote Desktop, PC Shelf, Asset Management, Company Chat · **Used in:** [INC-1058](#inc-1058)

**Purpose.** Find out whether the battery, the laptop or the charger is at fault, and fix it with the cheapest correct part.

**Before you start**

- Remote Desktop session to the laptop.

**Steps**

1. Settings › Power & battery: read Status, Power adapter wattage, Battery health and Charge cycles.
2. Device Manager › Batteries shows the USB-C power source.
3. A Northbook needs a 65 W charger. Any USB-C plug fits, so a weaker charger lights up but can’t keep up.
4. Battery health above 80% with few cycles is healthy: don’t replace the battery or the laptop.
5. Asset Management › Accessories shows what was issued or reported missing.
6. PC Shelf › Accessories: choose the device on the USB-C charger 65 W row and select Issue, so the asset record stays accurate.
7. Ask the user in Company Chat to swap chargers, then check Power & battery again.

**Verify**

- Power & battery reads Charging with a 65 W adapter, and the user confirms the percentage is rising.

**Escalate when**

- Status stays Not charging on a 65 W charger, or battery health is poor: send the laptop for hardware repair.

<a id="kb21"></a>

### Urgent requests to send devices or passwords somewhere new

*Security* · **Tools:** Voicemails, Directory, Asset Management, Company Chat · **Used in:** [INC-1057](#inc-1057), [INC-1065](#inc-1065)

**Purpose.** Spot pretexting (social engineering by phone or voicemail) and stop it without harming the real user.

**Before you start**

- A request arrives by phone or voicemail asking for a password, an MFA reset or a device to be sent to a new address or number.

**Steps**

1. Urgency + authority (an executive or their “assistant”) + a new address or phone number is the classic pattern.
2. Never use contact details the requester gives you. Compare the caller ID with Directory › Profile.
3. Look for evidence: Directory › Authentication shows a recent sign-in; Asset Management › Health shows whether the “lost” device is online.
4. Search Directory for the named assistant or caller; check Profile › Assistant.
5. Contact the real person through a trusted channel (Company Chat) using the ticket’s quick action.
6. If it’s fake, change nothing: no shipment, reset, lock, wipe or asset change. Don’t delete the voicemail.
7. On the voicemail select Save to the ticket and Forward to Security, then escalate the ticket.

**Verify**

- The real person has denied the request in chat and the ticket is escalated with the caller details.

**Escalate when**

- Always escalate a confirmed fake to Security, with the caller ID, time, what was asked for and the facts that contradict it.

<a id="kb22"></a>

### Offboarding a leaver

*Identity* · **Tools:** Directory, Mail Admin, Asset Management · **Used in:** [INC-1061](#inc-1061)

**Purpose.** Remove a leaver’s access completely while keeping their mail and data as HR requires.

**Before you start**

- An HR leaver record (Directory › Leavers) with the last day and instructions.

**Steps**

1. Directory › Leavers: read the HR instructions, then select Open account.
2. Authentication: read the sign-in log for activity after the last day, then select Disable account.
3. Sessions › Revoke all sessions. Disabling alone leaves existing sessions working.
4. Groups: Remove the department groups (Domain Users stays).
5. Mail Admin › Mailboxes: Convert to shared, then Grant the manager Full Access with the expiry HR asked for. Don’t add Send As unless asked.
6. Automatic replies: On, with HR’s text, then Save. Leave Forwarding empty unless HR asks for it.
7. Back in Directory › Licences: Remove each licence (the mailbox is shared now, so it isn’t deleted).
8. Asset Management › Open › Health › Return to shelf for the laptop, so it’s wiped before reuse.
9. Never select Delete account for an account under retention.

**Verify**

- Test sign-in fails with “the account is disabled”.
- Mail Admin › Test access as… the manager reads “can open”.

**Escalate when**

- The sign-in log shows activity after the last day from an unknown place: escalate to Security before anything else.

<a id="kb23"></a>

### Lost phone and MFA reset

*Identity* · **Tools:** Voicemails, Directory, Asset Management, Company Chat · **Used in:** [INC-1062](#inc-1062)

**Purpose.** Let someone who lost their phone sign in again, and make sure the lost phone can’t be used.

**Before you start**

- The request is logged as a ticket (voicemails: Log as ticket and Save to the ticket).

**Steps**

1. Verify first. A code to the registered phone won’t work if that phone is lost, and a number the caller gives proves nothing.
2. Directory › Verify identity… › “Callback to number on record” (the desk extension or another number already on file) › Run check.
3. Only then select Reset MFA… and confirm. The user re-enrols at next sign-in.
4. Sessions: Revoke the session belonging to the lost phone.
5. Asset Management › Mobiles: set the phone’s state to Lost/Stolen; optionally Queue remote wipe for a company phone.
6. Ask the user in Company Chat to sign in and re-enrol.

**Verify**

- Identity check reads Callback to number on record, MFA re-enrolled, the phone reads Lost/Stolen, and the user confirms.

**Escalate when**

- The caller can’t be reached on any number on record: don’t reset MFA; ask the manager to vouch through Company Chat or escalate to Security.

<a id="kb24"></a>

### Returning from long leave

*Identity* · **Tools:** Company Chat, Directory, Remote Desktop · **Used in:** [INC-1063](#inc-1063)

**Purpose.** Reactivate a returner’s own account safely, rather than creating a new identity.

**Before you start**

- A Directory HR note confirms the return date.

**Steps**

1. A request typed from someone else’s chat account proves nothing. Verify the returner through their own record: callback to the number on record, or a code to their registered mobile.
2. Read the HR note in Directory: leave workflows often disable the account, let the password expire and release licences.
3. Authentication: Enable account, then Reset password… with “must change at next sign-in”, read to the user on the verified call.
4. Licences: if Assign is greyed out, the pool is full. Follow “Licence pools: assigning and reclaiming seats”.
5. Test sign-in, then Remote Desktop › the user’s PC › Office Suite › Refresh licence.

**Verify**

- Test sign-in passes and Office Suite reads Licensed (“Product activated”).

**Escalate when**

- You can’t verify the returner: leave the account disabled and ask HR or the manager to confirm through a trusted channel.

<a id="kb25"></a>

### Shared mailbox access requests

*Email* · **Tools:** Mail Admin, Company Chat · **Used in:** [INC-1064](#inc-1064)

**Purpose.** Grant exactly the shared-mailbox access the owner approved, for as long as they approved it.

**Before you start**

- Mail Admin › Shared mailboxes shows the mailbox owner and access policy.

**Steps**

1. Approval comes from the mailbox owner, not from the requester or their line manager. Ask the owner in Company Chat so it’s written down.
2. Grant exactly what was approved: Full Access and Send As are separate rights.
3. Under Permissions choose the person, the right and the Expiry for temporary cover, then select Grant.
4. Under Test access as…, choose the person and select Test access.
5. Ask the person to confirm the mailbox appears, and quote the approval in your notes.

**Verify**

- The permission row reads Owner approved with the right expiry, and Test access reads “can open”.

**Escalate when**

- The owner refuses or can’t be reached: don’t grant anything; tell the requester and their manager.

<a id="kb26"></a>

### Internet down, internal services fine

*Network* · **Tools:** Remote Desktop, Server Room, Company Chat · **Used in:** [INC-1068](#inc-1068)

**Purpose.** Handle a provider outage: prove where the break is, get the provider working on it and keep staff informed.

**Before you start**

- Drives and internal servers still work while websites don’t.

**Steps**

1. From an office PC’s Terminal: ping 10.0.0.1 and ping file01 work; ping web.example fails.
2. tracert web.example shows the last hop that answers. If fw01 and edge01 answer, don’t reboot them.
3. Server Room › Overview or Topology › MetroFiber ISP: Check provider status and note the incident.
4. Keep the main circuit selected and select Log fault with provider. Note the reference.
5. Company Chat › office-announcements: post Full status update (impact, workaround, next update). Never post “Ask everyone to restart”.
6. Check provider status again until the circuit is restored, then post Resolved.

**Verify**

- ping web.example from an office PC gets replies.

**Escalate when**

- The outage passes the provider’s next-update time with no progress: escalate with the provider through your manager and consider the backup circuit.

<a id="kb27"></a>

### File server volume full

*Server* · **Tools:** Server Room, Remote Desktop · **Used in:** [INC-1069](#inc-1069)

**Purpose.** Free space on a full file-server volume safely and stop it filling again.

**Before you start**

- Reads work but every save fails on every share.

**Steps**

1. Server Room › Servers › Services on FILE01: if both services run, it isn’t an outage.
2. Storage (server FILE01): find the full volume and the folder that grew, using the “Older than 30 days” column.
3. Select Purge older than 30 days on that folder. Don’t use Delete entire folder.
4. Never select Delete all shadow copies to free space: they are everyone’s restore points.
5. Events & tasks (choose FILE01 in the Server list): find why it grew, often a clean-up task left Disabled after maintenance, and select Enable.
6. Back on Storage select Test write.

**Verify**

- Test write reads “Test file written to D: and removed”, and a user can save to a share.

**Escalate when**

- Purging old files doesn’t free enough space: ask the server team to extend the volume or add storage.

<a id="kb28"></a>

### Restoring a deleted file from a share

*Server* · **Tools:** Server Room, Remote Desktop, Company Chat · **Used in:** [INC-1070](#inc-1070)

**Purpose.** Bring back one deleted or damaged file without disturbing anything else on the share.

**Before you start**

- You know the share and the file name.

**Steps**

1. Deletes on network drives skip the Recycle Bin. Server Room › Shadow copies › File audit shows who deleted what and when.
2. Set Share, select the file and compare its previous versions by modified time and size, not by snapshot label.
3. Select Restore to original location on the right version (or Restore as a copy if the user wants to compare).
4. Never select Revert entire share to recover one file: it overwrites everyone’s changes since the snapshot.
5. If no snapshot holds the file, select Request restore from nightly backup.
6. Ask the user in Company Chat to open it and confirm the content.

**Verify**

- File Explorer lists the file again and the user confirms it holds the expected content.

**Escalate when**

- No snapshot or backup holds the version needed: tell the user honestly and involve the server team.

<a id="kb29"></a>

### Approving a new phone for company mail

*Email* · **Tools:** Mail Admin, Company Chat · **Used in:** [INC-1071](#inc-1071)

**Purpose.** Let a user’s new phone sync company mail, using the approved app, and retire the old one correctly.

**Before you start**

- The new phone is listed as Quarantined in Mail Admin › Mobile devices.

**Steps**

1. Ask the user in Company Chat for the Device ID from Settings › About and match it before approving.
2. Select Approve only on the Northstar Mail row. Select Block on third-party mail apps that store the password in someone else’s cloud.
3. Ask what happened to the old phone. Use Remove partnership or Account-only wipe for personal or traded-in phones; Remote wipe is for lost company phones only.
4. Select Test sync on the approved row.
5. Never select Disable quarantine for all to fix one phone.

**Verify**

- Test sync reads “sync test passed” and the user confirms mail and calendar.

**Escalate when**

- The Device ID doesn’t match what the user reads out: don’t approve; treat it as unknown and tell Security.

<a id="kb30"></a>

### DHCP scope full (169.254 address)

*Network* · **Tools:** Remote Desktop, Server Room · **Used in:** [INC-1067](#inc-1067)

**Purpose.** Get a PC a valid address when the floor’s DHCP scope has run out, without disrupting working devices.

**Before you start**

- The affected PC is reachable in Remote Desktop.

**Steps**

1. Terminal › ipconfig: a 169.254.x.x (Autoconfiguration) address with no gateway means no DHCP lease. ping 10.0.0.1 fails with General failure.
2. Server Room › Servers › Services on DC01: DHCP Server should be running. Its event log shows the scope-full event.
3. DHCP tab: read the floor’s “in use” count and lease time, then View leases to find stale, inactive clients.
4. Select Delete inactive leases. Never Delete all leases: every working device on the floor drops.
5. Choose a shorter lease (8 hours or 1 day) and select Set lease duration, so one-day guests can’t fill the scope again.
6. Never widen the range over fixed addresses below .100 (printers live there).
7. On the PC run ipconfig /renew, then ping 10.0.0.1.

**Verify**

- ipconfig shows a 10.0.x.1xx address with gateway 10.0.0.1, and ping 10.0.0.1 replies.

**Escalate when**

- The scope fills with active devices: the floor has outgrown it. Ask the network team to plan a bigger scope.

<a id="kb31"></a>

### New starter: account, access and day-one handover

*Identity* · **Tools:** Directory, Documentation, Computer Deployment, Company Chat · **Used in:** [INC-1053](#inc-1053), [INC-1059](#inc-1059)

**Purpose.** Have a new starter able to sign in, reach their team’s files and use the right laptop on day one, with no more access than the role needs.

**Before you start**

- An HR starter record (Directory › Starters) or role template on the account.

**Steps**

1. Directory › Starters: read the start date, department, manager, licences and equipment.
2. Read the Username standard; search Directory for the surname to catch clashes, including leavers.
3. Select Create account from this record…, fix the Username if the hint shows it’s taken, tick the licences HR listed, keep “Add the department share group”, and select Create user.
4. Compare Groups with the role template or the manager’s groups, and add nothing extra.
5. Deploy a laptop with the role’s image (see “Deploying a computer from the PC Shelf”).
6. Day-one password: the starter gets it in person after an ID check. Where the starter record says the manager is meeting them, use Reset password… with “Company Chat to their manager”. Never personal email, and never type a password into a chat yourself.
7. Select Test sign-in, then confirm with HR or the manager.

**Verify**

- Groups and licences match the template, the laptop is In use for the starter, and Test sign-in passes.

**Escalate when**

- The starter record is missing details or conflicts with the role template: ask HR before creating anything.

<a id="kb32"></a>

### Name change: display name and email alias

*Identity* · **Tools:** Directory, Mail Admin, Company Chat · **Used in:** [INC-1060](#inc-1060)

**Purpose.** Update someone’s name everywhere people see it, without breaking their sign-in or losing mail sent to the old address.

**Before you start**

- HR has recorded the new name (Profile shows “Pending HR change”).

**Steps**

1. Directory › Profile › Edit profile…: change Display name. Leave Username as it is.
2. Email addresses: type the new first.last@northstar.example, select Add address, then Make primary on it.
3. Keep the old address as an alias: suppliers and colleagues still use it.
4. Mail Admin › Mailboxes › Send test to: the old address, then Send test message.
5. Ask the person in Company Chat to confirm.

**Verify**

- The test to the old address reads “delivered to \<new name\>’s mailbox” and Profile shows the new display name.

**Escalate when**

- The person asks for a new username too: explain the impact (new profile, mapped drives, saved sign-ins) and get their manager’s agreement first.

<a id="kb33"></a>

### Licence pools: assigning and reclaiming seats

*Identity* · **Tools:** Directory, Remote Desktop · **Used in:** [INC-1059](#inc-1059), [INC-1061](#inc-1061), [INC-1063](#inc-1063)

**Purpose.** Keep licences with the people who need them, and free seats correctly when a pool runs out.

**Before you start**

- Directory › person › Licences shows what they have and how many seats are free.

**Steps**

1. Assign the licences the role needs: Office Suite (which also provisions the mailbox), Endpoint Protection, and department licences such as Sales Hub CRM.
2. If Assign is greyed out, select View licence pools and read each holder’s Account state and Last sign-in.
3. Reclaim a seat only from a Disabled leaver. Never take one from an active colleague.
4. For a leaver, convert their mailbox to shared before removing Office Suite, or the mailbox is scheduled for deletion.
5. After assigning Office Suite to someone who was unlicensed, refresh it on their PC: Remote Desktop › Office Suite › Refresh licence.

**Verify**

- The pool never goes negative, the user reads Assigned and Office reads Licensed.

**Escalate when**

- No disabled leaver holds a seat: ask the licence owner (IT manager) to buy more rather than taking one from a colleague.

<a id="kb34"></a>

### Escalating to Security with evidence

*Service desk* · **Tools:** Mail Admin, Directory, Voicemails · **Used in:** [INC-1049](#inc-1049), [INC-1057](#inc-1057), [INC-1065](#inc-1065)

**Purpose.** Hand a suspected compromise or social-engineering attempt to Security fast, with the evidence intact.

**Before you start**

- You have a security concern: a compromise indicator, an unverifiable urgent request, or a confirmed fake.

**Steps**

1. Stop changing things on the affected account or device. Evidence (rules, voicemails, sign-in logs) must stay as it is.
2. Collect the facts: who, what, when, from where (caller ID, address, rule target, timestamps) and what contradicts the request.
3. Save voicemails to the ticket and Forward to Security; don’t delete them.
4. Add work notes as you go so the timeline is on the ticket.
5. Select Escalate to Security, write the evidence (at least 15 characters) and select Escalate.

**Verify**

- Past tickets shows Routed to Security, and the preview included “Correct security escalation +12”.

**Escalate when**

- Escalation is the end of your part. Don’t escalate routine fixes: a needless escalation costs 8 points.

<a id="kb35"></a>

### Logging chat messages and voicemails as tickets

*Service desk* · **Tools:** Company Chat, Voicemails · **Used in:** [INC-1054](#inc-1054), [INC-1056](#inc-1056), [INC-1057](#inc-1057), [INC-1058](#inc-1058), [INC-1062](#inc-1062), [INC-1063](#inc-1063), [INC-1065](#inc-1065), [INC-1067](#inc-1067), [INC-1068](#inc-1068), [INC-1071](#inc-1071)

**Purpose.** Turn a request that arrives outside the queue into a ticket, so it’s tracked and scored.

**Before you start**

- The dashboard shows it under Incoming contacts, or the Voicemails badge has a new message.

**Steps**

1. Dashboard › Incoming contacts: select Open chat or Open voicemails to read the full message.
2. Read the caller ID or chat sender, and compare it with who the request is about. A chat sent from someone else’s account isn’t proof of identity.
3. Select Log as ticket (or Log as INC-… in the chat). The ticket joins the Incidents queue.
4. Voicemails: select Save to INC-… so the transcript is on the ticket. Never delete a suspicious voicemail.
5. Open the ticket and select Assign to me.

**Verify**

- The ticket is in My Queue and the contact no longer appears under Incoming contacts.

**Escalate when**

- A voicemail asks for something risky for someone else (an executive’s password, a device to a new address): see “Urgent requests to send devices or passwords somewhere new”.

<a id="kb36"></a>

### Verifying, documenting and closing a ticket

*Service desk* · **Tools:** Company Chat · **Used in:** every ticket

**Purpose.** Close tickets only when the fix is proven, with notes the next technician can use.

**Before you start**

- You have made the fix.

**Steps**

1. Select Check fix. Every requirement must be green; if not, the list tells you what’s missing.
2. Where the ticket offers it, ask the requester in Company Chat to confirm (“Ask to confirm the fix”).
3. Select Close ticket. In Resolution notes write cause, action and verification: at least 40 characters, a specific name (user, host or service) and a verification word (verified, confirmed or tested) earn up to +3.
4. Check the points preview, then select Close ticket. “Close anyway” means it’s still unresolved and costs points.
5. Security cases use Escalate to Security instead.

**Verify**

- Past tickets shows Resolved with your notes and the model answer for comparison.

**Escalate when**

- You can’t make Check fix go green without a risky change: ask a colleague, use the hint ladder (free), or read the solution guide in Documentation.

<a id="kb37"></a>

### Following a message with Message trace

*Email* · **Tools:** Mail Admin · **Used in:** [INC-1047](#inc-1047), [INC-1048](#inc-1048), [INC-1060](#inc-1060), [INC-1072](#inc-1072)

**Purpose.** Find out what happened to a message: delivered, quarantined, failed, pending or purged.

**Before you start**

- A sender, recipient, display name or domain to search for.

**Steps**

1. Open Tools › Mail Admin › Message trace.
2. Type part of an address, a display name or a domain in “Sender, recipient or display name”; optionally set Status and Received.
3. Select Search and read each row’s status and detail line (for example 550 5.2.2 Recipient mailbox full, or Held by the content filter).
4. After a fix, select Search again: the new status is the evidence.

**Verify**

- The status matches what you expect after the fix (Delivered, or Purged for phishing).

**Escalate when**

- Messages fail for many recipients at once: check MAIL01 in Server Room and tell the messaging team.
