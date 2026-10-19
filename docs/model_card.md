# Research model card: conditional ABSA for Indodax reviews

**Task:** Indonesian-language aspect classification and conditional sentiment classification of crypto-exchange app reviews.

**Model family:** IndoBERT (`indobenchmark/indobert-base-p1`) contextual encoder plus BiLSTM and task-specific classification heads. Separate models perform (1) five-class dominant-aspect classification and (2) three-class sentiment prediction for relevant aspects.

**Data:** 80,000 initially collected Google Play reviews; 68,204 after cleaning. An independently annotated sample of 8,000 reviews from three annotators yielded 7,775 final labeled reviews after review/voting steps. Held-out test set: 1,552.

**Reported metrics:** Aspect 93.62% accuracy, 90.19% Macro F1. Sentiment with reference aspect 93.22% accuracy, 86.26% Macro F1. Conditional sentiment with predicted aspect 93.43% accuracy, 86.55% Macro F1, with 98.82% coverage. Joint 13-class ABSA 89.43% accuracy, 77.71% Macro F1.

**Intended use:** Research and exploratory analysis of historical user reviews by service aspect. Useful for identifying *patterns of feedback* and priorities to investigate.

**Not intended for:** Live financial, trading, credit or account-security decisions; diagnoses of service incidents; automatic customer complaint adjudication; claims about current Indodax performance; deployment without validation.

**Important caveats:** Single app and source; date/domain shift possible; dominant-aspect-only task; class imbalance; lower joint Macro F1. Evaluations are taken from thesis results, **not independently rerun** for this repository.

**Weights and training data:** Not distributed in this repository.
