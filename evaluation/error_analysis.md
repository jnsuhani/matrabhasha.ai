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

### Suhani's cases (T01, T02, T07, T08, T09 · Gemini Flash · 2026-10-31)
Outputs: `outputs/v2/`. Log rows: `V2-T01` … `V2-T09` in `experiment_log.csv`. Counts below are out of these 5 runs, compared with the same 5 V1 runs. Team scores and reviewer verdicts are not in yet, so this is a reading of the outputs, not a score.

**What v2 fixed from the v1 list:**

| v1 pattern | v1 | v2 | Result |
|---|---|---|---|
| Script not controlled | 1 of 5 (T02 Roman Hinglish) | 0 of 5 | Fixed |
| Levels not defined | 4 of 5 | 2 of 5 (T01, T07) | Partly fixed. Intermediate depth is now steady (T02 deeper, T08 less overshoot). Beginners still get code, because the v2 text defines the level but never says "no code" |
| No fixed structure | 5 of 5 | 5 of 5 | Not fixed, as expected (v3) |
| Required key points missing | 3 of 5 | 2 of 5 (T07, T09) | Partly fixed. T02 now has initialisation, condition and update. Still missing: call stack in T07, fixed size in C in T09 |
| Accuracy and analogy errors | 2 of 5 | 1 of 5 (T08), plus overstatements in T07 and T09 | Partly fixed. T07's mirror and countdown slip are gone, and T08's three v1 errors are gone, but T08 has new ones (below) |

**What remains for v3:**

| Test id | What went wrong | Rubric criterion | How often | Fix to try in v3 |
|---|---|---|---|---|
| T01, T07 | **Code for Beginners:** Python in T01, pseudo-code in T07 | D Level fit | 2 of 5 | v3: "No code at all" for Beginner |
| All 5 | **No practice questions, no misconception section;** T02 and T08 have no analogy. Each answer has a different shape | E Analogy quality, F Completeness, G Practice questions | 5 of 5 | v3: fixed 5-section format |
| T07, T09 | **Key points missing:** call stack (T07), fixed size in C (T09) | A Technical accuracy | 2 of 5 | v3: require every key point; check against `must_include_key_points` |
| T01, T02, T07, T08 | **Target misconceptions not addressed as such:** T02 covers the condition by implication only; T01 never says it is rechecked; neither T07 nor T08 says recursion is not always faster than loops. T07 and T08 do cover the base case | A Technical accuracy, F Completeness | 4 of 5 | v3: name the misconception and correct it directly |
| T07, T08, T09 | **Accuracy:** T08 says the OS creates the stack frame, uses "Head Recursion" for all non-tail recursion, and says recursion "हमेशा" takes extra memory right after explaining TCO. T07 treats Infinite Loop and Stack Overflow as one thing. T09 says counting "हमेशा" starts from 0 in programming | A Technical accuracy (hallucination = Y for T08) | 3 of 5 | v3: accuracy rule, no absolutes; reviewer prompt checks facts |
| T01, T02, T07, T09 | **Term handling inconsistent:** the same term in two scripts (Loop/लूप, Memory/मेमोरी), general words transliterated (रियल-लाइफ, सब्जेक्ट्स), and glosses only sometimes given | C Term handling | 4 of 5 | v3: term gloss rule on first use |
| T01, T02, T08 | **Stiff or broken phrasing:** "2रा, 3रा" (T01), "तड़पाकर" for `break` and "निकल लें" (T02), "approch" (T08). T02 and T08 also end with an English question | B Natural Hindi | 3 of 5 | v3: conversational tone rule; ask for Hindi throughout, including the closing line |

Areas where v2 had **no** real problem (so v3 doesn't add rules nobody needed):
- All 5 answers are in Devanagari with English technical terms kept, and no coined Hindi terms.
- Digits are 0-9 in all 5, no mixed numeral styles.
- T07 and T08 no longer contradict themselves on the base case, and T09's analogy still fits.

**Why v3 is needed:** the two v2 additions worked where they were aimed (script and Intermediate depth), but Beginner level needs an explicit no-code limit, and structure, key points and accuracy cannot come from tone and level rules alone.

## v3 failures (M3)
| Test id | What went wrong | Rubric criterion | How often | Fix / limitation to report |
|---|---|---|---|---|
| | | | | |
