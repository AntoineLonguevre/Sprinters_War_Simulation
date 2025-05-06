# 🏁 Sprinters' War – Predictive Modeling for a Simulated Sprint League

This repository contains the scraping, modeling, and simulation tools for **Sprinters' War**, a fictional 100m sprint league featuring the world’s fastest athletes competing in a head-to-head championship format.

Inspired by Formula 1 and modern entertainment-focused sports formats, the league is structured as a **round-robin competition**, where each sprinter faces all others over multiple race nights. The project leverages real historical data to simulate race outcomes and athlete progression across a full season.

---

## 📦 Project Structure

```
Sprinters_War_Simulation/
│
├── data/              # Raw and processed data (athlete profiles, features)
│   ├── top_16_full.csv       # Enriched features for the top 16 sprinters
│   └── top_16_race.csv       # All scraped 100m race results for the top 16 athletes
│
├── figures/           # Visualizations and model output charts
│
├── notebook/          # Jupyter notebooks for scraping and modeling
│   ├── scraping_top_16_sprinters.ipynb    # Web scraping logic for athlete profiles and race histories
│   └── prediction_Sprinters_War_2025.ipynb # Modeling and simulation notebook for the championship
│
└── README.md          # Project documentation
```

# 🧠 Project Context

**Sprinters’ War** is a fictional sprint league, but built entirely on real-world performance data scraped from World Athletics. It serves as a sandbox to:

- Develop and test predictive models in elite track & field contexts  
- Simulate dynamic championship progressions  
- Integrate data storytelling into sprint competition formats  

In this championship, 16 sprinters face each other across multiple match days. Each race night, every athlete runs **twice**. Rankings are based on:

- **Duel victories** (1v1 head-to-head)  
- **Bonus points** for top performances (e.g., best times of the night)

---

# 🔍 Notebook Overview

### Phase 1 – Scraping the Top 16 Sprinters

- Scrapes the World Athletics 100m ranking page for the 2024 season  
- Identifies the top 16 sprinters by season best (SB)  
- Extracts athlete names and URLs to their World Athletics profiles

### Phase 2 – Scraping Career Race Histories

- Uses Selenium to scrape all 100m races listed on each athlete's profile  
- Collects:
  - Date and location  
  - Performance time  
  - Wind conditions  
  - Race type (e.g. final, semi-final, heat)  
- Compiles all results into a unified dataset for modeling

---

# 🎯 Modeling Objectives

This notebook simulates an entire **sprint championship season** by:

- Predicting individual 100m race times  
- Simulating race nights with scheduled head-to-head matchups  
- Dynamically updating season metrics after each round  
- Producing rankings based on duel results and time bonuses

---

# 📊 Key Features Used

The model uses a variety of contextual and performance-related features:

- `Name`, `Country`: identity features  
- `Age`: age on race day  
- `Wind_float`: wind conditions  
- `TimeGap`: estimated time difference between opponents  
- `HomeRace`: whether the athlete is racing in their home country  
- `RoundType`: race context (e.g. heat, duel, final)  
- `IsMajorEvent`: indicator for championship-level competitions  
- `PB_so_far`, `SB_so_far`: personal and seasonal bests to date  
- `avg_last_3`: average time over last 3 races (form)  
- `race_season_rank`: index of the race within the athlete’s season  
- `win_ratio_against_*`: win rates against each specific rival

---

# ⏱ Modeling Method

The main technique used is **Quantile Regression**, which allows the model to:

- Predict median and confidence intervals for 100m times  
- Account for uncertainty without needing probabilistic models  
- Simulate realistic variations in performance

---

# 🔧 Tech Stack

- Python  
- pandas, NumPy  
- scikit-learn  
- XGBoost  
- Selenium (for scraping)  
- Jupyter Notebooks  
- Matplotlib / Seaborn / Altair / Plotly

---

# 📊 Figures Visualization

The following visualizations are available as standalone interactive `.html` files and can be accessed via GitHub Pages:

- 🔗 [Average performance per athlete](https://antoinelonguevre.github.io/Sprinters_War_Simulation/figures/average_perf_per_athlete.html)  
- 🔗 [Championship standings](https://antoinelonguevre.github.io/Sprinters_War_Simulation/figures/classement_sprinters_war.html)  
- 🔗 [Top 8 performance chart](https://antoinelonguevre.github.io/Sprinters_War_Simulation/figures/perf_top8_chart.html)  
- 🔗 [Season best per athlete](https://antoinelonguevre.github.io/Sprinters_War_Simulation/figures/season_best_per_athlete.html)  
- 🔗 [Top 8 progression over the season](https://antoinelonguevre.github.io/Sprinters_War_Simulation/figures/top8_progression.html)  
- 🔗 [Top 10 individual performances](https://antoinelonguevre.github.io/Sprinters_War_Simulation/figures/top_10_individual_performances.html)

These HTML files can be opened directly in your browser, enabling zooming, tooltips, and interactive data exploration.

---

# 🤖 Why This Project Matters

Sprint performance analytics is often underutilized in sports data science. This project explores:

- The impact of contextual features on sprint results  
- Modeling matchups and rivalries dynamically  
- New formats for presenting track & field as a modern data-driven sport

---

# 👤 Author

Project by **Antoine Longuevre**, as part of an independent data science project focused on elite sprint performance.  
📧 [antoinelonguevre@icloud.com]  

---

## 📜 License

This project is licensed under the [MIT License](./LICENSE).  
You are free to use, modify, and distribute this code with proper attribution.
