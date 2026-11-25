# AI Usage Log – PA3 Software Design (Consolidated History)

**Project:** BadminBookingHub – Group 08  
**Phase:** PA3 – Software Design  
**Member:** Huỳnh Mạnh Tú  
**Role:** Business Analyst  
**AI tool:** ChatGPT (OpenAI)  
**Record consolidated:** 25/11/2026

> This record consolidates the AI assistance used by Huỳnh Mạnh Tú across the earlier Software Engineering (SE) discussion about BadminBookingHub PA3 and the follow-up work in the current conversation. It records this member's use only; it is not a statement about AI usage by other group members. Other members should complete their own AI Usage Log entries.
>
> The earlier SE conversation is not reproduced here as a complete verbatim transcript. Therefore, earlier work is summarized by evidenced activity area; exact prompt wording and per-turn dates are not invented. The PA2 SRS and the successive PA3 drafts are used as the basis for checking the work.

## 1. Purpose and scope of AI assistance

ChatGPT was used as a supporting tool during selected parts of PA3 to help the student understand, prepare, review, compare, and edit design documentation for BadminBookingHub. The assistance covered (including consolidating the history into this log):

- Preparation and review support for the Sequence Diagrams and Booking State Machine in the earlier SE discussion and its continuation.
- Checking consistency between PA3 design decisions and the PA2 Software Requirements Specification (SRS), especially use cases, business rules, acceptance criteria, and HTTP outcomes.
- Reviewing the section **Changes to the Requirements Since PA2** and distinguishing a proposed requirement refinement from a design clarification or implementation choice.
- Reviewing a group member's Data Design section: ERD, table specifications, normalisation, database integrity/concurrency mechanisms, and indexes.
- Helping with targeted Word document edits, Heading hierarchy, table of contents, diagram-image extraction, and image-quality troubleshooting.

ChatGPT was used as a reviewer, explainer, and drafting/editing assistant. It was not treated as the authority for project requirements, database implementation, or team decisions. The approved PA2 baseline and the current PA3 document remained the project references.

## 2. Consolidated activity log

### Activity 1 – Earlier SE discussion: Sequence and State Machine preparation

**Purpose**

Support the preparation and understanding of the booking-related Sequence Diagrams and the Booking State Machine for BadminBookingHub.

**Assistance requested (summary)**

- Help explain the purpose and structure of Sequence Diagrams and State Machine Diagrams for the project.
- Help organise the important booking flows and lifecycle concepts so that they can be represented in the PA3 design.
- Clarify the relationship between actors, controllers/services, database interactions, alternative flows, booking states, and state transitions.

**AI output / contribution**

ChatGPT provided explanatory and review support for the booking workflows and the structure of the diagrams. In the subsequent PA3 review, the five sequence-diagram use cases were identified as UC-06 (Book Court Online), UC-11 (Cancel My Booking), UC-13 (Check In Customer), UC-14 (Mark No-show), and UC-15 (Create Walk-in Booking). The discussion also covered the booking lifecycle states and the need to prevent overlapping active bookings, including concurrent requests.

**Student verification and changes**

The diagram content was checked against the PA2 use cases, business rules, and acceptance criteria. The student/group remained responsible for the final actors, messages, guards, status transitions, and diagram layout. No AI suggestion was treated as a formal change to the requirements without comparison with PA2.

### Activity 2 – Review of Sequence Diagrams and Booking State Machine

**Purpose**

Review the diagrams in PA3 for completeness and consistency with the approved PA2 requirements baseline.

**Assistance requested (summary)**

- Review the five sequence diagrams for their main, alternative, and exception flows.
- Check booking validation, availability, pricing, persistence, cancellation, check-in, no-show, and walk-in booking flows.
- Check the six booking statuses and allowed transitions against PA2 BR-25 and related rules.
- Identify whether the diagrams make the concurrent double-booking protection clear.
- Check actor permissions and use-case references against the correct PA2 version.

**AI output / contribution**

ChatGPT provided a structured review of the sequence flows and state transitions, identifying items that needed explicit explanation or cross-checking. It highlighted that an availability check before saving is not sufficient by itself to prevent two simultaneous requests from creating overlapping bookings; the design should rely on the database-level exclusion constraint and transaction handling described in the architecture/data design.

**Student verification and changes**

Suggestions were rechecked against the latest supplied PA2 baseline (`T08 - PA2(2).docx`). This was important because an earlier interpretation of actor permissions was corrected after checking PA2 FR-27–FR-29 and the statement that Admin can also perform Staff front-desk operations. Final actor permissions were therefore not changed to Staff-only where PA2 permits Staff and Admin. The student/group remained responsible for deciding which diagram changes to retain.

### Activity 3 – HTTP Error Mapping and Word Heading structure

**Purpose**

