# N-gram Language Model for Sentiment Analysis

This repository contains a Jupyter Notebook that demonstrates the implementation of an n-gram language model for sentiment analysis using the IMDB Dataset.

## Overview

The notebook explores the following aspects of n-gram language modeling:

- **Data Preprocessing:** Cleaning and preparing the IMDB dataset for analysis.
- **N-gram Generation:** Creating unigrams, bigrams, trigrams, quadgrams, and pentagrams from the text data.
- **Probability Calculation:** Computing n-gram probabilities using various smoothing techniques:
    - Laplace Smoothing
    - Good-Turing Discounting
    - Kneser-Ney Smoothing
- **Model Evaluation:** Assessing the performance of the language model using perplexity as a metric.
- **Cross-Validation:** Employing cross-validation to ensure model robustness.
- **Visualization:** Presenting the results with clear and informative plots.


## Dataset

The IMDB Dataset is used for this analysis. It consists of movie reviews labeled as positive or negative. You can download the dataset from [this link]. Make sure to update the file path in the notebook to reflect the location of the dataset on your system.


## Results

The notebook includes visualizations and analysis of the model's performance, including perplexity scores and comparisons between different smoothing techniques.
