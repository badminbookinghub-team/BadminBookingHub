# PA3 – AI Usage Log (detailed)

**Tool:** Claude (Anthropic), used in a chat attached to our project files. During the work the chat ran on Claude Sonnet 5.5 and Claude Opus 5.5.



### Entry 1 – Consistency check of Sections 2–8

**Why:** PA3 is written by several members. Before submission I wanted one pass that compares the sections with each other and with PA2.

**What I gave the tool:** The PA3 section files (each file number is the section number), the PA2 SRS, the teacher's PA3 template, the project guidelines and rubric, and the slides of lectures 06 and 07.

**What I asked for:** Check each section for consistency, say what should change and why. Apply the rule that the lower-numbered section and PA2 take priority.

**What the tool produced:** A list of 16 differences, for example:
- The cross-reference to the index section in Section 3.1 and in ADR-001 points to the wrong sub-section.
- Index and column names in the traceability table of Section 7 differ from Section 5.
- Section 8 does not mention the even-number CHECK on the booking length or the payment retry.
- The title of ADR-005 does not match its content.
- The error mapper in Section 4 uses HTTP 422 where the other sections use 400.
- The `UserAccount` class does not list the consent and deletion-request attributes that the database has.

**What I checked:** I opened the PA2 clause or the PA3 table behind each item. A suggestion is accepted only if it agrees with PA2 and the lower-numbered sections.

**What I changed:** Only Section 5 (my section). The other items stay as a mapping for the owners of Sections 3, 4, 7 and 8, because those sections need the team's agreement.

---

### Entry 2 – ERD check and redraw (Section 5.1)

**Why:** The Section 5 file contained tables but no real diagram, and I needed one in crow's foot notation that looks like the sample I was given.

**What I asked for:** Check whether the existing ERD was correct and redraw it. I also asked whether the existing diagram had really been checked, or only copied.

**What the tool produced:**
- Figure 5.1a: conceptual EER (weak entities with a double border, partial identifiers, the ONLINE / WALK_IN subtypes with a total and disjoint circle, composite attributes in brackets, dashed boxes for the Should features F08 and F09).
- Figure 5.1b: relational schema with PK, FK and UQ marks.
- One editable `.drawio` file with both figures.

**What I checked:**
- Each entity, attribute, key and cardinality against Tables 5.1 and 5.2 and the PA2 business rules.
- The cardinality symbols one by one (exactly one, zero or one, one or many, zero or many).
- Every rendered image. Several labels overlapped lines or boxes and the underline of some keys was too long. These were fixed and the images were rendered again.

**What I changed or decided:** I chose to show the two forms of the diagram (conceptual and relational) and to keep the F08 and F09 entities dashed. I later asked for the primary keys to have their own names (`user_id`, `booking_id`, …) so they are not all called `id`.

---

### Entry 3 – Rewrite of Section 5 (Data Design)

**Why:** The draft of Section 5 did not follow the layout I used in my database course report, and Section 5.3 did not bring every relation to BCNF.

**What I asked for:**
- 5.1: ERD, then the logical design (relational schema and functional dependencies), in the same layout as my earlier report.
- 5.2: one specification table per table (attribute, description, data type, constraint, explanation), plus derived values and value-meaning tables.
- 5.3: list the relations that are not in BCNF, transform them to BCNF, then show all relations in BCNF, then the index table in the style of the sample.
- Ask me before doing anything that is not clear.

**Questions the tool asked and my answers:**
- Specification layout: per table, like the sample images.
- The `time_range` column on bookings: using an expression in the exclusion constraint was too complex, so keep `time_range`, show the relation as 2NF first, then normalise it to BCNF.
- Small fixes to apply: add `created_by = player_id` for online bookings, `password_hash` as CHAR(60), `public_holidays.name` may be NULL.
- Output format: a `.docx` file that I can paste into PA3.
- BCNF approach: handle both `bookings` and `sessions`.

**What the tool produced:** A 17-page Word file with the three sub-sections, 11 relations, functional dependencies, 11 specification tables, the BCNF analysis and a table of 10 indexes.

