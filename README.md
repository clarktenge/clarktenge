# Hi, I'm Clark Enge

I build ML systems for **noisy, time-series data** — from recurrent neural network decoders on simulated quantum hardware to large-scale statistical pipelines. Currently a Statistics & Data Science student at UC Santa Barbara, with a focus on the mathematical foundations of machine learning and signal-driven modeling.

📄 **[Resume](https://github.com/clarktenge/clarktenge-documents/blob/main/Clark%20Enge%20-%20Resume.pdf)** · 💼 **[LinkedIn](https://www.linkedin.com/in/clark-enge-5a0775179/)** · 📬 **[clarkenge23@gmail.com](mailto:clarkenge23@gmail.com)**

---

## Tech Stack

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)
![R](https://img.shields.io/badge/r-%23276DC3.svg?style=for-the-badge&logo=r&logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white)

**Signal Processing · Time-Series Modeling · Recurrent Neural Networks · Bayesian Inference · Statistical Simulation**

---

## Projects

### [Continuous Quantum Error Correction with ML Decoders](https://github.com/clarktenge/cqec-ml-decoder) · *Co-authored with Pranav Reddy*

Built and benchmarked a GRU recurrent neural network decoder for continuous quantum error correction — a problem structurally identical to neural signal decoding: noisy real-valued time-series → classify hidden system state.

- **GRU achieved 96% accuracy** vs. 94% Bayesian filter and 86% threshold baseline under clean conditions
- Tested across **4 phases of increasing hardware realism**: colored noise (AR(1)), post-flip transients, random-walk parameter drift, and time-varying non-idealities — directly modeling real hardware failure modes
- Bayesian filter degrades sharply when its white-noise and static-parameter assumptions are violated; GRU adapts
- Developed **hybrid supervision strategy** (periodic ground-truth labels + pseudo-label self-training) to maintain decoder accuracy under distribution shift with <2% annotation overhead
- **248 unit tests** across 5 modules; trajectory-level train/test split to prevent data leakage
- Stack: Python · PyTorch · NumPy · SciPy · scikit-learn · QuTiP

---

### [Airbnb Los Angeles Real Estate Revenue Analysis](https://github.com/clarktenge/AirbnbLARealEstateRevenueAnalysis)

- Processed and analyzed **1.2M+ rows** of listing and calendar data via Parquet-based ETL pipelines
- Modeled neighborhood revenue drivers with OLS regression (interaction terms) and decision trees
- Identified high-performing bedroom–bathroom configurations that outperform local and citywide benchmarks
- Stack: Python · Pandas · scikit-learn · Matplotlib

---

### [Outlier-Resistant A/B Test Simulation Study](https://github.com/clarktenge/AB-Simulation-Study)

- Simulated **1M+ experiments** across 100 scenarios in R to stress-test A/B testing methods under outliers
- Compared standard t-test, Welch's t-test, and 10% trimmed mean t-test across effect sizes and sample sizes
- Found trimmed and Welch tests outperform under skewed, heavy-tailed distributions — with paired t-test validation
- Stack: R · ggplot2

---

### [March Madness Bayesian Predictor](https://github.com/clarktenge/March-Madness-Bayesian-Predictor)

- Analyzed **20+ years** of NCAA tournament data via SQL to weight predictive metrics (3PT%, FT%, PPG)
- Achieved **25% Final Four accuracy** in 2017 and 2018, outperforming baseline models by 15%+
- Stack: Python · NumPy · Pandas · SQL

---

### [TMDB Movie & TV Recommender System](https://github.com/jaydengould/Movie-TV-Show-Recommender) *(In Progress)*

- Content-based recommendation engine across 5,000–10,000 titles using TF-IDF on overview text combined with structured feature similarity
- Investigating cross-genre recommendation patterns vs. within-genre clustering
- Stack: Python · Pandas · scikit-learn

---

## Independent Work

**[Coursera IBM Data Science Professional Certificate](https://www.coursera.org/professional-certificates/ibm-data-science)** *(In Progress)*
12-course program covering ML modeling, SQL, data visualization, and end-to-end data science workflows.

**[SQL Essential Training](https://www.linkedin.com/in/clark-enge-5a0775179/)** — Joins, subqueries, window functions, stored procedures in MySQL and SQL Server.
