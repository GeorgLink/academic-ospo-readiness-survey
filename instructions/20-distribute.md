# 2. Distribute the survey

Once the survey is set up and activated, you send it to the people you want to hear from. Pair this with the [21-communications-plan.md](21-communications-plan.md) for timing and the [22-invitation-templates.md](22-invitation-templates.md) for the wording.

## Decide who to invite

Define your target population before you send anything. Common choices:

- Everyone at the institution (broadest picture, lower response rate).
- A defined group: research-software engineers, IT staff, library staff, faculty in computational fields, or members of a community you already run.
- A mix: a broad invitation plus a direct ask to groups you most want to hear from.

The survey works for a broad audience. Many questions are about whether the institution does something, and people are explicitly told that "not sure" is a fine answer (they just leave items unticked). So you don't need to limit it to experts.

## Pick a distribution method

LimeSurvey gives you two main options:

- **Open public link.** You activate the survey and share one link. Anyone with the link can respond, and responses are anonymous. Simplest to run and best for a broad, open invitation; you can't send automated reminders to specific people. After activating, the public link is shown on the survey **Overview** page (look for **Survey URL**). Copy that and share it in your emails and messages.

- **Participant list (tokens).** You load a list of invitees and LimeSurvey sends each person a unique link, tracks who has responded, and can send reminders only to those who haven't. More setup, but much better for reminders and for measuring your response rate. To set it up after activation: open **Survey participants** (top menu) → **Initialise participant table** → **Add participants** (type them in, or import a CSV of names and emails) → **Invitations & reminders → Send invitations**. Reminders work the same way (**Send reminders**) and go only to people who haven't responded yet.

A response rate is only reliable when you know the denominator: how many people could have responded. A participant list gives you that, since you know exactly who was invited, so it is the dependable way to measure a rate. With an open public link you can count responses but not how many people saw the link, so any rate there is an estimate against your best guess of the audience size.

Keep **Anonymised responses** on (the template already does this). LimeSurvey can then track *whether* someone responded without linking *what* they answered to their identity.

A good middle path: use a participant list for the groups you most want to reach (so you can remind them), and also publish an open link for everyone else.

## Tips for a good response rate

- **Send from a person, not a system.** Invitations from a named, recognisable sender do better than no-reply addresses.
- **Keep the invitation short.** Say why it matters, how long it takes (about 12 minutes), and that it's anonymous. The templates do this.
- **Time it well.** Avoid holidays, exam periods, and the first and last weeks of term. Mid-week mornings tend to work.
- **Send reminders.** Two reminders, spaced about a week apart, typically recover a meaningful share of responses. With a participant list, reminders go only to non-responders.
- **Get a visible endorsement.** A short note of support from a dean, CIO, or respected colleague raises response rates more than anything else.
- **Tell people what happens next.** Knowing the results will be shared and acted on makes people more likely to take part. The survey's closing message invites respondents to email the survey contact to hear the outcome.

## Closing the survey

Decide your end date in advance (two to three weeks is common) and put it in the invitation. You can set an expiry date (**Settings → Publication & access → Expiry date/time**) so the survey closes itself, or stop it manually by deactivating it (stopping keeps all the data; only new entries are blocked).

When you're done collecting, export the responses: **Results → Export results**. The exact settings are in [30-analyze.md](30-analyze.md). Keep the exported file safe for the analysis stage.

> Next, [30-analyze.md](30-analyze.md) turns the export into results with the notebook or the spreadsheet, and [40-interpret.md](40-interpret.md) explains how to read them.
