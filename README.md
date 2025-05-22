# The-Impact-of-Romanian-Dialects-on-Language-Models
LLM and cognition

# The Impact of Romanian Dialects on Language Models

This project investigates how Romanian dialectal variation affects the performance of large language models (LLMs). We analyze and compare the effectiveness of multiple Romanian-focused models across texts sourced from newspapers across Romania, Moldova, and the Romanian diaspora.

## 📌 Objectives

- Evaluate the ability of LLMs to distinguish and adapt to regional Romanian dialects.
- Use both statistical and machine learning methods for dialect classification.
- Measure model perplexity across dialect regions to understand linguistic influence.
- Provide a cleaned, labeled dataset of Romanian dialectal newspaper articles.

## 🧠 Models Evaluated

- **RoBERT** – Romanian-specific BERT model trained on diverse corpora.
- **RoLLaMA** – LLaMA 2 fine-tuned on Romanian translated data.
- **RoQLLaMA** – Lightweight Romanian-adapted LLaMA 2 model.

## 🗂️ Dataset

Collected from over 30 regions (Romania, Moldova, diaspora) using custom scraping and preprocessing pipelines. Data was cleaned using `goose3` and structured in JSON format with:

- `title` — News article title
- `content` — Cleaned article text
- `metadata` — Source HTML file name

> Total examples: **31,570**

## 🧪 Methods

### Random Forest Classifier
- Trained on both full articles and single sentences.
- Stopwords-only experiments to highlight dialect-specific syntactic patterns.
- Two vectorization methods used: **TF-IDF** and **Word2Vec**.

### Perplexity Analysis
- Applied on each model to measure uncertainty across regions.
- Analyzed both article content and titles.
- Higher perplexity suggests linguistic divergence from training distribution.

## 📊 Results Summary

| Method         | Best F1 Score | Notes                                      |
|----------------|---------------|--------------------------------------------|
| TF-IDF + RF    | **0.819**     | Strong dialect separation via stopwords    |
| Word2Vec + RF  | 0.559         | Lower performance; embeddings less useful  |
| RoBERT         | Low Perplexity| Most stable across all regions             |
| RoLLaMA        | ~5.4 PPL avg  | Some regional variation                    |
| RoQLLaMA       | ~7.2 PPL avg  | Higher and less stable perplexity          |

## 📈 Linguistic Statistics

Calculated per region:
- Vocabulary size
- Type-Token Ratio
- Avg. word/sentence length
- Words per sentence

These metrics help assess lexical richness and syntactic complexity.

## ⚠️ Ethical Use

This dataset and analysis are strictly intended for:
- Improving dialectal robustness in NLP tools
- Understanding linguistic variation
- Educational and research purposes

**Do not** use this data to create or support discriminatory systems.

## 📚 References

Key related works include:
- [Butnaru & Ionescu, 2019] Moroco dialect dataset
- [Dumitrescu et al., 2021] RoBERT
- [Masala et al., 2024] RoLLaMA
- [Dima et al., 2024] RoQLLaMA

Full bibliography available in the PDF report.

## 👨‍💻 Authors

- [Florin-Silviu Dinu](mailto:florin-silviu.dinu@s.unibuc.ro)
- [Andrei-Virgil Ilie](mailto:andrei-virgil.ilie@s.unibuc.ro)
- [Mihai Dilirici](mailto:mihai.dilirici@s.unibuc.ro)

---

Feel free to explore the code, review the findings, and contribute to improving dialect-aware language models.
