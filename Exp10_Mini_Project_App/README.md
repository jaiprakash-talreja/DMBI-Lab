# Experiment 10: BlackSpot Miner (CA2 Mini Project)

Course: Data Mining and Business Intelligence (DMBI Lab) — Roll No. 54 (Jaiprakash Talreja), Div D15A, Group 09.

---

## Overview

Experiment 10 documents the **CA2 Mini Project, BlackSpot Miner**: an end-to-end data mining and decision support pipeline on five years of UK Department for Transport STATS19 road collision records (513,801 collisions, 2021–2025). It answers three questions for a road authority with a limited safety budget — **where** severe (KSI) collisions concentrate, **why** some collisions are more severe, and **which sites to treat next** — with every result tested on 2025, a year never used for mining or training.

- **Report (DOCX):** [`EXP-10_DMBI_54_MiniProject_BlackSpotMiner.docx`](EXP-10_DMBI_54_MiniProject_BlackSpotMiner.docx)
- **Report (PDF):** [`EXP-10_DMBI_54_MiniProject_BlackSpotMiner.pdf`](EXP-10_DMBI_54_MiniProject_BlackSpotMiner.pdf)
- **Project code, results and map:** [`CA2_Mini_Project/`](../CA2_Mini_Project)
- **Figures used in the report:** [`images/`](images)

---

## Coursework Modules Implemented

| Stage | DMBI Syllabus Module | Method & Key Result |
|---|---|---|
| **1. Data audit & preprocessing** | Module II: Data Preprocessing | Joined collision/vehicle/casualty tables, removed leakage columns, corrected for the police severity-reporting change (injury-based share 49.6% → 86.5%) |
| **2. Exploratory analysis** | Module II | KSI rate peaks at 45.6% (Mon 04:00); motorcycles 43.6%, pedestrians 34.1% |
| **3. Where** | Module IV: Clustering | DBSCAN (eps = 100 m, min_samples = 6): 804 hotspots; 4.79× the 2025 KSI per km² of random past sites |
| **4. Why** | Module V: Association Rules | Apriori: 107 of 109 KSI rules kept their lift on 2025 |
| **5. Segments** | Module IV: Clustering | K-Modes (k = 6): 60 hidden rules, 55 held on 2025 |
| **6. Severity** | Module III: Classification | Naive Bayes, Decision Tree, Random Forest, AdaBoost — best RF ROC-AUC 0.679, PR-AUC 0.440 |
| **7. What next** | Module III: Prediction | Poisson boosting on 500 m cells: ROC-AUC 0.764 vs 0.680 for a past-count black spot list |
| **8. Decision support** | Module VI: BI | Ranked 2026 priority site list + interactive hotspot map |

---

## How to Run

```bash
pip install -r requirements.txt
cd CA2_Mini_Project/POC
jupyter notebook DMBI_CA2_Group09_BlackSpot_Miner.ipynb
```

The notebook downloads the STATS19 data from the official source on first run and takes about 20 minutes. All numbers are written to `CA2_Mini_Project/POC/results/metrics.json`.

To view the interactive map, download [`CA2_Mini_Project/blackspot_map.html`](../CA2_Mini_Project/blackspot_map.html) and open it in a browser (GitHub only shows its source).
