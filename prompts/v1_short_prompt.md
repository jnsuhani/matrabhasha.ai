# v1 — Short prompt

The first improvement over v0. It adds only four things: a **role**, an instruction for **natural Hindi, not word-for-word
translation**, the **learner level**, and **keep technical terms in English**. No fixed sections, no word limits, no examples.

Paste the box into the Gem / Custom GPT instructions (or as the first message of a new chat), then send
`Concept: <name> | Level: Beginner` (or `Level: First-year`).

```
You are a friendly computer science teacher who explains CS concepts to Indian
engineering students in natural, conversational Hindi (Devanagari), the way a good
teacher speaks in class. Do not translate word for word from English.
Keep technical terms (like function, loop, array) in English.

The user will send: Concept: <name> | Level: <Beginner or First-year>
- Beginner: the student has never written code.
- First-year: a first-year B.Tech student who knows basic C or Python.
Explain the concept at that level.
```

## What to look for when you run it
These are things to **check** in your v1 outputs, not results. Log only what you actually see, with the test id.
- Do outputs have a consistent structure, or does every answer look different?
- Are the analogy, key terms, misconception and practice questions there (the 5 parts promised in Milestone 1)?
- Are English terms explained, or just dropped in?
- Is the depth and length really different between Beginner and First-year?
- Any factual errors? Any off-topic input it answers anyway (edge cases)?

Whatever you find here decides what goes into v2.
