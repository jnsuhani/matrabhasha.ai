<!-- Source text of docs/SyntaxAI_Synopsis.pdf (2 pages, Milestone 2 supporting document). -->

# Synopsis: Matrabhāsha

Explaining first-year CS concepts in natural Hindi  
Team SyntaxAI (PE-B65-11) · Batch B65-80 · Bennett University · SCSE4041 Mini Project, Milestone 2 · Problem C19 (Bilingual explainer)  
Suhani Jain (S24CSEU2709, leader) · Khushi Upadhyay (S24CSEU1642) · Amna Khan (S24CSEU1623) · Ashima Singh (S24CSEU2720)


### Problem

Many Hindi-comfortable learners, such as Hindi-medium first-year B.Tech students, struggle with CS concepts taught only in English. Machine translation gives stiff, word-for-word Hindi, coins Hindi words for technical terms that nobody uses in class, and ignores what the learner already knows. NEP 2020 encourages mother-tongue learning, and UGC guidance on translated books asks that technical terms stay in English.

### Objectives

1.  Build a prompt that explains an introductory CS concept in natural, conversational Hindi (Devanagari), keeping technical terms in English, at two knowledge levels: Beginner (no programming background) and Intermediate (knows programming basics).
2.  Improve that prompt in versions, where each change is justified by failures logged in real runs of the previous version.
3.  Add a reviewer prompt that checks each answer for accuracy, terms, naturalness, level fit and format (prompt chaining).
4.  Test on normal, edge and invalid inputs and compare every version with the one-line baseline.

### Scope

**In scope:** 25 introductory CS concepts (programming, data structures, algorithms, OS, DBMS) × 2 levels = 50 test cases, plus 6 edge cases. Two prompts: the explainer (live as the Gemini Gem “Matrabhāsha v2”) and the reviewer. Milestone 2 tested 26 inputs (20 pilot cases + E01–E06) on one model across three prompt versions (v0, v1, v2). **Out of scope:** other Indian languages, voice input, advanced or non-CS topics, grading students.

### Methodology

- **Prototype:** no-code Gemini Gems in the Gemini app (Everyday help, 4 Hydrogen model; runs on 31 Oct–1 Nov 2026 were logged as Gemini Flash, the app's earlier label). The learner types *Concept: Stack \| Level: Beginner*.
- **Version ladder:** v0 one-line baseline (“Explain \<concept\> in Hindi for a \<level\> learner”) → v1 adds a friendly CS teacher role and the level → v2 adds natural Hindi in Devanagari, no word-for-word translation, English technical terms, and a definition of each level.
- **Reviewer:** a separate chat scores the answer on six rules (R1–R6) and returns JSON with quoted errors and a PASS/REVISE verdict; on REVISE the explainer rewrites once.
- **Testing:** each member ran 5 pilot cases under v0, v1 and v2 (60 runs); 6 edge cases on v1 and v2 (12 runs); 1 reviewer run: 73 logged runs in *evaluation/experiment_log.csv*, every failure quoted in *evaluation/error_analysis.md*. Pass rule: Devanagari, no code for a Beginner, all key points, no factual error. During testing, team members checked outputs for technical accuracy.

### Results so far (Milestone 2)

v2 passed 11 of 26 inputs (9/20 pilot, 2/6 edge), v1 7 of 26, v0 8 of 20. v2's natural-Hindi rule removed Roman Hinglish (6/20 answers in v1 → 0/20 in v2). Still open in v2: no practice questions in any answer (20/20), code for Beginners (3/10), a key point missing (9/20), factual errors (4/20), and no rule for off-topic inputs, unsupported levels or prompt injection (E01, E03, E05). The reviewer, run once on T01, returned REVISE with 4 errors that matched the team's own findings.

### Expected outcome

A final prompt (v3, Milestone 3) with the reviewer loop that gives a natural Hindi answer in a fixed 5-section format (explanation, analogy, key terms, misconception, practice questions), with no code for Beginners and every key point covered, so a learner can understand a concept on their own. It will be measured on all 50 cases on Gemini, ChatGPT and Claude, with a two-scorer rubric and anonymous ratings from Hindi-speaking students, against the v0 baseline.

References: Bennett University SCSE4041 Mini Project guidelines 2026; Ministry of Education, NEP 2020; UGC guidelines on translation of books in Indian languages (Careers360). Claude (Anthropic) helped draft documentation; every output and number comes from the team's own runs.
