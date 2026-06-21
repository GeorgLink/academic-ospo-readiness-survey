# Interpreting your results

This guide explains how to read the survey results: what the survey can tell you, the three ways to produce the analysis, and how to do the analysis by hand.

## What this survey answers

The survey is built to answer nine questions about your institution and the people who responded.

1. Who responded, and how representative are they of your institution?
2. How important is open source to your institution, and why?
3. Which areas of open source practice are most and least mature?
4. Where does your institution sit on the open source maturity ladder (OSMM levels L2–L5)?
5. Which support services does your community most want?
6. Where is the biggest gap, meaning low maturity but high demand, that an open source program office (OSPO) should address first?
7. How experienced is your community with open source, and in what roles do people participate?
8. Where does support for these practices currently come from inside your institution?
9. How confident is your community in the open source practices relevant to their roles?

The rest of this guide is organised around producing those answers.

## What the survey measures

The survey records what each respondent is aware of. That matters most for Section 3, which asks people to tick the practices "already in place." An unticked box means the practice is either not in place or not visible to that person. A practice that exists but nobody knows about is, for practical purposes, a practice that is not working. So read low scores as "absent or invisible," and treat either as a prompt to act.

Because of this, the numbers are best read as signals and proportions ("about two-thirds of respondents say we have an open source policy"), not as exact institutional facts. Whether a given practice actually exists is something you can confirm separately, and the write-in fields often point to where a policy or process lives when one does.

## Three ways to analyse your results

There are three ways to turn an export into the answers above. They use the same method and produce the same numbers.

1. **The analysis notebook.** A Python notebook that reads your export and produces the charts, tables, and a findings summary automatically. It also adds a completion funnel, data-quality flags, a priority chart, and a progressive view that reports each insight over everyone who completed that part of the survey, not only those who finished (see [`30-analyze.md`](30-analyze.md)). Setup and usage are in the [analysis README](../analysis/README.md).
2. **The analysis spreadsheet.** Paste your export into `analysis-helper.xlsx` and the tabs fill in. This guide's "spreadsheet" section below explains it.
3. **By hand.** The rest of this guide walks through the analysis step by step. This is also the background for anyone who wants to understand what the notebook and the spreadsheet are doing.

The notebook and the spreadsheet do the same counting and roll-ups described in the by-hand sections, so you can reproduce any of their numbers yourself.

### Which method answers which question

| Question | By-hand section | Spreadsheet tab |
|---|---|---|
| 1. Who responded / representativeness | Who answered | Respondents |
| 2. Importance and why | Who answered | Importance |
| 3. Most and least mature areas | Maturity, by area | Maturity by area |
| 4. Position on the L2–L5 ladder | Maturity, by level | Level summary |
| 5. Most-requested services | Service demand | Service summary |
| 6. Biggest maturity-versus-demand gap | The gap | Service summary |
| 7. Experience and roles | Who answered | Experience & roles |
| 8. Where support currently comes from | Write-in comments | Write-ins |
| 9. Community confidence | Who answered | Respondents |

## The spreadsheet (the shortcut)

`analysis-helper.xlsx` does the counting and the roll-ups for you; you paste your data in once. It works in Excel, LibreOffice Calc, and Google Sheets.

To use it:

1. Export your responses (settings in the next section).
2. Open `analysis-helper.xlsx`.
3. On the **Data (paste export here)** tab, select all, delete the demo rows, click cell A1, and paste your export.
4. Read **Service summary** (maturity, demand, and the gap for each service), **Level summary** (the L2–L5 ladder), and the per-question tabs.
5. On **Item results (auto)**, confirm the **Check** column is a tick on every row. A tick means the spreadsheet found that question in your data; a cross means the column was named differently than expected.

The spreadsheet computes the share of respondents who ticked each item, which matches LimeSurvey's own "Gross percentage," then averages those item scores into the 13 services and the OSMM levels and subtracts to get the gap. It assigns each item to one primary service and one OSMM level, using the same mapping shown in the tables below. If you disagree with an assignment, change it on the **Item results (auto)** tab and the summaries update.

## Exporting your responses

Both the spreadsheet and the notebook read one export. From LimeSurvey: **Results → Export results**, with these settings.

- Format: Microsoft Excel.
- Headings: Question code and question text. This puts codes like `Q300` and `Q400` in the column headers so you can match them to `../survey/survey-questions.md`.
- Strip HTML code: on.
- Completion state: all responses.
- Responses: full answers.
- Columns: leave all selected.

The notebook and the spreadsheet count only completed responses for the numbers. If you analyze by hand, count only completed responses (the rows that have a submit date), or use LimeSurvey's Statistics page with Complete only, which does this for you.

A few things to expect in the file:

