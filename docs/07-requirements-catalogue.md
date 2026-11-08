# MavenTech: Requirements catalogue and user stories (CRM migration case study)

## About this analysis

**Portfolio case study.** MavenTech is a fictional company, and its CRM data is a public-domain practice dataset from Maven Analytics. The analysis is Varun Kumar Darbari's own work, part of the [MavenTech CRM migration case study](../README.md). MavenTech's staff can't be interviewed, so the requirements come from the case study's own documents. Owners, priorities and the 2-minute target in NFR-02 are judgements made for this fictional case.

**Purpose.** To record what MavenTech's new CRM must do, as a requirements catalogue and a backlog of user stories with acceptance criteria, each traced to the problem, objective or law behind it.

## Key takeaway

> **MavenTech needs 11 requirements, 10 of them Musts: live pipeline reports, entry checks, a full data move and GDPR controls, each traced to a problem, objective or law.**

## 1. How the requirements were found

The work followed the BCS requirements engineering framework: elicitation, analysis and validation, with documentation and management alongside.

**Elicitation.** Document analysis of the [project brief](01-project-brief.md), the [stakeholder analysis](03-stakeholder-analysis.md), the [as-is map](04-as-is-process-map.md), the [to-be map and gap analysis](05-to-be-process-map.md) and the [business case](06-business-case.md) produced 14 raw statements, each with its source.

**Analysis.** Each statement went through the four BCS filters: clear, concise, consistent and relevant.

| Outcome | Statements | Why |
| --- | --- | --- |
| Kept | 8 | They passed all four filters |
| Split | 1 | It held two needs, so it became FR-03 and FR-04 |
| Rewritten | 1 | "User-friendly" can't be tested, so it became NFR-02, with a time limit |
| Merged | 1 | It repeated the live pipeline report, FR-05 |
| Became a business rule | 1 | "A deal can only be marked Won if its value is recorded" limits what agents may do, so it became BR-01 |
| Parked | 1 | A link to the finance system is wanted, but the brief rules out finance integrations |
| Dropped | 1 | Marketing emails are out of scope, and no document asks for them |

That leaves 11 requirements: the 8 kept, 2 from the split and 1 rewritten.

## 2. Requirements catalogue

Each requirement has an identifier, a type, a MoSCoW priority, an owner and the driver it traces to. The identifier's prefix shows the type: FR for functional, NFR for non-functional, GR for general and TR for technical.

| ID | Name | Description | Type | Priority | Owner | Driver |
| --- | --- | --- | --- | --- | --- | --- |
| FR-01 | Log a new deal | Agents can log a new deal in Salesforce at Prospecting. | Functional | Must | Sales managers | The decision to move to Salesforce |
| FR-02 | Update a deal's stage | Agents can move a deal to Engaging, then mark it Won or Lost. | Functional | Must | Sales managers | Objective 3: reporting inside the CRM |
| FR-03 | Validate entries on save | When an entry or update is saved, Salesforce rejects missing or inconsistent values. | Functional | Must | CRM administrator | P2: typed updates may hold errors |
| FR-04 | Block duplicate records | When an entry or update is saved, Salesforce blocks duplicate records. | Functional | Must | CRM administrator | P2: typed updates may hold errors |
| FR-05 | View the live pipeline | Managers can see a live report of their team's pipeline. | Functional | Must | Sales managers | Objective 3: reporting inside the CRM |
| FR-06 | Produce team reports | Managers can produce team reports in Salesforce without exporting data. | Functional | Must | Sales managers | P1: manual exports |
| FR-07 | Migrate all records | Every account, product, sales-team record and opportunity in the old CRM moves to Salesforce without losing its history. | Functional | Must | CRM administrator | Objective 1: move the data without losing history |
| GR-01 | Personal-data records | Every personal-data field has a recorded purpose, lawful basis and retention rule. | General | Must | Data protection lead | GDPR |
| NFR-01 | Access to personal data | Only authorised users can see agents' and managers' personal details. | Non-functional | Must | Data protection lead | Objective 4: handle personal data lawfully |
| TR-01 | Salesforce standard set-up | The CRM must be Salesforce Sales Cloud, set up with standard configuration only, with no custom code. | Technical | Must | Sales director | The decision to move to Salesforce |
| NFR-02 | Quick deal entry | A trained agent can log a new deal and pass the entry checks in under 2 minutes, without help. | Non-functional | Should | CRM administrator | Business case risk: agents may resist the entry checks |

**Why ten are Musts.** Each one is needed for the move to meet the brief's objectives, fix a core problem or follow GDPR.

**Why NFR-02 is a Should.** It matters for the 45-minute saving the business case depends on, but for now agents can cope with extra training and help from the CRM administrator while they get faster.

**Business rule**

| ID | Rule | Kind | Applies to | Owner | Driver |
| --- | --- | --- | --- | --- | --- |
| BR-01 | A deal can only be marked Won if its value is recorded. | Constraint | FR-02, and tested in FR-03 | Finance manager | Finance relies on deal values for forecasts |

