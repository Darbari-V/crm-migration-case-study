# MavenTech: Product backlog and Sprint 1 plan (CRM migration case study)

## About this analysis

**Portfolio case study.** MavenTech is a fictional company, and its CRM data is a public-domain practice dataset from Maven Analytics. The analysis is Varun Kumar Darbari's own work, part of the [MavenTech CRM migration case study](../README.md). No sprint has run yet, so the order of the backlog and the Sprint 1 plan are judgements made for this fictional case.

**Purpose.** To turn MavenTech's 10 user stories into one ordered product backlog, grouped into epics, with a Product Goal and a plan for the first sprint. It's the first piece of the Specification stage.

## Key takeaway

> **MavenTech's backlog of 10 user stories, 9 of them Musts, puts deal logging and entry checks first, protects personal data before the old records move, then adds live reports.**

## 1. Product Goal

The Product Goal is the target every sprint works towards:

> MavenTech's sales team tracks every deal in Salesforce, with clean data, full history and protected personal data, and managers see live pipeline and team reports inside the CRM.

## 2. Epics

An epic is a large body of work broken down into stories. The 10 stories from the [requirements catalogue](07-requirements-catalogue.md) fall into five epics.

| Epic | Stories | What it covers |
| --- | --- | --- |
| Deal tracking | US-01, US-02 | Logging deals and moving them through their stages |
| Entry checks | US-03, US-04, US-09, US-10 | Catching missing, inconsistent and duplicate entries when a record is saved, without slowing agents down |
| Reporting for managers | US-05, US-06 | Live pipeline and team reports inside Salesforce |
| Data migration | US-07 | Moving every record from the old CRM with its history |
| Protecting personal data | US-08 | Limiting who can see agents' and managers' personal details |

## 3. The ordered backlog

The backlog is ordered by priority first, so the nine Musts sit above the one Should. Among the Musts, any story that others depend on goes first.

| Order | Story | Epic | Priority |
| --- | --- | --- | --- |
| 1 | US-01: log a new deal | Deal tracking | Must |
| 2 | US-02: move a deal through its stages | Deal tracking | Must |
| 3 | US-03: tell the agent what's missing or inconsistent on save | Entry checks | Must |
| 4 | US-04: block duplicate records | Entry checks | Must |
| 5 | US-09: a Won deal must carry its value | Entry checks | Must |
| 6 | US-08: only authorised users see personal details | Protecting personal data | Must |
| 7 | US-07: move every record with its history | Data migration | Must |
| 8 | US-05: live pipeline report | Reporting for managers | Must |
| 9 | US-06: team reports | Reporting for managers | Must |
| 10 | US-10: log a deal and pass the checks in under 2 minutes | Entry checks | Should |

**Why this order:**

- **Deal tracking comes first,** because every other story needs deals in Salesforce.
- **The entry checks follow the steps they check.** US-03 and US-04 check a deal when it's saved, so they come after US-01. US-09 checks the Won step, so it comes after US-02.
- **Personal data is protected before the old records move.** US-08 comes before US-07, because the old records hold agents' and managers' names.
- **The reports come after the data move,** because they need the deals and their history in Salesforce.
- **US-10, the only Should, comes last.**

## 4. Sprint 1 plan

- **Length:** two weeks
- **Sprint Goal:** Agents can log a deal and move it through its stages in Salesforce, with mistakes and duplicates caught when they save.
- **Stories:** US-01, US-02, US-03 and US-04
- **Plan:**
  1. Set up the deal record and its four stages: Prospecting, Engaging, Won and Lost.
  2. Add the entry checks: validation rules for missing or inconsistent values, and a duplicate rule.
  3. Test each story against its acceptance criteria, then show the sales director at the Sprint Review.
- **Definition of Done:** a story is done when it's built in Salesforce, its acceptance criteria pass, and the sales director has seen it.

## 5. Next steps

- **Into Jira.** Done: the epics, the stories, their order and the Sprint 1 plan are now in Jira. See [Product backlog in Jira](09-jira-backlog.md).
- **Refinement.** US-07 is too big for one sprint, so it's split into smaller stories before it's ready for a sprint.
- **Build.** Sprint 1's stories are built in a Salesforce Trailhead Playground once the data model is specified.

## Assumptions

MavenTech is fictional, so these points couldn't be checked with its staff.

- **Product Owner.** The sales director is treated as the Product Owner, because they're the sponsor and sign off every task in the [RACI chart](03-stakeholder-analysis.md). The BA acts as a proxy product owner, writing and ordering the stories for the sales director to approve.
- **Planned, not held.** No sprint has run yet, so Sprint Planning and the Sprint Review are planned rather than held.
- **Scope and length.** With one analyst doing the work, the Sprint 1 scope and the two-week length are judgements, not a team's estimate. Scrum allows any fixed sprint length of one month or less.

## Sources

- [The 2020 Scrum Guide](https://scrumguides.org/docs/scrumguide/v2020/2020-Scrum-Guide-US.pdf): the Scrum Team, the sprint and its events, the three artifacts and their commitments, refinement and readiness
- [Atlassian: Epics, stories, and initiatives](https://www.atlassian.com/agile/project-management/epics-stories-themes): what an epic is
- [BCS Foundation Certificate in Business Analysis syllabus v4.1](https://www.bcs.org/media/e3fllbw3/ba-foundation-syllabus.pdf): learning outcomes 1.3 (BA role variants, including the proxy product owner), 11.6 (the product backlog) and 12.1 (validating requirements)
- [MavenTech: Requirements catalogue and user stories](07-requirements-catalogue.md): the 10 user stories, their priorities and acceptance criteria
- [MavenTech: Stakeholder analysis](03-stakeholder-analysis.md): the sales director as sponsor, and the RACI chart
- [MavenTech: To-be process map and gap analysis](05-to-be-process-map.md): Salesforce's standard validation and duplicate rules for the entry checks
