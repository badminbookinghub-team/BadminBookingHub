# AI Usage Log — BadminBookingHub (PA1)

> **Purpose:** This file records, in detail, how ChatGPT was used as a learning, discussion, drafting, review, and workflow-support tool while preparing PA1 for the BadminBookingHub project.
>
> **Important:** This is a reconstructed work log based on the conversation history, not a verbatim transcript. It does not claim exact timestamps for individual messages. The student/team should review this record, correct anything that does not match their actual work, and follow the course's required AI-disclosure format.

## 1. Project context

- **Project:** BadminBookingHub
- **Course deliverable:** PA1 — Project Proposal & Plan
- **Project idea:** A web-based badminton court booking and management system.
- **Main user groups identified in PA0:** Player, Staff, and Admin. The student clarified during the discussion that **Admin represents the court owner** in this project.
- **Core needs reflected in the discussion:** Players need to find courts, see prices and available time slots, and make or cancel bookings. Staff need to handle daily schedules and front-desk operations. Admins/court owners need to manage court information, pricing, accounts, roles, and booking policies.
- **Important system rule:** The system must not confirm two bookings for the same court when their time slots overlap, including when users submit booking requests at nearly the same time.
- **Working approach:** The student preferred to learn and decide through a guided discussion rather than immediately receiving a completed assignment. ChatGPT therefore asked questions, explained alternatives, commented on the student's choices, and drafted text after the student had clarified the intended content.

## 2. How ChatGPT was used

ChatGPT was used for the following kinds of support:

1. **Understanding the PA1 template:** Explaining what each section asks for and what information belongs in it.
2. **Guided discussion and brainstorming:** Asking questions and helping the student clarify the problem, target users, proposed system, and product differentiation.
3. **Drafting and rewriting:** Producing English drafts from the ideas and requirements discussed with the student.
4. **Consistency review:** Comparing proposed content with the project scope and features recorded in PA0, and identifying examples that did not fit BadminBookingHub.
5. **Translation and explanation:** Translating and explaining a supplied Risk Management table, including its risk categories and Risk Exposure calculations.
6. **Tool/workflow guidance:** Explaining how to create, upload, and manage a GitHub branch using the GitHub website. This was workflow guidance rather than a BadminBookingHub feature requirement.

AI-generated content was treated as a proposal for review, not as an automatically authoritative result. Project decisions and the final report wording remain the responsibility of the student and team.

---

## 3. Detailed interaction log

### 3.1 PA1 — Preliminary Problem Statement / project problem and environment

**Student's goal**

Develop a clear preliminary description of the current booking problem, the proposed system, the operating environment, and design/implementation constraints. The student wanted the content to be understandable, concise, and aligned with the project idea already documented in PA0.

**How the discussion proceeded**

- ChatGPT helped clarify the existing booking process: some badminton venues accept bookings through phone calls, Zalo, Facebook, or spreadsheets/notebooks.
- The discussion identified the effect of scattered booking information: players may have to contact multiple venues to ask about availability, prices, and locations; staff may struggle to keep court schedules and booking records consistent.
- The discussion covered common consequences such as wasted time, incorrect information, booking conflicts, manual price-calculation errors, and reduced customer satisfaction.
- The proposed system was framed as one web-based place to find and book courts, while helping staff and court owners organize booking information.
- The student clarified the target operating context: a responsive website usable on computers and mobile-device browsers, with staff mainly using computers at the front desk. The project would not include a dedicated mobile app.
- The student confirmed that local Docker deployment was sufficient for the course, while cloud deployment could be considered if time and resources allowed.
- The discussion reflected the team's intended Waterfall process and the V-model approach for test planning.
- The text emphasized the seven Must-have features from PA0 and treated optional features as dependent on the remaining time and resources.
- The concurrency requirement was described explicitly: if two users try to book the same court for overlapping time slots at the same time, only one booking can be confirmed and the other user must be told the slot is no longer available.

**AI contribution**

- Asked clarifying questions and organized the student's ideas into sections.
- Drafted and revised English paragraphs for background/current situation, proposed system/solution, operating environment, and constraints.
- Suggested making the simultaneous-booking rule explicit rather than describing double-booking prevention only as a general benefit.

**Student contribution and decisions**

