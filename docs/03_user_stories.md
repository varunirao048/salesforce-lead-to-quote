# User Stories and Acceptance Criteria

## Epic 1: Lead capture and routing

**US-01: Capture complete leads** (FR-01, FR-02)
*As a sales rep, I want every lead to include at least an email or a phone number, so that I can always contact it.*
- **Given** a new lead with neither email nor phone, **when** I save, **then** I see "Enter an email or phone number" and the record doesn't save.
- **Given** a lead with an email or a phone number, **when** I save, **then** it saves.

**US-02: Automatic lead assignment** (FR-03, FR-04)
*As a sales manager, I want new leads routed automatically by state, so that no lead sits unowned.*
- **Given** a new lead in New York, **when** it's created, **then** its owner is the East queue.
- **Given** a new lead in Texas, **when** it's created, **then** its owner is the Central queue.
- **Given** a lead with no state, **when** it's created, **then** it goes to the Unassigned queue and the manager is notified.
- **When** a lead is assigned, **then** the queue members receive an email notification.

## Epic 2: Qualification and conversion

**US-03: Qualify leads** (FR-05, FR-06)
*As a sales rep, I want to record a rating and qualification details, so that I focus on the best leads.*
- Lead Rating has the values Hot, Warm, and Cold.
- Budget Confirmed, Timeline, and Decision Maker fields are available on the lead page.
- **Given** Status = Unqualified, **when** I save without an Unqualified Reason, **then** I get a validation error.

**US-04: Convert qualified leads** (FR-07)
*As a sales rep, I want to convert a qualified lead in one step, so that I don't retype data.*
- **When** I convert a lead, **then** an Account, a Contact, and an Opportunity are created.
- Product Interest and Lead Rating are mapped to the matching Opportunity fields.

## Epic 3: Opportunities and quotes

**US-05: Track opportunity stages** (FR-08, FR-11)
*As a sales manager, I want consistent stages, so that the pipeline report is reliable.*
- Stages: Prospecting, Needs Analysis, Proposal/Quote, Negotiation, Closed Won, Closed Lost.
- **Given** Stage = Closed Lost, **when** I save without a Loss Reason, **then** I get a validation error.

**US-06: Quote from the price book** (FR-09, FR-10)
*As a sales rep, I want to create quotes from the current price book, so that prices are always correct.*
- **Given** an Opportunity with no products, **when** I move it to Proposal/Quote, **then** I see "Add at least one product before quoting."
- **When** I create a Quote from an Opportunity, **then** its line items and prices come from the active Price Book.

## Epic 4: Reporting

**US-07: Pipeline dashboard** (FR-12)
*As a sales manager, I want a dashboard of the pipeline, conversion, and response time, so that I can manage the team without chasing updates.*
- The dashboard shows pipeline amount by stage, conversion rate by lead source, average lead response time, and quotes by status.
- Each rep can filter it to their own records.
