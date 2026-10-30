# MavenTech: Stakeholder analysis (CRM migration case study)

## About this analysis

**Portfolio case study.** MavenTech is a fictional company, and its CRM data is a public-domain practice dataset from Maven Analytics. The analysis is Varun Kumar Darbari's own work, part of the [MavenTech CRM migration case study](../README.md). Stakeholder roles, power and interest levels are judgements made for this fictional case. MavenTech's EU operations are assumed to be based in Ireland, so its lead data protection regulator is Ireland's Data Protection Commission.

**Purpose.** To identify everyone affected by MavenTech's move to a new CRM, decide how to manage each of them, and agree who does what on the project's main tasks.

## Key takeaway

> **The sales director signs off every task, so keep them closely involved; bring the sales managers and data protection lead into every step, because almost nothing moves without them.**

## Stakeholder wheel

BCS's stakeholder wheel has eight groups: three inside the business and five outside it. Using it as a checklist means nobody is forgotten.

|  | Group | Stakeholders for the CRM project |
| --- | --- | --- |
| **Inside** | Owners | MavenTech's investors |
|  | Managers | Sales director (sponsor), sales managers, finance manager |
|  | Employees | Sales agents, CRM administrator, data protection lead, IT team |
| **Outside** | Customers | The large businesses that buy from MavenTech |
|  | Suppliers | Salesforce (the new CRM); hardware makers |
|  | Partners | None: MavenTech's own team builds the CRM |
|  | Regulators | Data Protection Commission |
|  | Competitors | Rival hardware sellers |

## Power/interest grid

Each stakeholder is placed by two questions: could they stop or change this project (power), and will it change their day-to-day work (interest)? Their place sets how they're managed.

|  | **Low interest** | **Some interest** | **High interest** |
| --- | --- | --- | --- |
| **High power** | **Watch:** investors; Data Protection Commission | **Keep satisfied:** nobody at present | **Constant active management:** sales director; sales managers |
| **Some power** | **Keep onside:** Salesforce | **Keep onside:** finance manager; data protection lead | **Keep onside:** CRM administrator; IT team |
| **Low power** | **Ignore:** customers; hardware makers; rival hardware sellers | **Keep informed:** nobody at present | **Keep informed:** sales agents |

**Why each stakeholder sits where they do**

| Stakeholder | Power | Interest | Strategy | Reason |
| --- | --- | --- | --- | --- |
| Sales director | High | High | Constant active management | Sponsor who controls the budget; wants reliable pipeline figures |
| Sales managers | High | High | Constant active management | Their teams must adopt the CRM; they need pipeline reports to run those teams |
| Sales agents | Low | High | Keep informed | One agent alone can't stop the project; they use the CRM every day |
| CRM administrator | Some | High | Keep onside | Owns data quality and settings; their daily work changes completely |
| Finance manager | Some | Some | Keep onside | Can question the costs; relies on deal values for forecasts |
| Data protection lead | Some | Some | Keep onside | Can block anything that breaks GDPR; involved wherever personal data moves |
| IT team | Some | High | Keep onside | Could stall the project if they can't support it; they'll run it every day |
| Investors | High | Low | Watch | Could stop the spending, but too far from a CRM change to follow it |
| Large business customers | Low | Low | Ignore | Can't affect the project, and never see MavenTech's internal tool |
| Salesforce | Some | Low | Keep onside | MavenTech must work within its platform, but it doesn't know about this project |
| Hardware makers | Low | Low | Ignore | The CRM change doesn't affect them |
| Data Protection Commission | High | Low | Watch | Can fine MavenTech if the new CRM breaks GDPR, but isn't watching this project |
| Rival hardware sellers | Low | Low | Ignore | Don't know or care about MavenTech's CRM |

## RACI chart

**R** does the work · **A** owns the result and signs it off (one per task) · **C** is asked for input · **I** is told. Each person has at most one letter per task.

| Task | Sales director | BA | Sales managers | Sales agents | CRM administrator | Finance manager | Data protection lead | IT team |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Write the requirements | A | R | C |  | C | I | C |  |
| Clean and move the data | A | R | C | I | C |  | C | I |
| Set up Salesforce | A | R | C | C | R | I | C | R |
| Run user acceptance testing | A | C | R | R | C | I | C | C |
| Train the sales team | A | R | C | I | R |  | C | I |

## Sources

- [BCS Foundation Certificate in Business Analysis syllabus v4.1](https://www.bcs.org/media/e3fllbw3/ba-foundation-syllabus.pdf): stakeholder wheel, power/interest grid strategies and RACI
- [MavenTech CRM migration: project brief](01-project-brief.md): case facts, scope and roles