Make the error outcomes in §4.4 consistent with PA2 acceptance criteria and correct the document's heading hierarchy.

**Assistance requested (summary)**

- Compare the status codes in §4.4 with PA2 AC-05.1, AC-05.10, AC-07.6a/b, AC-07.10b, and AC-07.14.
- Review the mapping of `RuleViolationError`, `InvalidTransitionError`, `SlotTakenError`, `PriceChangedError`, and other domain errors.
- Check Heading 2/Heading 3 levels for §4.4, the five UC subsections, §4.5, and §4.6.
- Explain how to update Word's Table of Contents after changing heading styles.

**AI output / contribution**

The review identified the following mapping as consistent with the cited PA2 acceptance criteria:

| Domain error | HTTP outcome |
|---|---:|
| `RuleViolationError` | 400 Bad Request |
| `InvalidTransitionError` | 400 Bad Request |
| `SlotTakenError` | 409 Conflict |
| `PriceChangedError` | 409 Conflict |
| `NotFoundError` | 404 Not Found |
| `InvalidCredentialsError` | 401 Unauthorized |
| `LoginLockedError` | 429 Too Many Requests |

ChatGPT also explained that §4.4 should be Heading 2; UC-06, UC-11, UC-13, UC-14, and UC-15 should be Heading 3; and §4.5 and §4.6 should be Heading 2.

**Student verification and changes**

The mapping was checked against the named PA2 acceptance criteria. The revised PA3 version was reviewed for consistency between the §4.4 introduction and Figures 4.3–4.7. A stale `422` reference in the §4.2 relationship summary was also identified for correction. The student checked the Heading hierarchy and refreshed the Table of Contents. Final visual confirmation remains the student's responsibility.

### Activity 4 – Review of §8: Changes to the Requirements Since PA2

**Purpose**

Check whether items appearing in PA3 are actual changes to approved requirements, clarifications of choices already allowed by PA2, or implementation decisions.

**Assistance requested (summary)**

- Compare the PA3 change log with the PA2 requirements baseline.
- Verify whether the 24-hour session expiration (`NFR-16`) was already in PA2.
- Evaluate the proposed positive-even-integer constraint for hourly court rates.
- Evaluate the selection of HTTP 404 for the privacy/ownership case in AC-03.9.
- Distinguish requirement changes from design clarifications and implementation choices.

**AI output / contribution**

The comparison confirmed that PA2 already contains `NFR-16`: an authenticated session expires 24 hours after login, logout invalidates the session, and subsequent requests using an expired/invalidated session return HTTP 401. Therefore, `NFR-16` must not be presented as a new PA3 requirement.

The review identified two items to document:

1. **Hourly-rate refinement:** PA2 UC-20 requires a positive whole-number VND hourly rate. PA3 adds an even-integer restriction so that half the hourly rate, used for each 30-minute block under BR-17, remains a whole-VND value consistent with BR-36. This is a proposed refinement that requires team approval.
2. **AC-03.9 response selection:** PA2 permits either HTTP 403 or HTTP 404 when a Player tries to access another Player's booking. PA3 selects HTTP 404 consistently. This is a design clarification/selection of an outcome already allowed by PA2, not a new business capability.

The review also confirmed that PostgreSQL server-side sessions, PostgreSQL GiST exclusion constraints, and two-second polling are design/implementation choices used to realise existing PA2 requirements rather than new requirements in themselves.

**Student verification and changes**

The conclusions were checked against PA2 `NFR-16`, `UC-20`, `BR-17`, `BR-36`, and `AC-03.9`, then compared with PA3 §8. The latest PA3 draft records the hourly-rate refinement and HTTP 404 selection and leaves the approval date to be entered after the actual design review. No approval is claimed in this log.

### Activity 5 – Peer review of Data Design (§5.1–§5.3)

**Purpose**

Review the Data Design prepared by a group member and provide feedback on consistency, database integrity, normalisation, and query performance.

**Assistance requested (summary)**

- Review the 3NF ERD and mapping between domain concepts and relational tables.
- Review table specifications: data types, PK/FK, nullability, uniqueness, CHECK constraints, and descriptions.
- Review the explanations of 1NF, 2NF, and 3NF.
- Review the database-level concurrency/privacy mechanisms and indexes for frequent queries.

**AI output / contribution**

ChatGPT provided a review and suggested clarifications/corrections concerning:

- The minimum booking duration and alignment of `start_time` to 30-minute boundaries.
- Consistency between `ONLINE` and `WALK_IN` booking data and the corresponding walk-in customer consent fields.
- The expression and wording of table-level CHECK constraints.
- Splitting grouped columns in the table specification so that each column's type/default/constraint is unambiguous.
- Numbering and explanations in the normalisation section.
- The distinction between a declarative database constraint and `SELECT ... FOR UPDATE` row-level locking.
- Index column order and whether the described query predicates/orderings match the proposed index.

