# 1. Set up the survey

*Written for LimeSurvey Cloud 6.17.9. The interface may look slightly different in other versions; the steps and menu names are usually stable even when the layout changes.*

This guide takes you from a blank slate to a live survey link. From creating an account to a shareable link, it takes about 30–45 minutes.

> **Before you launch: check whether you need ethics approval.** Running this as an internal quality-improvement exercise usually does not require review. But if you might **present or publish** the results (a paper, a conference talk, a public report), that typically makes it human-subjects research, and approval has to be in place **before** you collect data, not after. If publication is even possible, check with your **IRB, research ethics committee, or equivalent** first. Requirements differ by country and institution, so confirm with your own people rather than assuming.

## What you will need

- **A LimeSurvey instance.** Either a LimeSurvey Cloud account (Part 1) or your own self-hosted LimeSurvey. Everything happens inside your own instance, so your responses stay with you.
- **A plain-text editor.** The steps below use **VS Code**, a free editor for Mac, Windows, and Linux ([code.visualstudio.com](https://code.visualstudio.com)); any plain-text editor works, but not a word processor.
- **The survey package**, downloaded from the project repository (Part 2).
- **Four pieces of information** you will substitute into the survey file:
  - The name of the entity or scope you are surveying (e.g. "the School of Engineering" or "University of X").
  - The full name of the person administering the survey.
  - An email address respondents can write to with questions.
  - A one- or two-sentence statement about where response data is stored and who has access (a ready-to-use default is in [11-data-handling-statement.md](11-data-handling-statement.md)).

> **No LimeSurvey? You can still use this survey.** This package and its analysis toolkit are **optimised for LimeSurvey**: the importable template, the steps below, and the export-column references in the interpretation guide all assume it. You can still run the survey in another tool (Qualtrics, Microsoft Forms, Google Forms, and so on) by rebuilding it from the question list in
> [`../survey/survey-questions.md`](../survey/survey-questions.md). If you do, you can analyse the results using [`40-interpret.md`](40-interpret.md) together with whatever analysis features your survey tool provides, since the automated tooling reads LimeSurvey exports. We're sorry we don't currently offer other import formats.

---

## Part 1: Create a LimeSurvey Cloud account

If you already have a LimeSurvey instance and are logged in, skip to Part 2.

**1.1** Go to [limesurvey.org](https://www.limesurvey.org) and click **Sign up** (or **Get started free**).

**1.2** Fill in the registration form: a username, your name, email, and a password. The username becomes part of the address to your survey (e.g. `myorganisation.limesurvey.net`). Accept the terms and click **Create account**.

**1.3** Check your inbox for a confirmation email and click the activation link.

**1.4** Log in. You land on your LimeSurvey dashboard: a list of surveys (empty for a new account) and a **+** button at the top left for creating or importing surveys.

---

## Part 2: Download the survey package

**2.1** Open the project repository:

> `https://github.com/CURIOSSorg/Academic-OSPO-Readiness-Survey`
>
> *(The person who shared this package will have given you the URL.)*

**2.2** Click the green **Code** button, then **Download ZIP**. Your browser downloads `academic-ospo-readiness-survey.zip` (or similar).

**2.3** Extract the ZIP:

- **Mac:** double-click the `.zip` in Finder; a folder appears beside it.
- **Windows:** right-click the `.zip` → **Extract All…** → **Extract**.
- **Linux:** in a terminal, `unzip academic-ospo-readiness-survey.zip`.

**2.4** Open the extracted folder. The files you'll use here are:

- `survey/academic-ospo-readiness-survey-template.lss` is the file you import into LimeSurvey.
- `survey/survey-questions.md` is the full question list in plain text, if you want to read it.
- `instructions/` holds this guide and the rest: distribution, the communications plan, the data-handling statement, the invitation templates, and the analysis steps.
- `analysis/` holds the spreadsheet and the notebook for reading the results.

---

## Part 3: Replace the placeholder tokens

The survey file contains four placeholders in square brackets. Replace **all** of them with real values **before** importing. LimeSurvey validates email addresses at import time, so if a placeholder is still present the import fails with an "Invalid email address" error.

| Token                      | Replace with                                                                                                                                                                                                                                                                                                |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `[ORGANIZATION]`           | The concrete entity or scope you are surveying, for example "the School of Engineering" or "University of X." Use exactly the same wording every time. This token appears in the introduction and in several question stems; one consistent referent is what makes responses comparable across respondents. |
| `[CONTACT NAME]`           | Full name of the person administering the survey.                                                                                                                                                                                                                                                           |
| `[CONTACT EMAIL]`          | Email address for survey enquiries. **This token also fills the LimeSurvey admin and bounce-email fields inside the file**, so replacing it here covers those automatically, with no separate step in LimeSurvey afterwards.                                                                                |
| `[DATA-HOSTING STATEMENT]` | One or two sentences on where response data is stored and who can access it. The default in [11-data-handling-statement.md](11-data-handling-statement.md) is ready to adopt or adapt.                                                                                                                      |

**Opening the file in VS Code**

**3.1** Open VS Code.

**3.2** Open the file from inside VS Code: **File → Open…** (`⌘O` on Mac, `Ctrl+O` on Windows/Linux), navigate to the folder where you unzipped the package, select `academic-ospo-readiness-survey-template.lss`, and click **Open**. (Or drag the file from Finder / File Explorer onto an open VS Code window.)

The file opens as a large block of XML text; that's normal. VS Code may label it "plain text" because it doesn't recognise the `.lss` extension; that's fine and changes nothing.

**Running the find-and-replace**

**3.3** Open Find and Replace:

- **Mac:** `⌥⌘F` (Option + Command + F)
- **Windows / Linux:** `Ctrl + H`

A panel with **Find** and **Replace** fields appears at the top right.

**3.4** For each of the four tokens:

1. Type the token exactly as shown (including the square brackets) into **Find**.
2. Type your replacement value into **Replace**.
3. Click **Replace All** (the two-arrows button, or `⌥⌘Enter` on Mac / `Ctrl+Alt+Enter` on Windows/Linux).
4. Confirm the replacement count is greater than zero.

> **Important:** replace the token exactly as written, brackets included. Type `[CONTACT EMAIL]` (with brackets), not `CONTACT EMAIL`, and don't add quotes around it.

**3.5** Save the file (`⌘S` on Mac, `Ctrl+S` on Windows/Linux). Keep the `.lss` extension and UTF-8 encoding (VS Code's default). The filename itself can be anything (LimeSurvey reads the file's contents, not its name), but leaving it as `academic-ospo-readiness-survey-template.lss` matches the references in the steps that follow.

---

## Part 4: Import the survey

**4.1** Log in to your LimeSurvey instance (e.g. `yourname.limesurvey.net/admin`).

**4.2** From the survey-list dashboard, click the **+** button at the top left.

**4.3** Click **Import**.

**4.4** Click **Choose file** (or **Browse**), select the `.lss` you just edited, and confirm.

**4.5** Click **Import survey**. LimeSurvey processes the file.

**4.6** On success you see a summary, including **25 question groups, 46 questions, 135 subquestions, and 15 answers**. Click **Go to survey** to open the editor.

> **If you see "Invalid email address":** the `[CONTACT EMAIL]` token wasn't replaced before import. Go back to VS Code, finish the find-and-replace for all tokens (Part 3), re-save, and import again.

---

## Part 5: Configure the settings

Open the survey's **Settings** (the gear/cog icon in the left sidebar).

**5.1 General settings (verify).** Under **General**, check that your token substitution filled these correctly: **Administrator** (the contact name), **Administrator email address**, and **Bounce email address** (both the contact email). If any still shows a placeholder, fix it here and save.

**5.2 Anonymised responses (required).** Under **Participant settings**, set **Anonymised responses** to **On**. This is what makes the survey's promise of anonymity technically true: LimeSurvey will not link a response to the person who submitted it. Do not launch with this off.

Common reasons people give for turning it off, and why they don't hold:

- *"We need to send reminders."* You can use a participant (token) list to track *who* has responded without ever linking a token to a specific response. Anonymity and tracked participation are compatible.
- *"We might need to remove a response later."* Responses are still deletable in bulk (e.g. all from a time window); you just can't tie a submission to an individual, which is the point.
- *"It's only used internally."* Internal use doesn't reduce the obligation to protect participant data. If data is ever disclosed through an access request or a breach, identifiable responses create liability.

**5.3 Publication & access (optional).** Under **Publication & access**, set a **Start** and **Expiry date/time** if you want the survey to open and close automatically; otherwise leave them blank and open/close it manually. CAPTCHA and embedding can stay at their defaults for a standard open-link survey.

---

## Part 6: Edit Q10, the role question (required before launch)

Q10 ships with generic academic role categories. Review and adjust them to match the terms your institution uses (for example "academic staff" rather than "faculty," or splitting out "postdoctoral researchers").

**6.1** In the editor ("Structure"), find the **About you** section and the question *"What is your role at [ORGANIZATION]?"* (it shows the organisation name you substituted).

**6.2** Click the question to select it; a settings panel opens on the right and the answer options become editable.

**6.3** To **edit** an option, click its text, type your revised label, and press Enter.

**6.4** To **delete** an option, click the round red **⊗** (X) button on its row.

**6.5** To **add** an option, click **+ Add answer** at the bottom of the list.

**6.6** To **reorder**, drag the ⠿ (six-dot) handle on the left of a row.

The current default options are: Leadership / Administration · Faculty / Academic staff · Research staff (postdocs, research software engineers) · Professional / Support staff (including IT and library) · Student (graduate or undergraduate) · Other (please specify). Adjust the wording, add institution-specific categories, or remove ones that don't apply. If you are surveying **several institutions at once**, add a separate question for the institution name here so you can later separate responses by institution. Changes save automatically (look for "Saved at HH:MM").

---

## Part 7: Activate and get the link

> **Open link vs. a closed participant list.** The steps below activate the survey as an **open link** ("Anyone with link"): anyone who has the URL can respond (no account or invitation needed), and nothing prevents the same person from submitting more than once. That suits a broad, open call.
>
> If you instead need a **closed circle of named participants** (each able to answer only **once**, with a way to see **who has and hasn't responded**), use a LimeSurvey **Survey Participants** (token) list. With **Anonymised responses** kept **On** (Part 5.2), LimeSurvey can enforce one response per participant and track completion **without linking any response to the individual,** so you keep anonymity and tracked participation at the same time. See the LimeSurvey manual: [Survey participants](https://www.limesurvey.org/manual/Survey_participants#).

**7.1** Click the green **Activate** button at the top right of the editor.

**7.2** LimeSurvey activates immediately and shows a confirmation dialog with your (zero) response counts and a **sharing panel**.

**7.3** In the sharing panel, the access mode defaults to **Anyone with link**: anyone with the URL can respond without an account or access code. This is the right mode for an open survey.

**7.4** Click **Copy** next to the survey URL to copy the full link. (The dialog also has a downloadable QR code for printed materials.)

**7.5** Share the link. After closing the dialog, the link is always available from the sharing overview in the editor.

> **What "Activate" does:** the survey becomes publicly accessible and starts collecting responses. The editor's *question content* becomes read-only. You can still change settings, but not add, delete, or reorder questions while the survey is active. So finish all edits (Parts 3–6) before activating. To make structural changes later, deactivate (which archives existing responses), edit, and reactivate.

---

## What's next

- Decide who to reach and send it out, following [20-distribute.md](20-distribute.md).
- Plan the rollout with [21-communications-plan.md](21-communications-plan.md).
- Use the ready-to-edit messages in [22-invitation-templates.md](22-invitation-templates.md).

---

## Quick-reference checklist

- [ ] All four tokens replaced in the `.lss` **before** import (`[ORGANIZATION]`, `[CONTACT NAME]`, `[CONTACT EMAIL]`, `[DATA-HOSTING STATEMENT]`)
- [ ] Survey imported without errors (46 questions, 25 groups on the import screen)
- [ ] **Anonymised responses** set to **On** (Participant settings)
- [ ] Q10 answer options adjusted to your institution's terminology
- [ ] Survey activated, link copied and ready to distribute

---

## Troubleshooting

**"Invalid email address" on import.** The `[CONTACT EMAIL]` token wasn't replaced (part 3). Re-open the `.lss` in VS Code, run the find-and-replace for `[CONTACT EMAIL]`, save, and import again.

**I imported but I see `[ORGANIZATION]` in the question text.** That token wasn't replaced before import. LimeSurvey has no global find-and-replace, so the fix is to delete the imported survey, do the replacement in VS Code (part 3), and re-import (part 4).

**I can't edit questions after activating.** By design: LimeSurvey locks question structure once a survey is active. Deactivate the survey (top-right → Deactivate), make your edits, then reactivate. If you already have responses, choose *Deactivate* (not *Stop / pause*) to regain full editing; existing responses are archived and can be re-imported.

**I need to re-import to fix a token.** Delete the existing survey (three-dot menu → Delete), then import the corrected `.lss`. If you've collected responses, export them first.
