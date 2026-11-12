# Comparative Evaluation of Keyword, Semantic, and Hybrid Retrieval Strategies for RAG Systems

An independent benchmark-based experimental study comparing lexical, semantic, and hybrid document retrieval approaches using BEIR datasets.

## Research Overview

Retrieval-Augmented Generation (RAG) systems depend on retrieving relevant information before generating answers. This project investigates whether combining keyword-based and semantic retrieval improves document retrieval quality.

**Research Question:** Does combining BM25 and dense semantic retrieval improve retrieval performance compared with using either method independently?

## Research Objectives

- Implement keyword-based retrieval using BM25.
- Implement semantic retrieval using Sentence Transformers.
- Develop a hybrid retrieval approach using Reciprocal Rank Fusion (RRF).
- Evaluate retrieval performance using standard information retrieval metrics.
- Compare results across two BEIR benchmark datasets.

## Retrieval Methods

| Method | Description |
|---|---|
| BM25 | Keyword-based lexical retrieval |
| Dense Retrieval | Semantic search using sentence embeddings |
| Hybrid RRF | Combines BM25 and dense rankings using Reciprocal Rank Fusion |

## Datasets

Experiments were conducted using two BEIR benchmark datasets:

1. **SciFact:** Scientific claim verification retrieval dataset.
2. **NFCorpus:** Biomedical and nutrition-related information retrieval dataset.

## Technology Stack

- **Programming Language:** Python
- **Environment:** Google Colab
- **Libraries:** BEIR, Rank-BM25, Sentence Transformers, FAISS, NumPy, Pandas, Matplotlib
- **Embedding Model:** all-MiniLM-L6-v2
- **Ranking Technique:** Reciprocal Rank Fusion (RRF)

## Evaluation Metrics

- **NDCG@10:** Measures ranking quality.
- **MAP@10:** Measures average precision across the top 10 results.
- **Recall@10:** Measures how many relevant documents were retrieved.
- **Precision@10:** Measures how many retrieved documents were relevant.

## Experimental Results

### 1. SciFact Results

| Method | NDCG@10 | MAP@10 | Recall@10 | Precision@10 |
|---|---:|---:|---:|---:|
| BM25 | 0.65189 | 0.60697 | 0.77400 | 0.08500 |
| Dense | 0.64508 | 0.59593 | 0.78333 | 0.08833 |
| Hybrid RRF | **0.69217** | **0.64052** | **0.83767** | **0.09400** |

**Observation:** Hybrid RRF achieved the highest scores across all four reported metrics on SciFact.

![SciFact Comparison](scifact_comparison.png)

### 2. NFCorpus Results

| Method | NDCG@10 | MAP@10 | Recall@10 | Precision@10 |
|---|---:|---:|---:|---:|
| BM25 | 0.30610 | 0.11618 | 0.15214 | 0.21796 |
| Dense | 0.31594 | 0.11048 | 0.15499 | **0.24334** |
| Hybrid RRF 50:50 | **0.33812** | **0.12981** | **0.16667** | 0.24149 |

**Observation:** Hybrid RRF achieved the highest NDCG@10, MAP@10, and Recall@10. Dense retrieval achieved the highest Precision@10.

![NFCorpus Comparison](nfcorpus_comparison.png)

## Weighted RRF Experiment

Three BM25 and dense retrieval weight combinations were explored on SciFact.

| BM25 Weight | Dense Weight | NDCG@10 | MAP@10 | Recall@10 | Precision@10 |
|---:|---:|---:|---:|---:|---
