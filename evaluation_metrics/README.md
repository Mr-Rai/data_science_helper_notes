# Evaluation Metrics

## Topic 1: **IAA** (Inter Annotator Agreement)
A statistical measure of how consistently different annotators (raters) label or rate the same items within the dataset.

**Metrics:**
| Metric                | Raters | Data Types Supported             | Handles Missing Values | Notes        |
|-----------------------|---|---------------------------------------|-------|-------------------------------|
| Cohen's Kappa         | 2 | Nominal, Ordinal                      | No    | Simple, limited to 2 raters   |
| Fleis's Kappa         | 3+| Nominal, Ordinal                      | No    | Fixed rater groups            |
| Krippendroff's Alpha  | 2+| All (Nominal, Ordinal, Inerval, Ratio)| Yes   | Robust, Flexible              |

Example:

You design an annotation study with 3 raters, who rate each Al-generated text on a scale of 1 (not good) to 5 (very good). What do you consider when choosing a metric of inter-annotator agreement?

Pick ONE or MORE options:
1. That the metric is suitable for ordinal data ✅
2. That there are more than 2 raters ✅
3. That there are less than 5 raters
4. The time it took the raters to perform the annotations
5. Whether annotation values are missing ✅

### Kohen's Kappa

<font size="5">$k = \frac{p_o - p_e}{1 - p_e}$</font>

**where:**
- $p_o$: Observed agreement. It is the proportion of times both raters agree, found by dividing the number of
agreements by the total number of items.
- $p_e$: Expected agreement by chance. It is calculated by multiplying the probability that each rater would randomly assign each category, then summing across categories.

| Kappa | Interpretation |
|-------|----------------|
| > 0.8 | almost perfect |
| > 0.6 | substantial    |
| > 0.4 | moderate       |
| > 0.2 | slight         |
| < 0   | poor           |
