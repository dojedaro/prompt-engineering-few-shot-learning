# 🧠 Prompt Engineering for Few-Shot Learning (LLM Evaluation)

This project explores and evaluates **prompt engineering strategies**—**zero-shot**, **one-shot**, and **few-shot prompting**—using large language models on a **medical question-answering (QA)** dataset.

Rather than optimizing for peak model performance, the goal of this project is to demonstrate **systematic experiment design, evaluation methodology, and analytical reasoning** when working with LLMs.

---

## 🎯 Project Objectives

- Compare **zero-shot, one-shot, and few-shot prompting** strategies
- Evaluate performance across **two LLM configurations** (GPT-4-class and GPT-3.5-class)
- Measure output quality using:
  - String similarity metrics
  - Exact match scoring
- Analyze strengths, weaknesses, and trade-offs of each approach

---

## 🧪 Dataset

- **Source:** Hugging Face `bigbio/med_qa`
- **Domain:** Medical question answering
- **Format:** Question–answer pairs
- A small subset is sampled to control **cost and latency** during evaluation

---

## 🏗️ Methodology

### Prompting Strategies
- **Zero-shot:** Model answers without examples  
- **One-shot:** Model is shown one example Q&A  
- **Few-shot:** Model is given multiple example Q&A pairs  

### Evaluation Pipeline
- Structured prompt construction per strategy
- Controlled sampling of test questions
- Automatic retries with exponential backoff
- Logging for transparency and reproducibility
- Results saved to JSON for post-analysis

---

## 📊 Evaluation Metrics

**Similarity Score**  
Uses `difflib.SequenceMatcher` to measure textual similarity between model output and ground-truth answers.

**Exact Match Rate**  
Binary indicator of whether the correct answer appears in the model output.

**Aggregated Analysis**
- Average similarity
- Standard deviation
- Exact match rates by model and prompting strategy

---

## 📈 Analysis & Visualization

The project includes scripts to:

- Load and analyze raw evaluation results
- Generate comparative plots:
  - Average similarity by model and strategy
  - Exact match rates
  - Distribution of similarity scores
  - Heatmap comparisons
- Export summary statistics to CSV

Visualizations are saved locally for inspection and reporting.

---

## 🔐 API Key Handling (Intentional Design)

This repository **does not include any real API keys**.

The code contains a placeholder:

```python
api_key = "XXXXXXXXXXXXXXXXXXXXXXXX"

