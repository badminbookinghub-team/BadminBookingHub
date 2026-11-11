# Detailed AI Usage Log — PA2 Contributions by Tú

**Project:** BadminBookingHub — Badminton Court Booking and Management System  
**Document:** PA2 — Software Requirements Specification (SRS)  
**Member:** Tú  
**AI tool:** ChatGPT  
**Purpose of this file:** Detailed supporting record for the concise AI Usage Log in Section 11 of PA2.

> **Scope clarification:** This log records the work Tú carried out with ChatGPT. It distinguishes (1) sections Tú directly worked on, and (2) other team members' content that Tú asked ChatGPT to explain or summarize so that Tú could understand the whole system and check cross-section consistency. It does not claim that Tú authored every section of PA2.

---

## 1. Overview of AI assistance

ChatGPT was used as a supporting tool throughout Tú's PA2 work. The assistance included understanding requirements, drafting and refining content, reviewing teammate feedback, checking consistency, explaining Business Analysis concepts, and summarizing material written by other team members.

The main work directly carried out by Tú with ChatGPT covered:

- Section 4 — Stakeholders.
- Section 5.1 — Functional Requirements (FRs), especially understanding, drafting, refining, and checking requirement statements and their scope.
- Section 6 — Use Case Actors and Use Case List.
- Section 7 — Use Case Specifications, including the detailed specifications that Tú worked on and reviewed.
- Section 11 — AI Usage Log.
- Review and checking of Tú's assigned sections and feedback received from teammates.

In addition, Tú used ChatGPT to read, explain, and summarize other members' PA2 content. This was intended to help Tú understand the complete system and identify dependencies or inconsistencies; it does not mean those sections were Tú's own authored contributions.

## 2. Detailed activity records

### 2.1 Section 4 — Stakeholders

**Purpose**

Understand and prepare the Stakeholders section by identifying the parties affected by or interacting with BadminBookingHub, and describing their roles, interests, and expectations.

**How ChatGPT assisted**

- Explained the difference between a stakeholder and a UML Actor.
- Helped review the stakeholder set relevant to the project, including Player, Guest, Staff, Admin, Walk-in Customer, Development Team, Course Instructor / TA, and external services where applicable.
- Helped distinguish a person or organization that has an interest in the system from an Actor that directly interacts with the system.
- Reviewed stakeholder descriptions to make them more specific to the badminton court booking and management context.
- Discussed why Walk-in Customer can remain a stakeholder even when Staff performs the booking operation in the application on the customer's behalf.
- Discussed the role of E-wallet Payment Service and Email Delivery Service in relation to optional features.

**How Tú verified and changed the output**

Tú compared the suggestions with the project scope, PA1 materials, current PA2 requirements, and the actual workflows. Tú revised the stakeholder descriptions and classifications where needed and treated uncertain actor/stakeholder decisions as matters for team confirmation.

**Result / contribution**

A clearer Stakeholders section, with a distinction between stakeholders and direct system Actors that could be used later when constructing the Use Case Model.

### 2.2 Section 5.1 — Functional Requirements (FRs)

**Purpose**

Understand, draft, organize, and refine the functional behavior expected from BadminBookingHub.

**How ChatGPT assisted**

- Helped interpret the project scope and group functionality into features.
- Helped formulate requirement statements in a clearer and more consistent style.
- Explained the purpose of requirement identifiers, feature grouping, and MoSCoW priorities.
- Helped review whether proposed requirements described system behavior rather than implementation details.
- Discussed whether a feature belonged in the agreed scope or should be treated as optional, deferred, or outside the current project scope.
- Helped check relationships between requirements and related business processes, including registration, court catalog, availability, online booking, cancellation, front-desk operations, court administration, deposits, booking history, and email notifications.
- Helped interpret teammate feedback about FR renumbering and the effect of changed identifiers on Use Case traceability.

**How Tú verified and changed the output**

Tú compared suggested wording and mappings with the latest PA2 document, project objectives, agreed feature scope, stakeholder needs, and team decisions. Tú did not treat AI-proposed requirement IDs or scope changes as authoritative; identifiers and content were checked against the current PA2 baseline.

**Result / contribution**

Improved understanding and refinement of the FRs relevant to Tú's assigned work, plus a clearer basis for mapping Use Cases to the correct current FR identifiers.

### 2.3 Section 6 — Use Case Actors

**Purpose**

Identify which external roles or systems interact directly with BadminBookingHub and represent them correctly in the Use Case Model.

**How ChatGPT assisted**

