# PA2 – AI Usage Log


## 1. How I used AI in this phase

- I used Claude for four kinds of work: **mapping** (lecture/template → list of outputs), **cross-checking** (finding contradictions between FR, BR, AC, Glossary, PA0 and PA1), **second opinions** on reviews, and **first drafts** of my own sections that I then rewrote.
- Scope decisions and rule values were **never** taken from the tool. They were decided by me or by the team and recorded in the meeting notes / task issues (28/10, 31/10, 07/11, 11/11).
- I only used AI on **my own sections** (2.2.3 Business Rules, UC-17 – UC-21, §9, §10) and on **my reviews** of teammates' sections. I did not edit teammates' sections with AI; when I found a problem in their part I posted it on their GitHub task.
- Every review comment I posted on GitHub was written or rewritten by me before posting.
- Inputs given to the tool: the teacher's PA2 template, lecture slides 04 and 05, the rubric, PA0, PA1 and our PA2 draft. No personal data of anyone outside the team was given to the tool.

---

## 2. Detailed log

### Row 1 – Map lecture 04 to the PA2 template (22/10/2026)

| Item | Detail |
|---|---|
| WBS task | 2.1.1 – PA2 planning |
| What I asked | Summarise lecture 04 (Requirements Engineering) and map each topic to the sections of the PA2 template, so I know what output each section needs before splitting tasks. |
| What the AI gave | A list per template section (Problem Statement, Stakeholders, FR/NFR, Business Rules, Acceptance Criteria, Use Case Model, Prototype, RTM, Review), and a list of things PA0/PA1 left open (values N/M, weekly limit, missing "Project sponsor" stakeholder, vague real-time requirement for F04). |
| What I kept / changed | Kept the list of outputs as a checklist. The WBS tasks, owners and estimates were decided by the team at the W04 meeting, not taken from the tool. |
| How I verified | Checked each item against the template and the rubric (`00_Project Guidelines & Rubric`). |
| Evidence | W04 meeting note 24/10/2026; GitHub Projects tasks 2.1.1 – 2.2.4 |

### Row 2 – Business rules, my task 2.2.3 (25/10 – 28/10/2026)

| Item | Detail |
|---|---|
| WBS task | 2.2.3 – Domain Requirements and Business Rules (owner: me) |
| What I asked | List the values that PA0/PA1 left open and give some options for each rule (booking length, cancellation deadline, refund tiers, peak hours, check-in window, booking limit). |
| What the AI gave | Options for each rule, a first grouping of rules by policy area, and several versions of the rule list (16, ~50 and 36 rules). |
| What I rejected | – Peak price lasting until closing time → kept Peak at 17:00–21:00, 21:00–closing is Normal.<br>– 15-minute No-show → 25 minutes.<br>– System marking No-show automatically → only Staff marks No-show, because our check-in is manual (no QR / face scan).<br>– Sub-IDs like BR-04a / BR-04b → one number per rule.<br>– Wording "to be confirmed by interview" → rule source written as the court owner's policy. |
| What I decided | Weekly hour limit replaced by a quota of 10 hours of upcoming bookings; cancellation deadline 6 hours; refunds 100% (≥ 3 h) / 50% (< 3 h) / 0% No-show, paid back automatically to the e-wallet sandbox; walk-in bookings start at the next 30-minute mark and go straight to Checked-in; account deletion refused while the Player has an active booking. |
| Final text | I wrote the final 36 rules (BR-01 – BR-36) myself, one idea per rule, grouped by policy area. |
| How I verified | Recalculated every example price and time limit by hand; checked each rule against PA0/PA1 features. |
| Evidence | Task 2.2.3 on GitHub Projects; team decision 28/10/2026 |

### Row 3 – Second opinion on a classmate's 16-point review (27/10 – 28/10/2026)

| Item | Detail |
|---|---|
| WBS task | 2.2.3 – review round |
| What I asked | A classmate posted a 16-point review (M1–M6 major, m1–m10 medium) of §5.3. I asked the tool whether each point was valid before I changed anything. |
| What the AI gave | A short assessment of each point and drafts of a reply in Vietnamese and English. |
| What I changed | Decided agree / partly agree / disagree for each point myself and wrote the replies. The AI had mixed up which suggestions came from the reviewer and which were its own earlier ideas (e.g. walk-in status, sub-ID numbering); I corrected that. I also removed an extra "general notes" part that was not needed. |
| How I verified | Checked each point against the BR table and PA1. |
| Evidence | Reply comment on the §5.3 task issue |

