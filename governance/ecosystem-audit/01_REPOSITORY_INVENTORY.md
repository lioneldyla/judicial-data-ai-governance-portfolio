# 01 — Repository Inventory

> Complete inventory of the 110 repositories under
> [github.com/lioneldyla](https://github.com/lioneldyla) as of 2026-07-07.
> Source: `GET /search/repositories?q=user:lioneldyla` (paginated, 100 + 10).

---

## A. Programme repositories (14 non-Le-Wagon)

Sorted by role in the intended architecture.

| Repo | Visibility | Default | Description | Topics | Updated |
|---|---|---|---|---|---|
| **judicial-data-ai-governance-portfolio** | public | `main` | Research portfolio on Judicial Data Governance, Digital Justice, Responsible AI and Public Sector Transformation in Africa. | — | 2026-07-07 |
| **jdgf-framework** | public | `main` | Judicial Data Governance Framework — Tools, methodology and maturity model for governing data in African judicial institutions | africa, data-governance, digital-transformation, judicial-systems, justice, public-sector, python, responsible-ai | 2026-06-23 |
| **JDGF-LAB-FRAMEWORK** | public | `codex/advanced-rag-contracts` | A modular governed framework for AI-assisted projects knowledge systems and data-governance research | ai-governance, data-governance, judicial-data, knowledge-systems, multi-agent, python, rag | 2026-06-30 |
| **living-digital-governance-platform** | public | `main` | A public governance framework for digital transformation, data governance, AI governance and digital justice. | — | 2026-06-23 |
| **judicial-statistics** | public | `main` | Data pipelines and methodology for the Judicial Statistics Yearbooks — Ministry of Justice, Côte d'Ivoire (2019 & 2023) | africa, data-analysis, judicial-statistics, justice, power-bi, public-sector, python, statistics | 2026-06-23 |
| **monitor-the-reactor** | public | `main` | Industrial anomaly detection ML pipeline — Capstone project Le Wagon Data Science & AI Batch 2149 (2025) · FastAPI · Streamlit · Docker · GCP | anomaly-detection, docker, fastapi, le-wagon, machine-learning, mlops, python, streamlit | 2026-06-23 |
| **working-papers** | public | `main` | Working Papers on Judicial Data Governance & Responsible AI — Lionel Dyla | — | 2026-06-23 |
| **cs-greffe-os** | private | `main` | *(no description)* | — | 2026-06-14 |
| **cs-greffe-os-v2** | public | `main` | *(no description)* | — | 2026-07-02 |
| **cs-greffe-os-cloud** | private | `main` | CS GREFFE OS Learn - prototype cloud e-learning | — | 2026-06-24 |
| **data-agents** | private | `main` | *(no description)* | — | 2026-06-30 |
| **lioneldyla** | public | `main` | Judicial Data & AI Governance Architect \| Data Governance · Digital Justice · Responsible AI | — | 2026-07-04 |
| **personal-branding** | public | `main` | Building an international academic and professional identity in Judicial Data Governance, Digital Justice and Responsible AI. | — | 2026-06-30 |
| **personal-archive** | private | `main` | Private digital archive, knowledge base and long-term memory for documents, research and projects. | — | 2026-07-01 |

---

## B. Sandbox / experiment (2)

| Repo | Visibility | Default | Notes |
|---|---|---|---|
| **Playground** | public | `main` | Named sandbox — matches target architecture item "Playground" |
| **blank-app-1** | public | `main` | Streamlit blank-app template; likely Le Wagon scaffold |

---

## C. Website / branding side-projects (2)

| Repo | Visibility | Default | Notes |
|---|---|---|---|
| **Leken.ci** | private | `main` | Purpose unclear — name suggests a `.ci` domain project |
| **taxifare-website** | private | `master` | Le Wagon `taxifare` MVP frontend |

---

## D. GitHub onboarding / tutorial residue (2)

| Repo | Visibility | Default | Notes |
|---|---|---|---|
| **desktop-tutorial** | private | `main` | Auto-generated GitHub Desktop onboarding |
| **skills-introduction-to-github** | public | `main` | GitHub Skills course clone; 1 open issue |

---

## E. Le Wagon Data Science bootcamp exercises — 87 repositories

All private. All created 2025-10-03 → 2025-12-29. Default branch mostly
`master`. Language distribution: Jupyter Notebook (dominant), Python,
Makefile. Naming convention: `data-<exercise-slug>`.

Full list, alphabetized:

```
data-algebra-warmup
data-analyse-and-present
data-arima
data-arima-101
data-back_to_school_query
data-batch-gradient-descent
data-calling-llm-apis
data-car-prices
data-check
data-cifar-classification
data-classify-electrocardiograms
data-context-and-setup
data-custom-transformer
data-data-preparation
data-data-structures
data-electrocardiograms
data-embeddings-with-word2vec
data-exploratory-analysis
data-fast-api
data-feature-selection
data-first-transformer
data-git
data-ham-or-spam
data-hand-made-standardizer
data-houses-kaggle-competition
data-how-to-properly-prevent-overfitting
data-image-compression
data-intuition-on-convolutions
data-join-the-tables
data-knn
data-langchain-env
data-law-of-large-numbers
data-learning-curves
data-lecture-dashboarding
data-linear-regression
data-logit
data-loss-functions
data-mnist-classification
data-model-lifecycle
data-movie-recommendation
data-movie-reviews
data-multiclass-classification
data-nlp-with-cnn
data-notebook
data-numpy
data-olist
data-olist_ceo_request
data-olist_nps
data-olist_queries
data-orders-regression
data-pickle-pipe
data-playground
data-playground-part-ii
data-predict-temperature
data-preprocessing-workflow
data-preprocessor-tuning
data-prompting-slms
data-query-the-db
data-rag-with-langchain
data-random-variables
data-real-estate-advanced-estimator
data-real-estate-estimator
data-reboot-airbnb-prices
data-reboot-travel-agency-database
data-reboot-worlds-worst-variable
data-regularization
data-rl-car-racing
data-rl-cliff-walking
data-rl-custom-env
data-rl-lunar-lander
data-seaborn-regression
data-sellers
data-sentiment-analysis-with-word2vec
data-solvers
data-stock-market-api
data-streamlit-api
data-string-manipulation
data-sum-of-three
data-svm
data-text-generation
data-threshold-adjustments
data-train-at-scale
data-train-in-the-cloud
data-transfer-learning
data-transformer-finetuning-challenge
data-tuning-pipeline
data-workflow
data-your-first-embedding
data-your-first-neural-network
data-your-first-rnn
```

Corroborating evidence that this is one bootcamp batch: `monitor-the-reactor`
description says "Le Wagon Data Science & AI Batch 2149 (2025)"; all `data-*`
repos land in the same window; naming matches Le Wagon's standard exercise
scaffolds; the `.master` default branch is Le Wagon's historical default.

---

## Totals

| Category | Public | Private | Total |
|---|---:|---:|---:|
| Programme repositories (A) | 10 | 4 | 14 |
| Sandbox (B) | 2 | 0 | 2 |
| Websites/branding (C) | 0 | 2 | 2 |
| GitHub tutorial residue (D) | 1 | 1 | 2 |
| Le Wagon exercises (E) | 0 | 87 | 87 |
| Playground data-* variants (already in E) | 0 | 3 | (in E) |
| Duplicated JDGF (already in A) | 2 | 0 | (in A) |
| **Total** | **13** | **94** | **107** |

*(Discrepancy: search reported 110. Difference is that `data-playground`,
`data-playground-part-ii`, and `data-streamlit-api` are counted once in E.
Sanity check pending against `git ls-remote --heads` on cloning.)*

---

*Inventory captured 2026-07-07. Any repo created after that date is not
reflected. Re-run inventory before executing the migration plan.*