- One row per respondent.
- Each checkbox option is its own column, named with the question code and a sub-question code, for example `Q300[SQ001]`. A ticked box reads as `Yes`; an unticked box reads as `No` or is blank.
- "None of the above" is its own column in each checklist block. When a respondent picks it, LimeSurvey blanks that block's other options to `N/A`. Read those `N/A` cells as "not in place": the respondent answered the question, they just reported nothing in place.
- Single-choice questions (Q20 importance, Q22 confidence) have one column with the chosen option.
- Free-text boxes (the "where does support come from" notes, "Other," and the final comment) are plain text columns.

Keep `../survey/survey-questions.md` open beside the export so you can match codes to wording.

## Maturity

Section 3 asks which practices are already in place. The practices map onto the FINOS Open Source Maturity Model (OSMM), a five-level ladder.

- L1, ad-hoc usage: open source is used informally, with no governance.
- L2, compliant usage: governance, policy, compliance, security, and an OSPO.
- L3, contribution: the institution publishes, reviews, and rewards contributions.
- L4, engagement and hosting: it hosts and maintains its own projects, joins foundations, and measures project health.
- L5, leadership and strategy: open source is part of strategy, sustainability planning, and mission.

The survey measures L2 through L5. There is almost nothing at L1, because L1 is the absence of practice and there is little to tick. Most institutions show strength at L2 that thins out toward L4 and L5, and the shape of that decline is the story.

### Reading maturity by hand

1. Per item: count how many respondents ticked each box and divide by the total number of completed respondents, not by the number of non-blank cells. A blank or `N/A` cell counts as "not in place," so everyone stays in the denominator. That is the share who say the practice is in place.
2. Per area: average the item shares within a block (Q300, Q310, and so on) for a read on how mature your governance, security, or contribution practice is. This answers question 3.
3. Per level: group items by their OSMM level and average each group. This answers question 4.

### Section 3 items, by area, level, and service

Each item is tagged with its OSMM level and the Academic OSPO service it most closely supports (the 13 services are listed under Service demand). The mappings are best-fit defaults you can adjust to your own context.

| Area | Practice item | OSMM level | Primary service |
|---|---|---|---|
| **Q300 Policy & OSPO** | Has an open source program office (OSPO) or equivalent function | L2 | 1 |
| | Has an open source use policy | L2 | 4 |
| | Has a defined process for using open source software | L2 | 6 |
| | Provides staff with guidance on the responsible use of open source AI | L2 | 13 |
| **Q310 Compliance and risk** | Has standardized controls around open source use | L2 | 4 |
| | Has an automated process for managing open source IP / license compliance | L2 | 4 |
| | Includes open source risk management in its compliance policy | L2 | 5 |
| | Engages its technology-transfer or knowledge-exchange office when releasing or licensing open source software | L4 | 7 |
| | Provides internal license-compliance training | L2 | 4 |
| | Addresses AI-generated code (licensing, attribution, and IP) in its open source or compliance policy | L2 | 13 |
| **Q320 Security & supply chain** | Uses code-scanning tools to audit software composition and dependencies | L2 | 5 |
| | Runs penetration tests and periodic threat assessments for open source software | L2 | 5 |
| | Provides security training for teams working on open source software | L2 | 5 |
| **Q330 Selection, use & procurement** | Has a process to choose between open source alternatives | L2 | 6 |
| | Prefers open source solutions over proprietary software where appropriate | L2 | 8 |
| | Applies open source criteria in procurement decisions | L2 | 6 |
| | Has a procurement process that doesn't hinder open source use | L2 | 6 |
| | Maintains a software asset registry / inventory | L2 | 5 |
| | Provides internal training on open source usage policies and procedures | L2 | 4 |
| **Q340 Open source contribution** | Has policies to govern contribution to open source ecosystems | L3 | 8 |
| | Has a clear policy for how staff publish or contribute to open source projects | L3 | 8 |
| | Has processes that support open source contribution | L3 | 8 |
| | Has a review process for code and non-code contributions | L3 | 8 |
| | Has a lifecycle process for engaging with open source projects | L3 | 3 |
| **Q350 Community and outreach** | Promotes and rewards contribution to open source projects | L3 | 8 |
| | Tracks staff or members' open source contributions | L3 | 10 |
| | Maintains an inventory of open source projects created within [ORGANIZATION] | L4 | 10 |
| | Fosters outreach for the visibility of its open source projects | L3 | 12 |
| | Engages marketing / communications in open source publishing efforts | L3 | 12 |
| **Q360 Hosting and maintenance** | Has a defined process for open-sourcing internal projects | L4 | 7 |
| | Holds maintainer status on one or more open source projects | L4 | 3 |
| | Measures the health of the open source projects it maintains | L4 | 10 |
| | Tracks the adoption and impact of its research software (downloads, citations, reuse) | L4 | 10 |
| | Is a member of one or more software foundations | L4 | 2 |
| | Tracks KPIs / metrics around its open source foundation engagement | L4 | 10 |
| | Provides shared development infrastructure (e.g. code hosting, CI/CD) for its open source projects | L4 | 11 |
| | Offers compute or storage resources to support open source development | L4 | 11 |
| **Q370 Leadership and strategy** | Management recognises the benefits of open source | L3 | 8 |
| | Management understands the cost savings of open source | L3 | 8 |
| | Defines goals and objectives in an open source strategy | L5 | 1 |
| | Connects its open source work to its research mission and impact | L5 | 1 |
| | Has a strategy for the financial sustainability of its open source projects | L5 | 9 |
| | Allocates dedicated budget or funding to sustain and maintain its open source projects | L4 | 9 |
| | Formally allocates staff time to open source maintenance and contribution | L4 | 9 |

