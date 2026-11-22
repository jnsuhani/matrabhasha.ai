# Matrabhāsha

A prompt workflow that explains introductory computer science concepts in natural, conversational Hindi (Devanagari) to
Hindi-comfortable learners at two knowledge levels: **Beginner** (no programming background) and **Intermediate** (knows
programming basics, wants technical depth), whatever their year or degree. Technical terms stay in English. A second reviewer
prompt checks each answer. The final prompt (v3, Milestone 3) adds a fixed format with an everyday analogy, a common
misconception and practice questions.

Prompt Engineering mini-project, B.Tech CSE 5th semester, Bennett University. Problem Pool ID **C19** (Bilingual explainer).

**Team SyntaxAI (PE-B65-11), batch B65-80, faculty Sonal Kukreja:** Suhani Jain (S24CSEU2709, leader), Khushi Upadhyay (S24CSEU1642),
Amna Khan (S24CSEU1623), Ashima Singh (S24CSEU2720)

## Links and Milestone 2 documents
- **Prototype (Gemini Gem "Matrabhāsha v2"):** https://gemini.google.com/gem/1TlIzbCeMuz6TW7b8cdk342ahPaoP_hRO?usp=sharing
- **Reel (135 s):** https://youtu.be/7ZjnFfg_D7c
- **Milestone 2 report:** [docs/M2_PE-B65-11_Matrabhasha.pdf](docs/M2_PE-B65-11_Matrabhasha.pdf)
- **Supporting document (synopsis):** [docs/SyntaxAI_Synopsis.pdf](docs/SyntaxAI_Synopsis.pdf)
- **Final prompts:** [prompts/final/](prompts/final/) · **Changes since Milestone 1:** [CHANGELOG.md](CHANGELOG.md)

## How to open and run it
1. Open the prototype link above and sign in with any Google account.
2. Type, for example, `Concept: Stack | Level: Beginner` (or `Level: Intermediate`).
3. Optional reviewer step: open a new Gemini chat, paste [prompts/final/P2_reviewer.md](prompts/final/P2_reviewer.md) with the
   concept, level and the Gem's answer filled in. On REVISE, send the error list back to the Gem with the one-line rewrite message.

![Workflow](design/workflow.png)

## How it works
1. The student sends `Concept: <name> | Level: Beginner` (or `Intermediate`).
2. The **explainer prompt** answers. It is developed in versions (v0 baseline → v1 short → v2 guided → v3 final), and each
   version is adopted only after real runs of the previous one show what it gets wrong. See [prompts/README.md](prompts/README.md).
3. With the final prompt (v3), the **reviewer prompt** ([prompts/reviewer_prompt.md](prompts/reviewer_prompt.md)) scores it and returns PASS or REVISE with quoted errors. In Milestone 2 it was pilot-tested once, on the V2 answer for T01.
4. On REVISE the explainer rewrites once, and the student gets the final answer directly. During testing, team members checked outputs for technical accuracy.

The prototype is built as Gemini Gems in the Gemini app, Everyday help (4 Hydrogen) model: **Matrabhāsha v1** and **Matrabhāsha v2**, one per adopted prompt version (screenshots in [screenshots/](screenshots/)). Setup: [build/build_guide.md](build/build_guide.md).

**Model name:** all Milestone 2 runs (31 Oct to 1 Nov 2026) were logged as Gemini Flash. "Flash" was the Gemini app's earlier label for its fast model; the app's model picker now calls it "Everyday help (4 Hydrogen)".

## Reproduce the evaluation
- Test set: [test-set/test_set.csv](test-set/test_set.csv) (25 concepts × 2 levels) and [test-set/edge_cases.csv](test-set/edge_cases.csv).
- Conditions: V0 baseline, V1, V2 (plus one reviewer pilot run on T01); V3 and V3R (v3 + reviewer) in Milestone 3.
- Rubric and forms: [evaluation/](evaluation/). Raw model outputs go in [outputs/](outputs/), copied exactly.
- Pilot and demo steps: [build/demo_plan.md](build/demo_plan.md).

## Repository layout
| Folder | Contents |
|---|---|
| `prompts/` | Prompt versions v0–v2 (run in M2), v3 draft, reviewer prompt, few-shot examples; `final/` = the two final prompts |
| `test-set/` | Test inputs: 50 test cases and 6 edge cases (saved outputs are in `outputs/`) |
| `outputs/` | Raw model outputs and reviewer JSON |
| `evaluation/` | Rubric, scoring sheets, experiment log, student rating form |
| `design/` | Design description and diagrams |
| `build/` | Prototype build guide and demo plan |
| `docs/` | Milestone 2 report and synopsis (PDF and source) |
| `screenshots/` | Gem setup and demo evidence |

Contribution record: [CONTRIBUTIONS.md](CONTRIBUTIONS.md).

## Status
Milestone 1 submitted. Milestone 2 (submitted 22 Nov 2026): v0, v1 and v2 run on the 20 pilot cases (60 runs) and edge cases E01
to E06 on v1 and v2 (12 runs), plus one reviewer run on T01: 73 runs in
[evaluation/experiment_log.csv](evaluation/experiment_log.csv), error analysis in
[evaluation/error_analysis.md](evaluation/error_analysis.md). v2 passed 11 of 26 test inputs. Team rubric scores and student
ratings are planned for Milestone 3 (due 1 Dec 2026), with v3, the reviewer loop and the full 50 cases on three models.
All results in this repository come from the team's own runs.

## References
- Bennett University, Prompt Engineering Mini-Project Guidelines, 2026.
- Careers360, "UGC issues guidelines for translation of books in Indian languages".
- Ministry of Education, National Education Policy 2020.