- Supplied the project context and clarified intended system behavior and deployment expectations.
- Chose to keep the project web-based and not build a dedicated mobile application.
- Confirmed the project's five-member team context and intended development/test-planning approaches.
- Asked for clearer, more detailed wording in the Background and Current Situation section.
- Requested that the proposed section be renamed from **Proposed Solution** to **Proposed System** and supplied wording to guide its content.
- Specified a technology constraint: TypeScript on both frontend and backend, PostgreSQL for the database, and only free or low-cost services within the course budget.

**Verification and changes made**

- Content was discussed in relation to PA0's target users, seven Must-have features, scope, technology ideas, and known risks.
- The Background and Current Situation section was expanded to describe current manual booking methods, information being stored across different places, peak-hour demand (5 PM–9 PM), staff work, possible double bookings, manual price-calculation errors, and no-shows.
- The Proposed System section was rewritten to use a concise role-based description of Player, Staff, and Admin, plus explicit booking-conflict and booking-policy requirements.
- After review, the student asked whether the revised Proposed System fully covered the main ideas. ChatGPT recommended explicitly mentioning registration/login and automatic price calculation because those were part of the PA0 feature set.

**Result / status**

A revised English draft was created. The latest Proposed System draft states that players can register and log in, find courts, see prices and available slots, and make/cancel bookings; prices are calculated based on selected time slots including peak hours and weekends; staff handle schedules, check-ins, no-shows, and walk-in bookings; administrators/court owners manage accounts, roles, courts, opening hours, prices, and policies; overlapping bookings must not both be confirmed; and booking/cancellation policies must be enforced.

**Items the student/team should still verify**

- Ensure the final wording exactly reflects the team's approved PA0 scope and the instructor's expectations.
- Confirm that the technology stack and the requirement to use free/low-cost services are agreed by the team, not merely a draft proposal.
- Confirm any details such as price calculation and account registration/login against the final agreed requirements.

### 3.2 PA1 — Product Position Statement

**Student's goal**

Complete the Product Position Statement from the PA1 template, with simple English and wording consistent with BadminBookingHub's current problem and feature scope.

**How the discussion proceeded**

ChatGPT guided the student through the template elements instead of filling them in all at once:

- **For:** The student selected badminton players and badminton court owners as the target customers.
- **Who:** The need was described as an easier way to find and book courts and a more efficient way to manage booking schedules.
- **The (product name):** The student selected “A badminton court booking and management system.”
- **That:** The benefit was framed as helping players book more conveniently while helping court owners manage bookings efficiently and reduce errors.
- **Unlike:** The current alternative was described as manual booking through phone calls and messages, with schedules managed in notebooks, Excel spreadsheets, and separate communication channels.
- **Our product:** The student chose the combined differentiator: online booking, centralized management, and booking-rule validation to help prevent double bookings.

**AI contribution**

- Explained what each Product Position Statement element means.
- Offered alternative wordings and explained their trade-offs.
- Checked whether the chosen differentiator connected to the problem statement and the PA0 scope.
- Produced a formatted table after the student confirmed that section 1.2 was ready to finalize.

**Student contribution and decisions**

- Made the decisions about target customers, product category, benefits, current alternatives, and the product's primary differentiation.
- Explicitly chose to combine the three ideas of online booking, centralized management, and booking-rule validation.
- Confirmed “chốt 1.2” (finalize section 1.2) before receiving the formatted table.

**Verification and changes made**

The wording was checked against the previously discussed background/current situation and PA0's core ideas. It did not add a new major product capability beyond the discussed project scope.

**Result / status**

The finalized draft table reads:

| Element | Content |
|---|---|
| **For** | Badminton players and badminton court owners |
| **Who** | Need an easier way to find and book courts, and a more efficient way to manage booking schedules |
| **The BadminBookingHub** | Is a badminton court booking and management system |
| **That** | Helps players book courts more conveniently while helping court owners manage bookings efficiently and reduce errors |
| **Unlike** | Manual booking through phone calls and messages, and schedule management using notebooks, Excel spreadsheets, and separate communication channels |
| **Our product** | Combines online booking, centralized management, and booking rule validation to help prevent double bookings |

### 3.3 PA1 — Stakeholders and Users

**Student's goal**

Understand the PA1 Stakeholders and Users table and decide which groups should be listed, without receiving a completed table before understanding the choices.

**How the discussion proceeded**

