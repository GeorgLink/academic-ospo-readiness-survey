# Analyse your results

You have collected responses. This step turns them into results. There are three ways to do it, and they all read one LimeSurvey export and produce the same numbers. Once you have the numbers, [`40-interpret.md`](40-interpret.md) explains what each one means and how to turn it into priorities.

## Export your responses

In LimeSurvey: **Results → Export results**, with these settings.

- Format: Microsoft Excel.
- Headings: Question code and question text. This puts codes like `Q300` and `Q400` in the column headers so you can match them to [`../survey/survey-questions.md`](../survey/survey-questions.md).
- Strip HTML code: on.
- Completion state: all responses.
- Responses: full answers.
- Columns: leave all selected.

Save the file. One export feeds all three methods. The spreadsheet and the by-hand method count only completed responses (rows with a submit date) for the percentages; the notebook additionally reports how far people who did not finish got.

### What to expect in the file

- One row per respondent.
- Each checkbox option is its own column, named with the question code and a sub-question code, for example `Q300[SQ001]`. A ticked box reads as `Yes`; an unticked box reads as `No` or is blank. Read a blank as "not in place / not aware of it"; the respondent stays in the denominator either way.
- Single-choice questions (Q20 importance, Q22 confidence) have one column with the chosen option.
- Free-text boxes (the "where does support come from" notes, each "Other," and the final comment) are plain text columns.

Keep [`../survey/survey-questions.md`](../survey/survey-questions.md) open beside the export so you can match codes to wording.

## Choose a method

1. **The spreadsheet (no code; recommended).** Open [`../analysis/analysis-helper.xlsx`](../analysis/analysis-helper.xlsx). Start on the **How to use** tab; its nine-question index links each question to the tab that answers it. Open your exported `results-survey.xlsx`, select everything (Ctrl/Cmd+A) and copy it (Ctrl/Cmd+C). Then, in `analysis-helper.xlsx`, go to the **Data (paste export here)** tab, select all and delete the demo rows, click cell **A1**, and paste. The summary tabs fill in: **Respondents**, **Importance**, **Maturity by area**, **Level summary**, **Support needs by area**, **Service gaps**, **Experience & roles**, **Where support comes from**, and **Open comments**. On **Item results (auto)**, confirm the **Check** column is a tick on every row; a cross means a column was named differently than the spreadsheet expected. Setup details are in [`../analysis/README.md`](../analysis/README.md).
2. **By hand.** Work through [`40-interpret.md`](40-interpret.md), which walks through each count and roll-up step by step. It is also the background for understanding what the spreadsheet and the notebook are doing.
3. **The notebook (optional, automated).** Reproduces the spreadsheet's numbers and adds charts, a findings summary, a completion funnel, data-quality flags, a priority chart, and the progressive view described below. Setup and usage are in [`../analysis/README.md`](../analysis/README.md).

## Completed responses and the progressive view

A long survey loses people along the way: someone may answer the first parts and stop partway through. To use that data fairly, the numbers can be read two ways.

- The spreadsheet and the by-hand method use only **fully completed** responses. This is the simplest, most conservative view, and the numbers are directly comparable across institutions.
- The notebook reports those same completed-only numbers (Part A), then recalculates each insight over everyone who reached that part (Part B): who responded and why open source matters, over everyone who finished parts 1 and 2; the maturity picture, over everyone who completed part 3; and service demand, over everyone who completed part 4. Someone who answered the first parts and stopped in part 3 still counts toward "who responded and why."

How the tools decide who reached what: they read two fields LimeSurvey records for every response: the submission date and the last page the person reached. A response counts as completed once it has a submission date. To place a partial response, the notebook uses the last page reached, not which boxes were ticked. That distinction matters because the Section 3, 4, and 5 questions are optional: a respondent can deliberately skip one and leave it blank. Counting by the page reached means a skipped or blank section still counts as a real response, not a missed one.

Reporting that, say, 84 people told you open source matters is a stronger signal than reporting that 12 finished the whole survey. Expect drop-off on a survey this length, and use the progressive view so partial responses are not wasted.

## Then read the results

Whichever method you use, [`40-interpret.md`](40-interpret.md) explains what every number means and how to turn it into priorities. For drafting a summary or talking points from the results, see [`41-using-ai-to-analyze.md`](41-using-ai-to-analyze.md).
