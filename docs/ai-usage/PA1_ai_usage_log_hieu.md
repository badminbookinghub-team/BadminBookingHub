# PA1 – AI Usage Log · Lê Trọng Hiếu (24127168, Project Manager)

## Detailed entry
**Tool / model:** Claude (Anthropic), used in the team's claude.ai project with the course templates (PA0–PA5, Guidelines & Rubric), the lecture *03_Project Management* and our PA0/PA1 drafts as context.
**Work packages concerned:** PA1/ 4.1, PA1/ 4.2, PA1/ 4.3, PA1/ 4.4 (owner of 4.4: Trần Duy Khang – output handed over for review).

### What I asked
1. Should the exit criteria in §4.1 have the same structure for every PA, or be PA-specific? Reasoning required, based on all PA templates.
2. Should the WBS (§4.2/4.3) be broken down per PA (by template chapters) or by the exit-criteria structure? Is the template structure enough for “WBS ≥ 3 levels”?
3. Draw the §4.4 Gantt chart from §4.3 using the course WBS-with-Gantt template, with dependencies, milestones and critical path.

### What the AI produced
- **First draft (rejected by me):** 4.1 split into extra tables (common gate criteria G1–G7 + numbered exit criteria) and WBS levels counted from the project (levels 0–3). I rejected it because it does not follow the PA1 template and the lecture WBS template (Level 1 = phase).
- **Revised 4.1:** only the template table (PA | Phase | Due | Exit criteria); each Exit-criteria cell written in the same pattern: content required by the rubric, grouped by the level-2 deliverables (e.g., “(1.3)”), then the same closing gate (review, contribution table, AI log, PDF + source on Moodle and /pa/PAx). “PA0 approved by the TA” removed from PA1 (entry, not exit).
- **Revised 4.2:** WBS renumbered to 3 levels as in the lecture template (1 / 1.1 / 1.1.1): level 1 = phase (1–5 = PA1–PA5, 6 = Final, 7 = PM), level 2 = 33 deliverables, level 3 = the 75 work packages of §4.3 (every work package at level 3). New Figure 2 (levels 1–2).
- **4.3:** table renumbered with the new WBS IDs (owners, effort, O/M/P unchanged); recomputed E = (O + 4M + P)/6 for 75 work packages (all correct, total 352.6 h); noted the “about 7 hours” sentence should read 7.8 h.
- **4.4 schedule:** CPM schedule (forward/backward pass, resource links, float), Gantt workbook `T08-PA1-WBS-Gantt.xlsx` (bars drawn from Start/Due dates, critical path, milestones M1–M6, % complete, staff-allocation sheet), Figures 3a/3b and draft English text.
- **Findings:** a naive schedule (all PA5 work after the PA3 gate, deployment at the end) finishes PA5 on 15/12, 6 days late; proposed starting repo scaffold + CI in week 7 after the ADRs, deploying to the test environment after the booking engine, and levelling front-end packages inside their float → PA5 ends 6/12 with 1 day of buffer.
- Flagged inconsistencies in §4.6 and §5 (copied from a mobile-app project: 590 h, Apple Developer, Jira/sprints; risks R1/R8 cited in 4.3 do not exist).

### How I verified it
- Re-calculated 3 PERT rows by hand (e.g., PA1/ 2.1: (3 + 16 + 6)/6 = 4.2 h) and the phase subtotals.
- Checked the milestones against the course schedule (PA1 21/10, PA2 4/11, PA3 18/11, PA4 25/11, PA5 9/12, Final week 11).
- Walked the PA2 critical path on the Gantt (4 → 5.1 → 6 → 8 → 9 → 10 → PA2/ 1) and confirmed every link with the BA.
- Discussed the week-7 scaffold/CI start and early deployment with Phúc (developer) and agreed it does not break the waterfall gate (feature coding still starts after M3).
- Reviewed the Gantt with Khang (owner of 4.4) before inserting the figures.
- Renamed the board issues to the new WBS numbers (e.g., “PA1/ 4.3 Estimation” → “1.3.3 Estimation”) using the WBS sheet of the workbook.

### What I changed / did not take
- Rejected the first AI proposal for 4.1 (extra tables not in the template) and the level counting from the project; kept the template structure.
- Owners and estimates in §4.3 were **kept** as the team agreed; only the WBS IDs and the average-hours sentence changed.
- Rewrote the proposed text in the team's own wording before pasting into PA1; kept the numbers that I could re-check.
- *(fill in: anything rejected after team review)*