- ChatGPT explained the three columns in the template: Stakeholder/user, Description, and Main interests.
- The initial candidate groups discussed were Player, Staff, Admin, Development Team, and potentially a project sponsor/court owner.
- The student selected Player, Staff, Admin, and Development Team for evaluation.
- ChatGPT explained that Player, Staff, and Admin are direct system users, while the Development Team is a project stakeholder but is not an end user of the operational booking system.
- The student clarified that **Admin is the court owner** in BadminBookingHub, so a separate Court Owner role should not automatically be added as a duplicate.
- ChatGPT compared the likely contents of a three-group version (Player, Staff, Admin) with a four-group version that also includes Development Team, explained the pros and cons, and recommended the three direct user groups if the section is intended to focus on operational users.

**AI contribution**

- Explained the difference between direct users and broader project stakeholders.
- Drafted illustrative descriptions and interests for each possible group.
- Explained the difference between a project sponsor and the development team, and cautioned against treating them as interchangeable.

**Student contribution and decisions**

- Selected the groups to evaluate.
- Clarified the project's role model by stating that Admin is the court owner.
- Asked to compare the table with and without the Development Team before choosing.

**Verification and changes made**

The candidate groups were compared with PA0, where Player, Staff, and Admin were identified as target-user groups. The discussion did not invent a separate Court Owner role after the student clarified that Admin represents the owner.

**Result / status**

The stakeholder analysis and two possible table structures were prepared. **The final decision on whether to include Development Team was not explicitly confirmed in the conversation captured here.** The recommendation was to focus on Player, Staff, and Admin unless the instructor/team wants the table to include broader project stakeholders.

### 3.4 Risk Management — evaluation and translation of a supplied example

**Student's goal**

Ask whether a supplied five-risk table was suitable and request a Vietnamese translation to understand the risk descriptions, probabilities, losses, Risk Exposure (RE), mitigation, contingency plans, and owners.

**AI contribution**

- Evaluated that the table had five risk categories and that the provided RE arithmetic was correct for the numbers shown.
- Translated the five supplied risks: technology/integration, people/experience, organisation/coordination, requirements/scope creep, and estimation/testing.
- Explained the formula `RE = Probability × Loss` and recalculated the supplied examples: 5625, 3750, 3750, 4500, and 5625.
- Flagged mismatches with BadminBookingHub, including references to a mobile app, video analysis, a 590-hour estimate, 15% contingency, sprints, a senior mentor, and freelancers, all of which would need confirmation rather than being copied automatically into the project's risk register.
- Suggested adapting the risk themes to BadminBookingHub: web frontend/backend/database integration; student-team experience; coordination and PA deadlines; scope changes/optional features; and effort underestimated for concurrency, booking rules, testing, and bug fixing.

**Student contribution and decisions**

- Supplied the risk table for review and translation.
- No final, approved BadminBookingHub risk register was confirmed in this exchange.

**Verification and changes made**

The arithmetic was checked against the stated numbers. The probability/loss labels were not claimed to be fully validated against the course lecture scale because that scale was not provided in the conversation. Potentially ungrounded estimates (590 hours and 15%) were flagged for confirmation.

**Result / status**

The supplied table was translated and reviewed, and adaptation guidance was provided. It should not be treated as the final BadminBookingHub risk register until the team checks the lecture's scale, confirms estimates, and assigns owners based on the actual project plan.

### 3.5 GitHub website workflow — branches and uploading PA1 documents

**Student's goal**

Learn how to create a branch and upload PA1 documentation using the GitHub website, because the repository had not been cloned to a local computer.

**AI contribution**

- Explained a branch-based workflow: create a branch, upload or edit the document on that branch, commit the change, verify the file, and create a Pull Request if team review is required.
- Suggested a branch name, `feature/pa1-documentation`, and a sample commit message, `docs: update PA1 documentation`.
- Explained how to rename a branch on the website and offered a fallback of creating another branch if the rename option was unavailable.
- Helped troubleshoot the error: `Branch not created. The branch refs/heads/docs/11-pa1-2.1-preliminary-problem-statement already exists.`
- Recommended checking the branches list and direct branch URL, avoiding further deletion until the state was understood, and testing whether a different branch name could be created.

**Student contribution and decisions**

- Clarified the environment: GitHub website, repository not cloned locally.
- Reported that a branch had been created, deleted, and could not be recreated.
- Reported that the named branch was not visible in the branch list but GitHub still returned `already exists`.

**Verification and changes made**

The guidance was tailored to the website workflow rather than Git commands on a local clone. The cause of the `already exists` error was not confirmed, and the conversation did not confirm that the issue was resolved.

**Result / status**

A safe troubleshooting path was provided. This part of the conversation is workflow support and should only be recorded in the course AI log if the course/team expects the log to include this type of project-work assistance; it is not a functional requirement or feature of BadminBookingHub.

