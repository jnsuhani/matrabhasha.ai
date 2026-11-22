# Prompts: version ladder

We improve the prompt step by step, and **each step must be justified by failures seen in real runs of the previous version.**
Three versions (v0, v1, v2) were run in Milestone 2 and are the versions counted in the Milestone 2 report; v2 is the final
prompt for Milestone 2 (copy in `final/`). v3 is a draft for Milestone 3.

| Version | File | What it adds | Status |
|---|---|---|---|
| v0 | `v0_baseline_prompt.md` | One-line baseline from Milestone 1 | Final (don't change) |
| v1 | `v1_short_prompt.md` | Two lines: teacher role + learner level, nothing else | Adopted 31 Oct 2026 (Gem "Matrabhāsha v1"), run on the 20 pilot cases + 6 edge cases |
| v2 | `v2_guided_prompt.md` | Natural Hindi (not word-for-word), keep English terms, what each level means | Adopted 31 Oct 2026 (Gem "Matrabhāsha v2"), run on the 20 pilot cases + 6 edge cases |
| v3 | `v3_explainer_prompt.md` | Final version: level limits, term gloss rule, fixed 5-section format, accuracy/refusal rules, analogy guidance, numbers rule, team-written few-shot example | Draft, not adopted yet. To be finalised in M3 from the v2 error analysis |
| Reviewer | `reviewer_prompt.md` | Second prompt that checks the latest version's output (prompt chaining) | Ready; used with v3 (V3R, M3). Pilot-tested once on V2 T01 in M2 |

Also here: `few_shot_examples.md` (template for the examples v3 needs).

## Levels
Levels describe what the learner already knows, not their year or degree, so a second-year student or a non-B.Tech learner
picks whichever fits.
- **Beginner:** no programming or CS background yet.
- **Intermediate:** knows programming basics (variables, loops, functions in C or Python) and wants precise technical depth.

Milestone 1 called the second level "First-year B.Tech". It was renamed to Intermediate on 20 Oct 2026 because a learner's year
doesn't tell you what they know. Mention this change in the report.

## The rule: don't skip the evidence step
1. Run version N on the pilot cases and save every output.
2. Score them and write down the failures in `evaluation/error_analysis.md` (test id + what went wrong).
3. Only then make version N+1. Every change must point to a logged failure. **Edit the v2/v3 drafts to match what you found**:
   drop additions you didn't need, add fixes for problems the drafts don't cover.
4. If version N had no real problem in some area, say so honestly. That's a valid finding too.

v2 was adopted after the v1 runs; the v3 file is still a draft prepared in advance. Drafts are not evidence. Our logs are.

## Version history (this is graded as "iteration")
Dates come from `evaluation/experiment_log.csv` and the Gem screenshots in `screenshots/`. Failure details are in
`evaluation/error_analysis.md`.

| Version | Date adopted | Who | What changed | Failures that caused it (test ids from the log) |
|---|---|---|---|---|
| v0 | M1 | Team | One-line baseline from Milestone 1 | — |
| v1 | 31 Oct 2026 | Suhani built the Gem "Matrabhāsha v1"; all four members ran it | Two lines: friendly CS teacher role + "explain in Hindi at the level they mention (Beginner or Intermediate)" | v0 problems seen in the M1 sample output (see `v0_baseline_prompt.md`) |
| v2 | 31 Oct 2026 | Suhani built the Gem "Matrabhāsha v2"; all four members ran it | Natural, conversational Hindi in Devanagari, no word-for-word translation; technical terms kept in English; Beginner and Intermediate defined by what the learner already knows | v1 Roman Hinglish / uncontrolled script (T02; later also T10, T13, T45) and mixed scripts (T42); levels not defined: code for Beginners (T01, T07, T13) and uneven Intermediate depth (T02, T08) |
| v3 | Not adopted yet (M3) | — | Planned: level limits (no code for Beginner), term gloss rule, fixed 5-section format, accuracy/refusal rules, analogy guidance, numbers rule, few-shot example. Edit before adopting so each change matches a logged v2 failure | v2 failures to target: no practice questions or fixed structure in any of the 20 runs; code still given to Beginners (T01, T07); greeting/teacher-tone openings (T37, T38, T45); factual errors (T08, T46); edge cases E01, E03, E04, E05 |
