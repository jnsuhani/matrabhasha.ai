# Pilot run and demo plan (M2 "demonstration / pilot run", 2 marks)

## Part A: Pilot run (do this before 2 Nov)
Pilot = the 10 concepts marked `in_m2_pilot = yes` in `test-set/test_set.csv`, both levels = 20 test cases.

| Step | What | Output files |
|---|---|---|
| 1 | Run **A** (v0 baseline) on Gemini for all 20 cases, each in a **new chat** | `outputs/Txx_A_gemini.md` |
| 2 | Make **B** (English → Google Translate) for all 20 | `outputs/Txx_B_translate.md` |
| 3 | Run **C** (v1 Gem) for all 20 | `outputs/Txx_C_gemini.md` |
| 4 | Run the reviewer on every C output; if REVISE, ask for one revision = **D** | `outputs/Txx_D_gemini.md`, reviewer JSON in `outputs/reviews/` |
| 5 | Run the 6 edge cases on the v1 Gem | `outputs/E0x_C_gemini.md` |
| 6 | Two members score each A/B/C/D output with the rubric | `evaluation/team_scoring_sheet.csv` |
| 7 | Send the blind student form | `evaluation/student_ratings.csv` |
| 8 | Write 3 failure cases + the prompt change each one caused (that becomes v1.1) | `evaluation/error_analysis.md` |

That's about 80 model outputs. Split across 4 people, it's around 20 each, which is one evening.

Optional if time allows: run C on ChatGPT and Claude for the same 20 cases to compare models (otherwise do it in M3).

## Part B: Live demo in class (from 3 Nov)
Keep it under 4 minutes. Rehearse once.

1. **Problem (20 s):** show the M1 baseline recursion output and the Google Translate version. Point at a stiff sentence.
2. **Live run (60 s):** in the Gem, type `Concept: Stack | Level: Beginner`. Then `Concept: Stack | Level: First-year`. Point out the
   difference in depth, the English terms with Hindi gloss, and the 5 sections.
3. **Reviewer (45 s):** paste the answer into the Reviewer Gem and show the JSON verdict.
4. **Robustness (30 s):** type edge case E05 (prompt injection) and show it stays on task.
5. **Results (45 s):** show your pilot results table/bar chart (A vs B vs C vs D) and one failure case you fixed.

Backup plan: if Wi-Fi fails, have screenshots/screen recording of the same steps ready.
