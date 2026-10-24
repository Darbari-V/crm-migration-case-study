# MavenTech: Project brief (CRM migration case study)

By Varun Kumar Darbari

## About this case study

This is a portfolio case study, not client work. The company, MavenTech, is fictional, and its CRM data is a public-domain practice dataset published by Maven Analytics. The analysis is Varun Kumar Darbari's own work, produced to show IT business analysis on a CRM and customer-data migration.

## Background and problem

MavenTech sells computer hardware to large businesses. Its sales team tracks opportunities in a CRM, but managers have no visibility of that data outside the platform ([Maven Analytics](https://mavenanalytics.io/challenges/maven-sales-challenge)).

In this case, MavenTech has decided to move to Salesforce. Before it switches, it needs three things: the requirements the new system must meet, rules for moving and cleaning the existing data, and tests that prove the move worked.

## Objectives and success measures

| Objective | Success measure |
| --- | --- |
| Move accounts, products, sales teams and opportunities to Salesforce without losing history | Record counts and key values reconcile between the export and Salesforce for every in-scope table |
| Clean the data on the way | Every duplicate, missing value and inconsistent value found in profiling is fixed, or carried over under an agreed rule |
| Give sales managers pipeline and team reporting inside the CRM | Managers can produce the agreed pipeline and team reports in Salesforce without exporting data |
| Handle personal data lawfully | Every personal-data field has a recorded purpose, lawful basis and retention rule |
| Prove the change works | Every Must-have requirement traces to a passed UAT test |

## Scope

**In scope**

- The four tables in the CRM export: accounts, products, sales teams and opportunities
- The opportunity process, from first engagement to won or lost
- Data migration and cleansing rules
- Sales managers' pipeline and team reporting
- User acceptance testing of the migrated data and configured processes

**Out of scope**

- Marketing, customer service and support processes
- Integrations with finance, ERP or other systems
- Licence purchase, training rollout and the production cutover itself
- Custom code: the build uses Salesforce's standard configuration in a free practice org

## Stakeholders (initial list)

Roles are assumed for this case. The [stakeholder analysis](03-stakeholder-analysis.md) refines them.

| Stakeholder | Interest in the migration |
| --- | --- |
| Sales director (sponsor) | Funds the change and wants reliable pipeline figures |
| Sales managers | Track their teams' pipeline and performance |
| Sales agents | Daily users who record and update opportunities |
| Sales operations / CRM administrator | Owns data quality, configuration and access |
| Finance | Relies on deal values for revenue forecasts |
| Data protection lead | Makes sure personal data is handled under GDPR |
| IT / Salesforce platform team | Builds and supports the new system |
| Business analyst (Varun) | Requirements, migration rules and the UAT plan |

## The legacy data

The export is Maven Analytics' [CRM Sales Opportunities](https://mavenanalytics.io/data-playground/crm-sales-opportunities) dataset: B2B sales-pipeline data from a fictitious computer-hardware seller, public domain. It has four tables. Maven Analytics' own pages disagree on its size: 8,800 records and 18 fields on its [guided project page](https://mavenanalytics.io/guided-projects/sales-pipeline-analysis), but 499 records and 25 fields on its [dataset page](https://mavenanalytics.io/data-playground/crm-sales-opportunities).

| Table | What it holds |
| --- | --- |
| Accounts | The customer companies, including links to parent companies |
| Products | The hardware products sold |
| Sales teams | Sales agents and their managers |
| Sales pipeline | Each opportunity and its deal stage, from Prospecting and Engaging to Won or Lost |

**Personal data.** The sales-team table identifies individual agents and managers; the accounts are organisations. The target CRM will also hold contact people at customer companies, which the export doesn't include.

The deal stages and the parent-company links come from two Maven Analytics showcase projects ([deal stages](https://mavenanalytics.io/project/13846), [parent companies](https://mavenanalytics.io/project/14099)). Data profiling in the specification stage confirms them, along with the field definitions, the record count per table and the data-quality problems to fix.

## Constraints, assumptions and risks

Recorded as a CARDI log (constraints, assumptions, risks, dependencies and issues), the format the BCS syllabus uses for a business case. It grows as the business case is written.

| Type | Item |
| --- | --- |
| Constraint | Free tools only: a Salesforce Trailhead Playground, Atlassian's free Jira and Confluence plans, free SQL tools |
| Constraint | One analyst, so stakeholder interviews and workshops are planned and scripted rather than held |
| Assumption | Salesforce is the chosen target CRM |
| Assumption | MavenTech has customers and staff in the EU, so GDPR applies to personal data in the CRM. Its EU operations are based in Ireland, so its lead regulator is Ireland's Data Protection Commission |
| Assumption | The four-table export is the complete legacy dataset |
| Risk | Profiling finds more data-quality problems than the plan allows for |
| Risk | Scripted stakeholders miss the tacit knowledge a real team would surface |
| Dependency | Discovery deliverables follow the order of the BCS Foundation syllabus topics |
| Issue | None open yet |

## Stages and deliverables

| Stage | Deliverables |
| --- | --- |
| 1. Discovery | PESTLE and SWOT; stakeholder wheel, power/interest grid and RACI; AS-IS and TO-BE swimlanes with a gap analysis; business case summary with a CARDI log; requirements catalogue and first user stories |
| 2. Specification | BRD and FRD in Confluence; user stories in Jira; traceability matrix; source-to-target mapping with data-quality rules; GDPR data inventory; UAT plan |
| 3. Build and test | Target data model configured in a Salesforce Trailhead Playground; sample data imported; UAT run and defects logged |

Progress on each stage is tracked on the [case study's front page](../README.md).