- Explained the UML concept of an Actor and how it differs from a stakeholder.
- Reviewed the roles of Guest, Player, Staff, Admin, Walk-in Customer, E-wallet Payment Service, and Email Delivery Service.
- Discussed whether Guest should be an Actor when unauthenticated users can view the court catalog and availability.
- Discussed why Walk-in Customer should not automatically be modeled as an Actor if Staff enters the customer's booking details.
- Discussed the use of an abstract `System User` Actor to represent common authentication behavior such as Log In and Log Out.
- Discussed whether a time-triggered background process requires a separate Scheduler or Time Actor, depending on the course modeling convention and system boundary.
- Reviewed primary and secondary Actor distinctions where external services are involved.

**How Tú verified and changed the output**

Tú checked the proposed Actors against the Stakeholders section, FRs, Use Case descriptions, and the actual interaction flows. Tú considered teammate feedback and revised the Actor model where appropriate. Unresolved modeling choices were identified for discussion rather than being presented as confirmed business requirements.

**Result / contribution**

A more consistent Actor set and a better understanding of why some stakeholders are not necessarily Actors.

### 2.4 Section 6 — Use Case List

**Purpose**

Create and review the Use Case List so that each Use Case represents a meaningful system service or actor goal and can be traced to requirements.

**How ChatGPT assisted**

- Helped identify candidate Use Cases from the FRs and stakeholder interactions.
- Helped refine Use Case names so they describe goals or services clearly.
- Reviewed whether proposed Use Cases were independent actor goals or supporting behaviors that could be modeled using `<<include>>`.
- Explained the meaning and direction of `<<include>>` and `<<extend>>`.
- Reviewed the use of actor generalization, including the optional abstract `System User`.
- Helped map Use Cases to current FR identifiers and identify outdated references after FR renumbering.
- Discussed whether a capability should be a separate Use Case or remain part of another Use Case's flow.
- Reviewed teammate suggestions about Guest, Public Holidays, booking-price calculation, rule validation, availability checking, deposit payment, refunds, and email notifications.

**How Tú verified and changed the output**

Tú compared the Use Case List with the latest FRs, stakeholder roles, Use Case Diagram, and detailed specifications. Tú checked that IDs and Related FR references matched the current PA2 version and considered whether each Use Case had a distinct purpose. Changes that affected scope or business policy were left for team confirmation.

**Result / contribution**

A Use Case List intended to remain consistent with the Actors, Use Case Diagram, FRs, and Section 7 specifications.

### 2.5 Section 7 — Use Case Specifications

**Purpose**

Prepare detailed Use Case Specifications and understand the business logic behind each flow, rather than only improving wording.

**How ChatGPT assisted**

ChatGPT helped Tú work through specification elements such as:

- Use Case ID and name.
- Brief description.
- Primary and secondary Actors.
- Priority and Related Requirements.
- Trigger.
- Preconditions and postconditions.
- Main Flow.
- Alternative Flows.
- Exception Flows.
- Related Business Rules and Non-Functional Requirements.

The assistance focused on understanding the responsibility of each flow and checking whether the behavior was supported by the source requirements.

**Specific review activities**

- Reviewed the separation between viewing the court catalog and searching court availability.
- Reviewed booking-related flows and supporting Use Cases such as calculating booking price, validating booking rules, and checking court availability.
- Discussed how online booking and walk-in booking differ where booking rules apply.
- Reviewed booking status behavior and the conditions under which a slot is considered occupied or available.
- Reviewed cancellation behavior, including ownership, cancellation deadlines, booking start time, and the distinction between cancellation and refund processing.
- Reviewed the distinction between a valid alternative outcome and an exception caused by a system failure.
- Checked whether Alternative Flow and Exception Flow references pointed to existing Main Flow steps.
- Reviewed whether BR and NFR identifiers were relevant to the behavior described by a particular Use Case.
- Considered teammate feedback about keeping internal implementation details, UI labels, and duplicated behavior out of the specifications.
- Discussed the importance of not repeating another Use Case's responsibility inside the current Use Case.

**How Tú verified and changed the output**

Tú compared the proposed flows with the latest PA2 FRs, BRs, NFRs, ACs, and teammate review comments. Tú checked requirement identifiers, business conditions, status transitions, step references, and consistency between related Use Cases. AI suggestions were treated as proposals and were revised or questioned if they were not supported by the PA2 source.

**Result / contribution**

More detailed and consistent Use Case Specifications, with a stronger focus on business logic, traceability, and testability.

### 2.6 Section 11 — AI Usage Log

**Purpose**

Prepare a transparent record of how ChatGPT supported Tú's PA2 work.

**How ChatGPT assisted**

- Helped identify the work areas that should be disclosed.
- Helped summarize the tasks in concise English suitable for the SRS table.
- Helped distinguish Tú's direct work from other team members' work that Tú only read or summarized.
- Helped describe how AI suggestions were checked and changed.

**How Tú verified and changed the output**

Tú reviewed the log to ensure it reflected the actual collaboration and did not claim authorship of sections prepared by other members. The final disclosure should be updated if additional AI-assisted work is included before submission.

