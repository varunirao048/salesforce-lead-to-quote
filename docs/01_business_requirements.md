# Business Requirements Document (BRD)

**Project:** BrightDesk Lead-to-Quote on Salesforce Sales Cloud
**Prepared by:** Varuni Rao, Business Analyst
**Version:** 1.0

## 1. Background

BrightDesk's sales team of 6 reps and 1 sales manager tracks leads in a shared spreadsheet. Website enquiries and trade-show leads reach a general inbox and get assigned by hand. Quotes are written in Word from a price list that is often out of date.

## 2. Problem statement

- Leads wait too long for a first response because nobody owns them on arrival.
- The manager can't see the pipeline without asking each rep.
- Quotes take too long to produce and sometimes use outdated prices.
- There's no reliable data on which lead sources turn into revenue.

## 3. Objectives

| ID | Objective | Measure |
|---|---|---|
| OBJ-1 | Every new lead has an owner immediately | 100% of leads assigned automatically on creation |
| OBJ-2 | Faster first response | Lead response time is tracked and reported |
| OBJ-3 | One source of truth for the pipeline | Manager dashboard shows pipeline by stage and rep |
| OBJ-4 | Accurate, consistent quotes | Quotes are built only from the active Price Book |
| OBJ-5 | Know which lead sources convert | Conversion rate by lead source is reported |

## 4. Scope

**In scope:** lead capture, qualification, routing, conversion, opportunity stages, products and price books, quotes, reports, and dashboards.
**Out of scope:** CPQ discount approvals, e-signature, ERP and invoicing integration, marketing automation.

## 5. Stakeholders

| Role | Interest |
|---|---|
| Sales Manager (sponsor) | Pipeline visibility, accurate forecasts |
| Sales Reps | Clear lead ownership, faster quoting |
| Operations | Correct pricing on quotes |

## 6. Functional requirements

| ID | Requirement | Priority |
|---|---|---|
| FR-01 | The system captures leads with company, contact, email or phone, state, lead source, and product interest | Must |
| FR-02 | A lead can't be saved without an email or a phone number | Must |
| FR-03 | New leads are assigned automatically to a territory queue based on state | Must |
| FR-04 | The lead owner is notified as soon as a lead is assigned | Must |
| FR-05 | Reps can rate leads (Hot / Warm / Cold) and record qualification details (budget, timeline, decision maker) | Must |
| FR-06 | Unqualified leads must have an Unqualified Reason | Should |
| FR-07 | Converting a lead creates an Account, a Contact, and an Opportunity with the key fields mapped | Must |
| FR-08 | Opportunities follow defined stages: Prospecting, Needs Analysis, Proposal/Quote, Negotiation, Closed Won, Closed Lost | Must |
| FR-09 | An Opportunity can't move to Proposal/Quote without at least one product | Must |
| FR-10 | Quotes are generated from the Opportunity using the active Price Book | Must |
| FR-11 | Closed Lost opportunities require a Loss Reason | Should |
| FR-12 | Dashboards show pipeline by stage, conversion by lead source, response time, and quotes by status | Must |

## 7. Non-functional requirements

| ID | Requirement |
|---|---|
| NFR-01 | Reps see only their own leads and opportunities; the manager sees all of them (role hierarchy) |
| NFR-02 | Automation finishes on save, with no noticeable delay to the user |
| NFR-03 | Field labels and help text use the sales team's own terms |

## 8. Assumptions and constraints

- Built in a Salesforce Developer Edition org with standard Sales Cloud features only.
- Territories are by state: East, Central, and West.
- The Price Book is maintained by Operations.
