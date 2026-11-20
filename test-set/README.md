# Test set

- `test_set.csv`: 25 introductory CS concepts × 2 levels (Beginner, Intermediate) = **50 test cases** (T01–T50).
  - `must_include_key_points` is the checklist the human checker uses for accuracy (rubric criterion A).
  - `target_misconception` is a common mistake the answer would ideally address. It's fine if the model picks a different valid one.
  - `in_m2_pilot = yes` marks the **10 concepts (20 cases)** to run before 2 Nov. Run the rest for Milestone 3.
- `edge_cases.csv`: 6 tricky inputs (off-topic, missing level, prompt injection). These test reliability and are worth showing in the demo.

The concept list was drafted by Claude from a standard first-year syllabus.

## Syllabus check (pending record)
Khushi Upadhyay owns the check of this list against the Bennett first-year syllabus. Its result is **not recorded yet**. When
it is done, write here: the date, the syllabus/course codes used, and either "no changes" or each concept swapped (old → new,
with test ids). Note any swap in `prompts/README.md` too. No concept has been changed so far, so the pilot runs used the list
as drafted.
