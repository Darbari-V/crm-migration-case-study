# MavenTech: PESTLE and SWOT (CRM migration case study)

## About this analysis

**Portfolio case study.** MavenTech is a fictional company, and its CRM data is a public-domain practice dataset from Maven Analytics. The analysis is Varun Kumar Darbari's own work, part of the [MavenTech CRM migration case study](../README.md). The outside factors are illustrative for this fictional case; the GDPR factor reflects the real EU regulation.

**Purpose.** To look at the forces outside MavenTech (PESTLE) and its own strengths and weaknesses (SWOT), and show what the new CRM must handle before MavenTech moves to Salesforce.

## Key takeaway

> **The new CRM must let managers see accurate, up-to-date deal data at any time, and adapt quickly to change, from price rises and new kinds of deals to GDPR.**

## PESTLE: the outside world

Each row gives an outside factor, what it means for MavenTech, and what the new CRM needs because of it.

|  | Factor (outside) | Impact on MavenTech | What it means for the CRM |
| --- | --- | --- | --- |
| **Political** | The government adds extra taxes on electronics. | MavenTech may need to raise prices or accept less profit, and its sales team must explain the change to customers. | Hold up-to-date prices that can be changed quickly, and show which open deals were quoted at the old price. |
| **Economic** | The economy is slow, so big companies have less money to spend. | MavenTech will sell fewer computers, so its sales team must follow up every deal carefully. | Show every open deal and when it was last updated, so managers can spot deals that need a follow-up. |
| **Socio-cultural** | More office staff work from home some days of the week. | MavenTech should stock and sell more laptops and fewer desktop computers. | Show which customers bought desktop computers, so the sales team can offer them laptops. |
| **Technological** | Big companies are starting to use AI tools that need more powerful computers. | MavenTech can sell more powerful computers, and its sales team can contact customers about upgrading. | Record which computers each customer has and when they bought them, so the sales team can offer upgrades. |
| **Legal** | GDPR sets rules on how personal data about people in the EU is collected, stored and deleted. | MavenTech's systems must record why each contact's data is held, keep it no longer than needed, and delete it when asked. | Store why each contact's data is held and when to delete it, and delete a person's data when they ask. |
| **Environmental** | Many big companies have set targets to reach net zero carbon emissions. | MavenTech could recycle old computers and offer trade-in discounts, helping it win customers with green targets. | Record each trade-in (customer, old computer, discount), so managers can see how many computers were recycled and how many customers used the discount. |

## SWOT: the four-box summary

Strengths and weaknesses come from inside MavenTech; opportunities and threats come from the PESTLE above.

|  | **Helpful** | **Harmful** |
| --- | --- | --- |
| **Inside** | **Strengths:** a history of past deals to learn from; sales agents know their big customers well *(assumed for this case)* | **Weaknesses:** managers can't see CRM data outside the system; nobody has checked how complete or accurate the data is |
| **Outside** | **Opportunities:** home working means more laptop sales; AI tools mean more powerful computers to sell; net zero targets open a recycling and trade-in service | **Threats:** extra taxes on electronics; a slow economy cutting IT spending; GDPR rules and fines |

## Sources

- [Regulation (EU) 2016/679, the General Data Protection Regulation](https://eur-lex.europa.eu/eli/reg/2016/679/oj/eng) (EUR-Lex)
- [BCS Foundation Certificate in Business Analysis syllabus v4.1](https://www.bcs.org/media/e3fllbw3/ba-foundation-syllabus.pdf): PESTLE and SWOT definitions
- [Maven Analytics: CRM Sales Opportunities dataset](https://mavenanalytics.io/data-playground/crm-sales-opportunities)
