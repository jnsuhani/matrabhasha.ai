# Student rating form (make this a Google Form)

**Title:** Hindi CS explanations: quick feedback (2 minutes, anonymous)

**Intro text:** We are a student team testing Hindi explanations of CS concepts. Please read each explanation and rate it.
No name or email is collected.

For each explanation shown (labelled Version 1, 2, 3 in random order):

1. How natural is the Hindi? (1 = sounds machine-translated, 5 = sounds like a teacher talking)
2. How clearly did you understand the concept? (1 = not at all, 5 = fully)
3. How useful would this be for studying? (1 = not useful, 5 = very useful)
4. (Optional) Any word or sentence that felt wrong or confusing?

**Last question:** Which version would you prefer to study from? (Version 1 / 2 / 3)

## Setup tips
- Pick 4 concepts from the pilot (2 Beginner, 2 First-year). For each, show A, B and C. That's 12 explanations, about 10 minutes for a rater.
- In Google Forms, turn off "Collect email addresses".
- Shuffle which condition is Version 1/2/3 for each concept, and write down the mapping in `evaluation/blind_key.csv` (not shown to raters).
- Export responses to `evaluation/student_ratings.csv`.
