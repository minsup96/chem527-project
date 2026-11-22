# 005: Explore the replicates and make a first analysis

- **Status:** done
- **Created:** 2026-11-18
- **Updated:** 2026-11-21

## Goal

`analysis.ipynb` gives, for each element used, descriptive statistics of the replicates (n, mean, standard deviation, relative standard deviation, minimum, maximum) and at least one figure, each followed by a sentence with the numbers a reader should take from it. It then applies one method from the course to compare the observed replicate scatter with the reported `errpct`, with a first result that has units and an uncertainty, and a sentence on the property of the data that chose the method. The notebook runs top to bottom after a kernel restart and ends with a cell that prints the Python and package versions.

## Progress log
- 2026-11-18: Mentor recommended using Levene's test for evaluation of variance. Will decide to use or not in evaluation step
- 2026-11-19: Added descriptive statistics and two figures to analysis.ipynb. Ca and P errpct are reported to two decimals, so each takes only a few distinct values (Ca 0.96 to 1.00, P 0.71 to 0.74). Also found that the Spearman correlation of errpct with wt% was -0.87~-0.98 in all elements. Will choose how to summarize errpct and which variance test to use next.
- 2026-11-19: Made a first analysis cell in analysis.ipynb: R = observed SD / pooled reported error, with 95% bootstrap interval over rows. Ce, Ca, P, S, F had intervals over 1 (R = 1.45~ 2.70) while Sr (R = 0.91) and Na (R = 1.19) contained 1 in their interval. Dropping the flagged row (S, z = -3.9) moved Sr from "contains 1" to "below 1".
- 2026-11-19: Changed the main interval from chi-square to bootstrap as assistant suggested. I chose it because the course covers bootstrap. Chi-square is kept as a check as it was not in the course. For the next step, will decide whether to add Brown-Forsythe, write judgment log, commit.
- 2026-11-21: Wrote two judgement logs. Confirmed that Na changed from 1.04 (above 1) for Chi-square(R_chi2_low) to 0.99 (contains 1) for bootstrap(R_low) and the main result was not changed (S remained over 1, 1.64 → 1.49) regardless of row 71.

## Outcome
For the analysis, 5 elements (Ce, Ca, P, S, F) had larger scatter (1.45 to 2.70 times) than reported `errpct`, and the 95% interval of other two element (Sr, Na) had 1 (R=0.91, 1.19) while Na was in the borderline (lower limit 0.99). Therefore, the reported `errpct` (assumed 1σ) was reported smaller than the replicate scatter in five elements out of seven.
The multiple-comparison correction was not applied to the result and each interval was 95% for only its own element. For the limitation ,since there was no exact definition for `errpct` in original document, it is assumed to be read as 1σ. Reading it as 2σ would doubles R value, and would moves Sr above 1. 2σ interval was not calculated yet. I also calculated without the row exceeding 3.5σ (replicate 71, S −3.9) and only Sr changed the direction (from "contains 1" to "below 1") in bootstrap while other elements remained same.
For Further step, I will decide whether to add Brown-Forsythe as the mentor suggested and how to use the negative correlation between `errpct` and wt% (Spearman −0.87 to −0.98)