**Student verification and changes**

The comments were compared with PA2 business rules and the latest PA3 schema text. They were presented as review guidance for the group member, not as proof that the SQL was implemented or tested. The developer still needs to validate the final definitions against the actual PostgreSQL migrations and use `EXPLAIN ANALYZE`/load testing before making performance claims.

### Activity 6 – Word document editing and diagram-image support

**Purpose**

Help maintain consistency in the PA3 Word document and handle diagram images when the user could not directly edit or export them clearly.

**Assistance requested (summary)**

- Apply targeted edits to the PA3 Word document while preserving unrelated sections.
- Correct labels and error outcomes in selected Sequence Diagram images.
- Explain how to apply Heading styles and update the Word Table of Contents.
- Extract embedded diagram images and troubleshoot why images exported from Word still appeared blurry.

**AI output / contribution**

ChatGPT produced revised working copies of the Word document, extracted the selected embedded Sequence Diagram images, and explained the limitation of raster images: extracting a PNG preserves the embedded image but does not restore resolution that was already lost. SVG or a new high-resolution export from the editable diagram source was recommended for crisp diagrams.

**Student verification and changes**

The revised files and selected rendered pages were checked. The student was advised to review the final Word document and update its Table of Contents. No claim is made that extracting a raster image increased its quality or that an editable SVG source was available.

## 3. Representative prompt summaries

The following are summaries of requests made across the earlier SE discussion and the follow-up conversation. They are not presented as verbatim quotations:

1. Help prepare and understand the Sequence Diagrams and State Machine for the BadminBookingHub booking workflows.
2. Review the Sequence and State Machine diagrams against the PA2 SRS and identify missing or inconsistent flows, actors, references, and transitions.
3. Compare the HTTP status codes in §4.4 with the cited PA2 acceptance criteria and propose a consistent `ErrorMapper` mapping.
4. Explain the correct Heading hierarchy for §4.4–§4.6 and how to refresh the Word Table of Contents.
5. Compare §8 with the actual PA2 baseline, including `NFR-16`, hourly rate validation, and AC-03.9.
6. Review a group member's ERD, table specifications, 3NF explanation, constraints, and indexes.
7. Edit the relevant Word document sections and export/extract the modified diagrams without altering unrelated content.
8. Consolidate the AI Usage Log across the earlier SE discussion and the current follow-up work for the PA3 document and GitHub repository.

## 4. Project sources used for verification

The following project documents were used or referenced in the review process:

- **PA1:** `PA1 - 08.docx.pdf` – project plan and phase deadlines, including the PA3 design milestone.
- **PA2:** `T08 - PA2(2).docx` – Software Requirements Specification baseline, including FRs, NFRs, BRs, acceptance criteria, and Use Case Specifications.
- **PA3 working drafts:** `T08 - PA3(3).docx`, `T08 - PA3(4).docx`, `T08 - PA3(5).docx`, `T08 - PA3(6).docx`, and `T08 - PA3(7).docx` – successive Software Design drafts reviewed during the work.

The PA2 SRS was the authoritative source for checking project requirements. The PA3 drafts were used to inspect how the design and the documented decisions evolved.

## 5. Human verification, limitations, and pending decisions

- AI output is advisory. It does not replace review by the Project Manager, instructor, or group.
- The positive-even-integer hourly-rate refinement requires an explicit team decision because PA2 UC-20 states that rates must be positive whole numbers of VND but does not state that they must be even.
- The use of HTTP 404 for AC-03.9 is a selected design outcome from the two options (403 or 404) already allowed by PA2. If the team's design-review process requires approval, the decision and approval date should be recorded after the review.
- `NFR-16` (24-hour session expiration) is part of PA2 and is not a new PA3 requirement.
- The final database schema must be compared with the actual migrations. CHECK constraints, exclusion constraints, transaction behaviour, and indexes cannot be considered implemented solely because they appear in design text.
- Index performance should be supported by `EXPLAIN ANALYZE` and the planned load tests; AI review does not establish measured performance.
- Earlier SE conversation details are summarized at activity level because a complete verbatim transcript is not part of this record. No exact prompt wording, per-turn dates, or team approvals have been fabricated.
- This log does not claim that ChatGPT independently authored every PA3 section, diagram, database schema, UI screen, or architecture decision. It records the work areas for which AI assistance is evidenced in the available discussion and documents.

## 6. Responsibility statement

ChatGPT was used as a supporting tool for explanation, review, comparison, drafting, and document-editing assistance. Huỳnh Mạnh Tú remains responsible for checking the output against the approved PA2 baseline, deciding which suggestions to retain, validating the final document, and obtaining team approval for any proposed requirement refinement or design decision that requires approval.

---

**Record status:** Consolidated individual AI Usage Log for PA3.  
**Last consolidated:** 25/11/2026.
