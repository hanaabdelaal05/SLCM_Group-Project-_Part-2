CS 430 SLCM Group Project - Part 2: Patterns of Need
Team: Hana Abdelaal, Hanan Mohamed

WHAT'S IN THIS SUBMISSION
1. CS430_project_part2.ipynb 
2. Part 2 written report 
3. Slides - presented in class Nov 19

HOW TO RUN
- Put these files in the same folder as the notebook:
  SLCM_part2_intake_profiles_clean.csv
  SLCM_part2_household_members_clean.csv
  SLCM_part2_care_path_subtickets.csv
  SLCM_part2_data_dictionary.csv
  SLCM_part2_cleaning_log.csv
- Colab: Runtime -> Restart session and run all.
- Libraries: pandas, numpy, scikit-learn, scipy, matplotlib, seaborn.

ANALYSIS DECISIONS (short version)
- Unit: one row per person (PID), not per ticket. 426 tickets -> 395 people.
  We kept each person's latest ticket that was not flagged duplicate.
  6 duplicate-flagged tickets remain (those people have no other ticket); flagged, not dropped.
- Clustering inputs: income (log), children 17 and under, household size,
  housing group, eviction status ("Unknown" kept as its own level), employment status.
- Not used as inputs: past-due rent (only 153 of 395 have it), urgent_housing_proxy,
  identifiers, sensitive fields (age, gender, race, language). Past-due rent is used only to describe clusters.
- K-Means k = 3 (n_init = 20, random_state = 0). Hierarchical: Ward, k = 3.
  Agreement: Adjusted Rand Index 0.824.

WHERE THINGS ARE IN THE NOTEBOOK
- Task 0: analysis unit | Task 1: features and cleaning log additions
- Task 2: K-Means, hierarchical, cluster names and profiles
- Policy Questions 1-4 | What Did We Learn?

DATA AND AI USE
- Masked, classroom-approved data only; no re-identification; files not shared publicly.
- AI was used for explanations and debugging; we checked the analyses and wrote our own interpretations.
