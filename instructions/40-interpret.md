# Interpreting your results

This guide explains what every survey result means and how to turn it into priorities, with the calculation behind each number so you can reproduce or adjust it. To *produce* the results in the first place (exporting from LimeSurvey and running the spreadsheet, the notebook, or the by-hand method), see [`30-analyze.md`](30-analyze.md). The sections here follow the same order as the analysis spreadsheet's tabs, so you can read them side by side with `analysis-helper.xlsx`.

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

The spreadsheet carries the same list: its **How to use** tab has a "Where to find each answer" index that links each of these nine questions to the tab that answers it.

## What the survey measures

The survey records what each respondent is aware of. That matters most for Section 3, which asks people to tick the practices "already in place." An unticked box means the practice is either not in place or not visible to that person. A practice that exists but nobody knows about is, for practical purposes, a practice that is not working. So read low scores as "absent or invisible," and treat either as a prompt to act.

Because of this, the numbers are best read as signals and proportions ("about two-thirds of respondents say we have an open source policy"), not as exact institutional facts. Whether a given practice actually exists is something you can confirm separately, and the write-in fields often point to where a policy or process lives when one does.

## Which question is answered where

| Question                              | Section below (Spreadsheet tab) |
| ------------------------------------- | ------------------------------- |
| 1. Who responded / representativeness | Respondents                     |
| 2. Importance and why                 | Importance                      |
| 3. Most and least mature areas        | Maturity by area                |
| 4. Position on the L2–L5 ladder       | Level summary                   |
| 5. Most-requested support             | Support needs by area           |
| 6. Biggest maturity-versus-demand gap | Service gaps                    |
| 7. Experience and roles               | Experience & roles              |
| 8. Where support currently comes from | Where support comes from        |
| 9. Community confidence               | Respondents                     |

Each section below gives the calculation (so you can reproduce it by hand) and what the result tells you. To produce these numbers automatically instead, paste your export into the spreadsheet; see [`30-analyze.md`](30-analyze.md).

---

## Respondents

Answers **question 1** (who responded) and **question 9** (confidence). These do not stand alone as findings; they tell you how much weight to put on everything else.

**How it's calculated.**

- Roles (Q10): count how many respondents chose each role option. `count of each role`. Because Q10's options are meant to be customised per institution, the spreadsheet reads the role labels straight from your data on the **Respondents** tab (anything that does not match a label you listed is flagged as "Unmatched").
- Confidence (Q22): count respondents at each of the four levels: Not confident, Somewhat confident, Confident, Very confident.
- Unit / department: the free-text comment on Q10 is listed verbatim in the "In their own words" block on the same tab.

**What it tells you.** Look at the role mix first. If most respondents come from one unit, then "maturity" really means "what that unit is aware of," and thin areas may reflect who did not answer, so note the mix before generalising. Confidence conditions how to read Section 3: a respondent who is new to open source and ticks few boxes is closer to "does not know" than "we do not do this." When unticked boxes cluster among the least-confident respondents, lean toward the "invisible" reading and treat better internal communication as part of the fix.

## Importance

Answers **question 2**: how much the community values open source, and why.

**How it's calculated.**

- Importance (Q20): `share = round( count of each answer ÷ completed responses × 100 )` for each of Not important / Somewhat important / Important / Critical.
- Reasons (Q21, tick all that apply): for each reason, `% = round( respondents who ticked it ÷ completed responses × 100 )`. Q21 only appears for respondents who said open source was at least somewhat important.
- The "Other reason it matters" free-text is listed verbatim on the same tab.

**What it tells you.** "X% say open source is important to our mission, mainly for [top reasons]" is often the single most persuasive line in a proposal. The reasons tell you which argument (cost, vendor lock-in, transparency, funder requirements, sovereignty) may likely resonate with leadership.

## Maturity by area

Answers **question 3**: which areas of practice are most and least mature. Section 3 asks which practices are already in place. The practices map onto the FINOS Open Source Maturity Model (OSMM), a five-level ladder.

- L1, ad-hoc usage: open source is used informally, with no governance.
- L2, compliant usage: governance, policy, compliance, security, and an OSPO.
- L3, contribution: the institution publishes, reviews, and rewards contributions.
- L4, engagement and hosting: it hosts and maintains its own projects, joins foundations, and measures project health.
- L5, leadership and strategy: open source is part of strategy, sustainability planning, and mission.

The survey measures L2 through L5. There is almost nothing at L1, because L1 is the absence of practice and there is little to tick. Most institutions show strength at L2 that thins out toward L4 and L5, and the shape of that decline is the story.

**How it's calculated.**

