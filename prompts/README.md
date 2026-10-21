# Prompts: version ladder

We improve the prompt step by step, and **each step must be justified by failures seen in real runs of the previous version.**
There are four versions (v0 to v3). The guidelines don't ask for a fixed number; four is enough to show the iteration, and v3 is the
final prompt.

| Version | File | What it adds | Status |
|---|---|---|---|
| v0 | `v0_baseline_prompt.md` | One-line baseline from Milestone 1 | Final (don't change) |
| v1 | `v1_short_prompt.md` | Two lines: teacher role + learner level, nothing else | Ready to run |
| v2 | `v2_guided_prompt.md` | Natural Hindi (not word-for-word), keep English terms, what each level means | Draft, adopt after v1 error analysis |
| v3 | `v3_explainer_prompt.md` | Final version: level limits, term gloss rule, fixed 5-section format, accuracy/refusal rules, analogy guidance, numbers rule, team-written few-shot example | Draft, adopt after v2 error analysis |
| Reviewer | `reviewer_prompt.md` | Second prompt that checks the latest version's output (prompt chaining) | Ready, used from v2 on |

Also here: `word_for_word_baseline.md` (English answer + Google Translate, the comparison faculty asked for) and
`few_shot_examples.md` (template for the examples v3 needs).

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

The v2 and v3 files are drafts prepared in advance so you have a starting point. They are not evidence. Your logs are.

## Version history (fill in as you go, this is graded as "iteration")
| Version | Date adopted | Who | What changed | Failures that caused it (test ids from the log) |
|---|---|---|---|---|
| v0 | M1 | Team | Baseline | — |
| v1 | | | Teacher role, learner level | v0 problems seen in M1 (see v0 file) |
| v2 | | | | |
| v3 | | | | |
