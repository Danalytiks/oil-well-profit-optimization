# 🛢️ Oil Well Profit Optimization  
Linear Regression + Bootstrapping for Profit & Risk Evaluation

---

## 📖 Project Overview

This project supports strategic decision-making for new oil well development by predicting reserve volume and estimating profitability under uncertainty. Using data from three regions, a linear regression model is trained to predict reserves in new wells. The most promising wells are selected, and bootstrapping is used to simulate profit distribution and quantify financial risk.

---

## 🎯 Business Objective

- Predict oil reserve volume for new wells using **Linear Regression**  
- Select top-performing wells based on predicted reserves  
- Estimate total profit under a fixed development budget  
- Evaluate risk using **bootstrapping** and select a region with:
  - loss risk < **2.5%**
  - highest expected (mean) profit among eligible regions  

---

## 🗂 Data

Three regional datasets with the following fields:
- **id** – unique well identifier  
- **f0, f1, f2** – numeric features  
- **product** – reserve volume (thousand barrels)  

---

## 🛠️ Methodology

### 1️⃣ Model Training (Linear Regression Only)
- Train a linear regression model per region  
- Evaluate prediction quality and stability  

### 2️⃣ Well Selection Strategy
- Sample 500 candidate wells  
- Select top 200 wells by predicted reserves  
- Compute profit based on:
  - budget of **$100M** for 200 wells  
  - revenue of **$4.5 per barrel** (i.e., **$4,500 per product unit**)  

### 3️⃣ Bootstrapping for Profit & Risk
- Simulate profit distribution across many bootstrap samples  
- Estimate:
  - mean expected profit  
  - confidence intervals  
  - probability of loss  

### 4️⃣ Region Recommendation
- Filter regions with loss risk below 2.5%  
- Select the region with the highest mean profit

---

## 📊 Results

| Region | Mean Profit (USD) | Loss Risk |
|--------|------------------|----------|
| Region 0 | ~$39.2M | ~5.1% |
| Region 1 | ~$44.8M | ~1.5% |
| Region 2 | ~$37.9M | ~7.6% |

Only **Region 1** meets the risk threshold (<2.5%) while also providing the highest expected profit.  

**Final Recommendation:** Develop oil wells in Region 1.

---

## 📈 Key Deliverables

- Profit distribution per region  
- Loss risk estimation per region  
- Final recommended region based on risk threshold and expected profit  

---

## 🧰 Tools & Technologies

- Python  
- Pandas  
- NumPy  
- Scikit-learn (LinearRegression)  
- Matplotlib  
