# Reproduction and data availability

## Important: this is a research showcase, not a one-click runnable repository

The four original notebooks depend on files saved to Google Drive across earlier phases. The attached source files did **not** include the Excel datasets, final annotated workbooks or trained model `.pt` checkpoints. For this reason the repository preserves the experimental code and sampled charts but cannot reproduce the results without the missing artifacts.

## Expected workflow and required inputs

1. **Phase 1:** create/upload `indodax_reviews.xlsx` (the original study's raw-review export) and configure `RAW_DATA_PATH`/`PROJECT_DIR`. This notebook reads an exported Excel file; it does not include the original crawling script.
2. **Phase 2:** use the outputs of Phase 1 and place the three manually filled annotation spreadsheets in the expected `annotator_results/` directory; run data checks, voting and partitioning.
3. **Phase 3:** use cleaned and labeled data from earlier phases; train models on a compatible Colab environment, generating model weights and evaluation artifacts under `03_model_training_evaluation/`.
4. **Phase 4:** restore the model checkpoints and reports from Phase 3 and the Phase 1/2 datasets, then run full-corpus inference and export figures.

The original project structure references a Google Drive directory named `ABSA_Indodax_Pipeline_V5_4_4Fase` and uses subfolders `01_data_preparation/`, `02_annotation_processing/`, `03_model_training_evaluation/`, and `04_corpus_analysis_bab4/`. Edit configuration variables before use if your Drive is organized differently. **Phase 4 validates checkpoint provenance and may reject artifacts produced by different pipeline versions.**

## Environment notes

The notebooks use IPython `%pip` or `!pip` cells, Google Colab mounting, and Colab-provided PyTorch/CUDA. For Colab runs, execute notebook setup cells first and confirm Python, GPU, PyTorch, Transformers and other library versions. `requirements.txt` is informative rather than a guaranteed complete environment lockfile.

## Data and privacy

- Raw Google Play reviews and annotator files have **not** been bundled here.
- Do not publish account identifiers, raw reviewer metadata, annotator identities or access credentials without appropriate rights and privacy review.
- Check any university / supervisor permission or publication restrictions before posting the complete thesis.
- Trained model checkpoints can be large and may be inappropriate for a source-code repository; consider a separate artifact host **only with appropriate permissions**.

## Changes from original attached notebooks

To prepare a cleaner public source package, raw execution logs, data previews, most stored outputs, and run counts were removed. A handful of aggregated chart outputs were preserved in Phases 3–4, and the exported research figures are included in `docs/figures/`. An unrelated post-Phase-3 diagnostic cell mistakenly appearing before Phase 2 initialization was removed. One non-functional Phase 3 markdown heading was renamed for clarity. Core substantive Phase 1–4 logic was otherwise retained. **No notebooks were retrained or re-executed for this packaging.**