### Row 4 – Cross-check the FR table before reviewing Tú's section (28/10 – 31/10/2026)

| Item | Detail |
|---|---|
| WBS task | Review of 2.2.1 – Functional Requirements (owner: Tú) |
| What I asked | Cross-check the FR table against the BR table, PA0, PA1 and the template. |
| What the AI found | 20 of 37 FRs cited old BR numbers after renumbering; some FRs contradicted BRs (check-in / No-show time, walk-in, cancellation, first booking status); some BRs had no FR; "team needs to confirm" notes still left in the text. |
| What went to the team | Scope questions (rentable equipment, account deletion, area search, booking quota) were decided by the team on 28/10 and 31/10, not by me or the tool. |
| What I changed | Confirmed every finding in the document myself; wrote the review comments to Tú in my own words; asked for BR numbers to be removed from the FR Source column. Later fixes to my own BR section were done by me. |
| How I verified | Opened each FR and BR in the document and compared values. |
| Evidence | Review comment on task 2.2.1; Requirements Review issues #1 – #7 |

### Row 5 – Consistency check of §1 – §5 and boundary scenarios for AC (31/10/2026)

| Item | Detail |
|---|---|
| WBS task | 2.2.4 – Acceptance Criteria; consistency of §1 – §5 |
| What I asked | Check that §1 – §5 agree with each other, and draft boundary-value scenarios for the acceptance criteria. |
| What the AI found | Single venue vs. search by area; Glossary No-show 15 min vs. 25 min in FR/BR; old BR-15 reference in Stakeholders; a 10-hour example vs. the 180-minute maximum; a goal implying every booking reaches a final status even though No-show is not automatic. |
| What the AI gave | Given/When/Then scenarios with boundary values (6 h / 5 h 59 m cancellation, 14 / 15 days booking window, 17:44 / 17:45 / 18:25 / 18:26 check-in). |
| What I changed | Recalculated prices and time limits against FR/BR. Open questions (area search, 180-minute limit, Vietnamese-only UI) were decided by the team. "Changes from PA1" paragraphs were rewritten as bullet lists. |
| Evidence | Team decision 31/10/2026; Requirements Review issues #1, #5, #8, #13 |

### Row 6 – Reschedule WBS 2.3 – 2.6 after the deadline moved (31/10 – 04/11/2026)

| Item | Detail |
|---|---|
| WBS task | PM – schedule for 2.3.1, 2.3.2.x, 2.4.1, 2.5.1, 2.5.2, 2.6.1, 2.6.2 |
| What I asked | Re-plan the remaining PA2 tasks after the deadline moved to 11/11/2026; check in lectures 04 and 05 which tasks had already been taught and which could run in parallel. |
| What the AI gave | A day-by-day schedule with owners and reviewers, and a short team guide (UC writing conventions, review checklist). |
| What I changed (several rounds) | – Too much work on one day → spread across days.<br>– "Group" tasks → every task has one owner.<br>– Use case specs split into 2.3.2 / 2.3.3 → all under one 2.3.2.x prefix.<br>– Focus on the 23 Must/Should use cases, not all 30.<br>– More use cases for the BA (Tú: UC-04 – UC-11).<br>– Reviewers balanced by workload. |
| Also | Translation of my Discord announcement (Vietnamese → English); I added the line asking people to tag the PM when blocked. |
| Evidence | GitHub Projects tasks 2.3 – 2.6 (assignees, reviewers, dates) |

### Row 7 – First draft of my use cases UC-17 – UC-21 (06/11 – 08/11/2026)

| Item | Detail |
|---|---|
| WBS task | 2.3.2.6 – Use case specifications UC-17 – UC-21 (owner: me) |
| What I asked | A first draft of UC-17 – UC-21 (court information, opening hours, court status, price lists, public holidays) in the agreed UC-17 format, using only FR/BR/AC already in the document. |
| What I decided | Court status rules: a new court is Active as soon as it is created; the Admin can reactivate a deactivated court → UC-19 renamed "Change Court Status" with an activation flow (team decision 07/11). |
| What I removed from the draft | – Constraints that no BR supports: rounding of opening hours, price multiples of 1,000 VND, date limits for public holidays, unique court name, minimum capacity, holiday names.<br>– Trace IDs inside flows (kept only in Related requirements).<br>– Rule text in the Business rules / NFR rows (IDs only, team format 07/11).<br>– Vietnamese UI labels, button names and messages (steps describe actions only). |
| How I verified | Compared my working file with the team's agreed version to undo changes outside my section; kept only three fixes I judged were real errors and sent other problems (e.g. Glossary No-show) to the section owner via the review table. |
| Evidence | Task 2.3.2.6; teammates' reviews on GitHub |

