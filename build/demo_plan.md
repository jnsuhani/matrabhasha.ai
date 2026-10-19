# Pilot run and demo plan (M2 "demonstration / pilot run", 2 marks)

## Part A: Pilot run (do this before 2 Nov)
Pilot = the 10 concepts marked `in_m2_pilot = yes` in `test-set/test_set.csv`, both levels = 20 test cases.

| Step | What | Output files |
|---|---|---|
| 1 | Run **V0** (v0 baseline) on Gemini for all 20 cases, each in a **new chat** | `outputs/Txx_V0_gemini.md` |
| 2 | Make **TR** (English → Google Translate) for all 20 | `outputs/Txx_TR.md` |
| 3 | Run **V1** (v1 short prompt in the Gem) for all 20, plus the 6 edge cases | `outputs/Txx_V1_gemini.md`, `outputs/E0x_V1_gemini.md` |
| 4 | Two members score V0, TR and V1 with the rubric | `evaluation/team_scoring_sheet.csv` |
| 5 | **Error analysis 1:** list v1's real failures with test ids. Edit the v2 draft so it fixes exactly those, then adopt it | `evaluation/error_analysis.md`, `prompts/README.md` |
| 6 | Run **V2** for the same 20 cases + 6 edge cases | `outputs/Txx_V2_gemini.md` |
| 7 | Run the reviewer on every V2 output; if REVISE, ask for one revision = **V2R** | `outputs/Txx_V2R_gemini.md`, reviewer JSON in `outputs/reviews/` |
| 8 | Score V2 and V2R; **error analysis 2** (this decides what v3 needs, for M3) | scoring sheet, `evaluation/error_analysis.md` |
| 9 | Send the blind student form (TR vs V1 vs V2) | `evaluation/student_ratings.csv` |

Don't skip step 5. If you jump to v2 without logged v1 failures, the version change has no evidence behind it, which is exactly
what the "iteration" marks check.

That's about 110 model outputs. Split across 4 people, it's under 30 each.

Optional if time allows: run V2 on ChatGPT and Claude for the same 20 cases to compare models (otherwise do it in M3).

## Part B: Live demo in class (from 3 Nov)
Keep it under 4 minutes. Rehearse once.

1. **Problem (20 s):** show the M1 baseline recursion output and the Google Translate version. Point at a stiff sentence.
   Then show one real v1 failure from your log and the v2 rule that fixed it (this shows iteration).
2. **Live run (60 s):** in the Gem (on v2), type `Concept: Stack | Level: Beginner`. Then `Concept: Stack | Level: First-year`. Point out the
   difference in depth, the English terms with Hindi gloss, and the 5 sections.
3. **Reviewer (45 s):** paste the answer into the Reviewer Gem and show the JSON verdict.
4. **Robustness (30 s):** type edge case E05 (prompt injection) and show it stays on task.
5. **Results (45 s):** show your pilot results table/bar chart (V0 vs TR vs V1 vs V2 vs V2R) and one failure case you fixed.

Backup plan: if Wi-Fi fails, have screenshots/screen recording of the same steps ready.
