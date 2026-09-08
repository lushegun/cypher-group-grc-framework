<!--
=============================================================================
FICTIONAL DATA NOTICE
All employee names, IDs, departments, dates and statuses below are INVENTED
for the fictional company Cypher Group Inc. No real personal data appears here.
Author: O.S | Portfolio project 1 of 7 | September 2026
=============================================================================
Cypher Group Inc. — Employee Policy Sign-off and Training Tracker
Tracker ID: CGI-TRK-001
Version: 1.0
Classification: Confidential (contains employee records)
Owner: Sofia Lindqvist, Head of People and Operations
Approved by: Jerry Olugboye, Chief Executive Officer
Approval date: 01 September 2026
Update cadence: Weekly, and on every joiner, mover and leaver event
Reporting cadence: Monthly summary to the CTO; quarterly to the CEO
Data as at: 05 September 2026
> **All data below is fictional.** This tracker demonstrates how policy
> acknowledgement and security training completion are evidenced.
---
Purpose of this tracker
This is the evidence artefact for the policy pack. A policy that exists but
that nobody has acknowledged provides no assurance and satisfies no auditor. When
a customer's security questionnaire asks "Do all employees acknowledge an
acceptable use policy?", this tracker is the answer, and the auditor will ask to
see it rather than take the answer on trust.
It supports CGI-POL-001 section 6.2, CGI-POL-003 section 4.3.5 (access is
not activated until sign-off is complete) and CGI-POL-002 section 4.3.2 (MFA
enrolled within one business day).
---
Main tracker
Employee ID	Name	Department	AUP Sign-off Status	MFA Verification	Training Completion (Yes/No)	Last Updated
CGI-014	Priya Raman	Engineering	Signed	Verified	Yes	2026-09-02
CGI-027	Tomas Whitfield	IT Operations	Signed	Verified	Yes	2026-09-02
CGI-039	Amara Boateng	Customer Success	Signed	Verified	Yes	2026-09-04
CGI-045	Jonas Keller	Finance	Pending	Verified	No	2026-09-05
CGI-050	Lena Fischer	Sales	Not Started	Not Enrolled	No	2026-09-05
Notes on these rows (why they look like this)
CGI-045 Jonas Keller — MFA is verified but the AUP is unsigned and training is incomplete. Automated reminder sent 05 September 2026; escalation to his line manager due 10 September 2026 if still outstanding.
CGI-050 Lena Fischer — a joiner with a start date of 15 September 2026. Her account exists but is not activated, in line with CGI-POL-003 section 4.3.5. Nothing is wrong here; this is the control working as designed.
A tracker with every row green is usually a tracker nobody is maintaining. Auditors expect to see in-progress rows and evidence that they are being chased.
---
Status value definitions
Use only these values, so the tracker filters and pivots cleanly in a spreadsheet.
Column	Permitted values
AUP Sign-off Status	Signed / Pending / Not Started / Overdue / Not Applicable
MFA Verification	Verified / Pending / Not Enrolled / Exception
Training Completion	Yes / No
Why single values matter. Each cell holds one fact and nothing else. Do not
write "Signed on 2 Sep by Priya" in a status cell — the moment you do, you cannot
filter by status, count by status, or build a chart from the column. This is the
difference between a tracker and a document that looks like a tracker.
---
Extended tracker (optional upgrade)
If you want richer evidence, add these columns. Keep the seven core columns above
in the same positions so any existing report or filter still works.
Employee ID	Name	Department	Start Date	AUP Sign-off Status	AUP Sign-off Date	Policy Pack Version Acknowledged	MFA Verification	MFA Factor Type	Training Completion (Yes/No)	Training Completion Date	Next Annual Re-acknowledgement Due	Line Manager	Last Updated
CGI-014	Priya Raman	Engineering	2023-02-06	Signed	2026-09-02	1.0	Verified	Hardware Key	Yes	2026-09-02	2027-09-02	Daniel Okafor	2026-09-02
CGI-027	Tomas Whitfield	IT Operations	2024-05-13	Signed	2026-09-02	1.0	Verified	Hardware Key	Yes	2026-09-02	2027-09-02	Priya Raman	2026-09-02
CGI-039	Amara Boateng	Customer Success	2024-11-04	Signed	2026-09-04	1.0	Verified	Authenticator App	Yes	2026-09-04	2027-09-04	Daniel Okafor	2026-09-04
CGI-045	Jonas Keller	Finance	2025-08-18	Pending	Not Applicable	Not Applicable	Verified	Authenticator App	No	Not Applicable	Not Applicable	Jerry Olugboye	2026-09-05
CGI-050	Lena Fischer	Sales	2026-09-15	Not Started	Not Applicable	Not Applicable	Not Enrolled	Not Applicable	No	Not Applicable	Not Applicable	Amara Boateng	2026-09-05
---
Monthly compliance summary (reported to the CTO)
Metric	Value	Target	Status
Total personnel in scope	5	5	On track
AUP signed	3	5	Below target
AUP sign-off rate (percentage)	60	100	Below target
MFA verified	4	5	Below target
MFA coverage rate (percentage)	80	100	Below target
Security training completed	3	5	Below target
Training completion rate (percentage)	60	100	Below target
Overdue beyond 10 business days	0	0	On track
Joiners pending activation	1	Not applicable	Expected
> **Reading note.** This sample covers five illustrative personnel records rather
> than the full 50-person population, so the percentages describe the sample, not
> the company. A production tracker would carry one row per person.
---
Escalation rules
Condition	Action	Owner	Timescale
Sign-off outstanding at 5 business days	Automated reminder to the individual	Head of People and Operations	Day 5
Sign-off outstanding at 10 business days	Escalate to line manager	Head of People and Operations	Day 10
Sign-off outstanding at 15 business days	Escalate to CTO; access to Confidential systems suspended	Chief Technology Officer	Day 15
MFA not enrolled at 1 business day after account creation	Access to Confidential and Restricted systems suspended	IT Operations Manager	Day 1
Training outstanding at 10 business days from start date	Escalate to line manager	Head of People and Operations	Day 10
Leaver recorded	Row archived, not deleted; retained 2 years as evidence	Head of People and Operations	Same day
---
How to use this in a spreadsheet
Copy the Main tracker table and paste it into Google Sheets or Excel. Use Paste special → Values only so the pipe characters do not carry across as formatting.
If it lands in a single column, select the column and use Data → Split text to columns, choosing the pipe character `|` as the separator, then delete the empty first and last columns and the separator row of dashes.
Freeze the header row: View → Freeze → 1 row.
Add data validation to the three status columns using the permitted values above: Data → Data validation → Dropdown from a list. This is what stops the tracker degrading into free text within a month.
Add conditional formatting: green for `Signed` / `Verified` / `Yes`, amber for `Pending`, red for `Not Started` / `Not Enrolled` / `No`.
Build the monthly summary with `COUNTIF`. For the AUP sign-off rate, with data in rows 2 to 51:
`=COUNTIF(D2:D51,"Signed")/COUNTA(D2:D51)`
then format the cell as a percentage.
Protect the sheet so only People and Operations can edit, and share it read-only with the CTO.
---
Evidence retention
Signed acknowledgements, the tracker itself and its monthly snapshots shall be
retained for a minimum of two years in accordance with CGI-POL-004. Monthly
snapshots matter: a live tracker proves the position today, whereas an auditor
testing a period needs to see the position throughout that period.