## Service demand

Section 4 asks which kinds of support people want. The survey does not ask "which services do you want?" directly. Instead, the seven themed support blocks (Q400–Q460) each map to the 13 Academic OSPO service categories. Tallying those across respondents tells you which services are most in demand, which answers question 5.

The 13 Academic OSPO services:

*Foundational*
1. OSPO Strategy & Vision: define the OSPO's purpose, scope, and how its success is measured.
2. Community of Practice: a facilitated forum that produces concrete deliverables.
3. Project Lifecycle Support & Maintenance: guide projects from prototype through maintenance.
4. License & IPR Compliance: actionable licensing guidance and a clear IPR policy.
5. Supply-Chain Security & SBOM: SBOMs, vulnerability tracking, regulation-aligned compliance.

*Core body*
6. Choosing, Using & Procuring Open Source: guidance for evaluating, adopting, and procuring open source.
7. Open-Sourcing Guidance: a defined process for releasing an internal project as open source.
8. Internal Advocacy & Buy-In: help teams make the open source case to leadership.
9. Sustainability & Funding Support: connect projects to funding instruments and sustainability planning.
10. Impact Measurement: a small set of measures that show what the institution's open source work delivers.

*Leadership and forward-looking*
11. Developer Tooling & Infrastructure: shared infrastructure such as hosting, CI/CD, compute, and onboarding.
12. Outreach & Events: visibility activities such as conference sessions, outreach materials, and event presence.
13. Open Source AI Policy: guidance on open source AI, including licensing of AI-generated code, AI tooling, and AI-regulation-aligned policy.

### Reading demand by hand

1. For each ticked Section 4 item, credit its primary service (the first one listed in the table below).
2. Sum the credits per service across all respondents.
3. Rank the 13 services. The top of the ranking is what your community asks for most.

Two things to watch while you tally:

- The Tools and compute block (Q450) is infrastructure-heavy: nearly all its items map to Developer Tooling & Infrastructure (service 11). If service 11 dominates, check whether the "access to … at low/no cost" items are driving it.
- Service 1 (OSPO Strategy & Vision) receives no direct support item. It is read from the Section 3 practice questions, not from demand.

### Section 4 items and services

The mapping is many-to-many; the primary service is listed first. Each block also has a free-text comment box, read by hand under Write-in comments.

| Block | Support item | Services (primary first) |
|---|---|---|
| **Q400 Legal, compliance, and risk** | Legal and open source licensing advice and support | 4 |
| | Advice on security management | 5 |
| | Advice on dependency management | 5, 6 |
| | Assessing vendor open source obligations (e.g. CRA compliance, software bills of materials) | 5, 4 |
| | Grant compliance with respect to open source requirements | 9, 4 |
| | Policy recommendations and best practices around open source AI | 13 |
| **Q410 Selection, use, and procurement** | Guidelines or policies for using open source software within [ORGANIZATION] | 6, 4 |
| | Guidelines or policies for procuring open source software | 6 |
| | A curated catalogue or directory of open source tools relevant to [ORGANIZATION]'s community | 6, 11 |
| **Q420 Project creation and maintenance** | Guidelines or policies on managing and maintaining an open source project | 3, 7 |
| | Guidance on transitioning an internal project to open source | 7 |
| | Support writing documentation for open source projects | 3, 11 |
| | An assessment or audit of my open source project's community health and contributor readiness | 10, 3 |
| **Q430 Community and mentoring** | An open source community of practice, discussion group, or learning group | 2 |
| | Mentorship on open source practices for myself or my team | 2 |
| | Mentoring programmes to bring new people into my project | 2, 12 |
| | Training, workshops, and educational materials on open source topics and tools (e.g. programming languages, popular packages) | 2, 4, 5, 11 |
| **Q440 Funding and sustainability** | Support identifying potential funding sources | 9 |
| | Support with grant applications and grant writing | 9 |
| | Dedicated grants or funding from [ORGANIZATION] to sustain and maintain my open source projects | 9 |
| | Help developing a sustainable business or funding model for my open source project | 9 |
| **Q450 Tools and compute resources** | Hosted development tools and infrastructure for open source software | 11 |
| | Support creating containers (e.g. Docker) for my open source software | 11 |
| | Access to CPU or high-performance computing resources at low or no cost | 11 |
| | Access to GPU resources (e.g. for AI/ML workloads) at low or no cost | 11, 13 |
| | Access to data storage infrastructure at low or no cost | 11 |
| | Access to CI/CD pipelines and automated testing infrastructure at low or no cost | 11 |
| | Access to hosted test or staging environments at low or no cost | 11 |
| | Access to licensed software, SaaS tools, or development platforms at low or no cost | 11 |
| **Q460 Advocacy and outreach** | Internal advocacy support to secure organisational buy-in for open source | 8 |
| | Marketing and promotion support for my open source projects | 12 |
| | Help hosting, planning, or co-sponsoring open source events (e.g. conferences and hackathons) | 12 |
| | Support building partnerships and collaborations with external organisations | 12, 2 |
| | Support communicating or measuring the societal impact of my open source work | 10, 12 |

