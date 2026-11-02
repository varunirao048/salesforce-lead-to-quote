# UAT Test Cases

| TC | Story | Scenario | Steps | Expected result | Type |
|---|---|---|---|---|---|
| TC-01 | US-01 | Lead with no email or phone | Create a lead with only a name and company, then save | Error "Enter an email or phone number"; not saved | Negative |
| TC-02 | US-01 | Lead with a phone only | Create a lead with a phone number, then save | Saves | Positive |
| TC-03 | US-02 | East routing | Create a lead with State = NY | Owner = East queue; queue members get an email | Positive |
| TC-04 | US-02 | Central routing | Create a lead with State = TX | Owner = Central queue | Positive |
| TC-05 | US-02 | Missing state | Create a lead with State blank | Owner = Unassigned queue; manager gets an email | Edge |
| TC-06 | US-02 | Lowercase or invalid state | Create a lead with State = "xx" | Owner = Unassigned queue | Edge |
| TC-07 | US-03 | Unqualified without a reason | Set Status = Unqualified, leave the reason blank, then save | Error "Select an Unqualified Reason" | Negative |
| TC-08 | US-04 | Convert a qualified lead | Convert a lead with Product Interest = Desks and Rating = Hot | Account, Contact, and Opportunity created; Opportunity shows Desks and Hot | Positive |
| TC-09 | US-06 | Quote stage without products | Move an Opportunity with no products to Proposal/Quote | Error "Add at least one product before quoting" | Negative |
| TC-10 | US-06 | Quote from the price book | Add 2 products, then create a Quote | Quote line items match the active Price Book prices | Positive |
| TC-11 | US-05 | Closed Lost without a reason | Set Stage = Closed Lost with no Loss Reason | Error "Select a Loss Reason" | Negative |
| TC-12 | US-07 | Dashboard refresh | Close one Opportunity as Won, then refresh the dashboard | The Won vs Lost and Pipeline components update | Positive |
| TC-13 | NFR-01 | Rep visibility | Log in as Rep A and open Rep B's opportunity | No access (private sharing model) | Negative |
| TC-14 | Flow | First response time | Create a lead, then change its status 2 hours later | First Response Hours is about 2 | Positive |

**Exit criteria:** all Must-priority test cases pass, with no open severity-1 or severity-2 defects.
