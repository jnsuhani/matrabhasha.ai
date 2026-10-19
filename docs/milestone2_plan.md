# Milestone 2 plan

Team SyntaxAI · Matrabhāsha (C19) · **Milestone 2 due 2 November 2026 (12 marks)**

Everything you need for Milestone 2 is drafted here. What's **not** done (and can't be done by Claude) is the part the guidelines
require you to do yourselves: running the prompts, scoring outputs and getting student ratings. Never put a made-up number in
any file. Leave `[ ]` until you have the real one.

## Do these 3 things first (today or tomorrow)
1. **Read `prompts/v1_explainer_prompt.md`** (5 minutes). It's the heart of the project.
2. **Build the Gem:** follow `build/build_guide.md` Option 1. Type `Concept: Stack | Level: Beginner` and see what you get.
3. **Share this folder with the team** and agree on the roles below.

## What's in the pack, mapped to the marks
| M2 component (marks) | Files |
|---|---|
| Design description + diagrams (2) | `design/design.md`, `design/workflow.png` |
| Running build (3) | `prompts/*`, `build/build_guide.md` |
| Demo / pilot run (2) | `build/demo_plan.md`, `test-set/*`, `evaluation/*` |
| Git repo / Drive (2) | `docs/repo_layout.md` |
| Synopsis (1) | `docs/synopsis.md` (draft, fill in results) |
| 90–150 s video (2) | `docs/video_script.md` |

## Suggested roles (change as you like)
| Member | Owns | Also |
|---|---|---|
| Suhani (leader) | Build Gems/GPT, keep prompt versions + repo | Scores outputs (scorer 1) |
| Khushi | Runs baselines A and B, checks test set vs syllabus | Writes 1 few-shot example |
| Amna | Reviewer runs (D), student rating form, error analysis | Scores outputs (scorer 2) |
| Ashima | Synopsis, video, slides | Writes 1 few-shot example, edge cases |

Everyone runs a quarter of the pilot cases and commits their own files (contribution evidence).

## Plan to 2 November
| Dates | Do | Done when |
|---|---|---|
| 19–21 Oct | Check test set against syllabus; write 2 few-shot examples; build Gems; create repo | Gem answers correctly in 5 sections |
| 22–25 Oct | Pilot runs: A, B, C, D for 20 cases + 6 edge cases; log every run | ~80 output files + experiment log |
| 26–28 Oct | Score with rubric (2 scorers); send blind student form; write error analysis → v1.1 | Scoring sheet full, ≥5 student responses |
| 29–31 Oct | Results table + chart; fill synopsis; record video; screenshots | All `[ ]` filled with real numbers |
| 1 Nov | Final check against the table above; submit on LMS | Submitted a day early |

## Roadmap to Milestone 3 (due 1 Dec 2026, 10 marks)
- **3 Nov onward:** class presentation of M2 (use `build/demo_plan.md` Part B).
- **Early Nov:** run all 50 cases on Gemini, ChatGPT and Claude with the latest prompt (v1.1/v2); second student rating round.
- **Mid Nov:** final error analysis, v2 prompt, results chapter.
- **Late Nov:** final report (structure in guidelines section 12: 9 chapters + appendices with prompt versions, test cases, scoring
  sheets), PPT, LinkedIn blog, 3–5 min YouTube video, viva prep (every member must be able to explain the prompts, workflow,
  evaluation and limitations).