**Result / contribution**

A concise Section 11 entry and this detailed supporting record.

### 2.7 Review and checking of Tú's assigned work

**Purpose**

Review the quality and consistency of Tú's PA2 contributions and respond to teammate feedback.

**How ChatGPT assisted**

- Reviewed Stakeholders, FR-related work, Actors, Use Case List, and Use Case Specifications.
- Read teammate review comments and explained what each suggested change meant.
- Helped distinguish changes that should be accepted, changes that needed discussion, and changes that might be unnecessary or incorrect.
- Checked whether a proposed correction was supported by the latest PA2 requirements.
- Identified possible duplicate responsibilities between Use Cases.
- Checked consistency of requirement references and Use Case step references.
- Explained BA review principles: each behavior should be permitted by an FR, governed by applicable BRs, and verifiable through ACs.
- Helped formulate questions for the PM or team when a business rule was ambiguous.

**How Tú verified and changed the output**

Tú checked review findings against the current PA2 file and the teammate's comments. Tú did not automatically accept every review suggestion. Corrections, ambiguities, and team decisions were kept distinct.

**Result / contribution**

A more systematic review process and a clearer understanding of the reasoning behind changes to the SRS.

### 2.8 Reading and summarizing other members' work

**Purpose**

Understand the complete PA2 document even where a section was primarily prepared by another team member, so Tú could perform BA reviews and check dependencies with the sections Tú owned.

**How ChatGPT assisted**

- Explained unfamiliar or complex sections in Vietnamese while retaining English technical terms.
- Summarized requirements, business rules, acceptance criteria, prototype information, and other material supplied from the team's PA2 document.
- Explained how other members' content related to Stakeholders, FRs, Actors, Use Cases, and Use Case Specifications.
- Helped identify cross-section dependencies and possible inconsistencies.
- Helped Tú understand the rationale behind business rules and acceptance criteria before reviewing Use Case flows.

**How Tú verified and changed the output**

The supplied PA2 document and teammate materials were treated as the source. Tú checked explanations against those materials and used the summaries to understand and review the overall system. This activity is recorded as understanding and review support, not as authorship of the other members' sections.

**Result / contribution**

Better understanding of the complete BadminBookingHub SRS and improved ability to review whether Tú's assigned sections aligned with the work of other members.

---

## 3. Summary of Tú's direct contributions and supporting activities

| Work area | Nature of Tú's work with ChatGPT |
|---|---|
| Stakeholders | Direct analysis, drafting support, refinement, and review |
| Functional Requirements (FRs) | Understanding, drafting/refinement support, checking scope and traceability |
| Use Case Actors | Direct analysis and review of Actor selection and relationships |
| Use Case List | Direct drafting/refinement support and consistency checking |
| Use Case Specifications | Detailed drafting, explanation, business-logic analysis, and review |
| AI Usage Log | Direct preparation and refinement |
| Review and checking | Review of Tú's assigned work and analysis of teammate feedback |
| Other members' PA2 sections | Reading, explanation, and summarization to understand the whole system; not claimed as authorship |

## 4. Verification principles used

When working with ChatGPT, Tú used the following principles to assess AI-generated suggestions:

1. **Source alignment:** Compare suggestions with the latest PA2 document and relevant PA1 context.
2. **Requirement traceability:** Check that each Use Case behavior is supported by an FR and that relevant BRs, NFRs, and ACs are correctly referenced.
3. **Business-rule correctness:** Check conditions, limits, status transitions, timing rules, pricing rules, cancellation, and availability behavior against the documented rules.
4. **Use Case responsibility:** Avoid duplicating another Use Case's responsibility or describing implementation details as actor goals.
5. **Testability:** Ensure flows and outcomes can be observed and verified through Acceptance Criteria.
6. **Uncertainty management:** Do not turn assumptions into approved requirements. Raise ambiguous business decisions with the PM or team.
7. **Authorship transparency:** Distinguish Tú's own contributions from other members' work that Tú only studied or summarized.

## 5. Limitations and responsibility

- AI-generated content may be incomplete, inaccurate, or based on an incorrect interpretation of an ambiguous requirement.
- AI suggestions do not constitute approval by the PM, stakeholders, instructor, or project team.
- Tú remains responsible for understanding, checking, and approving the content submitted under Tú's contribution.
- The project team remains responsible for final scope, business-policy decisions, requirement approval, and the PA2 baseline.
- This detailed file supplements the concise AI Usage Log in Section 11; it does not replace the required SRS table.

---

**Disclosure statement:** ChatGPT supported Tú with analysis, explanation, drafting, refinement, and review of the work areas listed above. Tú checked the outputs against the project materials and team feedback. Other members' work was read and summarized to support understanding and consistency checking; it is not claimed as Tú's authored contribution.
