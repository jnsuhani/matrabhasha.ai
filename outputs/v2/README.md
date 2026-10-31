# V2 outputs (guided prompt)

**Condition:** the **Matrabhāsha v2** Gem on Gemini **Flash**, with the instructions from `prompts/v2_guided_prompt.md`. Setup screenshots: `screenshots/gem_v2_setup.png`, `screenshots/gem_v2_chat.png`.

**What to send** (one new chat per case):

```
Concept: <concept> | Level: <Beginner or Intermediate>
```

Example: `Concept: For loop | Level: Beginner`

**Files:** save each answer unchanged as `outputs/v2/<test_id>.md` (for example `T01.md`), the same way as `outputs/v1/`. Each member adds their own test ids to this folder.

**Log:** add one row per run to `evaluation/experiment_log.csv` with condition `V2`, model `Gemini Flash`, prompt_version `v2`, and your name in the member column. Run `git pull` before you push.
