# Test set

- `test_set.csv`: 25 introductory CS concepts × 2 levels (Beginner, Intermediate) = **50 test cases** (T01–T50).
  - `must_include_key_points` is the checklist the team used to check accuracy during testing (rubric criterion A).
  - `target_misconception` is a common mistake the answer would ideally address. It's fine if the model picks a different valid one.
  - `in_m2_pilot = yes` marks the **10 concepts (20 cases)** to run before 2 Nov. Run the rest for Milestone 3.
- `edge_cases.csv`: 6 tricky inputs (off-topic, missing level, prompt injection). These test reliability and are worth showing in the demo.

The concept list was drafted by Claude from a standard first-year syllabus.

## Syllabus check
Done by Khushi Upadhyay: the concept list was checked against the Bennett first-year syllabus and found to fit, so **no concept
was changed**. The pilot runs and the full test set use the list as drafted.
