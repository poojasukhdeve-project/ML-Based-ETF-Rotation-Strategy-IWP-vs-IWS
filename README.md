# 📊 ML-Based ETF Rotation Strategy (IWP vs IWS)

---

## 🧩 Problem Statement

Investors often face a fundamental question:

👉 **Should I invest in Growth (IWP) or Value (IWS)?**

Both strategies outperform at different times depending on:
- Market cycles  
- Interest rates  
- Economic conditions  

However, most investors rely on **static allocation (buy & hold)**, which fails to adapt to changing market regimes.

💡 **Objective:**  
Can we build a **data-driven strategy** that dynamically switches between Growth and Value to improve returns?

---

## 💡 Hypothesis

Markets are not entirely random — **patterns exist in price, momentum, and volatility**.

Instead of predicting absolute returns, we reframe the problem:

👉 Predict **relative outperformance**  
> Will *IWP outperform IWS tomorrow?*

---

## 🛠️ Strategy Design

### 🔹 Step 1: Feature Engineering

We engineered features to capture **market behavior**, not just price:

- 📈 Trend → Moving Averages (MA10, MA50)  
- ⚡ Momentum → 5-day price change  
- 📊 Volatility → Rolling standard deviation  
- 🔁 Lagged Returns → Short-term memory  
- ⚖️ Relative Strength → Return differences  
- 📉 Trend Ratio → MA10 / MA50  
- 📊 Mean Returns → Smoothed signals  
- ⚖️ Volatility Ratio → Risk comparison  

---

### 🔹 Step 2: Machine Learning Models

Models used:
- Random Forest  
- XGBoost  

**Target Variable:**
- 1 → IWP outperforms IWS
- 0 → IWS outperforms IWP

---

**Train/Test Split:**
- Train: Pre-2022  
- Test: 2022–2026  

---

### 🔹 Step 3: Trading Strategy

To reduce noise, we applied **confidence-based filtering**:

- If probability > 0.55 → Invest in IWP  
- If probability < 0.45 → Invest in IWS  
- Otherwise → Hold previous position  

✅ Helps avoid overtrading  
✅ Improves stability  

---

### 🔹 Step 4: Portfolio Construction

- Daily dynamic allocation between IWP and IWS  
- Strategy driven by ML signals  
- Compared against Buy & Hold benchmarks  

---

## 📊 Results

### 📈 Performance

- Strategy **outperformed both ETFs**
- Captured **market regime shifts**
- Delivered consistent growth vs benchmarks  

---

### ⚖️ Risk Metrics

| Metric            | Value     |
|------------------|----------|
| Sharpe Ratio     | ~0.72     |
| Max Drawdown     | ~-26%     |

---

### 🔄 Trading Behavior

- Total Trades: **48**
- Reduced overtrading due to confidence thresholds  
- More stable than raw predictions  

---

## 🔍 Key Insights

### 1️⃣ Feature Engineering > Model Complexity  
Well-designed features mattered more than complex models.

### 2️⃣ Confidence Filtering is Critical  
Raw ML predictions are noisy — filtering improves performance.

### 3️⃣ Relative Prediction Works Better  
Predicting *which asset wins* is more effective than predicting returns.

### 4️⃣ Market Regime Rotation Exists  
The model successfully captured **Growth vs Value cycles**.

---

## 🚀 Impact

This project demonstrates:

- ✅ Real-world application of ML in finance  
- ✅ End-to-end pipeline: **data → model → strategy → portfolio**  
- ✅ Importance of combining **ML + domain knowledge**  

---

## 📉 Limitations

- No transaction costs included  
- No slippage modeling  
- Daily frequency only  
- Limited hyperparameter tuning  

---

## 🔮 Future Improvements

- Add transaction costs & execution modeling  
- Walk-forward validation  
- Ensemble models  
- Market regime detection  
- Live trading dashboard  

---

## 🏁 Conclusion

A well-designed ML strategy combined with strong feature engineering can:

👉 **Outperform traditional buy-and-hold approaches**

💡 *The edge is not just in the model — it's in the strategy design.*

---

## 👩‍💻 Author

**Pooja Sukhdeve**  
MS Computer Science  
Boston University  

---
  
