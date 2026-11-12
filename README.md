# Comparative Evaluation of Retrieval Strategies for RAG Systems

An independent AI research project comparing keyword-based, semantic, and hybrid retrieval approaches using BEIR benchmark datasets.

## Research Objective

To investigate whether combining lexical and semantic retrieval improves document retrieval quality in Retrieval-Augmented Generation (RAG) systems.

## Retrieval Methods

- **BM25:** Keyword-based document retrieval.
- **Dense Retrieval:** Semantic search using Sentence Transformers.
- **Hybrid Retrieval:** Reciprocal Rank Fusion (RRF) combining BM25 and dense rankings.

## Datasets

- BEIR SciFact
- BEIR NFCorpus

## Technology Stack

- Python
- Sentence Transformers
- FAISS
- BM25 / rank-bm25
- BEIR
- NumPy and Pandas
- Matplotlib

## Evaluation Metrics

- NDCG@10
- MAP@10
- Recall@10
- Precision@10

## Preliminary Experimental Results

### SciFact

| Method | NDCG@10 | MAP@10 | Recall@10 | Precision@10 |
|---|---:|---:|---:|---:|
| BM25 | 0.6519 | 0.6070 | 0.7740 | 0.0850 |
| Dense | 0.6451 | 0.5959 | 0.7833 | 0.0883 |
| Hybrid RRF | **0.6922** | **0.6405** | **0.8377** | **0.0940** |

### NFCorpus

| Method | NDCG@10 | Recall@10 | Precision@10 |
|---|---:|---:|---:|
| BM25 | 0.3061 | 0.1521 | 0.2180 |
| Dense | 0.3159 | 0.1550 | **0.2433** |
| Hybrid RRF | **0.3381** | **0.1667** | 0.2415 |

*The exact NFCorpus Hybrid MAP@10 value is pending verification.*

## Key Observation

Hybrid RRF achieved the highest NDCG@10 and Recall@10 across both evaluated benchmarks. The findings are preliminary and specific to the experimental setup.

## Project Structure

- `notebooks/` – Experimental implementation.
- `results/` – Evaluation outputs and graphs.
- `research/` – Research report and documentation.

## Future Work

- Independent held-out validation.
- Additional embedding model comparisons.
- Hybrid retrieval optimization.
- Statistical significance testing.
- End-to-end RAG answer evaluation.

## Reproducibility

Experiments were implemented in Google Colab. See the notebook for implementation details and execution instructions.

## Research Status

Independent experimental research project. Not peer-reviewed or published.
