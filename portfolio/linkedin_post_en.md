I recently completed an NLP research project focused on a question that overall sentiment scores often miss: **what exactly are users happy or unhappy about?**

For my undergraduate thesis, I built a hybrid **IndoBERT–BiLSTM** pipeline for Aspect-Based Sentiment Analysis (ABSA) of Indonesian-language Google Play reviews of Indodax.

The workflow covered:
- 80,000 collected reviews, reduced to 68,204 after preprocessing
- 8,000 samples annotated by three annotators, with agreement assessment and majority voting
- Group-aware dataset preparation, model training, and test-set evaluation
- Full-corpus inference and aspect-level sentiment analysis

**Test-set results:**
- Aspect classification: **90.19% Macro F1** (93.62% accuracy)
- Sentiment with reference aspect: **86.26% Macro F1**
- End-to-end joint aspect–sentiment evaluation: **77.71% Macro F1**

Beyond the scores, the most interesting outcome was being able to distinguish issues related to the interface, security, transactions, and customer support. The analysis found that transaction-related feedback had the highest absolute number of negative reviews, while customer support had the highest negative share in the corpus.

The repository includes the research pipeline, methodological notes, evaluation figures, and limitations. The raw datasets and model weights are not public.

GitHub: [PASTE YOUR REPOSITORY URL HERE]

#NaturalLanguageProcessing #MachineLearning #DataScience #IndoBERT #DeepLearning
