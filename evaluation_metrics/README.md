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

$k = \frac{p_o - p_e}{1 - p_e}$

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

**Example:**<br>
Two annotators are evaluating the summaries of `model A` and `model B` on five different texts and decide which one is better. What is the cohen's Kappa?

| Text          | 1 | 2 | 3 | 4 | 5 |
|---------------|---|---|---|---|---|
| Annotator 1   | A | B | B | A | A |
| Annotator 2   | A | A | B | A | B |

- **Observed Agreement ($p_0$):**  Out of total 5, annotators agreed on 3 texts i.e. 1, 3, 4 so $p_0$ = 3/5 = 0.6
-  **Expected Agreement by chance ($p_e$):** Calculated using the probability that both annotators assign the same label.
   -  Proportion for A: Annotater 1: 3/5, Annotater 2: 3/5
   -  Proportion for B: Annotater 1: 2/5, Annotater 2: 2/5
   -  $p_e = \frac{3}{5}*\frac{3}{5} + \frac{2}{5}*\frac{2}{5} = 0.52$
-  Kappa:
   -  $k = \frac{0.6 - 0.52}{1 - 0.52} = 0.17$
  
-----------------------------

## Topic 2: Confusion Metrics
A confusion matrix is a table that summarizes classification results. It visually displays how many predictions were correct and how many were incorrect for each class in a dataset.

1. **Binary Confusion Matrix**
   - Example - Email filter classifies messages as spam or not spam
2. **MultiClass Confusion Matrix**
   - Example - For models predicting three or more classes (e.g., Cat, Dog, Horse)

### Key Metrics
1. Accuracy = $\frac{TP + TN}{TP + TN + FP + FN}$
2. Precision = $\frac{TP}{TP + FP}$
3. Recall (Senstivity) = $\frac{TP}{TP + FN}$
4. F1 Score: Harmonic mean of Precision and Recall