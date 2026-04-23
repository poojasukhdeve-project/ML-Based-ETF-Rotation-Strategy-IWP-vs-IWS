# 📊 ML-Based ETF Rotation Strategy (Growth vs Value)

## 🧩 The Story Behind This Project

Most investors face a simple but frustrating question:

> ❓ *Should I invest in Growth stocks or Value stocks?*

Some years, **Growth (IWP)** dominates.  
Other years, **Value (IWS)** takes the lead.

👉 The problem?  
No one knows **when to switch**.

So instead of guessing, I asked:

> 💡 *Can machine learning learn this switching pattern automatically?*

---

## 🎯 Problem Statement

Traditional strategies:
- Buy & Hold Growth ❌  
- Buy & Hold Value ❌  

👉 Both fail because:
- Markets **rotate between styles**
- One ETF underperforms depending on the cycle

### 🚨 Core Problem:
> Build a system that dynamically selects the **better-performing ETF at the right time**

---

## 🧠 How I Thought About the Problem

Instead of predicting:
❌ “Will market go up or down?”

I reframed it:

> ✅ *Which ETF will perform better relative to the other?*

This small shift made a BIG difference.

---

## ⚙️ Approach

### 1️⃣ Data Collection

- Source: Yahoo Finance (`yfinance`)
- ETFs:
  - IWP → Growth  
  - IWS → Value  
- Time period: 2002 – Present

---

### 2️⃣ Feature Engineering (Where the magic happens ✨)

I created features that capture market behavior:

#### 🔹 Momentum
- Recent price movements  

#### 🔹 Volatility
- Market risk levels  

#### 🔹 Trend
- Short vs long-term averages  

#### 🔥 Relative Strength (MOST IMPORTANT)

```python
RS = IWP_Close / IWS_Close
This tells:

Which ETF is stronger RIGHT NOW
---
### 3️⃣ Target Design
-Target = 1  # IWP outperforms  
-Target = 0  # IWS outperforms

- Model learns relative performance, not absolute

---
### 4️⃣ Model
-Algorithm: XGBoost
-Why?
--Handles noisy financial data
--Captures non-linear patterns
--Works well on tabular data
---

## 🔄 Strategy Logic (Core Idea)
