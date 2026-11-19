# 004: Load the data and list its problems

- **Status:** done
- **Created:** 2026-11-18
- **Updated:** 2026-11-18

## Goal

The project notebook `analysis.ipynb` starts from a clean kernel and loads `data/EMPA_Apatite_Standards.csv` with a relative path. It separates the 85 replicate analyses of `7802 Apatite` from the `Detection Limit` row, states the unit of each kind of column and what one row is, and gives for each problem found on loading (blank cells, detections per element, negative `errpct`) one sentence on what was done about it. The numbers that encode a choice, such as the elements used and the detection rule, are constants in a Parameters section with a unit and a reason.

## Progress log
- 2026-11-18: Started the notebook analysis.ipynb and made parameter cell and loaded 86 rows (85 data, 1 detection-limit)
- 2026-11-18: Made the detection data table from raw data, and decided the list of elements to include and exclude for the calculation (use Ce, Ca, Sr, Na, P, S, F, not use Mn, Ba, Cl). Elements that were detected 85 of 85 times were selected while elements that were detected less than 85 were excluded.

## Outcome
Decided which elements will be used (Ce, Ca, Sr, Na, P, S, F, detected 85/85) or not (Mn, Cl, Ba, detected less than 85 and have negative errpct) in calculation.