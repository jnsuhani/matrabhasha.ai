# V0 outputs (baseline, no prompt)

**Condition:** plain Gemini **Flash**, no Gem instructions (a new Gemini chat, or a Gem with empty instructions named "Matrabhāsha v0").

**What to send** (same wording for every case, one new chat per case):

```
Explain <concept> in Hindi for a <level> learner
```

Example: `Explain For loop in Hindi for a Beginner learner`

**Files:** save each answer unchanged as `outputs/v0/<test_id>.md` (for example `T01.md`), the same way as `outputs/v1/`. Each member adds their own test ids to this folder.

**Log:** add one row per run to `evaluation/experiment_log.csv` with condition `V0`, model `Gemini Flash`, prompt_version `v0`, and your name in the member column. Run `git pull` before you push.
