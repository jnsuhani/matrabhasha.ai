# Git repo / Drive folder layout (M2 component, 2 marks)

Make a GitHub repo (e.g. `syntaxai-matrabhasha`), public or shared with your faculty. Every member should commit their own work
from their own GitHub account, since commit history counts as contribution evidence. A Google Drive folder with the same layout
is fine if the LMS asks for Drive instead.

```
syntaxai-matrabhasha/
├── README.md                 ← project summary, how to reproduce, team + roles
├── prompts/
│   ├── v0_baseline_prompt.md
│   ├── v1_explainer_prompt.md    ← includes version history table
│   ├── v1.1_explainer_prompt.md  ← after error analysis
│   ├── reviewer_prompt.md
│   ├── few_shot_examples.md
│   └── word_for_word_baseline.md
├── test-set/
│   ├── test_set.csv
│   └── edge_cases.csv
├── outputs/                  ← raw model outputs, copied exactly
│   ├── T01_A_gemini.md ...
│   └── reviews/
├── evaluation/
│   ├── rubric.md
│   ├── experiment_log.csv
│   ├── team_scoring_sheet.csv
│   ├── student_rating_form.md
│   ├── student_ratings.csv
│   ├── blind_key.csv
│   ├── error_analysis.md
│   └── results.md            ← tables + charts from your real scores
├── design/
│   ├── design.md
│   ├── workflow.png
│   └── workflow.svg
├── build/
│   ├── build_guide.md
│   └── demo_plan.md
├── screenshots/              ← Gem/GPT setup, demo runs
├── docs/
│   ├── synopsis.md
│   └── video_script.md
└── CONTRIBUTIONS.md          ← who did what, with dates
```

## Quick start for GitHub (if you've never used it)
1. Leader creates the repo on github.com → **Add a README**. Settings → Collaborators → add the other 3.
2. Easiest way without the command line: on the repo page click **Add file → Upload files**, drag in the folders from this pack, write
   a short message like "Add M2 prompts and test set", **Commit**.
3. Each member uploads their own outputs and scores the same way, from their own account.
4. Commit small and often (e.g. "Add pilot outputs T01–T10 condition C"); a single big upload the night before looks weak.

`CONTRIBUTIONS.md` template:

| Date | Member | What they did | Files |
|---|---|---|---|
| | | | |
