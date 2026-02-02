# Student Performance – Multiple Linear Regression Analysis

## Project Overview

This project explores how different academic, behavioral, and lifestyle factors influence student performance using **multiple linear regression**.  
Rather than fitting a single model upfront, the analysis follows a **stepwise, hypothesis-driven approach**, starting from a strong baseline and incrementally adding variables to evaluate their true contribution.

The goal is not only to achieve good predictive performance, but also to **understand which factors matter, how much they matter, and why**.

---

## Dataset

- **Source**: Kaggle – Student Performance Dataset  
- **Target Variable**:  
  - **Performance Index**: An overall measure of student academic performance (range: 10–100, rounded).

### Features Used
- **Hours Studied**: Total number of hours spent studying  
- **Previous Scores**: Scores obtained in previous exams  
- **Sample Question Papers Practiced**: Number of past/sample papers practiced  
- **Sleep Hours**: Average number of hours of sleep per day  
- *(Extracurricular Activities were intentionally not included in the final model)*

---

## Modeling Strategy

The analysis was structured into clear phases, each answering a specific question:

### Phase 1 – Data Exploration
- Checked data structure, ranges, and missing values  
- Verified feature plausibility and consistency  
- No preprocessing or feature engineering was applied at this stage  

### Phase 2 – Baseline Model
**Features**:
- Hours Studied  
- Previous Scores  

Purpose:
- Establish a strong, interpretable baseline  
- Validate linear regression assumptions using residual diagnostics  

### Phase 3 – Effort Quality Expansion
**Added Feature**:
- Sample Question Papers Practiced  

Purpose:
- Test whether targeted, exam-aligned practice explains performance beyond study time and prior ability  

### Phase 4 – Lifestyle Expansion
**Added Feature**:
- Sleep Hours  

Purpose:
- Evaluate whether a lifestyle factor contributes incremental explanatory power  
- Check whether linear treatment remains reasonable  

At each stage, models were compared using:
- Residuals vs predicted plots  
- Actual vs predicted plots  
- Test-set metrics (R², MAE, MSE)  

---

## Key Results

Final expanded model performance (test set):

- **R² ≈ 0.989**
- **MAE ≈ 1.63**
- **MSE ≈ 4.18**

### Key Insights

- **Previous Scores** is the dominant predictor, explaining most of the variance in performance.
- **Hours Studied** has a consistent positive effect, confirming that effort quantity matters.
- **Sample Question Papers Practiced** adds a **small but consistent improvement**, supporting the idea of *studying smarter*, not just longer.
- **Sleep Hours** contributes a **modest but meaningful improvement**, with residual diagnostics suggesting that a linear approximation is reasonable within the observed range.
- Improvements from additional variables are **incremental**, which is expected given the already strong baseline model.

---

## Limitations

- The Performance Index is rounded and bounded, introducing minor discretization effects in residuals.
- Only linear relationships were modeled; potential non-linear or interaction effects were not explored.
- Results are based on a controlled dataset and may not generalize fully to real-world educational settings.

---

## Project Structure

