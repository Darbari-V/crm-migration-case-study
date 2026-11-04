# MavenTech: Business case summary (CRM migration case study)

## About this analysis

**Portfolio case study.** MavenTech is a fictional company, and its CRM data is a public-domain practice dataset from Maven Analytics. The analysis is Varun Kumar Darbari's own work, part of the [MavenTech CRM migration case study](../README.md). Because MavenTech is fictional, its costs, time savings and hourly rates are assumptions, labelled in the appendix. Salesforce's prices and the size of the sales team come from the sources listed.

**Purpose.** To compare the ways of fixing the problems found in the as-is map and recommend one, with its costs, benefits, risks and payback, so that MavenTech's sales director can decide.

## Key takeaway

> **MavenTech should move to Salesforce, which fixes all three problems and adds about €32,500 in today's money over three years, if each agent saves 45 minutes a week.**

## 1. Introduction

MavenTech's sales managers can't see live pipeline data, agents' typed updates may hold errors, and agents' and managers' names sit in spreadsheets outside the CRM. MavenTech has decided to move to Salesforce. This business case sets out the options considered and the evidence for that choice, so the sales director can confirm it before money is spent.

It builds on the [project brief](01-project-brief.md), which recorded the first idea, and on the [as-is map](04-as-is-process-map.md) and the [to-be map and gap analysis](05-to-be-process-map.md). Like any business case, it will be updated as the project learns more, for example once data profiling shows how much cleaning the data needs.

## 2. Management summary

Three options were compared: do nothing, improve the current CRM, and move to Salesforce.

- **Do nothing** costs nothing up front, but MavenTech keeps losing about €73,000 a year in staff time, and the GDPR risk stays.
- **Improving the current CRM** may not be possible without custom-built code, and it goes against MavenTech's decision to move to Salesforce.
- **Moving to Salesforce** fixes all three problems. It costs €21,000 up front and €51,600 a year in licences, pays back in just under a year, and adds about €32,500 in today's money over three years.

**We recommend moving to Salesforce**, once a check confirms that agents save at least 45 minutes a week each, because the case depends on it.

## 3. Current state

The [as-is map](04-as-is-process-map.md) found three problems in how a deal moves today. Two of them cost staff time every week, worked out in the appendix.

| Problem | What happens today | What it costs |
| --- | --- | --- |
| P1 | Managers export deals to spreadsheets by hand to see the pipeline, so figures go out of date | About 552 manager hours a year: €24,840 |
| P2 | Agents type every update by hand, so records may hold duplicate, missing or inconsistent values | About 1,610 agent hours a year spent fixing records: €48,300 |
| P3 | Agents' and managers' names, which are personal data, sit in spreadsheets outside the CRM | A GDPR risk that can't be priced |

## 4. Options considered

A scripted brainstorm produced five options. Two were dropped at the shortlist: staff building one report by hand, and hiring someone to track the pipeline. Neither fully fixes any problem, both keep names in spreadsheets, and the second adds a salary every year. "Do nothing" stays on the shortlist as the yardstick the other options are measured against.

### Option 1: Do nothing

- **The option.** Keep the current CRM and the spreadsheets.
- **Costs and benefits.** No new costs, but the €73,140 a year of staff time in section 3 keeps being lost.
- **Impact.** None. All three problems stay.
- **Risks.** Managers keep deciding on out-of-date figures, and personal data stays outside the CRM.

### Option 2: Improve the current CRM

- **The option.** Keep the current CRM, and add live reports and entry checks to it.
- **Costs and benefits.** Can't be costed until a technical review shows whether the CRM can do this, and at what price. If it can, the benefits would match option 3's.
- **Impact.** Smaller for staff, who already know the CRM.
- **Risks.** It may need custom-built code, and it goes against MavenTech's decision to move to Salesforce.

### Option 3: Move to Salesforce

- **The option.** Replace the current CRM with Salesforce Sales Cloud, set up with standard configuration, as in the [to-be map](05-to-be-process-map.md).
- **Costs and benefits.** €21,000 one-off (€15,000 to set up Salesforce and move the data, €6,000 for training) and €51,600 a year in licences, against €73,140 a year of staff time saved. It pays back in about 11.7 months, and its net present value over three years at 10% is +€32,567. It also brings intangible benefits: managers decide on live, accurate figures, and personal data stays under control.
- **Impact.** The five POPIT gaps in the [gap analysis](05-to-be-process-map.md): training for 43 people, a bigger job for the CRM administrator, a new check-and-fix loop, clean data with GDPR records, and Salesforce set up.
- **Risks.** Agents may save less time than assumed (the case breaks even at about 45 minutes a week each), Salesforce may raise its prices, and agents may resist the entry checks. All three are in the CARDI log.

### Feasibility

"Do nothing" needs no feasibility check, because there's nothing to put in place.

| Option | Business | Technical | Financial |
| --- | --- | --- | --- |
| 2. Improve the current CRM | **Doubtful.** Staff already know the CRM, but improving it goes against MavenTech's decision to move to Salesforce. | **Doubtful.** Nobody knows whether the current CRM can add live reports and entry checks without custom-built code, and managers' lack of visibility today suggests weak reporting. | **Unknown** until a technical review prices it |
| 3. Move to Salesforce | **Feasible.** It matches MavenTech's decision to move to Salesforce, and keeping personal data under control in Salesforce helps it follow GDPR. The training and bigger administrator role it needs are manageable. | **Feasible.** Salesforce's standard validation rules and duplicate rules can run the entry checks, and its standard reports give live pipeline views, with no custom code. | **Feasible** if agents save at least about 45 minutes a week each |

## 5. Recommendation

