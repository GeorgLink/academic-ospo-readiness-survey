# Using AI to analyse your results

An AI assistant (such as ChatGPT, Claude, Gemini, or Copilot) can turn your computed results into a readable summary, suggest priorities, draft communications for stakeholders, and group the free-text answers into themes. It is a writing and interpretation aid, not a calculator. Do the counting with the spreadsheet or the notebook first, then give the AI the results rather than the raw data.

## Privacy comes first

Your responses, and especially the free-text write-ins, can contain names, team or department names, project names, and other identifying details. Treat them as sensitive.

Give the AI aggregated results, not raw response rows. The service and level summaries, the item percentages, and the notebook's findings file are already aggregated and carry little personal information. The raw export and the verbatim write-ins do not.

Before pasting any write-ins, remove names, unit names, and anything that points to an individual. Better still, paste a summary of the write-ins instead of the verbatim text.

Check your institution's rules. If you used the survey for anything beyond internal quality improvement, your IRB or ethics approval and your institution's AI-use policy may limit what can go into a third-party tool. When in doubt, use an institution-approved or local AI, or do not paste the text.

The AI sees only what you paste. It has no access to your files unless you provide them.

## What AI does and does not do well here

It is useful for summarising the numbers in plain language, turning the gap table into a phased plan, drafting a leadership one-pager or talking points, grouping free-text comments into themes, and explaining what a maturity pattern typically means.

It is not reliable for producing the numbers, which you should always compute yourself, and it will guess at figures if you let it. It does not make the final call on priorities. It drafts, and you decide.

Add this line to every prompt: "Use only the numbers I provide. Do not invent or estimate any figures. If something isn't supported by the data I gave you, say so."

## What to paste in

The most useful and safest input is the Service gaps and Level summary tabs of `../analysis/analysis-helper.xlsx`, which give the maturity, demand, and gap per service and the L2–L5 ladder. The item results add the per-item percentages when you want the detail behind a service. The notebook's `findings.md` is already a plain-text summary of the headline numbers. The LimeSurvey Statistics export gives per-question counts for demographics, importance, and confidence. Write-ins should go in only after de-identification, and ideally as themes rather than verbatim text.

To copy a table from the spreadsheet, select it and paste. The AI reads tab-separated or comma-separated text.

## Sample prompts

Executive summary for leadership:

> Below are aggregated results from an open source survey at our institution. Write a one-page summary for university leadership: where we stand on open source maturity, what our community most wants, and the three priorities where maturity is low but demand is high. Plain language, no jargon. Use only the numbers I provide. Do not invent or estimate any figures. If something isn't supported by the data I gave you, say so.
>
> [paste Service gaps + Level summary]

Turn the gaps into a phased plan:

> Here is our service gap table (gap = demand − maturity; higher = more urgent). Propose a phased 12-month plan for a new open source program office, grouped into "quick wins" and "strategic investments." For each item, name the evidence (the service and its gap) that supports it. Use only the numbers I provide. Do not invent or estimate any figures. If something isn't supported by the data I gave you, say so.
>
> [paste the 13 services with maturity %, demand %, gap]

Interpret the maturity pattern:

> These are our maturity scores by OSMM level (L2–L5). Explain, in plain language, what this pattern typically means for an institution and what it suggests we should focus on next. Note any caveats given our sample size of [N] respondents. Use only the numbers I provide. Do not invent or estimate any figures. If something isn't supported by the data I gave you, say so.
>
> [paste Level summary]

Theme the free-text comments (de-identified):

> Below are anonymised free-text comments about where open source support currently exists at our institution. Group them into themes, summarise each theme in a sentence, and flag any that name a specific existing capability or a specific gap. Do not infer identities. Use only the numbers I provide. Do not invent or estimate any figures. If something isn't supported by the data I gave you, say so.
>
> [paste de-identified write-ins]

Talking points for a specific audience:

> Using the summary below, write five talking points to make the case for investing in open source support to [audience: e.g. the CIO, a faculty senate, or a funding body]. Keep each to two sentences and ground each in a specific number. Use only the numbers I provide. Do not invent or estimate any figures. If something isn't supported by the data I gave you, say so.
>
> [paste Service gaps + the importance and confidence figures]

## Checking the AI's output

Verify every number the AI cites against your own tables, and delete any figure you did not give it. Treat the text as a draft, and edit the framing and priorities to fit what you know about your institution. With a small sample the AI may state patterns too strongly, so add "given our sample size" and soften claims. The numbers come from your survey, and the spreadsheet and notebook show how they were produced. The AI only helps you say it well.
