# Matrabhāsha: prompt and solution design (M2 component 1, 2 marks)

## 1. What the system does
**Input:** a first-year CS concept + a level (Beginner or First-year).
**Output:** a natural-Hindi explanation in 5 fixed sections (explanation, analogy, key terms, misconception, practice),
checked by a second reviewer prompt and a human before it is used.

## 2. Task decomposition
The one big task ("explain this in Hindi") is split into smaller prompt tasks:

| Step | Who/what | Prompt technique |
|---|---|---|
| 1. Read input, check it's a valid CS concept and level | Explainer prompt | Input validation, refusal rule |
| 2. Write explanation at the right depth | Explainer prompt | Role + audience-aware prompting, level constraints |
| 3. Handle technical terms | Explainer prompt | Constraint: English term + Hindi gloss |
| 4. Keep format fixed | Explainer prompt | Structured output, few-shot example |
| 5. Check accuracy, terms, tone, level, format | Reviewer prompt (separate chat) | Prompt chaining, LLM-as-judge, JSON output |
| 6. Fix flagged problems | Explainer prompt (revision message) | Self-refinement from feedback |
| 7. Final accuracy check | Team member | Human oversight |

## 3. Workflow diagram
Image version: `workflow.png` (ready for slides/report) and `workflow.svg` (editable).

```mermaid
flowchart TD
    U[Student types: Concept + Level] --> V{Valid CS concept<br/>and level?}
    V -- No --> Q[Ask to clarify, in Hindi]
    Q --> U
    V -- Yes --> E[Explainer prompt v1<br/>role + level rules + term rules<br/>+ few-shot example]
    E --> O[Draft answer<br/>5 fixed sections]
    O --> R[Reviewer prompt<br/>separate chat, JSON scores R1-R6]
    R --> D{Verdict}
    D -- REVISE --> F[Send errors back to explainer<br/>rewrite once]
    F --> O
    D -- PASS --> H[Team member checks accuracy]
    H --> S[Final Hindi explanation<br/>to student]
```

## 4. Prompt architecture (what's inside the explainer prompt)
```mermaid
flowchart LR
    subgraph Explainer system prompt
      A[ROLE<br/>friendly CS teacher] --> B[LEVELS<br/>Beginner / First-year limits]
      B --> C[LANGUAGE RULES<br/>English term + gloss,<br/>no literal translation]
      C --> D[ACCURACY RULES<br/>don't guess, refuse if unclear]
      D --> F[OUTPUT FORMAT<br/>5 fixed headings]
      F --> G[FEW-SHOT EXAMPLE<br/>team-written]
    end
    In[Concept + Level] --> A
    G --> Out[Structured Hindi answer]
```

## 5. Evaluation flow
```mermaid
flowchart LR
    T[Test set<br/>25 concepts x 2 levels] --> A[A: v0 baseline]
    T --> B[B: English + Google Translate]
    T --> C[C: v1 prompt]
    C --> D[D: v1 + reviewer loop]
    A & B & C & D --> S1[Team rubric<br/>2 scorers, 7 criteria]
    A & B & C --> S2[Blind student ratings<br/>naturalness, clarity, usefulness]
    S1 & S2 --> Res[Results table + error analysis<br/>-> next prompt version]
```

## 6. Interface
No-code prototype: a **Gemini Gem** (main) and a **Custom GPT** (backup), both using the same v1 instructions.
The student just types `Concept: Stack | Level: Beginner`. The reviewer is a second Gem/GPT.
See `build/build_guide.md`.

## 7. Responsible-AI design choices
- No personal data: inputs are only concept names. Student ratings are anonymous.
- Hallucination: accuracy rules in the prompt + reviewer + human check before use.
- Bias/inclusion: analogies from everyday Indian life, not region- or religion-specific; reviewers watch for this.
- Copyright: outputs are generated; the team's few-shot examples are original. No textbook text is pasted in.
- Limit stated to users: "AI-generated, verify with your teacher."

## How to view the mermaid diagrams
GitHub shows them automatically. Elsewhere, paste a block into https://mermaid.live and export PNG.
