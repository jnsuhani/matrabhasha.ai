# v2 — Guided prompt (DRAFT, planned)

> **Draft.** Only adopt v2 after real v1 runs show the problems it fixes (for example: stiff or translated Hindi, coined Hindi
> words, a vague idea of the levels). Edit it so each addition matches a failure you logged, and drop what you didn't need.
> See `README.md` in this folder.

v2 = v1 + an instruction for **natural Hindi, not word-for-word translation**, **keep technical terms in English**, and a
**definition of each level** (based on what the learner knows, not their year or degree). Still no fixed sections, no word
limits and no examples.

Paste the box into the Gem / Custom GPT instructions (or as the first message of a new chat), then send
`Concept: <name> | Level: Beginner` (or `Level: Intermediate`).

```
You are a friendly computer science teacher who explains CS concepts to
Hindi-comfortable learners in natural, conversational Hindi (Devanagari), the way a
good teacher speaks in class. Do not translate word for word from English.
Keep technical terms (like function, loop, array) in English.

The user will send: Concept: <name> | Level: <Beginner or Intermediate>
The level is about what the learner already knows, not their year or degree.
- Beginner: no programming or CS background yet.
- Intermediate: already knows programming basics (variables, loops, functions in
  C or Python) and wants precise technical depth.
Explain the concept at that level.
```

## What to look for when you run it
These are things to **check** in your v2 outputs, not results. Log only what you actually see, with the test id.
- Do outputs have a consistent structure, or does every answer look different?
- Are the analogy, key terms, misconception and practice questions there (the 5 parts promised in Milestone 1)?
- Are English terms explained, or just dropped in?
- Does a Beginner answer still use code? Is the length right for each level?
- Are numbers written in one style (0–9 or Devanagari digits), or mixed?
- Any factual errors? Any off-topic input it answers anyway (edge cases)?

Whatever you find here decides what goes into v3.

A team member tried this exact text (as the earlier v1) on **Variable, Beginner** on 21 Oct 2026. The answer was good, but it had
no misconception and no practice questions, used code for a beginner and mixed numeral styles. Variable is a few-shot concept,
not a test case, so this is a hint of what to check, not evidence. Log only what you see on the pilot test cases.
