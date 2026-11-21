# V1 outputs (short prompt)

**Condition:** the **Matrabhāsha v1** Gem on Gemini **Flash**, with the two-line instructions from `prompts/v1_short_prompt.md`:

```
You are a friendly computer science teacher. Explain the concept the user gives
in Hindi, at the level they mention (Beginner or Intermediate).
```

> Model name: our runs were logged as Gemini Flash. "Flash" was the Gemini app's earlier label for its fast model; the app's model picker now calls it "Everyday help (4 Hydrogen)". Log new runs with the label the app shows.

Setup screenshots: `screenshots/gem_v1_setup.png`, `screenshots/gem_v1_chat.png`.

**What to send** (one new chat per case):

```
Concept: <concept> | Level: <Beginner or Intermediate>
```

Example: `Concept: For loop | Level: Beginner`

**Files:** save each answer unchanged as `outputs/v1/<test_id>.md` (for example `T01.md`). Each member adds their own test ids to this folder.

**Log:** add one row per run to `evaluation/experiment_log.csv` with condition `V1`, model `Gemini Flash`, prompt_version `v1`, and your name in the member column. Run `git pull` before you push.
