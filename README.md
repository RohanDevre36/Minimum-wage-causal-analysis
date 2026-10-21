# Minimum Wage Policy and Food Services Outcomes

A Python study of New Jersey’s January 2014 minimum wage policy,
using Difference-in-Differences to examine employment and average
weekly wages in private-sector food services and drinking places.

## Research question

How did New Jersey’s employment and weekly wages change after
the policy, relative to selected comparison states?

## Data

- BLS Quarterly Census of Employment and Wages (QCEW).
- Annual minimum wage histories from FRED, sourced from the
  US Department of Labor.
- Prepared panel: 1,836 state-quarter observations across
  50 states and Washington, DC, from 2010–2018.
- Estimation sample: New Jersey, Pennsylvania, Indiana, Kansas,
  Kentucky, and Virginia.
- Industry: NAICS 722, private-sector food services and drinking places.

## Methods

- State and calendar-quarter fixed effects.
- State-specific seasonal adjustments.
- Year-specific relative differences.
- Alternative comparison groups and study windows.
- Leave-one-control-out sensitivity analysis.
- A pre-policy placebo intervention.
- Approximate HAC uncertainty intervals for quarterly outcome gaps.

## Main results

For 2010–2017, excluding Q4 2013, relative to five equally weighted
comparison states:

| Outcome | Estimate | Approximate conditional 95% interval |
|---|---:|---:|
| Employment | +1.02% | +0.15% to +1.90% |
| Average weekly wages | −0.26% | −0.80% to +0.28% |

Employment estimates change materially with the comparison group.
Using Pennsylvania alone produces an estimate of +2.65%.
The wage estimate changes sign when Kansas is excluded.

These are conditional comparisons, not definitive causal effects.
Pre-policy differences, concurrent policies, a small control group,
and short-series inference limit interpretation.

## Project files

- `notebooks/01_Data_Collection.ipynb`: data retrieval, preparation,
  validation, and initial comparison screening.
- `notebooks/02_Causal_Analysis.ipynb`: models, diagnostics,
  sensitivity checks, and interpretation.
- `data_processed/`: prepared datasets.
- `outputs/`: result tables, charts, and analytical report.
- `requirements.txt`: recorded package versions.
- `environment.txt`: initial Python environment information.

[Read the analytical report](outputs/Minimum_Wage_Analysis_Report.md)

## Reproduce the analysis

1. Open the notebooks in Google Colab.
2. Create the project folders described in the collection notebook.
3. Run `01_Data_Collection.ipynb` to retrieve and prepare data.
   Historical BLS archives require several GB of storage.
4. Run `02_Causal_Analysis.ipynb` using the prepared panel.

The analysis notebook can run without repeating the downloads if
the prepared panel is available at its configured Drive path.
Adjust `PROJECT_DIR` to match your folder location.

Package versions document the initial environment; they are not
a complete dependency lockfile.

## Interpretation limits

- Average weekly wages are not hourly pay.
- The intervention includes subsequent inflation-linked adjustments.
- Local policies may overlap with the minimum wage intervention.
- HAC intervals are approximate and conditional on the selected model.
- The findings do not establish a national minimum wage policy effect.

Detailed sources and limitations appear in the report.
