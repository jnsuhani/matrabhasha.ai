# Build guide: making the prototype (M2 "running build", 3 marks)

The prototype is two no-code chatbots built from your prompts. No coding needed. Menu names change sometimes; if a button
has moved, look for "Gems" / "Create a GPT" / "Project instructions".

## Option 1 (main): Gemini Gems
1. Go to https://gemini.google.com and sign in (a personal Google account is safest; college accounts sometimes block Gems).
2. In the left sidebar open **Gems** (or "Explore Gems") → **New Gem**.
3. **Name:** `Matrabhāsha – Hindi CS Explainer`
4. **Instructions:** paste the full box from `prompts/v1_explainer_prompt.md`, with your team's few-shot example pasted in place of
   `{PASTE ONE TEAM-WRITTEN EXAMPLE HERE}`.
5. Click **Save**. Test it: type `Concept: Stack | Level: Beginner`.
6. Make a second Gem: **Name** `Matrabhāsha Reviewer`, **Instructions** = the reviewer box from `prompts/reviewer_prompt.md`
   (keep the last 3 lines as they are; you'll paste concept/level/explanation as your message).
7. Screenshot both Gem setup pages. These are evidence for the "build" marks. Save to `screenshots/`.

## Option 2 (backup / comparison): ChatGPT Custom GPT
1. Go to https://chatgpt.com → **Explore GPTs** → **+ Create**. (Creating GPTs may need a paid plan. If it's not available,
   use Option 3 or just paste the prompt as the first message of a new chat.)
2. Open the **Configure** tab.
3. **Name:** same as above. **Instructions:** same v1 prompt.
4. **Conversation starters:** `Concept: Array | Level: Beginner`, `Concept: Recursion | Level: First-year`
5. Turn off web browsing and image generation (not needed; keeps answers grounded in the prompt).
6. Save as **Only me** or **Anyone with the link** (for the demo).

## Option 3: Claude Project
1. https://claude.ai → **Projects** → **Create project** → name it Matrabhāsha.
2. Paste the v1 prompt into **Project instructions**. Every new chat in that project then uses it.

## Keep the build reproducible
- The exact text pasted into each tool must match a file in `prompts/`. If you change the Gem, change the file and add a row to the
  version history table.
- Write the model and date of every run in `evaluation/experiment_log.csv` (models change over time).

## Saving outputs
For every run, copy the answer into a text file named like `outputs/T07_C_gemini.md` (test id, condition, model) and add a row in the
experiment log. Copy-paste the text exactly; don't fix anything by hand, since the evaluation must show what the model really produced.
