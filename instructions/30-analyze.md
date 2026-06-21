# Analyze your results

You have collected responses. This step turns them into results. There are three ways to do it, and they all read one LimeSurvey export and produce the same numbers.

## Export your responses

In LimeSurvey: **Results → Export results**, with these settings.

- Format: Microsoft Excel.
- Headings: Question code and question text.
- Strip HTML code: on.
- Completion state: all responses.
- Responses: full answers.
- Columns: leave all selected.

Save the file. One export feeds all three methods. The notebook and the spreadsheet automatically count only completed responses for the percentages; the notebook additionally reports how far people who did not finish got.

## Choose a method

1. **The notebook (automated).** Produces the charts, tables, a findings summary, a completion funnel, data-quality flags, and a priority chart. Setup and usage are in [`../analysis/README.md`](../analysis/README.md).
2. **The spreadsheet (no code).** Open [`../analysis/analysis-helper.xlsx`](../analysis/analysis-helper.xlsx), go to the **Data (paste export here)** tab, delete the demo rows, and paste your export into cell A1. The summary tabs fill in.
3. **By hand.** Work through [`40-interpret.md`](40-interpret.md), which walks through the counting and roll-ups step by step.

## Completed responses and the progressive view

A long survey loses people along the way: someone may answer the first parts and stop partway through. To use that data fairly, the notebook reports results two ways.

- The spreadsheet and the by-hand method use only **fully completed** responses. This is the simplest, most conservative view, and the numbers are directly comparable across institutions.
- The notebook reports those same completed-only numbers (Part A), then recalculates each insight over everyone who reached that part (Part B): who responded and why open source matters, over everyone who finished parts 1 and 2; the maturity picture, over everyone who completed part 3; and service demand, over everyone who completed part 4. Someone who answered the first parts and stopped in part 3 still counts toward "who responded and why."

How the tools decide who completed what: they read two fields LimeSurvey records for every response — the submission date and the last page the person reached. A response counts as completed once it has a submission date. To place a partial response, the notebook uses the last page reached, not which boxes were ticked. That distinction matters: each maturity and support question ends with a "None of the above" option, and when someone picks it LimeSurvey leaves the other options blank (shown as N/A in the export). Counting by the page reached means a "None of the above" answer is treated as a real response, not a skipped section.

Reporting that, say, 84 people told you open source matters is a stronger signal than reporting that 12 finished the whole survey. Expect drop-off on a survey this length, and use the progressive view so partial responses are not wasted.

## Then read the results

Whichever method you use, [`40-interpret.md`](40-interpret.md) explains what every number means and how to turn it into priorities. For drafting a summary or talking points from the results, see [`41-using-ai-to-analyze.md`](41-using-ai-to-analyze.md).