**Parked: want to have, but won't have this time.** Won deal values flowing automatically into the finance system, for revenue forecasts. Finance relies on deal values, but the brief rules finance integrations out of this project, so its resolution is deferred.

## 3. Three requirements in full

BCS lists 18 elements for each requirement in a catalogue. These three entries show all 18, one for each problem the move fixes: entry errors (P2), manual exports (P1) and personal data in spreadsheets (P3). The other entries are completed the same way in the specification stage.

### FR-03: Validate entries on save

| Element | Entry |
| --- | --- |
| Identifier | FR-03 |
| Name | Validate entries on save |
| Description | When an entry or update is saved, Salesforce rejects missing or inconsistent values. |
| Type | Functional |
| Priority | Must |
| Business area | Sales |
| Source | To-be map, fix F2 |
| Owner | CRM administrator |
| Author | Varun Kumar Darbari (business analyst) |
| Stakeholders | Sales agents, sales managers |
| Rationale | Agents type every update by hand, so records may hold missing or inconsistent values (P2). The brief's objective 2 is to clean the data on the way. |
| Acceptance criteria | 1. When an agent saves a deal with a required field missing, Salesforce rejects the save and tells the agent what to fix. 2. When an agent marks a deal Won with no value, Salesforce rejects it and asks for the deal's value. |
| Associated non-functional requirements | NFR-02, Quick deal entry |
| Related requirements | FR-04, Block duplicate records; BR-01, Won deals need a value |
| Related documents | [As-is map](04-as-is-process-map.md) (P2); [to-be map](05-to-be-process-map.md) (F2) |
| Comments | Run with Salesforce's standard validation rules (TR-01). Which fields they check is decided in the specification stage. |
| Resolution | Open: not yet built |
| Version history | v1.0, 8 Nov 2026: first draft |

### FR-05: View the live pipeline

| Element | Entry |
| --- | --- |
| Identifier | FR-05 |
| Name | View the live pipeline |
| Description | Managers can see a live report of their team's pipeline. |
| Type | Functional |
| Priority | Must |
| Business area | Sales |
| Source | Project brief, objective 3; to-be map, fix F1 |
| Owner | Sales managers |
| Author | Varun Kumar Darbari (business analyst) |
| Stakeholders | Sales director, sales agents, finance manager |
| Rationale | Managers export deal data to spreadsheets by hand, so their figures go out of date (P1). The brief needs pipeline reporting inside the CRM (objective 3). |
| Acceptance criteria | 1. When an agent moves a deal to a new stage, the manager's pipeline report shows the change the next time it's opened, with no export. 2. The report's deal count for each stage matches the number of deals at that stage in Salesforce. |
| Associated non-functional requirements | NFR-01, Access to personal data: the report shows agents' names |
| Related requirements | FR-02, Update a deal's stage; FR-06, Produce team reports |
| Related documents | [Project brief](01-project-brief.md); [as-is map](04-as-is-process-map.md) (P1); [to-be map](05-to-be-process-map.md) (F1) |
| Comments | Built with Salesforce's standard reports, so no custom code is needed (TR-01). |
| Resolution | Open: not yet built |
| Version history | v1.0, 8 Nov 2026: first draft |

### GR-01: Personal-data records

| Element | Entry |
| --- | --- |
| Identifier | GR-01 |
| Name | Personal-data records |
| Description | Every personal-data field has a recorded purpose, lawful basis and retention rule. |
| Type | General |
| Priority | Must |
| Business area | Sales |
| Source | Project brief, objective 4; to-be map, gap analysis (Information) |
| Owner | Data protection lead |
| Author | Varun Kumar Darbari (business analyst) |
| Stakeholders | Sales agents, sales managers, CRM administrator |
| Rationale | GDPR applies to MavenTech's personal data, and agents' and managers' names are personal data (P3). The brief's objective 4 is to handle personal data lawfully. |
| Acceptance criteria | 1. Every personal-data field in Salesforce is listed in the GDPR data inventory, each with a purpose, lawful basis and retention rule. 2. The data protection lead has reviewed and agreed the inventory. |
| Associated non-functional requirements | NFR-01, Access to personal data |
| Related requirements | FR-07, Migrate all records |
| Related documents | [Project brief](01-project-brief.md); [to-be map, gap analysis](05-to-be-process-map.md) |
| Comments | Recorded in the GDPR data inventory, a specification-stage deliverable. |
| Resolution | Open: not yet done |
| Version history | v1.0, 8 Nov 2026: first draft |

## 4. User stories

The ten stories form a product backlog in priority order: the nine Musts first, then the one Should. Each links to the catalogue item it delivers, and each has an acceptance criterion written as "Given… when… then…".

