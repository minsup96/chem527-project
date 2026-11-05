# Proposal: Does the reported EPMA error match the observed replicate scatter?

## Question

In the 85 replicate EPMA analyses of reference material 7802 Apatite, does the reported `errpct` match the observed replicate scatter for each element?

## Data

- **Source:** Benson, E.K., and Watts, K.E., 2024, Apatite and monazite geochemistry data at Mountain Pass, California, 2024: U.S. Geological Survey data release, https://doi.org/10.5066/P1LGUGBG (CC0 1.0). Accessed 2026-11-03.
- **Companion paper:** Benson and Watts (2024), Economic Geology, 119(7), 1611-1642, https://doi.org/10.5382/econgeo.5108.
- **File used:** `data/EMPA_Apatite_Standards.csv`, committed as downloaded.
- **Instrument (from the paper):** JEOL JXA-8530FPlus electron microprobe, USGS Denver Microbeam Laboratory. Apatite analyses used 15 kV, 10 nA and a 10 µm spot.

## Are the data sufficient?

**Observations.** The file has 86 data rows: 85 replicate analyses of the reference material labeled `7802 Apatite`, and one `Detection Limit` row, which is not a measurement and is excluded from the scatter. The paper reports 85 replicate analyses of the Wilberforce apatite reference material. I assume the two are the same material, because the counts match; the files do not say so.

**Variables.** For each element, `*_wtpct` (weight percent) and `*_errpct` (percent). Ce, Ca, Sr, Na, P, S and F are detected in all 85 analyses and are used. Mn (32 of 85), Cl (5) and Ba (2) are excluded as they are detected too rarely to estimate a scatter (value under detection limit remains empty and leaves only detected values, which leads to smaller scatter and higher average).

**What is missing or unclear.**
- `errpct` is defined in the data dictionary only as "Error of ... analysis, percent". It is not stated whether it is relative or absolute, whether it is 1σ or 2σ, or whether it comes from counting statistics alone. I will state my assumption and test how the answer changes under the alternatives.
- The files give no accepted values for the reference material, so accuracy cannot be assessed. The question concerns precision only.
- Counting times are not given, and I cannot confirm that the row order is the measurement order.
- The excluded elements are those near the detection limit, so the answer does not cover the low-concentration regime.

**If the data do not answer the question.** If conclusion differs by interpretation, try possible combinations of interpretation of `errpct` (relative/absolute/1σ/2σ) before the final result and report the result. If the difference lies within the sampling uncertainty of the observed scatter, also report that.
