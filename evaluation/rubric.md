# Evaluation rubric

Fix this rubric **before** you look at results (the guidelines ask for criteria defined before claiming improvement).

## What we compare (conditions)
| Code | Condition | How it's made |
|---|---|---|
| A | v0 baseline prompt | `prompts/v0_baseline_prompt.md` |
| B | Word-for-word translation | English answer → Google Translate (`prompts/word_for_word_baseline.md`) |
| C | v1 structured prompt | `prompts/v1_explainer_prompt.md` |
| D | v1 + reviewer loop | C, then reviewer, then one revision if verdict = REVISE |

## Part 1: Team scoring (every output, by 2 team members independently)
Score 1–5. Use the anchors so two people give similar scores.

| # | Criterion | 1 | 3 | 5 |
|---|---|---|---|---|
| A | **Technical accuracy** | A clear factual error | Correct but misses a key point from the test set | All `must_include_key_points` correct, no errors |
| B | **Natural Hindi** | Reads like machine translation | Understandable, a few stiff phrases | Sounds like a teacher speaking |
| C | **Term handling** | Coined Hindi terms or no English terms | English terms present, glosses missing/unclear | English term + short clear gloss on first use |
| D | **Level fit** | Wrong level (code for Beginner, too shallow for First-year) | Mostly right, some parts too hard/easy | Exactly right depth and length |
| E | **Analogy quality** | Missing or misleading | Present but generic | Fits well, Indian context, says where it breaks |
| F | **Completeness / format** | Most sections missing | 3–4 of the 5 sections | All 5 sections, correct counts |
| G | **Practice questions** | Missing or unrelated | Present, too easy/hard | 2–3, match level, test understanding |

**Hard fail flag:** mark `hallucination = Y` if the answer states anything false as fact. Report the % of outputs with this flag.

**Agreement check:** if two scorers differ by 2 or more on any criterion, they discuss and record the agreed score. Report how
often this happened (it shows your rubric is reliable).

## Part 2: Student ratings (faculty's suggestion)
Ask **5–10 Hindi-speaking classmates** (anonymous) to rate a sample of outputs on the 3 criteria faculty named:
**Naturalness, Clarity, Usefulness** (1–5 each). Use `student_rating_form.md`.

Make it a **blind** test: show outputs labelled only "Version 1 / 2 / 3", in random order, without saying which is your prompt.

## Part 3: Numbers to report
- Average score per criterion for A, B, C, D (a table and a bar chart).
- % of outputs with hallucination flag, per condition.
- % of v1 outputs the reviewer marked REVISE, and how many of those improved after revision.
- Student averages for Naturalness/Clarity/Usefulness per condition.
- 3–5 failure cases with what you changed in the prompt because of them (error analysis).

Every number must come from your own real runs. Leave cells empty until you have them.