1. Per item: `item % = round( respondents who ticked it ÷ completed responses × 100 )`. A blank counts as "not in place," so everyone stays in the denominator. In the spreadsheet this is the **Item results (auto)** `%` column, `=ROUND( ticks ÷ completed × 100, 0 )`.
2. Per area: `area % = round( average of that area's item %s )`. In the spreadsheet, **Maturity by area** = `ROUND( AVERAGEIFS(item %, area = Q3x0), 0 )`.

**What it tells you.** The highest areas are where your practice (or at least awareness of it) is strongest; the lowest are where it is absent or invisible. The least-mature areas are candidates for early attention, especially if Section 4 shows demand there (see Service gaps).

### Section 3 items, by area, level, and service

Each item is tagged with its OSMM level and the Academic OSPO service it most closely supports (the 13 services are listed under Service gaps). The mappings are best-fit defaults you can adjust on **Item results (auto)**.

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

## Level summary

Answers **question 4**: where your institution sits on the OSMM ladder.

**How it's calculated.** `level % = average of that level's item %s`, using the OSMM level tagged on each Section 3 item above. In the spreadsheet, **Level summary** = `AVERAGEIFS( item %, type = "Maturity", level = "Lx" )` for each of L2–L5.

**What it tells you.** Read the shape, not a single number. A typical profile is solid at L2 and declining through L4–L5. A high L2 with a steep drop says "we have the basics but little contribution, hosting, or strategy yet," which is a normal and defensible starting point. If L2 itself is low, foundational governance is the first priority.

## Support needs by area

Answers **question 5**: which kinds of support your community most wants. Section 4 asks people to tick the support they would value, across seven themed blocks (Q400–Q460).

**How it's calculated.** `area % = round( average of that block's item %s )`, where each item % is the share of completed respondents who ticked it. In the spreadsheet, **Support needs by area** = `ROUND( AVERAGEIFS(item %, area = Q4x0, type = "Support"), 0 )`. The "Other support wanted" free-text for each block is listed verbatim on the same tab.

**What it tells you.** The highest area is the broad kind of support your community asks for most: the headline of "what an OSPO should offer." For the service-by-service breakdown and how it compares with maturity, see Service gaps next.

## Service gaps

Answers **question 6**: where the biggest maturity-versus-demand gap is. This is the most decision-useful view. It restates Section 4 demand at the level of the 13 Academic OSPO services and sets it against the matching Section 3 maturity.

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

**How it's calculated.** Each Section 4 support item credits one primary service (table below); each Section 3 practice item credits one primary service (the table above, under Maturity by area). Then, for each service:

- `maturity % = average of the Section 3 item %s mapped to that service` (spreadsheet **Service gaps**: `AVERAGEIFS( item %, service = n, type = "Maturity" )`).
- `demand % = average of the Section 4 item %s mapped to that service` (spreadsheet **Service gaps**: `AVERAGEIFS( item %, service = n, type = "Support" )`).
- `gap = demand % − maturity %`.

Two things to watch: the Tools and compute block (Q450) is infrastructure-heavy: nearly all its items map to Developer Tooling & Infrastructure (service 11), so if 11 dominates, check whether the "access to … at low/no cost" items are driving it. And service 1 (OSPO Strategy & Vision) has no demand item; its reading comes from the Section 3 practice questions only.

**What it tells you.** The services to act on first are those where maturity is low and demand is high, a positive and large gap. For example, if few respondents tick the supply-chain security practices and many ask for "advice on security management" or "assessing vendor obligations," that is an evidence-backed case for investing in Supply-Chain Security & SBOM. The **Service gaps** tab sorts this for you; the top of the list, filtered to genuinely low-maturity services, is your priority order.

### Section 4 items and services

Each support item is credited to one primary service. (The full many-to-many mapping is available on **Item results (auto)** if you want to adjust it.)

| Block | Support item | Primary service |
|---|---|---|
| **Q400 Legal, compliance, and risk** | Legal and open source licensing advice and support | 4 |
| | Advice on security management | 5 |
| | Advice on dependency management | 5 |
| | Assessing vendor open source obligations (e.g. CRA compliance, software bills of materials) | 5 |
| | Grant compliance with respect to open source requirements | 9 |
| | Policy recommendations and best practices around open source AI | 13 |
| **Q410 Selection, use, and procurement** | Guidelines or policies for using open source software within [ORGANIZATION] | 6 |
| | Guidelines or policies for procuring open source software | 6 |
| | A curated catalogue or directory of open source tools relevant to [ORGANIZATION]'s community | 6 |
| **Q420 Project creation and maintenance** | Guidelines or policies on managing and maintaining an open source project | 3 |
| | Guidance on transitioning an internal project to open source | 7 |
| | Support writing documentation for open source projects | 3 |
| | An assessment or audit of my open source project's community health and contributor readiness | 10 |
| **Q430 Community and mentoring** | An open source community of practice, discussion group, or learning group | 2 |
| | Mentorship on open source practices for myself or my team | 2 |
| | Mentoring programmes to bring new people into my project | 2 |
| | Training, workshops, and educational materials on open source topics and tools | 2 |
| **Q440 Funding and sustainability** | Support identifying potential funding sources | 9 |
| | Support with grant applications and grant writing | 9 |
| | Dedicated grants or funding from [ORGANIZATION] to sustain and maintain my open source projects | 9 |
| | Help developing a sustainable business or funding model for my open source project | 9 |
| **Q450 Tools and compute resources** | Hosted development tools and infrastructure for open source software | 11 |
| | Support creating containers (e.g. Docker) for my open source software | 11 |
| | Access to CPU or high-performance computing resources at low or no cost | 11 |
| | Access to GPU resources (e.g. for AI/ML workloads) at low or no cost | 11 |
| | Access to data storage infrastructure at low or no cost | 11 |
| | Access to CI/CD pipelines and automated testing infrastructure at low or no cost | 11 |
| | Access to hosted test or staging environments at low or no cost | 11 |
| | Access to licensed software, SaaS tools, or development platforms at low or no cost | 11 |
| **Q460 Advocacy and outreach** | Internal advocacy support to secure organisational buy-in for open source | 8 |
| | Marketing and promotion support for my open source projects | 12 |
| | Help hosting, planning, or co-sponsoring open source events (e.g. conferences and hackathons) | 12 |
| | Support building partnerships and collaborations with external organisations | 12 |
| | Support communicating or measuring the societal impact of my open source work | 10 |

### Priority tiers

As a rough starting order, the 13 services are often grouped into tiers. These are illustrative, a reasonable sequence for a new OSPO, not a prescription. Always set your own priorities from your own gap results.

- Essential: 1 OSPO Strategy & Vision, 2 Community of Practice, 3 Project Lifecycle Support & Maintenance, 4 License & IPR Compliance, 5 Supply-Chain Security & SBOM.
- Should do: 6 Choosing, Using & Procuring Open Source, 7 Open-Sourcing Guidance, 8 Internal Advocacy & Buy-In, 9 Sustainability & Funding Support, 10 Impact Measurement.
- Optional and forward-looking: 11 Developer Tooling & Infrastructure, 12 Outreach & Events, 13 Open Source AI Policy.

## Experience & roles

Answers **question 7** (how people participate and in what roles) and feeds **question 9**. Section 5 is optional and gated by Q51: only respondents who said yes saw Q52–Q58.

**How it's calculated.** The denominator is the people who opted in (Q51 = Yes), not all completed respondents, because only they saw these questions. For each option, `% = round( respondents who ticked it ÷ opted-in respondents × 100 )`. The spreadsheet reports the Q51 opt-in count first, then each block (participation Q52/Q53, contributor roles Q54, motivations Q55, project categories Q56, challenges Q57) on that basis. The "Other …" free-text for Q52, Q54, Q55, Q56 and the Q58 challenges note are listed verbatim on the same tab.

**What it tells you.** This describes the community the OSPO would serve: how hands-on they are (from "follow updates" to "maintain a project"), the roles they hold, why they take part, and the challenges they hit. High challenge counts (limited time, recognition, funding) point to support an OSPO can offer directly, and line up with the Service gaps.

## Where support comes from

Answers **question 8**: where support for each area of practice currently lives inside your institution. This is answered entirely by free text: each Section 3 area has a "where is support for this currently available?" box (Q301–Q371).

**How it's calculated.** There is nothing to average: the spreadsheet lists every non-empty answer verbatim, grouped by area, with a count per area. Read them directly.

**What it tells you.** These notes locate existing capability the checkboxes miss ("the library already runs this," "central IT handles compliance"). They turn a low maturity score into something actionable: either the practice exists in one unit and needs to be made visible, or it genuinely is not there.

## Open comments

The closing free-text question (Q70) collects anything respondents felt was missed. The spreadsheet lists these verbatim on the **Open comments** tab. Read them for context and for issues the structured questions did not capture.

---

## Data-quality checks

Before trusting the numbers, scan for two patterns in the checklist questions (Sections 3 and 4).

- Ticks everything. A respondent who checks every box in a long checklist is often straight-lining rather than answering carefully. Consider setting these aside.
- Ticks nothing. This may indicate disengagement, or a genuine "we do not do any of this." Read it alongside their other answers.

With a small sample, consider reporting headline figures both with and without these respondents and noting the difference. The optional notebook flags both patterns automatically.

## A note on these mappings

The item-to-level and item-to-service mappings are best-fit interpretations. They give you a consistent, defensible way to read results out of the box, but they are not the only reasonable reading. If a mapping does not fit how your institution thinks about its work, adjust it on **Item results (auto)**, and apply the same mapping consistently across all respondents so your comparisons stay valid.
