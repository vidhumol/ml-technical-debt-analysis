# An Empirical Analysis of Technical Debt in Open-Source Machine Learning Repositories

Master's Thesis — Transport and Telecommunication Institute, Riga, Latvia, 2026

---

## Author

| Field | Details |
|---|---|
| Name | Vidhumol Pandippilly Antony |
| Student Code | ST86889 |
| Programme | Master of Natural Sciences in Computer Science |
| Institution | Transport and Telecommunication Institute, Riga, Latvia |
| Supervisor | Dr. sc. ing. Boriss Misnevs |
| Year | 2026 |

---

## About This Study

This thesis presents a multi-modal empirical analysis of Self-Admitted Technical Debt (SATD) across 526 open-source machine learning repositories. The study examines how technical debt manifests differently across five ML sub-categories — Deep Learning, NLP, Computer Vision, MLOps, and AutoML/RL — and compares these against a non-ML control group.

The analysis goes beyond Python source files to include YAML configurations, Jupyter notebooks, Dockerfiles, and CI/CD pipelines. An LLM-based semantic classifier (Llama 3.1 via Groq API) was used to categorize and score the severity of each debt comment, achieving a 0% false positive rate compared to 44% for prior keyword-based approaches.

---

## Research Questions

| RQ | Question | Finding |
|---|---|---|
| RQ1 | Are there statistically significant SATD volume differences across ML sub-categories? | Yes — Kruskal-Wallis H = 25.26, p = 0.000045 |
| RQ2 | Are there new debt types unique to MLOps and LLM repositories? | Yes — 6 novel categories and 2 unnamed clusters identified |
| RQ3 | Does Python-only analysis underestimate total ML debt? | Yes — 4.1% underestimation confirmed (up to 6.2% for Deep Learning) |
| RQ4 | Does a composite model outperform single-signal debt prediction? | Yes — Random Forest 90.4% vs Logistic Regression 73.1% |
| RQ5 | Do ML-specific debt patterns differ from traditional software? | Yes — Chi-Square = 1204.66, p = 1.72e-250 |

---

## Dataset

526 open-source repositories across 6 categories:

| Category | Count | Examples |
|---|---|---|
| Deep Learning | 112 | tensorflow, pytorch, vllm, llama.cpp |
| NLP | 94 | langchain, llama_index, autogen |
| Computer Vision | 78 | yolov5, segment-anything, ComfyUI |
| MLOps | 87 | mlflow, wandb, dagster, airflow |
| AutoML / RL | 75 | optuna, gymnasium, LightGBM |
| Non-ML Control | 80 | flask, django, pytest, ruff |
| **Total** | **526** | |

---

## Repository Structure

```
ml-technical-debt-analysis/
├── notebooks/
│   ├── NB01_repo_collection.ipynb
│   ├── NB02_satd_extraction.ipynb
│   ├── NB03_static_analysis.ipynb
│   ├── NB04_commit_history.ipynb
│   ├── NB05_ml_classifier.ipynb
│   ├── NB06_llm_classifier.ipynb
│   ├── NB07_kmeans_clustering.ipynb
│   ├── NB08_multi_file_scan.ipynb
│   ├── NB09_statistical_validation.ipynb
│   ├── NB10_scale_526_repos.ipynb
│   ├── NB11_replicate_pipeline.ipynb
│   └── NB12_full_validation.ipynb
├── data/
│   ├── master_dataset.csv
│   ├── llm_classified_results.csv
│   ├── cluster_results.csv
│   └── repo_metadata.csv
├── analysis/
│   └── figures/
├── presentation/
│   ├── defence_presentation.pdf
│   └── defence_poster.pdf
├── docs/
├── .gitignore
├── LICENSE
├── repo_metadata.csv
└── README.md
```

---

## Technologies Used

- Python 3.10+
- PyDriller, PyGithub — repository mining
- Flake8, Radon, Pylint, Vulture — static analysis
- Llama 3.1 via Groq API — LLM-based SATD classification
- Scikit-learn — Random Forest and Logistic Regression classifiers
- K-means clustering with TF-IDF features — unsupervised debt pattern discovery
- Pandas, Matplotlib, Seaborn — data processing and visualisation
- SciPy — Kruskal-Wallis, Chi-Square, Dunn post-hoc, Spearman correlation

---

## Key Findings

**SATD Volume:** MLOps is the structural outlier with a bimodal distribution — many zero-SATD repos alongside high-count orchestration tools like Airflow and Prefect.

**Novel Debt Types Discovered:**
- Experiment Tracking Debt — deferred metric logging in MLflow and W&B
- Prompt Template Debt — hardcoded prompts in LangChain and LlamaIndex
- Data Versioning Debt — missing dataset lineage in DVC and Feast
- Monitoring and Observability Debt — missing drift-detection thresholds
- Token Budget Debt — unmanaged context window costs in LLM repositories
- Import Suppression Debt — NOQA-based linting bypasses (novel keyword, first in SATD literature)

**Python-Only Underestimation:** Prior studies that scan only Python files underestimate total SATD by at least 4.1%. Documentation and CI/CD debt are entirely invisible without multi-artifact scanning.

**SDLC Phase:** 93% of all SATD accumulates in the Model Development phase (P3). CI/CD and Documentation debt only become visible through multi-file scanning.

**Classifier:** Llama 3.1 achieved a 0% false positive rate versus 44% for prior NLP-based detectors. Random Forest using composite signals achieved 90.4% accuracy versus 73.1% for Logistic Regression.

---

## How to Reproduce

```bash
git clone https://github.com/vidhumol/ml-technical-debt-analysis
cd ml-technical-debt-analysis
pip install -r requirements.txt
```

Run the notebooks in order from NB01 through NB12. Each notebook builds on the outputs of the previous one. Processed CSV files are included in the `data/` folder so individual notebooks can be run independently.

A Groq API key is required for NB06 (LLM classifier). A GitHub personal access token is required for NB01 (repository collection).

---

## Presentation Materials

The defence presentation and thesis poster are available in the `presentation/` folder:

- `presentation/defence_presentation.pdf` — Master's defence slides (June 2026)
- `presentation/defence_poster.pdf` — Research poster

---

## Statistical Validation Summary

| Test | Statistic | p-value | Conclusion |
|---|---|---|---|
| Kruskal-Wallis | H = 25.26 | 0.000045 | SATD volume differs across ML sub-categories |
| Chi-Square | 1204.66 | 1.72e-250 | Debt type distribution is domain-specific |
| Spearman (SATD vs Commits) | 0.369 | < 0.0001 | Commit churn is the strongest debt predictor |
| Spearman (SATD vs Age) | 0.054 | 0.213 | Repository age does not predict debt |

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

## Contact

Vidhumol Pandippilly Antony
vidhumol04@gmail.com
Transport and Telecommunication Institute, Riga, Latvia
