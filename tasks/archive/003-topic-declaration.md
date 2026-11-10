# 003: Topic declaration

- **Status:** done
- **Created:** 2026-11-05
- **Updated:** 2026-11-05
- **Due:** 2026-11-08, 11:59 pm

## Goal

The topic declaration is in on Canvas: the URL of a pushed commit in this repository that holds `topic.ipynb`, and for CHEM 527 the proposal. Section 1 of the final project page says what both contain and how the declaration is scored. CHEM 427 students start this task after projects are assigned on Tuesday, November 3.

## Steps

1. Put your data in `data/`, exactly as you downloaded them, to be committed in step 5. Task 001's data section gives GitHub's limits and the exemption for data that cannot be stored there.
2. Make `topic.ipynb` in the top folder of the repository, on the `.venv` kernel. Its first markdown cell gives your question in one sentence, the data source with its URL and access date, and for CHEM 427 the name of the project you were assigned. Its one code cell loads the data from a relative path and prints the number of rows, the column names, and the unit of the measured variable, such as:

```python
import pandas as pd

data = pd.read_csv("data/spectra.csv")
print(f"{len(data)} rows")
print(list(data.columns))
print("absorbance: AU")
```

3. CHEM 527 only: write the one page proposal the final project page describes, as `proposal.md` or `proposal.pdf` in the top folder.
4. Fill in the three lines under "This project" at the end of `AGENTS.md`. They tell the assistant your question, your data, and your unit from the first prompt on.
5. Restart the kernel and click **Run All**, so that the notebook is saved with its output. Then check what git will commit before you commit it. The first command below should list `data/` and `topic.ipynb` as untracked.

```bash
git status
```

```bash
git add .
```

```bash
git commit -m "Topic declaration"
```

```bash
git push
```

6. Find the URL of the commit you just pushed. Open your repository on GitHub, click **Commits**, and click the message of your latest commit, "Topic declaration". Copy the address from your browser. It ends in `/commit/` and the commit's hash, a string of 40 letters and digits that names this commit. To check that it is the commit you pushed, compare its hash with the one this command prints:

```bash
git rev-parse HEAD
```

7. If your repository is private, check under **Settings**, **Collaborators** that the three invitations from the README were sent.
8. On Canvas, open the assignment "Project topic declaration" and submit the commit's URL as a website URL.

## Done when

The Canvas entry is in. Close this task after it is, with the URL you submitted in **Outcome**, and commit and push the closed task. Your mentor reads the repository at the commit you submitted, so later commits do not change what is scored.

## Progress log

- 2026-11-03: Chose the USGS Mountain Pass data release (https://doi.org/10.5066/P1LGUGBG, CC0, accessed 2026-11-03) because it has data dictionaries, a companion paper, and reference-material replicates. Put the CSV files, data dictionaries and metadata in `data/` unchanged.
- 2026-11-05: Fixed the question: in the 85 replicate analyses of reference material 7802 Apatite, does the reported `errpct` match the observed replicate scatter for each element? `data/EMPA_Apatite_Standards.csv` has 86 data rows, 85 analyses plus one `Detection Limit` row. Ce, Ca, Sr, Na, P, S and F are detected in all 85; Mn (32), Cl (5) and Ba (2) are excluded because values below the detection limit are blank, which truncates the scatter. The paper (n = 85 Wilberforce apatite) does not define `errpct` either, so the proposal tests the alternative interpretations.
- 2026-11-05: Filled the three lines in `AGENTS.md`, made and ran `topic.ipynb`, and drafted `proposal.md`.

## Outcome
https://github.com/minsup96/chem527-project/commit/8bb83b92d980a569f7b2552382635c4c4c40ed1e