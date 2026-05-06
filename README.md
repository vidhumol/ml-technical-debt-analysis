# An Empirical Analysis of Technical Debt in Open-Source Machine Learning Repositories

![Status](https://img.shields.io/badge/Status-In%20Progress-blue)
![Language](https://img.shields.io/badge/Language-Python-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

## Author
| Field | Details |
|-------|---------|
| **Name** | Vidhumol Pandippilly Antony |
| **Student Code** | ST86889 |
| **Programme** | Master of Natural Sciences in Computer Science |
| **Institution** | Transport and Telecommunication Institute, Riga, Latvia |
| **Supervisor** | Dr.sc.ing. Boriss Misnevs |
| **Year** | 2026 |

---

## Research Questions
- **RQ1:** What is the prevalence of technical debt in open-source ML repositories?
- **RQ2:** What types of technical debt are most commonly observed?
- **RQ3:** How does technical debt evolve over time relative to development activity?
- **RQ4:** Can ML techniques automate technical debt detection?

---

## Repository Structure

ml-technical-debt-analysis/
├── notebooks/
│   ├── 01_repo_collection.ipynb
│   ├── 02_satd_extraction.ipynb
│   ├── 03_static_analysis.ipynb
│   ├── 04_commit_history.ipynb
│   └── 05_ml_classifier.ipynb
├── scripts/
│   ├── collect_repos.py
│   ├── satd_extractor.py
│   ├── static_analyzer.py
│   └── utils.py
├── data/
│   ├── raw/
│   ├── processed/
│   └── results/
├── analysis/
│   ├── figures/
│   └── stats/
├── docs/
│   └── methodology.md
└── requirements.txt

---

## 🛠️ Technologies Used
- Python 3.10+
- PyDriller, PyGithub
- pylint, radon, flake8, vulture
- scikit-learn, HuggingFace Transformers
- pandas, matplotlib, seaborn

---

## How to Reproduce
```bash
git clone https://github.com/vidhumol/ml-technical-debt-analysis
pip install -r requirements.txt
# Run notebooks in order: 01 → 02 → 03 → 04 → 05
```

---

## sample of Repositories Analysed
20 open-source ML repositories across 5 categories:
Deep Learning, NLP, Computer Vision, MLOps, AutoML/RL

---

## Current Progress
- [x] Repository created
- [x] Methodology defined
- [ ] Data collection (In Progress)
- [ ] Static analysis
- [ ] ML classifier
- [ ] Thesis writing
