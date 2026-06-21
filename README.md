# Academic OSPO Readiness Survey

A ready-to-run survey that any university or research institution can use to take stock of its open source practices and find out what support its community most wants.

This repository contains the survey, step-by-step instructions to run it, and two tools to analyse the results: a no-code spreadsheet and a Python notebook. (You can also work through the analysis by hand, so the guides describe three ways in total.)

## What it answers

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

## Who it's for

Staff at a university or research institution who want to run an open source maturity and support needs survey on their own: a research-software group, a library, central IT, or an emerging Open Source Programs Office (OSPO). The guides assume no special technical background beyond being able to run your own LimeSurvey.

## What you need to run the survey

You need a survey tool to host the questions and collect responses. This package was built and tested on **LimeSurvey**, and that is what we recommend.

You can use another tool if you prefer. Qualtrics, Google Forms, and SurveyMonkey can all run a survey like this, but you would recreate the questions by hand from [`survey/survey-questions.md`](survey/survey-questions.md): the `.lss` template and the analysis spreadsheet and notebook are specific to LimeSurvey's export and will not apply directly. If you go that route, check that your tool supports multi-select questions and the conditional opt-in for Section 5, and plan to adapt the analysis yourself.

LimeSurvey is a strong fit on its own merits. It is open source, so you can self-host it or use LimeSurvey's own hosting and keep your responses under your control. It supports the conditional logic this survey relies on, such as the optional Section 5 questions that appear only if a respondent opts in and the "tick all that apply" questions in Sections 3 and 4. And it makes both the survey template and the collected results easy to import and export.

Any tool can run this survey, but choosing LimeSurvey is the easy path: we already provide the importable `.lss` template, and the analysis spreadsheet and notebook read the LimeSurvey export directly, so you do not have to build anything custom.

## You don't need an institutional sponsor

You can run this survey without a formal mandate, a budget, or an existing OSPO. A single research-software group, a library team, central IT, or one motivated person can send it to colleagues and run the analysis.

Running the survey is itself a way to build the case for an OSPO. It gives you evidence of where practices are thin and what support people actually want, in your own institution's words. Start small, share what you find with the people who responded and with anyone who can act on it, and use the results to argue for the next step. The [communications plan](instructions/21-communications-plan.md) includes a path for this kind of small, grassroots distribution alongside a full institution-wide campaign.

## What's included

| Path | What it is |
|------|------------|
| `instructions/` | The step-by-step guides: set up (10, 11), distribute (20, 21, 22), analyse (30), and interpret (40, 41). Start here. |
| `survey/survey-questions.md` | The full question list in plain text, so you can read or share the survey without a LimeSurvey login. |
| `survey/academic-ospo-readiness-survey-template.lss` | The importable LimeSurvey template. Load it into your own LimeSurvey instance. |
| `analysis/analysis-helper.xlsx` | A spreadsheet that computes the results from an export, with no code. |
| `analysis/survey-analysis.ipynb` | A Python notebook that produces charts, tables, and a findings summary from an export. |
| `instructions/Academic-OSPO-Readiness-Survey-Training.pptx` · `.pdf` | A step-by-step training slide deck (PowerPoint with speaker notes, plus PDF) covering set up, distribute, export, analyse, and interpret. |
| `LICENSE.md` | The full Creative Commons Attribution 4.0 (CC BY 4.0) license. |

## Quick start

1. Read [`instructions/README.md`](instructions/README.md) first. It lays out the order to work through the guides. Prefer slides? A full training deck is included: [PPTX](instructions/Academic-OSPO-Readiness-Survey-Training.pptx) · [PDF](instructions/Academic-OSPO-Readiness-Survey-Training.pdf).
2. You will need a survey tool. We recommend LimeSurvey, self-hosted or hosted by LimeSurvey. The survey template was built and tested on **LimeSurvey 6.17.9**.
3. Set up the survey: [`instructions/10-setup.md`](instructions/10-setup.md). Before importing, open the `.lss` in a plain-text editor and replace the placeholders (`[ORGANIZATION]`, `[CONTACT NAME]`, `[CONTACT EMAIL]`, `[DATA-HOSTING STATEMENT]`), then import, make the few edits your institution needs, and activate.
4. Distribute it: [`instructions/20-distribute.md`](instructions/20-distribute.md), with the communications plan and invitation templates alongside.
5. Analyse and interpret the results: [`instructions/30-analyze.md`](instructions/30-analyze.md) and [`instructions/40-interpret.md`](instructions/40-interpret.md).

## A note on hosting

This package does not include hosting. Each institution runs the survey on its own LimeSurvey instance, so your responses stay under your control.

## License and attribution

This package is licensed under **Creative Commons Attribution 4.0 International (CC BY 4.0)**. You are free to use, adapt, and redistribute it, including for your own institution, as long as you give appropriate credit. Please attribute as:

> Academic OSPO Readiness Survey © CURIOSS, licensed under CC BY 4.0.

The full license text is in [`LICENSE.md`](LICENSE.md) ·
<https://creativecommons.org/licenses/by/4.0/>
