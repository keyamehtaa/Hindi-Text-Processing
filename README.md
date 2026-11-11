# Hindi Text Processing and Translation Pipeline

## Project Overview

This project implements a Hindi text-processing pipeline to process seven raw Hindi text files containing shuffled and unpunctuated text.

The pipeline performs:
1. Punctuation restoration.
2. Sentence segmentation.
3. Semantic similarity analysis and candidate sentence grouping.
4. Hindi-to-English machine translation.
5. Export of processed sentences and bilingual groups.

## Models Used

This project uses pretrained models. No models were trained or fine-tuned from scratch.

| Task | Model |
|---|---|
| Punctuation restoration | `Horizon-Labs/punctuation-restoration-small` |
| Sentence embeddings | `sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2` |
| Hindi-to-English translation | `facebook/nllb-200-distilled-600M` |

The pretrained models are downloaded from Hugging Face when required. No custom model weights are included because no model was trained.

## Methodology

- Original Hindi text files are extracted and processed independently.
- Punctuation is restored using a pretrained model.
- Text is divided into sentence-level segments while preserving NULL markers.
- Multilingual sentence embeddings are generated to calculate semantic similarity.
- Similar sentences are grouped into candidate groups, with a maximum group size of five.
- NLLB-200 is used to translate Hindi sentences into English.
- Results are exported as CSV files.

**Note:** Semantic grouping represents candidate relationships and does not guarantee recovery of the exact original sentence order. Machine-generated translations may contain errors.

## Repository Contents

- `Hindi_text_processing_NLP_task (1).ipynb` – Complete implementation.
- `Hindi_Text_Processing_Outputs (1).zip` – Processed results and output files.
- `candidate_groups.csv` – Semantic candidate groups.
- `final_bilingual_groups.csv` – Hindi and English grouped results.
- `sentence_translations.csv` – Sentence-level translations.

## Model Weights

No custom models were trained or fine-tuned in this project. Therefore, there are no custom model weights to upload. The pretrained models are downloaded from Hugging Face during execution.

## Execution

The notebook is designed to run in Google Colab using a CPU environment. Upload the original dataset ZIP when prompted and execute the notebook cells in order.

## Links

- **GitHub Repository:** https://github.com/keyamehtaa/Hindi-Text-Processing
- **Google Drive Model Weights:** Not applicable; no custom models were trained.

## Limitations

- Sentence grouping is based on semantic similarity and is not guaranteed to reproduce the original order.
- Translation quality depends on the pretrained translation model.
- Some Hindi idioms, names, and contextual expressions may not translate accurately.
- No manually verified English reference translations were available for quantitative translation evaluation.
