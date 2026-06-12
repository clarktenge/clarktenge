# Hi, I'm Clark Enge

I make AI useful. I take state-of-the-art models and tools and weigh the tradeoffs/costs, wire the pieces together, and turn the output into something people can actually act on.

Quantitative foundation in statistics & data science from **UC Santa Barbara**, ISR research at the **Air Force Research Laboratory**, and a multi-agent automation system I run on my own life.

📄 **[Resume](https://github.com/clarktenge/clarktenge-documents/blob/main/Clark%20Enge%20-%20Resume.pdf)** · 💼 **[LinkedIn](https://www.linkedin.com/in/clark-enge-5a0775179/)** · 📬 **[clarkenge23@gmail.com](mailto:clarkenge23@gmail.com)**

---
## What I'm doing now

### ML Research Intern - Air Force Research Laboratory (AFRL) - Summer 2026
Studying the reality gap between synthetic and real-world multispectral satellite imagery for intelligence, surveillance, and reconnaissance. I characterize both datasets, build domain-alignment metrics to quantify the gap, and benchmark how different blends of real and synthetic training data affect model performance, then turn the findings into practical recommendations for using synthetic data in operational ML pipelines.


## What I do
**Applied ML** · **AI integration & orchestration** · **Model Eval & Tradeoffs** · **Time-Series Modeling** · **Statistical Analysis** · **Turn Data into Decisions** · **Agentic Design**


## Tech Stack
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![R](https://img.shields.io/badge/r-%23276DC3.svg?style=for-the-badge&logo=r&logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white)
![Agentic AI](https://img.shields.io/badge/Agentic%20AI-%236B21A8.svg?style=for-the-badge&logoColor=white)

---

## Projects

### [Swiss Guard](https://github.com/clarktenge/swiss_guard) · *In Progress*

A personal multi-agent intelligence OS for automation of daily tasks. five specialized AI agents that run on a schedule, surface what matters, and report into a unified dashboard. Built to explore agent architecture, persistent memory, and production deployment patterns.

- **Multi-agent orchestration via n8n** — agents run on independent cron schedules with dependency resolution (email digest waits on triage completion before executing)
- **Persistent semantic memory** using Supabase (Postgres + pgvector) and Voyage AI embeddings — agents retrieve contextually relevant prior outputs before each run, enabling continuity across sessions
- **Governance layer** classifies every agent output as READ_ONLY, DRAFT, or ACTION before surfacing to dashboard — explicit human-in-the-loop design for any autonomous action
- **Covers five domains**: email triage & deep summarization (ISW, research papers, opportunities), end-of-day market reports with portfolio P&L, daily health sync from Strava and Garmin, and weekly productivity wrap
- Stack: Python · Anthropic SDK · n8n · Supabase · pgvector · Voyage AI · Retool → React

---

### [Continuous Quantum Error Correction with ML Decoders](https://github.com/clarktenge/cqec-ml-decoder) · *Co-authored with Pranav Reddy*

Built and benchmarked a GRU recurrent neural network decoder for continuous quantum error correction — a problem structurally identical to neural signal decoding: noisy real-valued time-series → classify hidden system state.

- **GRU achieved 96% accuracy** vs. 94% Bayesian filter and 86% threshold baseline under clean conditions
- Tested across **4 phases of increasing hardware realism**: colored noise (AR(1)), post-flip transients, random-walk parameter drift, and time-varying non-idealities — directly modeling real hardware failure modes
- Bayesian filter degrades sharply when its white-noise and static-parameter assumptions are violated; GRU adapts
- Developed **hybrid supervision strategy** (periodic ground-truth labels + pseudo-label self-training) to maintain decoder accuracy under distribution shift with <2% annotation overhead
- **248 unit tests** across 5 modules; trajectory-level train/test split to prevent data leakage
- Stack: Python · PyTorch · NumPy · SciPy · scikit-learn · QuTiP

---

### [EEG Sleep Alpha Power Forecasting · ARMA & Spectral Analysis](https://github.com/clarktenge/eeg-sleep-sarima)
Modeling EEG alpha band power (8–13 Hz) as a time series across human sleep cycles using a hand-built ARMA pipeline — framed around the neural state estimation problem faced by adaptive brain-computer interfaces.
- Extracting a **~2650-epoch univariate series** from a PhysioNet Sleep-EDF overnight recording via per-epoch band-pass filtering and Welch power estimation
- Applying a **log transform** to stabilise multiplicative variance; rejecting seasonal differencing (it increases variance and has no ACF/PACF signature); selecting **ARMA(2,0,1)** on the log level via hand-coded AICc and MA root diagnostics confirming d=0
- Conducting **spectral analysis** via periodogram and Fisher's g-test to identify the ultradian band (~66–95 min) and explain why no single seasonal lag could capture it; confirming residual spectral whiteness with a KS cumulative-periodogram test
- Reporting **1-step-ahead forecasts** (19.6% MAPE) back-transformed with log-normal bias correction, beating persistence and naive-seasonal baselines; McLeod-Li test identifies residual ARCH structure as the direction for future GARCH work
- Stack: Python · MNE · SciPy · NumPy · statsmodels · Matplotlib

---

### [TMDB Movie & TV Recommender System](https://github.com/clarktenge/movie-recommender)
- Content-based recommendation engine across ~9,900 titles using TF-IDF vectorization and cosine similarity on weighted metadata (genres 3×, cast 2×, keywords 2×)
- Tuned a blended ranking score (text similarity 0.95 · popularity 0.03 · vote average 0.02) to surface thematically relevant results over popular-but-unrelated ones
- Stack: Python · Pandas · scikit-learn · NLTK · TMDB API

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

## Independent Work

**[Coursera IBM Data Science Professional Certificate](https://www.coursera.org/professional-certificates/ibm-data-science)** 
12-course program covering ML modeling, SQL, data visualization, and end-to-end data science workflows.

**[SQL Essential Training](https://www.linkedin.com/in/clark-enge-5a0775179/)** — Joins, subqueries, window functions, stored procedures in MySQL and SQL Server.