**What I checked:**
- Every table, column, data type and constraint against Tables 5.1 and 5.2 and the business rules.
- The functional dependencies one relation at a time.
- The BCNF steps. `sessions` and `bookings` each had a transitive dependency (`session_id → created_at → expires_at`, and `booking_id → (start_time, end_time) → time_range`). Both were fixed by removing a column that can be computed (`expires_at`, and `start_time` and `end_time`).
- That the final relations and the figures agree with each other.

**What I changed or decided during review:**
- Online payment can be retried, so a booking can have several deposit payment attempts (0..N). This changed the schema and added a unique index for the one open or paid payment.
- Primary keys got distinct names.
- I asked what `booking_settings` is for and why some columns are grey with a † in Figure 5.2. The answer was that the table holds the one row of Admin-editable policy values, and that the † columns are the ones removed during normalisation. The question of whether Figure 5.2 should show the final schema is still open for me.
- I asked whether the index "Type" wording could follow the sample (Clustered, Non-clustered, Covering, Filtered). PostgreSQL has no clustered index and needs GiST for the time range, so the wording is still being decided.

---

### Entry 4 – Hold time versus UC-23

**Why:** UC-23 says bookings created before a policy change keep their status and time, and that new values apply only to bookings created afterwards. The design computed the end of the hold from the current `holding_minutes`.

**What I asked for:** Explain the issue, say whether it is real, and say what changes in the later sections if the ERD is changed.

**What the tool produced:**
- The failure case: a booking created with a 10-minute hold, then the Admin lowers the hold to 2 minutes, and the scheduler cancels the booking early.
- A fix: store `hold_expires_at` on the booking when it is created and use only that value afterwards.
- An impact table for Sections 3 to 8 and for PA4.

**What I checked:** I read UC-23, FR-32, FR-34, BR-21 and the glossary of the payment-holding period in PA2. I also read the places in Sections 3, 4, 5, 6 and 7 that mention the hold. Section 6 already says that the countdown uses the server-side hold expiry, which supports the fix. Section 8 does not need a change because this is a design correction, not a requirement change.

**What I changed:**
- In Section 5: the new column (nullable, with `chk_bookings_hold`), the functional dependency, a short paragraph in 5.3.2 explaining why this column is kept while `sessions.expires_at` is removed, the index `idx_bookings_pending_expiry`, and both figures.
- Not changed by me: Section 4 (`holdExpiresAt`, `createOnline`, `expireUnpaid`, state machine, sequence diagram, class diagram), Section 7 (data column of the deposit rules) and the PA4 test case. These are listed for their owners.

---

### Entry 5 – Building the Word file

**Why:** Section 5 is long and has many tables, so I used a script to generate the Word file, then checked the result.

**What the tool produced:** A script that builds the `.docx` (A4, headings, bullet lists, tables, the two figures) and the file itself.

**What I checked:**
- Rendered the file to PDF and looked at the changed pages.
- Ran the validator for the `.docx` format.
- Opened the file in Word myself. The `bookings` table ran outside the page, because one constraint (the list of statuses) has no spaces and Word widened the column.

**What I changed:** The tables now have a fixed width and long SQL lists can wrap inside the cell. I rendered the file again and checked the page.

---

## 3. What was my own work

- The decisions listed above: per-table specification, which relations to normalise and how, the extra CHECK and column fixes, payment retry, distinct primary-key names, storing the hold deadline.
- Reading and accepting or rejecting each point of the consistency list.
- Checking the output against PA2, the template and the lectures.
- Deciding which sections I may change (Section 5 only) and keeping the rest as notes for the section owners.

## 4. Limits and open points

- The SQL in Section 5 has not been run on a PostgreSQL database yet. It was checked by reading and against the business rules.
- Figure 5.2 still shows the † columns of the initial schema. I still need to decide whether it should show the final schema.
- The wording of the index "Type" column is still to be decided.
- The Word file was rendered with LibreOffice and opened once in Word. A final look in Word before submission is still needed.

## 5. Data handling

Only project material was given to the tool: the PA2 SRS, the PA3 sections, the lecture slides, my own earlier database report and the sample images from the teacher. No passwords, keys or other personal or confidential data were entered. I can explain every part of Section 5 and the changes listed above.
