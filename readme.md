# Subjectivity Bias in Digital Media  
### A causal ml study of whether subjective writing drives online virality

This repository contains our final project for **Machine Learning for Econometrics**.  
We study whether the **subjectivity** of an online news article has a causal effect on its **popularity**, measured through social media shares.

Our empirical application uses the **Online News Popularity** dataset from the UCI Machine Learning Repository:  
https://archive.ics.uci.edu/dataset/332/online+news+popularity

## Project question

Online media often mixes information, commentary, and emotionally framed language. A simple descriptive relationship may suggest that more subjective articles are shared more often. However, this does not by itself establish causality: subjectivity may be correlated with topic, channel, publication timing, article format, or pre-existing audience interest.

We therefore frame the problem as a causal comparison between **more subjective and less subjective articles**, within a population of online news pieces, and study their effect on **log social media shares** as the outcome of interest.

> **Is article subjectivity a causal driver of virality, or does it mainly reflect the kinds of content that are already more likely to spread?**

## Data

The analysis is based on a dataset of **39,644 Mashable articles**, with article-level features including:

- textual characteristics,
- keyword statistics,
- topic indicators and LDA topic proportions,
- channel dummies,
- sentiment and subjectivity measures,
- multimedia variables,
- publication timing,
- internal reference and engagement history,
- observed article popularity through `shares`.

## Methodology

This project is not a standard predictive task. We treat the question as an **observational causal inference problem** and build a full pipeline combining econometric reasoning with modern machine learning tools.

Key elements of the analysis include:

- a structured **causal framing of treatment, outcome, and population**,  
- extensive **exploratory data analysis** to understand distributions, associations, and group differences,  
- construction of a **causal DAG** to formalize the data generating process and guide identification,  
- careful **covariate selection** based on causal reasoning rather than predictive convenience,  
- explicit handling of **data leakage**, particularly for sentiment-related variables that are mechanically linked to subjectivity,  
- empirical verification of the **overlap assumption** using propensity score diagnostics,  
- **nested cross-validation** for principled model selection,  
- implementation of a **Double Machine Learning (DML)** estimator,  
- use of flexible learners such as **Random Forests** and **XGBoost** for nuisance estimation,  
- analysis of **heterogeneous treatment effects** across channels and publication timing,  
- and **robustness checks** including placebo tests and alternative covariate specifications.

## Repository structure

- `main.ipynb` — full analysis notebook  
- `data/` — dataset files  
- `readme.md` — project overview  

## Authors

- Benjamin Cerf  
- Céline Ferbach  
- Carla Lucas  
- Elyan Rougon  
- Chiara Tagiullo