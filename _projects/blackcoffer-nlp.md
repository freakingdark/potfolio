---
layout: default
title: Web Scraping & NLP Text Analysis
---

# Web Scraping and NLP Text Analysis

## Project Overview

This project focuses on automated **web data extraction and natural language processing (NLP)** to analyze textual content from multiple online articles.

The system extracts article content from given URLs and performs **sentiment analysis and readability analysis** to generate structured analytical metrics.

The objective was to build a **complete data pipeline** including data extraction, text preprocessing, sentiment scoring, and linguistic feature computation.

This project was developed as part of a technical assignment involving **text mining and sentiment analysis of financial articles**.

---

## Problem Statement

Given a dataset containing article URLs, the task was to:

1. Extract article titles and text content from web pages.
2. Clean and preprocess the extracted text.
3. Perform sentiment and readability analysis.
4. Compute multiple linguistic and statistical metrics.
5. Store the results in a structured output dataset.

The extracted analysis includes metrics such as sentiment polarity, subjectivity, readability scores, and linguistic complexity indicators. :contentReference[oaicite:0]{index=0}

---

## Methodology

### 1. Data Extraction

- URLs were provided in an input dataset.
- Python-based web scraping was implemented using **BeautifulSoup and requests**.
- The script extracts only:
  - Article title
  - Article body text

Website headers, footers, and irrelevant elements were removed during extraction.

Each article was saved as a separate text file for further analysis.

---

### 2. Text Preprocessing

The extracted text was cleaned using:

- Stopword removal
- Tokenization
- Lowercasing
- Punctuation removal

Stopword lists were used to remove non-informative terms before performing sentiment analysis. :contentReference[oaicite:1]{index=1}

---

### 3. Sentiment Analysis

Sentiment scores were calculated using custom **positive and negative word dictionaries**.

Computed metrics:

- Positive Score
- Negative Score
- Polarity Score
- Subjectivity Score

These scores help determine whether the article sentiment is positive, negative, or neutral. :contentReference[oaicite:2]{index=2}

---

### 4. Readability Analysis

Readability metrics were calculated to measure linguistic complexity.

Key indicators include:

- Average sentence length
- Percentage of complex words
- Fog Index
- Average number of words per sentence

The **Gunning Fog Index** was used to evaluate readability difficulty. :contentReference[oaicite:3]{index=3}

---

### 5. Linguistic Feature Extraction

Additional linguistic metrics were computed:

- Word Count
- Complex Word Count
- Syllables per Word
- Personal Pronoun Frequency
- Average Word Length

These features provide deeper insight into writing style and textual complexity. :contentReference[oaicite:4]{index=4}

---

## Technologies Used

- Python
- BeautifulSoup
- Requests
- NLTK
- Pandas
- Regular Expressions
- Natural Language Processing

---

## Key Outcomes

- Built an automated **web scraping pipeline**
- Implemented **dictionary-based sentiment analysis**
- Calculated multiple **readability and linguistic complexity metrics**
- Generated structured output for further analytical use

---

## Repository

GitHub Repository:  
https://github.com/freakingdark/blackcoffer-text-analysis