## The gap

This combines maturity and demand, and it is the most decision-useful view. It answers question 6.

For each service you now have two readings: maturity from the Section 3 items mapped to that service, and demand from the Section 4 roll-up. The services to act on first are those where maturity is low and demand is high. For example, if few respondents tick the supply-chain security practices (the Q310 risk item and the Q320 security items) and many ask for "advice on security management" or "assessing vendor obligations," that is an evidence-backed case for investing in Supply-Chain Security & SBOM.

A simple way to present it: list the 13 services and, for each, note "practice: low/medium/high" beside "demand: low/medium/high." The low-practice, high-demand rows are your priorities.

## Who answered

The nine questions above include several about the people who responded, not the institution. These do not stand alone as findings; they tell you how much weight to put on the rest and let you read it in context.

- **Representativeness (question 1).** Look at the role question (Q10) first. If most respondents come from one unit, then "maturity" really means "what that unit is aware of," and thin areas may reflect who did not answer. Note the mix before generalising. If you customised Q10’s role options, the notebook reads roles straight from your data, while in the spreadsheet you update the role labels on the **Respondents** tab to match (anything unmatched is flagged there).
- **Importance and reasons (question 2).** Q20 and Q21 show how much the community values open source and why. "X% say open source is important to our mission, mainly for [reasons]" is often the most persuasive line in a proposal.
- **Confidence (question 9).** Q22 conditions how to read Section 3. A respondent who is new to open source or low in confidence and ticks few boxes is closer to "does not know" than "we do not do this." When unticked boxes cluster among the least-confident respondents, lean toward the "invisible" reading and treat better internal communication as part of the fix.
- **Experience and roles (question 7).** Section 5 (Q52, Q54) shows how people participate in open source and in what roles, which describes the community the OSPO would serve.

## Write-in comments

The optional free-text boxes answer question 8. Each Section 3 area has a "where is support for this currently available?" box (Q301–Q371), each Section 4 block has an "any other support?" box (Q401–Q461), and Q70 is the final comment. Read them verbatim, grouped by question. They locate existing capability ("the library already does this") and surface needs the checkboxes miss.

## Priority tiers

As a rough starting order, the 13 services are often grouped into tiers. These are illustrative, a reasonable sequence for a new OSPO, not a prescription. Set your own priorities from your own results.

- Essential: 1 OSPO Strategy & Vision, 2 Community of Practice, 3 Project Lifecycle Support & Maintenance, 4 License & IPR Compliance, 5 Supply-Chain Security & SBOM.
- Should do: 6 Choosing, Using & Procuring Open Source, 7 Open-Sourcing Guidance, 8 Internal Advocacy & Buy-In, 9 Sustainability & Funding Support, 10 Impact Measurement.
- Optional and forward-looking: 11 Developer Tooling & Infrastructure, 12 Outreach & Events, 13 Open Source AI Policy.

## Data-quality checks

Before trusting the numbers, scan for two patterns in the checklist questions (Sections 3 and 4).

- Ticks everything. A respondent who checks every box in a long checklist is often straight-lining rather than answering carefully. Consider removing these responses.
- Ticks nothing, or only "None of the above." This may indicate disengagement, or a genuine "we do not do any of this." Read it alongside their other answers.

With a small sample, consider reporting headline figures both with and without these respondents and noting the difference. The notebook flags both automatically.

## A note on these mappings

The item-to-level and item-to-service mappings are best-fit interpretations. They give you a consistent, defensible way to read results out of the box, but they are not the only reasonable reading. If a mapping does not fit how your institution thinks about its work, adjust it, and apply the same mapping consistently across all respondents so your comparisons stay valid.
