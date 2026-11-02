# Reports and Dashboard Specification

**Dashboard:** BrightDesk Sales Overview (running user: Sales Manager)

| # | Component | Source report | Report type | Grouping | Measure | Chart |
|---|---|---|---|---|---|---|
| 1 | Pipeline by Stage | Open Pipeline | Opportunities | Stage | Sum of Amount | Funnel |
| 2 | Conversion Rate by Lead Source | Lead Conversion | Leads | Lead Source | Converted ÷ Total (row-level formula) | Bar |
| 3 | Avg Lead Response Time | Lead Response | Leads | Owner | Average of First Response Hours | Gauge, target ≤ 24h |
| 4 | Quotes by Status | Quote Status | Quotes | Status | Record count | Donut |
| 5 | Won vs Lost (this quarter) | Closed Deals | Opportunities | Stage (Closed Won/Lost) | Sum of Amount | Bar |
| 6 | Top Loss Reasons | Closed Lost | Opportunities | Loss Reason | Record count | Bar |

**Filters:** Close Date (this quarter, by default) and Owner (so reps can view their own numbers).

**How each component maps to an objective**

| Objective | Component |
|---|---|
| OBJ-2 Faster response | 3 |
| OBJ-3 Pipeline visibility | 1, 5 |
| OBJ-5 Source conversion | 2 |
| OBJ-4 Quote accuracy and throughput | 4 |
