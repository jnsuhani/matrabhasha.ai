# Milestone 2 plan

Team SyntaxAI · Matrabhāsha (C19) · **Milestone 2 due 2 November 2026 (12 marks)**

Everything you need for Milestone 2 is drafted here. What's **not** done (and can't be done by Claude) is the part the guidelines
require you to do yourselves: running the prompts, scoring outputs and getting student ratings. Never put a made-up number in
any file. Leave `[ ]` until you have the real one.

## Do these 3 things first (today or tomorrow)
1. **Read `prompts/README.md`** (5 minutes). It explains the prompt versions v0 → v3 and the rule that each new version needs
   evidence from real runs of the one before. Don't skip that step.
2. **Build the Gem:** follow `build/build_guide.md` Option 1. Type `Concept: Stack | Level: Beginner` and see what you get.
3. **Share this folder with the team** and agree on the roles below.

## What's in the pack, mapped to the marks
| M2 component (marks) | Files |
|---|---|
| Design description + diagrams (2) | `design/design.md`, `design/workflow.png` |
| Running build (3) | `prompts/*` (versions v0 → v3), `build/build_guide.md` |
| Demo / pilot run (2) | `build/demo_plan.md`, `test-set/*`, `evaluation/*` |
| Git repo / Drive (2) | `docs/repo_layout.md` |
| Synopsis (1) | `docs/synopsis.md` (draft, fill in results) |
| 90–150 s video (2) | `docs/video_script.md` |

## Roles
| Member | Owns | Also |
|---|---|---|
| Suhani (leader) | Build Gems/GPT, keep prompt versions + repo | Scores outputs (scorer 1) |
| Khushi | Runs baselines V0 and TR, checks test set vs syllabus | Writes 1 few-shot example |
| Amna | Video (narration and recording), reviewer runs (V2R), error analysis | Scores outputs (scorer 2) |
| Ashima | Synopsis, slides, student rating form, edge cases | Writes 1 few-shot example |

Everyone runs a quarter of the pilot cases and commits their own files (contribution evidence).

## Plan to 2 November
| Dates | Do | Done when |
|---|---|---|
| 20 Oct (today) | Check test set against syllabus; build the Gem with v1; repo is already set up | Gem answers a test concept |
| 21–24 Oct | Pilot runs V0, TR, V1 for 20 cases + edge cases; score them; error analysis 1 | v1 failures logged with test ids |
| 25–28 Oct | Adopt v2 (edited to fix those failures); run V2 and V2R; score; error analysis 2; send blind student form | Scoring sheet full, ≥5 student responses |
| 29–31 Oct | Results table + chart; Ashima fills synopsis; Amna records video; screenshots | All `[ ]` filled with real numbers |
| 1 Nov | Final check against the table above; submit on LMS | Submitted a day early |

## Roadmap to Milestone 3 (due 1 Dec 2026, 10 marks)
- **3 Nov onward:** class presentation of M2 (use `build/demo_plan.md` Part B).
- **Early Nov:** write 2–3 few-shot examples; adopt v3 only for the v2 failures it fixes; run all 50 cases on Gemini, ChatGPT and
  Claude with v3 (+ reviewer); second student rating round.
- **Mid Nov:** final error analysis, results chapter.
- **Late Nov:** final report (structure in guidelines section 12: 9 chapters + appendices with prompt versions, test cases, scoring
  sheets), PPT, LinkedIn blog, 3–5 min YouTube video, viva prep (every member must be able to explain the prompts, workflow,
  evaluation and limitations).
