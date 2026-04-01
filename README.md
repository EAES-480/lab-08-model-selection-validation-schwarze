# Lab 08 — Model Selection and Validation

EAES 480: Modern Statistics in Earth & Environmental Science  
University of Illinois Chicago  
Instructor: Dr. Gavin McNicol

---

# Dataset & Study Context

This lab continues using the simplified **AmeriFlux-style dataset** from the **US-AMS site at Argonne National Laboratory (near Chicago, IL)** covering **2023 at 30-minute resolution**.

## What is AmeriFlux?

AmeriFlux is a network of ecosystem observation sites (primarily **eddy covariance towers**) that measure exchanges of:

- carbon dioxide (CO₂),
- water vapor,
- energy,

between ecosystems and the atmosphere, along with supporting meteorological variables.

AmeriFlux overview:  
https://ameriflux.lbl.gov/about/about-ameriflux/

AmeriFlux variable documentation:  
https://ameriflux.lbl.gov/data/aboutdata/data-variables/

---

# Why This Dataset is Ideal for Model Evaluation

The US-AMS time series contains:

- strong seasonality,
- continuous environmental gradients (e.g., temperature, radiation, moisture),
- structured variability across time,
- and substantial short-term fluctuations.

These properties make it ideal for exploring:

- how well **models explain variation in environmental data**,  
- how different predictors contribute to model performance, and  
- how we evaluate whether a **model meaningfully captures system behavior**.

---

# Overview

This lab extends your work from **fitting linear models** to **evaluating and comparing them**.

Rather than asking:

> Does this model describe a relationship?

we now ask:

> Which model best explains the data, and how do we know?

This assignment introduces:

- **sum of squares (SST, SSE, SSR)**
- **R-squared as explained variance**
- **mean squared error (MSE)**
- **root mean squared error (RMSE)**
- **model comparison using multiple criteria**

You will work in a structured **R Markdown (`.Rmd`) document** with:

- guided code chunks with fill-in sections,
- sections where you write code from scratch,
- and short written interpretation responses.

---

# Learning Goals

By the end of this lab, you should be able to:

- Fit and compare multiple **linear regression models**
- Use `tidy()`, `glance()`, and `augment()` to interpret models
- Understand **sum of squares decomposition**
- Compute and interpret **R-squared**
- Compute and interpret **MSE and RMSE**
- Compare models using both **numerical metrics and visual diagnostics**
- Explain trade-offs between **model complexity and performance**
- Produce a fully reproducible **R Markdown analysis**

---

# What You’ll Do

In the provided R Markdown template, you will:

- Select a **response variable** from the dataset
- Choose **two predictor variables**
- Fit multiple regression models
- Compare models using:
  - **R-squared**
  - **RMSE**
  - **residual plots**
- Compute model metrics manually and using `broom`
- Interpret differences between models
- Justify a **model selection decision**

You will also prepare for:

- **train-test validation**, introduced in the next lecture

This lab emphasizes:

> understanding how models balance **explained variation** and **prediction error**

---

# Repository Contents

Contents

* `lab-07-model-selection-validation.Rmd`  
→ The lab template you will complete and submit

* `README.md`  
→ This file

* `data/us-ams-simple.csv`  
→ Simplified AmeriFlux-style dataset (US-AMS, 2023)

---

# Instructions

1. Fork or clone this repository to your own GitHub account  
2. Open `lab-07-model-selection-validation.Rmd` in **RStudio**  
3. Work through the document **from top to bottom**  
4. Complete all code chunks (some fill-in, some from scratch)  
5. Answer interpretation prompts in complete sentences  
6. Knit regularly to catch errors early  

⚠️ Code that runs in the Console but not in the `.Rmd` does not count.

---

# Reproducibility Requirements

Your submission must:

- Knit without errors  
- Run top-to-bottom in a clean R session  
- Include all required libraries in the setup chunk  
- Avoid hard-coded local file paths  
- Use `na.rm = TRUE` where appropriate  
- Clearly define chosen variables (e.g., `response_var`, `pred1`, `pred2`)  

These are not stylistic preferences—they are **scientific standards**.

---

# Submission

You should:

- Commit and push your completed `.Rmd` file to your GitHub repository  

You do **not** need to submit the knitted HTML unless instructed.

Your work will be evaluated on:

- correctness of model calculations,  
- clarity of interpretation,  
- understanding of model comparison,  
- and reproducibility.  

---

# Collaboration Policy

Please consider:

- You may discuss statistical concepts and modeling strategies with classmates  
- You may not copy code verbatim from others  
- Code you submit must be written and understood by you  

---

# Why This Matters

In Earth & Environmental Science:

- we often model relationships between environmental variables,  
- multiple plausible models may exist,  
- and selecting the “best” model requires careful evaluation.  

Model assessment provides a framework to determine whether:

> a model meaningfully captures environmental processes  
> or simply fits noise in the data  

This lab marks a key transition toward:

> **predictive modeling, validation, and data-driven environmental inference**
