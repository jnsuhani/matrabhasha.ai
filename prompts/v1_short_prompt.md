# v1 — Short prompt

The first, small step up from v0. It adds only two things: a **teacher role** and the **learner level**. It does not say how to
write the Hindi, what to do with English terms, what the levels mean, or what the answer should contain. Those are left out on
purpose, so the v1 runs show which of them are really needed.

Paste the box into the Gem / Custom GPT instructions (or as the first message of a new chat), then send
`Concept: <name> | Level: Beginner` (or `Level: Intermediate`).

```
You are a friendly computer science teacher. Explain the concept the user gives
in Hindi, at the level they mention (Beginner or Intermediate).
```

## What to look for when you run it
These are things to **check** in your v1 outputs, not results. Log only what you actually see, with the test id.
- Does the Hindi sound natural, or stiff and translated word for word?
- Does it coin pure-Hindi words for technical terms (like "पुनरावर्तन"), or keep the English terms students hear in class?
- Is the depth really different between Beginner and Intermediate? Does it guess what "Intermediate" means?
- Does it use code for a Beginner?
- Do outputs have a consistent structure, or does every answer look different?
- Are the analogy, key terms, misconception and practice questions there (the 5 parts promised in Milestone 1)?
- Any factual errors? Any off-topic input it answers anyway (edge cases)?

Whatever you find here decides what goes into v2. Run it on the pilot test cases only. **Variable** is a few-shot example
concept (see `few_shot_examples.md`), not a test case, so a run on Variable is a quick try-out, not evidence.