---

## 4. Working pattern: how the student collaborated with ChatGPT

The conversation followed an iterative, student-led pattern:

1. The student stated a specific question or requested help with a section.
2. ChatGPT explained the purpose of that section or asked clarifying questions instead of immediately finalizing everything.
3. The student made explicit choices (for example, choosing the combined product differentiator and clarifying that Admin represents the court owner).
4. ChatGPT compared those choices with PA0 and highlighted omissions, inconsistencies, or assumptions that required confirmation.
5. ChatGPT proposed English wording or a table for review.
6. The student requested revisions when the wording did not fully match the intended content, including expanding the background section, renaming Proposed Solution to Proposed System, specifying the technology and cost constraints, and adding registration/login and automatic price calculation.
7. The student asked follow-up questions to understand the reasons for the suggestions before deciding what to keep.

This description reflects the observed working method; it does not mean that every AI suggestion was automatically accepted or that all project decisions are final.

## 5. Outputs drafted or discussed

- A preliminary problem statement covering background/current situation, proposed system/solution, operating environment, and design/implementation constraints.
- A Product Position Statement for BadminBookingHub, later confirmed by the student as finalized for section 1.2.
- A stakeholder analysis with candidate descriptions for Player, Staff, Admin, and Development Team, with the final inclusion of Development Team still to be confirmed.
- A review and Vietnamese translation of a supplied Risk Management example, plus guidance for adapting risks to BadminBookingHub.
- Step-by-step GitHub website guidance for branches, uploading documents, Pull Requests, and a branch-creation error.

## 6. Items requiring student/team confirmation

Before treating the material as final, the student/team should check:

- [ ] The final problem statement matches the current approved PA0 scope.
- [ ] The team agrees to the exact frontend/backend/database technology stack and the free/low-cost service constraint.
- [ ] The Proposed System wording reflects the seven Must-have features and does not accidentally promise optional features as mandatory.
- [ ] The stakeholder table's final scope is decided, especially whether to include Development Team.
- [ ] The Risk Management table uses the probability/loss scale required by the Project Management lecture.
- [ ] Any estimates (such as total hours and contingency percentage), mitigation actions, and risk owners reflect the real project plan.
- [ ] The GitHub branch issue is checked/resolved before deleting or recreating additional branches.
- [ ] The AI log reflects all significant AI use by the relevant team member(s), including other tools or tasks not captured in this record.

## 7. Suggested concise entry for the official PA1 AI Usage Log

The official PA1 form may prefer a compact table, while this file preserves the detail. The following is a draft to adapt to the team's reporting rules and actual usage:

| # | Member | Tool | Task / purpose | How the output was verified and changed |
|---|---|---|---|---|
| 1 | [Member name] | ChatGPT | Discussed, drafted, and refined the PA1 preliminary problem statement and proposed system for BadminBookingHub. | Compared the draft with PA0, clarified the existing booking problems, user roles, operating environment, technology constraints, and out-of-scope items; revised the wording and added missing agreed features such as registration/login and automatic price calculation. |
| 2 | [Member name] | ChatGPT | Developed the PA1 Product Position Statement. | Selected the target customers and product differentiation through discussion, then checked the final wording against PA0 and the project's current scope. |
| 3 | [Member name] | ChatGPT | Evaluated stakeholder/user candidates for PA1. | Compared direct users and project stakeholders with PA0; clarified that Admin represents the court owner. Final inclusion of the Development Team should be recorded according to the team's decision. |
| 4 | [Member name] | ChatGPT | Reviewed and translated a supplied Risk Management example and discussed how the risks could apply to BadminBookingHub. | Checked the RE calculations, flagged examples and estimates that did not match the project, and noted that the lecture scale and final risk values still require team verification. |

**Note:** Include GitHub workflow assistance in the official PA1 AI Usage Log only if it falls within the course's definition of significant AI use for the submitted deliverable. Do not claim verification or final approval that has not actually happened. Replace `[Member name]` with the actual person who used the tool, and consolidate entries only if permitted by the course instructions.

## 8. Recordkeeping note

This file is a detailed summary of AI assistance, decisions, and unresolved items. It is not a verbatim chat export and should not be described as one. Keep it in the team's agreed location (for example, `/docs/ai-usage/PA1-ai-chat-log.md`) if that location matches the repository's documentation convention, and update it when there are further significant AI-assisted tasks for PA1.
