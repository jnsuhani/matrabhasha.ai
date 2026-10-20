# Synopsis (M2 component, 1 mark) — DRAFT

> Fill every `[ ]` from your real pilot results. Delete this note before submitting. Target length: 1–2 pages.

**Title:** Matrabhāsha: A Prompt-Engineered Bilingual Explainer for Introductory Computer Science Concepts in Hindi
**Team:** SyntaxAI (Suhani Jain – leader, Khushi Upadhyay, Amna Khan, Ashima Singh), B.Tech CSE 5th semester, Bennett University
**Problem ID:** C19 (Bilingual explainer)

## Abstract
Many Hindi-comfortable learners, such as Hindi-medium first-year B.Tech students, struggle with CS concepts taught only in
English, and machine translation gives stiff, word-for-word Hindi that ignores what the learner already knows. Matrabhāsha is a
prompt workflow that explains an introductory CS concept in natural, conversational Hindi at two knowledge levels (Beginner: no
programming background; Intermediate: knows programming basics), keeping technical terms in English with a short Hindi
gloss, and adding an everyday analogy, a common misconception and practice questions. A second reviewer prompt checks each answer
for accuracy, term use, naturalness, level fit and format, and a team member verifies accuracy before use. We built the workflow as
a no-code Gemini Gem [and Custom GPT] and developed the prompt in versions, from a one-line baseline to a short prompt (v1) and a
structured prompt (v2), with each change driven by failures found in the previous version. We piloted it on [20] test cases from a
50-case test set and compared it against a word-for-word Google Translate version. [One sentence with the main real result, e.g.
"v2 scored [x.x] vs [y.y] for v1 on ..."]

## 1. Problem and users
Primary users are Hindi-comfortable learners of introductory CS at any year or in any programme, with Hindi-medium first-year
B.Tech students as the main group; secondary users are teachers/TAs who re-explain
concepts in Hindi. NEP 2020 encourages mother-tongue learning, and UGC guidance on translated books asks that word-to-word output be
rephrased and that technical terms be kept in English. Existing tools (Google Translate, general chatbots, AICTE's Anuvadini)
translate text but do not adapt to learner level or add analogies and practice.
Levels are defined by prior knowledge rather than year of study. (Milestone 1 used "First-year B.Tech" as the second level; it was
renamed Intermediate so that, for example, a second-year student or a non-B.Tech learner with the same knowledge fits.)

## 2. Objectives
1. Develop, in evidence-driven versions, a prompt that produces natural Hindi explanations at two learner levels with a 5-part structure.
2. Add a reviewer prompt that catches accuracy, terminology and format problems (prompt chaining).
3. Evaluate against a baseline prompt and word-for-word translation using a rubric and blind student ratings.

## 3. Method / prompt design
- **Explainer prompt, built as a version ladder:**
  - v0: one-line baseline (Milestone 1).
  - v1: role, natural Hindi instead of literal translation, learner level, technical terms kept in English.
  - v2: level limits, term gloss rule (English term + short Hindi meaning), fixed 5-section output. [Adopted because v1 showed: ...]
  - v3 (Milestone 3, planned): accuracy/refusal rules, analogy guidance, one team-written few-shot example, only if v2 failures
    call for them.
- **Reviewer prompt (from v2):** separate chat; scores rules R1–R6 and returns JSON with quoted errors and a PASS/REVISE verdict; on REVISE
  the explainer rewrites once.
- **Human oversight:** a team member verifies technical accuracy before an output is used.
- **Prototype:** Gemini Gem [+ Custom GPT / Claude Project].
- (Insert `design/workflow.png`.)

## 4. Evaluation design
- Test set: 25 introductory CS concepts (programming, data structures, algorithms, OS, DBMS) × 2 levels = 50 cases, plus 6 edge cases.
- Conditions: V0 baseline, TR English + Google Translate, V1 short prompt, V2 structured prompt, V2R v2 + reviewer.
- Team rubric (1–5, two independent scorers): accuracy, natural Hindi, term handling, level fit, analogy, completeness, practice
  questions; hallucination flag.
- Blind student ratings ([n] anonymous Hindi-speaking classmates): naturalness, clarity, usefulness.

## 5. Pilot results (Milestone 2)
| Criterion (avg, 1–5) | V0 baseline | TR translate | V1 short | V2 structured | V2R v2+review |
|---|---|---|---|---|---|
| Accuracy | [ ] | [ ] | [ ] | [ ] | [ ] |
| Natural Hindi | [ ] | [ ] | [ ] | [ ] | [ ] |
| Term handling | [ ] | [ ] | [ ] | [ ] | [ ] |
| Level fit | [ ] | [ ] | [ ] | [ ] | [ ] |
| Completeness | [ ] | [ ] | [ ] | [ ] | [ ] |
| % outputs with hallucination | [ ] | [ ] | [ ] | [ ] | [ ] |
| Students: naturalness / clarity / usefulness | — | [ ] | [ ] | [ ] | — |

Failures of v1 that led to v2, and failures of v2 that will shape v3: [2–3 lines each from error_analysis.md]

## 6. Responsible AI
No personal data is entered (inputs are concept names only); student ratings are anonymous. Hallucination is reduced by accuracy
rules, the reviewer step and a human check, and the tool tells users to verify with their teacher. Few-shot examples are the team's
own writing; no copyrighted textbook text is used as input.

## 7. Limitations and next steps (Milestone 3)
[Real limitations you saw, e.g. analogy quality varies, reviewer sometimes misses errors.] Next: run the full 50-case test set on
ChatGPT, Gemini and Claude, adopt v3 if the v2 failures call for it, larger student rating round, final report and video.

## References
1. Bennett University, Prompt Engineering Mini-Project Guidelines, 2026.
2. Careers360, "UGC issues guidelines for translation of books in Indian languages", https://news.careers360.com/ugc-issues-guidelines-for-translation-of-books-in-indian-languages/amp
3. Ministry of Education, National Education Policy 2020.
4. Tools used: Google Gemini, OpenAI ChatGPT, Anthropic Claude, Google Translate (state versions and dates of use).
