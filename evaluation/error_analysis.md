# Error analysis

Fill one section per prompt version, from **real scored outputs only**. The next version must be built from this list.

## v1 failures (from V1 pilot runs)

### Suhani's cases (T01, T02, T07, T08, T09 · Gemini Flash · 2026-10-31)
Outputs: `outputs/v1/`. Log rows: `V1-T01` … `V1-T09` in `experiment_log.csv`. Counts below are out of these 5 runs; add the other members' cases to get "x of 20".

| Test id | What went wrong | Rubric criterion | How often (x of 5) | Fix to try in v2 |
|---|---|---|---|---|
| T02 | **Script not controlled:** answered in Roman Hinglish, the other four in Devanagari | B Natural Hindi, C Term handling | 1 of 5 | v2: ask for natural Hindi in Devanagari, English technical terms kept as they are |
| T01, T07 (code), T02, T08 (depth) | **Levels not defined:** code given to Beginners (T01, T07) but not to T09; Intermediate ranges from light and Python-only (T02) to far beyond "knows programming basics" (T08: recurrence relations, TCO, DP) | D Level fit | 4 of 5 | v2: define Beginner (no programming background, no code) and Intermediate (knows basics, wants technical depth) |
| All 5 | **No fixed structure:** no practice questions in any answer, misconception never a separate section, long greetings and filler | F Completeness, G Practice questions | 5 of 5 | v3: fixed 5-section format (explanation, analogy, key terms, misconception, practice) |
| T02, T07, T09 | **Required key points missing:** initialisation/condition/update in T02, call stack in T07, fixed size in C in T09 | A Technical accuracy | 3 of 5 | v3: tell the model to cover every key point of the concept; check against `must_include_key_points` |
| T07, T08 | **Accuracy and analogy errors:** mirror analogy ("infinite" reflections) reinforces the no-base-case misconception; T07 says it counts 5 to 1 but calls `countdown(3)`; T08 claims tail-call optimisation for a Python example, names Java's `StackOverflowError`, and its `fact` never stops for n=0 | A Technical accuracy, E Analogy quality (hallucination = Y for T08) | 2 of 5 | v3: accuracy rule, analogy must say where it breaks; reviewer prompt checks facts |

Target misconceptions from the test set were not addressed as such in any of the 5 (T01/T02: condition checked only once; T07/T08: no base case / always faster than loops; T09 did state index from 0).

**Why both v2 and v3 are needed:** v2 (natural Hindi in Devanagari + level definitions) targets the first two patterns. Patterns 3 to 5 (structure, key points, accuracy and analogy) need v3's format, key-point/accuracy rules and analogy check.

Areas where v1 had **no** real problem (write them too, so v2 doesn't add rules nobody needed):
- English technical terms were kept (not coined into Hindi) in all 5 answers.
- The Devanagari answers (T01, T07, T08, T09) read as natural Hindi, not machine translation.
- Analogies were present for every Beginner case (park laps, mirrors, ice tray), and T09's ice-tray analogy fit well.

## v2 failures (from V2 / V2R pilot runs)
| Test id | What went wrong | Rubric criterion | How often | Fix to try in v3 |
|---|---|---|---|---|
| | | | | |

## v3 failures (M3)
| Test id | What went wrong | Rubric criterion | How often | Fix / limitation to report |
|---|---|---|---|---|
| | | | | |
