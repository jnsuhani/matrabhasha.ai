# Prompts: version ladder

We improve the prompt step by step, and **each step must be justified by failures seen in real runs of the previous version.**

| Version | File | What it adds | Status |
|---|---|---|---|
| v0 | `v0_baseline_prompt.md` | One-line baseline from Milestone 1 | Final (don't change) |
| v1 | `v1_short_prompt.md` | Role, natural Hindi (not word-for-word), learner level, keep English terms | Ready to run |
| v2 | `v2_structured_prompt.md` | Level limits, term gloss rule, fixed 5-section format | Draft, adopt after v1 error analysis |
| v3 | `v3_explainer_prompt.md` | Accuracy/refusal rules, analogy guidance, team-written few-shot example | Draft, adopt after v2 error analysis |
| Reviewer | `reviewer_prompt.md` | Second prompt that checks the latest version's output (prompt chaining) | Ready, used from v2 on |

Also here: `word_for_word_baseline.md` (English answer + Google Translate, the comparison faculty asked for) and
`few_shot_examples.md` (template for the examples v3 needs).

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
| v1 | | | Role, natural Hindi, level, English terms | v0 problems seen in M1 (see v0 file) |
| v2 | | | | |
| v3 | | | | |
