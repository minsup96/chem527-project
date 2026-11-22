# Judgment log: Minsup So

## How I used AI in this project

(Final submission only.)

## Entries

### Nov 19: Switching into bootstrap method

- **What the assistant suggested:** From the original Chi-square interval, the assistant suggested to switch into bootstrap as the bootstrap method was included in the course materials.
- **What I did:** I accepted the suggestion and kept Chi-square as a check.
- **Why, from my data:** In First analysis section table, Na changed from 1.04 (above 1) for Chi-square(R_chi2_low) to 0.99 (contains 1) for bootstrap(R_low) while other elements also had their low end decreased but remained in same direction.  

### Nov 19: Not excluding row 71

- **What the assistant suggested:** For the row 71 (flagged row), the assistant suggested multiple options for whether to drop the flagged row from the analysis.
- **What I did:** I checked the original CSV and confirmed the line data and accepted one of the option that assistant suggested (keep everything and show the dropped row-result only as a sensitivity).
- **Why, from my data:** The z value in row 71 was S −3.9, F −2.8, Sr 2.77, Ca 1.77, P 1.66, Na 0.37, Ce −0.54. If the row 71 was excluded, the direction for Sr would become "under 1" from "including 1" (from R=0.91 to 0.88). However, even |z| value was larger than 3.5 in S, the statistical distance alone was not enough for excluding a measurement, and the data had no record of an analysis fault. Also, the main result was not changed (S remained over 1, 1.64 → 1.49) regardless of row 71.