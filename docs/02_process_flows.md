# Process Flows

## As-is (before Salesforce)

```mermaid
flowchart TD
    A[Lead arrives: web form, email, trade show] --> B[Lands in shared inbox]
    B --> C[Manager copies it into a spreadsheet]
    C --> D[Manager picks a rep by hand]
    D --> E{Rep notices it?}
    E -->|Days later| F[Rep calls the lead]
    E -->|Missed| X[Lead goes cold]
    F --> G[Rep writes a quote in Word from a PDF price list]
    G --> H[Status updated in the spreadsheet, if remembered]
```

**Pain points**
1. Manual assignment delays first contact (sometimes by days).
2. No single owner, so leads get missed.
3. Old price lists cause quoting errors.
4. The manager has to chase reps for pipeline updates.
5. No data on which lead sources convert.

## To-be (Salesforce Sales Cloud)

```mermaid
flowchart TD
    A[Lead created in Salesforce] --> B{Validation: email or phone present?}
    B -->|No| B1[Save blocked with a clear error]
    B -->|Yes| C[Flow: assign queue by state, notify owner]
    C --> D[Rep qualifies: rating, budget, timeline, decision maker]
    D -->|Qualified| E[Convert to Account, Contact, Opportunity]
    D -->|Not qualified| F[Status = Unqualified + reason required]
    E --> G[Opportunity stages]
    G --> H{Products added?}
    H -->|No| H1[Can't move to Proposal/Quote]
    H -->|Yes| I[Generate Quote from active Price Book]
    I --> J[Closed Won / Closed Lost with reason]
    J --> K[Dashboards update automatically]
```

## Gap analysis

| Area | As-is | To-be | Gap closed by |
|---|---|---|---|
| Lead ownership | Assigned by hand | Automatic by state | Record-triggered Flow + queues |
| Data quality | Free-form spreadsheet | Required fields and picklists | Validation rules, picklists |
| Quoting | Word + PDF price list | Quote from Price Book | Products, Price Books, Quotes |
| Visibility | Asking each rep | Live dashboards | Reports & Dashboards |
| Source ROI | Unknown | Conversion by source | Lead Source field + report |
