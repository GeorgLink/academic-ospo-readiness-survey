# Analysis

Two tools turn a LimeSurvey export into results. Both use the same item mapping and produce the same numbers, so you can use whichever you prefer. To produce and read the results, follow [`../instructions/30-analyze.md`](../instructions/30-analyze.md) and [`../instructions/40-interpret.md`](../instructions/40-interpret.md).

## The spreadsheet (no code)

`analysis-helper.xlsx` does the counting for you. Open it, go to the **Data (paste export here)** tab, delete the demo rows, and paste your export into cell A1. The summary tabs fill in: Service summary, Level summary, Maturity by area, Respondents, Importance, Experience & roles, and Write-ins. It works in Excel, LibreOffice Calc, and Google Sheets. It uses fully completed responses only; for a richer view that also uses partial responses, use the notebook.

## The notebook (automated)

`survey-analysis.ipynb` reads the same export and produces charts, tables, a findings summary, a completion funnel, data-quality flags, and a priority chart. It reports the completed-only numbers (Part A, matching the spreadsheet) and then a progressive view (Part B) that recalculates each insight over everyone who completed that part, finished or not. Use it when you want that richer view, the saved chart and table files, or the extra checks the spreadsheet does not do.

### Run it in VS Code (recommended)

You need Visual Studio Code with the **Python** and **Jupyter** extensions (install both from the Extensions view), and Python 3.10 or later.

1. **Open this `analysis` folder in VS Code** (File → Open Folder, then choose the `analysis` folder). Opening this folder specifically lets VS Code find `requirements.txt` and keeps the environment local to it.
2. **Open `survey-analysis.ipynb`.** If VS Code offers to install the **Python**/**Jupyter** extensions or `ipykernel`, accept.
3. **Point it at your data.** Put your exported `.xlsx` in this folder and set `INPUT_PATH` in the first code cell to its file name, for example `INPUT_PATH = "results-survey.xlsx"`.
4. **Create the environment from the notebook.** Click **Select Kernel** (top-right of the notebook) → **Python Environments…** → **+ Create a Python Environment** → **Venv** → pick a **Python 3.10+** interpreter → tick **`requirements.txt`** so the dependencies install. VS Code builds a `.venv`, installs everything, and **auto-selects it as the kernel** (the top-right shows `.venv`), so there is no separate kernel-selection step.
   - *Tip:* create the environment this way rather than building a `.venv` by hand in a terminal — a hand-made venv in this sub-folder may not be auto-discovered by the kernel picker. (The Command Palette command **Python: Create Environment** does the same thing if you prefer.)
5. **Run it.** Click **Run All** in the toolbar.

Prefer JupyterLab instead? From this folder, run `pip install -r requirements.txt`, then `jupyter lab`, and open the notebook there.

### What you get

Results appear inline in the notebook, and each run also writes a new timestamped folder under `output/` (nothing is overwritten) containing the charts as images, `summary_tables.xlsx`, and a plain-text `findings.md`. The notebook also prints the write-in comments verbatim, grouped by question.

### If something goes wrong

- **`ModuleNotFoundError: No module named 'pandas'`** (or similar) means the dependencies are not installed in the selected environment. Open **Terminal → New Terminal** and run `pip install -r requirements.txt`, then Run All again.
- **A file-not-found error on the first data cell** means `INPUT_PATH` does not match a file in this folder. Check the file name and that your export is in the `analysis` folder.

## Notes

With a small number of respondents, read everything as proportions and signals rather than precise facts. The notebook flags respondents who ticked everything or nothing.

The write-in output can name people or units. The notebook processes it only on your machine with Python, with no external service and no AI. Handle it according to your institution's privacy and IRB rules.

The role question (Q10) is the one question you are encouraged to customise in setup. The notebook handles this by reading the role breakdown directly from whatever answer labels appear in your export, so it always matches your survey. The spreadsheet's **Respondents** tab lists the role labels in column A (pre-filled with the template's defaults); if you changed Q10's options, update those labels to match. Any response whose role is not in the list is counted in the **Unmatched** row so a mismatch is visible rather than silently dropped.

The item-to-level and item-to-service assignments match [`../instructions/40-interpret.md`](../instructions/40-interpret.md). In the spreadsheet they live on the **Item results (auto)** tab; in the notebook they live in the "Mappings" cell. If your institution reads an item differently, edit them there and re-run.
