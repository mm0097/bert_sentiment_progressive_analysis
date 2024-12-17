# Correlation Analysis Between Sentiment and Use of the Progressive

This repository contains the code for my **Bachelor Thesis**, which investigates correlations between **sentiment valence** and the use of **progressive verb forms** in Reddit posts. The study uses **BERT** fine-tuning, linguistic feature extraction, and logistic regression for analysis.

---

## Table of Contents
1. [Overview](#overview)
2. [Setup and Dependencies](#setup-and-dependencies)
3. [Data Collection and Preprocessing](#data-collection-and-preprocessing)
4. [Fine-Tuning BERT for Sentiment Analysis](#fine-tuning-bert-for-sentiment-analysis)
5. [Linguistic Feature Extraction](#linguistic-feature-extraction)
6. [Statistical Analysis](#statistical-analysis)
7. [Visualization](#visualization)
8. [Qualitative Analysis](#qualitative-analysis)
9. [Results](#results)
10. [How to Run](#how-to-run)
11. [Acknowledgments](#acknowledgments)

---

## Overview

The study explores:
- Fine-tuning a **BERT** model to analyze sentiment valence (positive, negative, compound).
- Extracting linguistic features, focusing on **progressive constructions**.
- Analyzing correlations between sentiment and linguistic features using logistic regression.

---

## Setup and Dependencies

All necessary libraries are installed within the 

Additional requirements include:
-	Python 3.8+
-	Pytorch 1.7+
-	HuggingFace Transformers

---

## Data Collection and Preprocessing

The code uses data from the **ConvoKit Reddit Corpus**, including subreddits like:
- `IdiotsInCars`
- `AmItheAsshole`
- `Confessions`

### Steps:
1. Filtered out empty, deleted, or AutoModerator posts.
2. Split data into:
   - **Training Set** for fine-tuning BERT.
   - **Analysis Set** for linguistic correlation.

---

## Fine-Tuning BERT for Sentiment Analysis

### Steps:
1. Preprocessed text by removing **stopwords**.
2. Used **VADER** for initial sentiment annotations (negative, positive, compound).
3. Fine-tuned **`bert-base-uncased`** for 3-label regression:
   - `neg`: Negative Sentiment Score
   - `pos`: Positive Sentiment Score
   - `compound`: Compound Sentiment Score

**Training Details**:
- Two approaches: BERT for sequence classification, BERT with a regression head
- Optimizer: RMSProp
- Learning Rate: `1e-5`
- Loss Function: Huber Loss
- Early Stopping: Based on validation loss.

---

## Linguistic Feature Extraction

Using **SpaCy** and NLTK:
- Extracted **progressive constructions**.
- Identified:
  - Verb categories (action, stative, mental, other).
  - Clause types (main, subclause).
  - Tense (present, past).

---

## Statistical Analysis

Performed logistic regression to:
1. Test correlations between **sentiment valence** and progressives.
2. Analyze **verb types** and **clause localizations** in progressives.

---

## Visualization

Histograms and kernel density estimation (KDE) plots illustrate:
- **Sentiment distributions** in all sentences vs sentences with progressives.

---

## Qualitative Analysis

Progressive sentences can be extracted for further manual qualitative inspection.

---

## Results

- Correlation coefficients between sentiment valence and progressives.
- Distribution of progressive verb categories and clause types.

---

## How to Run

- Run the notebook, and pay attention to loading the packages according to the information provided in the notebook to rule out compatibility issues.
