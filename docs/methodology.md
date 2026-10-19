# Research methodology

This document summarizes the workflow reported in the final undergraduate thesis and reflected in the four supplied notebooks. It is not a replacement for the thesis.

## Phase 1 — Collection and preprocessing

- Source: Google Play Store reviews of Indodax, initially 80,000 records.
- Filtering and light preprocessing yielded 68,204 cleaned reviews.
- The supplied Phase 1 notebook loads the exported spreadsheet `indodax_reviews.xlsx`; the collection script is not part of the four notebooks.
- A sample of 8,000 reviews was prepared for manual annotation by three annotators.

## Phase 2 — Annotations and data partitions

- Each review receives a **single dominant aspect**: interface, security, transaction, customer service or irrelevant.
- Relevant reviews receive negative / neutral / positive sentiment labels.
- Annotators labeled independently. Reported Fleiss' Kappa: 0.7609 (aspect) and 0.8707 (sentiment).
- Majority voting and validation produced 7,775 final labeled reviews.
- Near-duplicate grouping was used to reduce leakage across train/validation/test.
- Split counts: 4,675 / 1,548 / 1,552, respectively.
- Random oversampling was used **only for training**. The resulting aspect training set had 5,363 rows; sentiment training set had 3,537 rows.

## Phase 3 — Modeling and evaluation

Two separate classifiers use an IndoBERT language model plus BiLSTM sequence processing:

1. **Aspect classification** across five classes, with `tidak_relevan` as a gate.
2. **Conditional sentiment classification** across three labels for a relevant aspect.

Configurations are compared using validation Macro F1; thesis-selected configurations use a two-layer BiLSTM for aspects and a four-layer BiLSTM for sentiment. Test-set evaluation includes separate aspect classification, sentiment with reference aspects, conditional predicted-aspect pipeline, and a 13-class joint evaluation. Because the conditions differ, the scores should not be treated as a direct comparison of interchangeable models.

| Evaluation setting | Accuracy | Macro F1 |
| --- | ---: | ---: |
| Aspect classification | 93.62% | 90.19% |
| Sentiment with reference aspect | 93.22% | 86.26% |
| Conditional sentiment with predicted aspect | 93.43% | 86.55% |
| Joint aspect–sentiment (13 classes) | 89.43% | 77.71% |

The thesis also reports 98.82% **coverage** for conditional sentiment prediction. Coverage is not accuracy; it measures how often truly relevant test reviews reached the downstream sentiment stage.

## Phase 4 — Full-corpus inference

The selected classifiers were applied to all 68,204 clean reviews without another training or selection step. Predicted relevant: 45,584; predicted irrelevant: 22,620.

The analysis uses aspect frequencies, sentiment frequencies, aspect–sentiment tables, charts, heatmaps and word clouds. Transactions had the highest absolute negative count (2,288); customer support had the highest negative proportion (25.17%). These are model-derived observations about the historical review sample, not verified diagnoses of current product quality.

## Limitations

- Single-app, single-source Google Play dataset; domain and time effects limit external generalization.
- Single-dominant-aspect annotation does not capture all aspects mentioned in multi-topic reviews.
- Class imbalance and small support for some joint classes reduce the joint Macro F1.
- No baseline comparison is reported in the finalized thesis; the project does not claim superiority to other architectures.
- Annotator spreadsheets, source review data and trained checkpoints are not publicly included in this package, so the workflow is not fully reproducible from the repository alone.
