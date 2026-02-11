Project Overview

This project leverages Machine Learning to identify "irrational" betting behavior in Texas Hold'em Poker. 
By analyzing over 12,000 hands of unstructured log data, I developed a model that flags when my personal decision-making deviates significantly from optimal strategies based on hand strength and board texture.

The Three-Stage Pipeline

1. Unstructured Data Extraction (logfilescraper.ipynb)
Regex-Based Parsing: Developed a custom scraper using Regular Expressions to transform raw, text-based poker hand histories into a structured format.
High-Efficiency Storage: Implemented Parquet serialization to handle large-scale data storage and retrieval with minimal memory footprint.

2. Feature Engineering & Domain Analysis (Data-Analysis.ipynb)
Hand Evaluation: Integrated the treys library to calculate exact hand rankings for every player across every street (Flop, Turn, River).
Metric Normalization: Standardized all betting data into "Big Blinds" to ensure comparability across different game stakes.
Statistical Profiling: Conducted exploratory data analysis using boxplots to map betting distributions against hand equity.

3. Behavioral Modeling (Thesis_model.ipynb)
Model Selection: Built and compared Gradient Boosting, Random Forest, and Logistic Regression models.
Class Imbalance Handling: Applied SMOTE (Synthetic Minority Over-sampling Technique) to ensure the model could accurately detect rare irrational play events.
Irrationality Detection: Defined a "Non-Compliance Index" (NCI) to flag decisions where the model predicted a "Fold" but the player chose to "Call" or "Bet".

Tech Stack
Core: Python (Pandas, NumPy)
ML: Scikit-Learn, Imbalanced-Learn (SMOTE)
Domain: Treys (Hand Evaluation)
Data: Regular Expressions (Regex), Parquet