| Story | Links to | Priority | User story | Acceptance criterion |
| --- | --- | --- | --- | --- |
| US-01 | FR-01 | Must | As a sales agent, I want to log a new deal in Salesforce at Prospecting, so that every possible sale is tracked in one place from the start. | Given I'm signed in to Salesforce, when I save a new deal with every required field filled in, then it appears in my pipeline at Prospecting. |
| US-02 | FR-02 | Must | As a sales agent, I want to move a deal to Engaging, then mark it Won or Lost, so that my manager can see where each of my deals stands without asking me. | Given a deal at Prospecting, when I move it to Engaging and save, then its stage shows as Engaging in my pipeline and in my manager's report. |
| US-03 | FR-03 | Must | As a sales agent, I want Salesforce to tell me what's missing or inconsistent when I save, so that I can fix mistakes straight away instead of hunting for them later. | Given a deal with a required field left empty, when I save it, then Salesforce blocks the save and tells me which field to fill in. |
| US-04 | FR-04 | Must | As a CRM administrator, I want Salesforce to block duplicate records when they're saved, so that I don't have to find and merge duplicates by hand. | Given an account called "Acme Corporation" already exists, when an agent tries to save a new account with the same name, then Salesforce blocks the save and tells the agent the account already exists. |
| US-05 | FR-05 | Must | As a sales manager, I want a live report of my team's pipeline, so that I can decide on up-to-date figures without exporting data by hand. | Given an agent has moved a deal from Engaging to Won, when the manager next opens the pipeline report, then the deal shows as Won, with no export needed. |
| US-06 | FR-06 | Must | As a sales manager, I want to produce team reports in Salesforce, so that I can see how each agent is doing and coach them, without exporting data. | Given the manager's team has closed deals this quarter, when the manager runs the team report in Salesforce, then it shows each agent's won and lost deals, with no export. |
| US-07 | FR-07 | Must | As a CRM administrator, I want every record moved from the old CRM with its history, so that no deal history is lost, and reports still show past results. | Given the migration has finished, when each table is compared with the old CRM's export, then Salesforce holds the same number of records (for example, all 8,800 opportunities), and every deal keeps its stage and dates. |
| US-08 | NFR-01 | Must | As a data protection lead, I want only authorised users to see agents' and managers' personal details, so that MavenTech follows GDPR and avoids action from the Data Protection Commission. | Given a user who isn't authorised to see personal data, when they try to open an agent's personal details, then access is refused. |
| US-09 | BR-01 | Must | As a finance manager, I want every Won deal to carry its value, so that my revenue forecasts are built on complete deal values. | Given a deal at Engaging, when an agent marks it Won without entering a value, then Salesforce blocks the save and asks for the value. |
| US-10 | NFR-02 | Should | As a sales agent, I want to log a deal and pass the checks in under 2 minutes, so that the checks don't slow down my selling. | Given a trained agent with a new deal's details to hand, when they log it in Salesforce without help, then they finish, checks passed, in under 2 minutes. |

## 5. Next steps

- **Validation.** The sales director signs off the requirements in the [RACI chart](03-stakeholder-analysis.md), so they review and agree the catalogue and the stories. Because the case is fictional, this review is planned rather than held.
- **Specification.** The stories move into Jira. The catalogue becomes the requirements catalogue section of the business requirements document in Confluence, beside the process models, a function model, a data model and a glossary.
- **Management.** Every change after sign-off gets a new entry in the version history, and the related requirements show what else the change affects.

## Assumptions

MavenTech is fictional, so these points couldn't be checked with its staff.

- **Where the requirements came from.** They were elicited from the case study's documents, not from interviews, because the brief plans and scripts stakeholder contact rather than holding it.
- **Owners and priorities.** These are judgements based on the stakeholder analysis and the business case.
- **NFR-02's target.** Two minutes is an assumed target, to be confirmed with agents during user acceptance testing.
- **Field-level detail.** Which fields the entry checks cover, and how duplicates are matched, is decided in the specification stage.

## Sources

- [BCS Foundation Certificate in Business Analysis syllabus v4.1](https://www.bcs.org/media/e3fllbw3/ba-foundation-syllabus.pdf): learning outcomes 10.1 (the requirements engineering framework), 10.3 (types of requirement), 10.4 (the hierarchy of requirements), 10.5 (elicitation techniques), 10.6 (filters, MoSCoW and business rules), 11.2 (the requirements catalogue), 11.3 (user stories), 11.6 (the product backlog) and 11.7 (the business requirements document)
- [MavenTech CRM migration: project brief](01-project-brief.md): objectives, scope, constraints and personal data
- [MavenTech: Stakeholder analysis](03-stakeholder-analysis.md): owners, stakeholders and the RACI chart
- [MavenTech: As-is process map](04-as-is-process-map.md): problems P1 to P3
- [MavenTech: To-be process map and gap analysis](05-to-be-process-map.md): fixes F1 to F3, and the gap analysis
- [MavenTech: Business case summary](06-business-case.md): the chosen option, the 45-minute break-even and the risk that agents resist the entry checks
- [Salesforce Help: Validation Rules](https://help.salesforce.com/s/articleView?id=sf.fields_about_field_validation.htm&type=5) and [Customize Duplicate Rules](https://help.salesforce.com/s/articleView?id=sf.duplicate_rules_create.htm&type=5): the standard features behind FR-03 and FR-04
- [Maven Analytics: CRM Sales Opportunities](https://mavenanalytics.io/data-playground/crm-sales-opportunities), public domain, with [a public copy of its tables on GitHub](https://github.com/nghiant3110/b2b_crm_3): the 8,800 opportunities in the migration check
