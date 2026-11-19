# 005: Explore the replicates and make a first analysis

- **Status:** active
- **Created:** 2026-11-18
- **Updated:** 2026-11-19

## Goal

`analysis.ipynb` gives, for each element used, descriptive statistics of the replicates (n, mean, standard deviation, relative standard deviation, minimum, maximum) and at least one figure, each followed by a sentence with the numbers a reader should take from it. It then applies one method from the course to compare the observed replicate scatter with the reported `errpct`, with a first result that has units and an uncertainty, and a sentence on the property of the data that chose the method. The notebook runs top to bottom after a kernel restart and ends with a cell that prints the Python and package versions.

## Progress log
- 2026-11-18: Mentor recommended using Levene's test for evaluation of variance. Will decide to use or not in evaluation step
- 2026-11-19: Added descriptive statistics and two figures to analysis.ipynb. Ca and P errpct are reported to two decimals, so each takes only a few distinct values (Ca 0.96 to 1.00, P 0.71 to 0.74). Also found that the Spearman correlation of errpct with wt% was -0.87~-0.98 in all elements. Will choose how to summarize errpct and which variance test to use next.
- 2026-11-19: Made a first analysis cell in analysis.ipynb: R = observed SD / pooled reported error, with 95% bootstrap interval over rows. Ce, Ca, P, S, F had intervals over 1 (R = 1.45~ 2.70) while Sr (R = 0.91) and Na (R = 1.19) contained 1 in their interval. Dropping the flagged row (S, z = -3.9) moved Sr from "contains 1" to "below 1".
- 2026-11-19: Changed the main interval from chi-square to bootstrap as assistant suggested. I chose it because the course covers bootstrap. Chi-square is kept as a check as it was not in the course. For the next step, will decide whether to add Brown-Forsythe, write judgement log, commit.

## Outcome
