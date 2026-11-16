# DMBI Lab — Jaiprakash Talreja (Roll No. 54, D15A)

Repository for Data Mining and Business Intelligence (DMBI) coursework, laboratory practicals, and Continuous Assessment (CA) submissions.

**Lab experiments domain:** Video streaming platform subscriber analytics (Exp 1–9).
**CA domain:** Road safety — BlackSpot Miner on UK STATS19 collision data (CA1, CA2, Exp 10) and High-Utility Itemset Mining (CA3).

---

## Continuous Assessment (CA) Submissions

| Component | Marks | Title / Topic | Folder |
|---|---|---|---|
| **CA1 Case Study** | 10 | BlackSpot Miner: A Case Study-Based Data Mining Analysis of Severe Road Collisions | [`CA1_Case_Study/`](CA1_Case_Study) |
| **CA2 Mini Project** | 10 | BlackSpot Miner: Mining Road Collision Data to Locate Severe-Crash Hotspots and Prioritise Road Safety Action | [`CA2_Mini_Project/`](CA2_Mini_Project) |
| **CA3 Content Beyond Syllabus** | 10 | High-Utility Itemset Mining: When the Most Frequent Pattern Is Not the Most Valuable One | [`CA3/`](CA3) |

CA work was done in VESIT D15A Group 09: Jaiprakash Talreja (54), Adarsh Singh (52), Vidushi Singh (53), Piyush Shukla (49).

---

## Laboratory Experiments (Syllabus Practical Sessions)

| Folder | Experiment | Description & Artifacts |
|---|---|---|
| [`Exp1_Star_Snowflake_Schema/`](Exp1_Star_Snowflake_Schema) | Experiment 1: Schema Design | Dimensional modeling for streaming BI: Star schema vs Snowflake schema design, fact/dimension structures, ER diagrams |
| [`Exp2_Data_Preprocessing/`](Exp2_Data_Preprocessing) | Experiment 2: Data Preprocessing | Handling missing data, deduplication (13 duplicates removed), outlier capping, and data transformation pipeline |
| [`Exp3_EDA_Visualization/`](Exp3_EDA_Visualization) | Experiment 3: EDA & Visualization | Statistical profiling, distribution plots, genre watch-time histograms, and spend correlation matrices |
| [`Exp4_Classification/`](Exp4_Classification) | Experiment 4: Classification Models | Decision Tree (CART) and Gaussian Naïve Bayes classification for subscriber churn prediction |
| [`Exp5_Custom_Classification/`](Exp5_Custom_Classification) | Experiment 5: Custom Classifier | Inbuilt vs from-scratch custom classification functions, evaluation metrics, and comparative benchmarking |
| [`Exp6_KMeans_Clustering/`](Exp6_KMeans_Clustering) | Experiment 6: K-Means Clustering | Customer segmentation and cluster analysis using K-Means algorithm in Python |
| [`Exp7_KMeans_RapidMiner/`](Exp7_KMeans_RapidMiner) | Experiment 7: K-Means RapidMiner | Graphical workflow and cluster validation using RapidMiner Studio |
| [`Exp8_Apriori_Association/`](Exp8_Apriori_Association) | Experiment 8: Apriori Association | Market basket analysis and frequent itemset generation using Apriori algorithm in Python |
| [`Exp9_FP_Growth_RapidMiner/`](Exp9_FP_Growth_RapidMiner) | Experiment 9: FP-Growth RapidMiner | Frequent pattern mining using FP-Growth and association rule evaluation in RapidMiner |
| [`Exp10_Mini_Project_App/`](Exp10_Mini_Project_App) | Experiment 10: Mini Project (CA2) | BlackSpot Miner: DBSCAN hotspots, Apriori + K-Modes rules, severity classifiers, next-year site risk ranking, interactive map |

---

## Quick Start

```bash
pip install -r requirements.txt
```

### Run the CA2 / Exp 10 BlackSpot Miner notebook
```bash
cd CA2_Mini_Project/POC
jupyter notebook DMBI_CA2_Group09_BlackSpot_Miner.ipynb
```
Download [`CA2_Mini_Project/blackspot_map.html`](CA2_Mini_Project/blackspot_map.html) and open it in a browser for the interactive hotspot map.

### Run the CA3 High-Utility Itemset Mining demo
```bash
cd CA3/POC
jupyter notebook DMBI_CA3_HUI_Demo.ipynb
```

### Run Individual Lab Experiments
Each experiment script can be executed from its respective directory, e.g.:
```bash
# Exp 2 Preprocessing
cd Exp2_Data_Preprocessing && python preprocessing.py

# Exp 6 K-Means Clustering (Python)
cd Exp6_KMeans_Clustering && python kmeans_clustering.py

# Exp 7 K-Means RapidMiner Comparison (Python)
cd Exp7_KMeans_RapidMiner && python kmeans_rapidminer_comparison.py

# Exp 8 Apriori Association Rule Mining (Python)
cd Exp8_Apriori_Association && python apriori_association.py

# Exp 9 FP-Growth Association Rule Mining (Python)
cd Exp9_FP_Growth_RapidMiner && python fpgrowth_association.py
```