### Row 8 – Check teammates' UC-06 – UC-11 and UC-22 – UC-23 before my review (07/11 – 08/11/2026)

| Item | Detail |
|---|---|
| WBS task | Review of 2.3.2.x (Tú: UC-06 – UC-11; Khang: UC-22 – UC-23) |
| What I asked | Check these use cases against FR, BR and AC and against the UC-17 format. |
| What the AI found | Use cases describing another use case's steps (UC-06 repeating UC-08 / UC-25, UC-11 repeating UC-10 / UC-27); missing extension points; UC-06 concurrency check not covering the booking quota; UC-07 not using the public holiday list; UC-22 / UC-23 adding rules that are not in the BR section. |
| What I changed | Gave my own wording for UC-06 (concurrency, price recalculation, e-mail timing) and UC-11 (separate "not started" and deadline checks). Dropped points that relied on rules outside the agreed BR section instead of raising them as new rules, since §5.3 was already final. Split the review into two documents (UC-06 – UC-09 → #112, UC-10 – UC-11 → #113). |
| Evidence | Review comments on issues #112, #113 and the UC-22 / UC-23 task |

### Row 9 – Summary of PA0 – PA2 for the progress meeting (08/11/2026)

| Item | Detail |
|---|---|
| WBS task | PM – PA2 progress meeting |
| What I asked | Summarise PA0, PA1 and the PA2 draft for the meeting; list PA1 feedback from the teacher that still needs fixing. |
| What the AI gave | A meeting summary (agenda, PA status, list of changed decisions, PA2 checklist) and a list of PA1 feedback points (copied tool text in "Tools & Collaboration", risk register mismatches, Gantt dependencies, local vs. AWS deployment, file name and identical evidence links). |
| What I changed | Corrected the venue / branch wording (one venue, one owner). The fixes and owners were agreed in the meeting. |
| Evidence | Meeting note 08/11/2026 |

### Row 10 – Final consistency check of §1 – §7 before the baseline (11/11/2026)

| Item | Detail |
|---|---|
| WBS task | 2.5.2 – Requirements Review (preparation) |
| What I asked | Check whether the whole PA2 is consistent, and compare it with the teacher's PA2 comments for other groups to see which mistakes we also make. |
| What the AI found | 180-minute limit still in FR-15 / BR-02; FR-03 traced in different places; out-of-scope list different in §2 and §3; some missing BR IDs in UC-01, UC-02, UC-22; and points from the teacher's comments (accessibility results, HTTP codes in AC, time-based functions without a use case, mockup readability). |
| What I changed | Chose which issues to fix in my own sections (§9, §10) and sent the rest to the section owners. The outcome is recorded in §10. |
| Evidence | §10 Requirements Review; task comments 11/11/2026 |

### Row 11 – RTM (§9) and review table (§10) (11/11/2026)

| Item | Detail |
|---|---|
| WBS task | 2.5.1 – Requirements Traceability Matrix; 2.5.2 – Requirements Review (owner: me) |
| What I asked | Build the FR → use case → screen mapping from §6.3 and §8, and format the review table. |
| What the AI gave | RTM rows FR-01 – FR-42 (Design / Test columns left empty for PA3 / PA4), and the review table layout. |
| What I changed | Checked each RTM row against the Use Case List and the screen table. The review issues all come from our task reviews and meetings (28/10, 31/10, 07/11, 11/11), not from the tool. Meeting date and participants filled in by me. |
| Evidence | §9, §10 of PA2 |

---


## 3. Link to other PAs

- **From PA1:** PA1 feedback (evidence links per member, deployment target, file name) was handled in PA2 – see rows 9, 13 and 15.
- **To PA3:** the SRS of 11/11/2026 is the requirements baseline. AI use in PA3 will be logged in the same format; any change to requirements after 11/11 goes into PA3 "Changes to the Requirements Since PA2".

## 4. Lessons for the next phase

- The tool tends to **add rules that nobody agreed** (validation limits, UI text). In PA3 I will give it the agreed BR/FR list and ask it to flag gaps instead of filling them.
- It sometimes **mixes up who said what** in a review. I will always check attribution before posting a reply.
- Cross-checking large tables (FR ↔ BR ↔ AC ↔ RTM) is where it saved the most time; final decisions stay with the team.
