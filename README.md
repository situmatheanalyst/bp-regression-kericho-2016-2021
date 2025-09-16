# bp-regression-kericho-2016-2021
# A CASE STUDY OF KERICHO LEVEL 5 HOSPITAL (2016–2021)

## 📌 Project Title
**A Regression Analysis of Factors Affecting High Blood Pressure**

---

### 👥 Authors
- Situma Patrick Nyongesa (PA100/G/7105/19)  
- Victor Kipkirui Tapkigen (PA100/G/10210/20)  
- Conrad Onkanga Nyakundi (PA100/G/11478/20)  
- Naomi Muthoni (PA100/G/9183/20)  

**Supervisor:** Mr. Lucas Macharia  
**Institution:** Kirinyaga University — Department of Statistics  
**Date:** November 2023  

---

## 📖 Project Overview
This project investigates the relationship between **age, gender, Body Mass Index (BMI), and blood pressure** among patients at **Kericho Level 5 Hospital (2016–2021)**.  
Regression analysis is employed to evaluate whether BMI and age significantly predict hypertension levels (systolic and diastolic blood pressure).  

The project is submitted in partial fulfillment of the requirements for the award of the degree **Bachelor of Science in Statistics** at Kirinyaga University.

---

## ✍️ Declaration
We declare that this research proposal is our original work and has not been presented in any other university.

**Signatures:**  
- Situma Patrick Nyongesa: ………………… Date: …………………  
- Victor Kipkirui Tapkigen: ………………… Date: …………………  
- Conrad Onkanga Nyakundi: ………………… Date: …………………  
- Naomi Muthoni: ………………… Date: …………………  

This research proposal has been submitted for examination with the approval of the supervisor.  

**Supervisor:** Mr. Lucas Macharia  
Signature: ………………… Date: …………………

---

## 💡 Dedication
We dedicate this project to our loving families who supported us throughout our studies and this research journey.

---

## 🙏 Acknowledgement
We express gratitude to:  
- The Almighty for life and health.  
- Our supervisor, **Mr. Lucas Macharia**, for his invaluable guidance and feedback.  
- Kirinyaga University lecturers for their knowledge and resources.  
- Our families and friends for their encouragement and unwavering support.

---

## 🔤 Abbreviations
- **BMI** — Body Mass Index  
- **BP** — Blood Pressure  
- **HBP** — High Blood Pressure  
- **HTN** — Hypertension  
- **KG** — Kilograms  

---

## 📑 Table of Contents
- [Chapter 1: Introduction](#chapter-1-introduction)  
- [Chapter 2: Literature Review](#chapter-2-literature-review)  
- [Chapter 3: Research Methodology](#chapter-3-research-methodology)  
- [Chapter 4: Results and Discussion](#chapter-4-results-and-discussion)  
- [Chapter 5: Summary, Conclusion & Recommendations](#chapter-5-summary-conclusion--recommendations)  
- [📌 How to Use This Repository](#-how-to-use-this-repository)  
- [📜 License](#-license)  

---

## Chapter 1: Introduction
- **Background:** High blood pressure is strongly linked with BMI. Increasing weight often increases the risk of hypertension, which in turn raises the risk of heart disease, kidney failure, and stroke.  
- **Problem Statement:** Gaps exist in understanding how socio-economic factors and BMI interact with blood pressure.  
- **Purpose:** To assess the relationship between BMI, age, and gender with blood pressure using regression analysis.  
- **Hypotheses:** Tested positive/negative correlations between BP, age, gender, and BMI.  
- **Significance:** Helps in developing better hypertension prevention and management strategies.  

---

## Chapter 2: Literature Review
- Overview of hypertension, causes, and risks.  
- Relationship between blood pressure and lifestyle factors.  
- Review of Body Mass Index (BMI) categories and trends.  
- Age-related vascular changes affecting blood pressure.  

---

## Chapter 3: Research Methodology
- **Design:** Descriptive case study.  
- **Population:** Hypertensive patients at Kericho Level 5 Hospital.  
- **Data Source:** Secondary data (hospital records 2016–2021).  
- **Analysis:** Regression models using R software.  
- **Variables:**  
  - Dependent: Blood Pressure (systolic & diastolic).  
  - Independent: Age, Gender, BMI.  

---

## Chapter 4: Results and Discussion
- **Summary Statistics:**  
  - BMI: 25.52 (overweight) – 49.38 (obese).  
  - Systolic BP: 120–150 mmHg.  
  - Diastolic BP: 87–148 mmHg.  
  - Age: 30–87 years.  

- **Regression Models:**  
  - Systolic BP: R² = 55.07% (explained by BMI & Age).  
  - Diastolic BP: R² = 91.8% (explained by BMI & Age).  

- **Findings:**  
  - Strong relationship between BMI, age, and BP.  
  - BMI significantly influences hypertension risk.  
  - Both models statistically significant.  

---

## Chapter 5: Summary, Conclusion & Recommendations
- **Summary:** Hypertension is strongly associated with BMI and age. Regression confirmed significant predictive power.  
- **Conclusion:** Overweight and obese individuals face higher hypertension risks. Early interventions are crucial.  
- **Recommendations:**  
  - Public health interventions should target weight reduction.  
  - Regular monitoring and lifestyle adjustments for at-risk groups.  
  - Further studies should include more socio-economic variables.  

---

## 📌 How to Use This Repository
- `data/` — Contains cleaned datasets.  
- `scripts/` — R scripts for regression analysis.  
- `notebooks/` — RMarkdown or Jupyter notebooks for step-by-step analysis.  
- `results/` — Regression outputs and tables.  
- `visuals/` — Graphs and plots of BP trends.  

---

## 📜 License
This project is for **academic purposes** and submitted in partial fulfillment of the BSc. in Statistics program at Kirinyaga University.

---
---
title: "Hypertension Data Analysis"
author: "patrick Situma (Situma the Analyst)"
date: "`r Sys.Date()`"
output: R_document
---

# 4.1 Importing Data from Excel and Extracting Variables

The data to be examined is initially entered into Excel (or CSV) and then exported to R for analysis.

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE, warning = FALSE, message = FALSE)
# Extract each variable
blood_pressure <- data$blood_pressure
age <- data$age
weight <- data$weight
cholesterol <- data$cholesterol
library(car)

# Fit a regression model
model <- lm(blood_pressure ~ age + weight + cholesterol, data = data)

# Check Variance Inflation Factor (VIF)
vif(model)

---