We recommend option 3, moving to Salesforce, because it is the only option that fixes all three problems and is clearly feasible. It pays back in just under a year and adds about €32,500 in today's money over three years. Before signing, MavenTech should check that agents really save at least 45 minutes a week each, because the case depends on it.

## 6. Appendix: cost and benefit workings

### Facts from sources

| Fact | Value | Source |
| --- | --- | --- |
| Sales team | 35 sales agents and 6 managers, across 3 regional offices | The dataset's sales-team table |
| Licence price | Sales Cloud Pro Suite: €100 per user per month, billed annually | Salesforce's EU pricing page, updated 28 Sep 2026 |
| Pro Suite fits | Its base, Professional Edition, includes validation rules and duplicate rules | Salesforce Help |

### Assumptions

| Item | Assumption |
| --- | --- |
| Salesforce users | 43: the 41 agents and managers, plus the sales director and the CRM administrator |
| Managers' export time | 2 hours a week each, over 46 working weeks a year |
| Agents' error-fixing time | 1 hour a week each |
| Cost of an hour's work, including employer costs | Manager €45, agent €30 |
| Setting up Salesforce and moving the data | €15,000, one-off |
| Training | €6,000, one-off: half a day for each of the 43 people, plus materials |
| Saving from ending the old CRM's licence | Left out, because its amount is unknown. This keeps the case cautious. |
| Discount rate and period | 10% a year, over three years |

### Calculations

- **Benefits per year:** managers 6 × 2 × 46 = 552 hours × €45 = €24,840; agents 35 × 1 × 46 = 1,610 hours × €30 = €48,300; total €73,140
- **Licences per year:** 43 × €100 × 12 = €51,600
- **Net benefit per year:** €73,140 − €51,600 = €21,540
- **Payback:** €21,000 ÷ €21,540 = 0.975 years, about 11.7 months

### Net present value

| Year | Money | Divide by | Worth today |
| --- | --- | --- | --- |
| 0 | −€21,000 | 1 | −€21,000 |
| 1 | +€21,540 | 1.1 | €19,582 |
| 2 | +€21,540 | 1.21 | €17,802 |
| 3 | +€21,540 | 1.331 | €16,183 |
| **NPV** |  |  | **+€32,567** |

### What if agents save less time?

At 30 minutes a week each, the agents' benefit falls to €24,150, the net benefit to −€2,610 a year, and NPV to about −€27,500. About 33 minutes a week each just covers the licences, and about 44 minutes makes NPV zero over three years. That's why the recommendation sets the pass mark at 45 minutes.

## CARDI log

The log records the constraints, assumptions, risks, dependencies and issues this business case rests on. It carries over every item from the project brief and adds the ones this business case brought up.

| Type | Item | Added in |
| --- | --- | --- |
| Constraint | Free tools only: a Salesforce Trailhead Playground, Atlassian's free Jira and Confluence plans, free SQL tools | Brief |
| Constraint | One analyst, so stakeholder interviews and workshops are planned and scripted rather than held | Brief |
| Constraint | The build uses Salesforce's standard configuration, with no custom code | Business case |
| Assumption | Salesforce is the chosen target CRM | Brief |
| Assumption | MavenTech has customers and staff in the EU, so GDPR applies to personal data in the CRM. Its EU operations are based in Ireland, so its lead regulator is Ireland's Data Protection Commission | Brief |
| Assumption | The four-table export is the complete legacy dataset | Brief |
| Assumption | Agents save about 1 hour a week each on fixing records | Business case |
| Assumption | Managers save about 2 hours a week each on exports | Business case |
| Assumption | The 43 users fit Sales Cloud Pro Suite, plus any add-ons the data load needs | Business case |
| Risk | Profiling finds more data-quality problems than the plan allows for | Brief |
| Risk | Scripted stakeholders miss the tacit knowledge a real team would surface | Brief |
| Risk | Agents save less time than assumed, so the change doesn't pay for itself. The case breaks even at about 45 minutes a week each. | Business case |
| Risk | Salesforce raises its prices before MavenTech signs | Business case |
| Risk | Sales agents resist the new entry checks | Business case |
| Dependency | Discovery deliverables follow the order of the BCS Foundation syllabus topics | Brief |
| Dependency | Moving the data can't start until Salesforce is set up | Business case |
| Issue | None open yet | Brief |

## Sources

- [BCS Foundation Certificate in Business Analysis syllabus v4.1](https://www.bcs.org/media/e3fllbw3/ba-foundation-syllabus.pdf): learning outcomes 8.3 (developing options), 9.1 (the business case lifecycle), 9.2 (feasibility), 9.3 (the structure of a business case), 9.5 (the CARDI log) and 9.6 (payback, discounted cash flow and net present value)
- [MavenTech CRM migration: project brief](01-project-brief.md): the problem, the decision to move to Salesforce, the stakeholders and the first CARDI log
- [MavenTech: As-is process map](04-as-is-process-map.md): the current state and problems P1 to P3
- [MavenTech: To-be process map and gap analysis](05-to-be-process-map.md): option 3's design and its impact
- [Salesforce EU pricing: Sales Cloud](https://www.salesforce.com/eu/sales/pricing/): Pro Suite at €100 per user per month, billed annually
- [Salesforce Help: Validation Rules](https://help.salesforce.com/s/articleView?id=sf.fields_about_field_validation.htm&type=5) and [Customize Duplicate Rules](https://help.salesforce.com/s/articleView?id=sf.duplicate_rules_create.htm&type=5): both available in Professional Edition
- [Maven Analytics: CRM Sales Opportunities](https://mavenanalytics.io/data-playground/crm-sales-opportunities), public domain, with [a public copy of its tables on GitHub](https://github.com/nghiant3110/b2b_crm_3): the size of the sales team
