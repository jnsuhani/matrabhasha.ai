# v0 — Baseline prompt (from Milestone 1)

This is the simple prompt from Milestone 1 (Q18). Keep it unchanged so you can show how much v1 improves on it.

```
Explain the concept of {CONCEPT} in Hindi for a student.
```

**Known problems seen in the M1 sample output (recursion, ChatGPT):**
- No learner level, so depth is random.
- Coins a Hindi word ("पुनरावर्तन") that students never use in class.
- No analogy, no misconception, no practice questions.
- Format changes from run to run, so outputs are hard to compare.

These problems are why v1 adds a role, level control, a term rule, a fixed output format and a few-shot example.
