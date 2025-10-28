# Quantifying Home Field Advantage in the English Premier League


---

## 1. Project Proposal & Motivation

This project is for the DSA 210 Fall 2025-2026 term. The "home-field advantage" (HFA) is a widely accepted phenomenon in team sports, where teams are statistically more likely to win when playing at their home venue.

The motivation for this project is to move beyond simply acknowledging HFA's existence and to quantify its impact within the English Premier League (EPL), one of the world's most-watched sports leagues.

This project will follow the full data science pipeline to answer three primary questions:
* How strong is the home-field advantage in the EPL, measured by win percentage and goal difference?
* Has the strength of the HFA changed over time (e.g., before and after the introduction of VAR, or during the 2020-2021 "COVID" season played in empty stadiums)?
* Which factors, if any, correlate with a stronger HFA? (e.g., stadium capacity).

---

## 2. Data Sources and Collection Plan

This project will use publicly available data and will satisfy the enrichment requirement by combining two distinct datasets.

### Main Dataset: EPL Match Results
* **Data Source:** Kaggle. A comprehensive dataset containing match-by-match results for the English Premier League, ideally spanning from the early 2000s to the present day.
* **Collection Plan:** This dataset (typically a single `.csv` file) will be downloaded directly from Kaggle and stored within this GitHub repository. It is expected to contain columns such as `Date`, `HomeTeam`, `AwayTeam`, `FTHG` (Full Time Home Goals), and `FTAG` (Full Time Away Goals).

### Enrichment Dataset: EPL Stadium Information
* **Data Source:** Kaggle or other public sources (e.g., Wikipedia). This dataset will link each EPL team to its home stadium.
* **Collection Plan:** A secondary `.csv` file will be sourced or manually created that lists each unique team in the main dataset and its corresponding `Stadium_Name` and `Stadium_Capacity`. This file will be used to merge with the main match results data.

---

## 3. Initial Analysis Plan

This section outlines the planned steps to meet future project deadlines.

* **By 28 November (EDA & Hypothesis Tests):**
    1.  **Data Cleaning:** Merge the two datasets. Handle any missing values.
    2.  **Feature Engineering:** Create new columns: `Home_Win` (1 or 0), `Goal_Difference` (Home Goals - Away Goals), and `Season`.
    3.  **EDA:** Visualize the overall home win percentage. Plot the average `Goal_Difference` per season to observe trends.
    4.  **Hypothesis Test:** Conduct a t-test to determine if the mean `Goal_Difference` for home games is statistically greater than zero.

* **By 02 January (Machine Learning):**
    1.  **Model Selection:** Implement a Logistic Regression model to predict the `Home_Win` outcome (a binary classification problem).
    2.  **Feature Selection:** Use features like `Stadium_Capacity` (from the enrichment data) and potentially the relative league standing of the teams.
    3.  **Analysis:** Analyze the model's coefficients to determine which factors are significant predictors of a home win, thereby quantifying their contribution to the "home-field advantage."

All code will be written in Python and all dependencies will be listed in a `requirements.txt` file.
