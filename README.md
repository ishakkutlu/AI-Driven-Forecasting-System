# AI-Driven Banknote Forecasting System

## 🔍 Overview  
Forecasting banknote demand is a critical challenge for central banks, since banknotes in circulation depend on many external and macroeconomic factors. Accurate forecasts are essential for monetary stability and efficient cash management.  

This system addresses the problem by combining 48 forecasting models with artificial intelligence (neural networks) and classical time series approaches. Developed at the Central Bank of the Republic of Türkiye, it was a high-impact prototype trained and validated on real-world national and regional data. The system achieved up to 99% accuracy (SMAPE), delivering strategic insights for more precise and efficient banknote management planning.

## ✨ Key Features

**Implementation scope (48 models)**
- Implemented neural networks (LSTM, MLP/FNN, TLNN) and SARIMA across six denominations (₺5…₺200) at both national and regional levels.  
- This makes 48 models in total (4 model families × 6 denominations × 2 scales).
- All evaluated under a consistent, leakage-safe protocol (shared train/validation/test splits with past-only windows).

**Training & modeling safeguards**  
- Neural networks: early stopping, loss monitoring, normalization, and systematic evaluation to improve generalization and prevent overfitting.  
- Time series models: stationarity and seasonality checks, systematic model selection, and residual diagnostics to ensure robustness and validity.

**Metrics & interpretability**  
- **RMSE** to assess errors in real-world units (domain-level interpretability).  
- **SMAPE** as the main reporting metric, also expressed as Accuracy = 100 − SMAPE for clear comparison and communication.

**Transparent data policy**  
- National datasets are public, enabling full end-to-end reproducibility.  
- Regional datasets are restricted: raw series cannot be shared, only aggregated metrics and result figures are reported.  

## 📊 Real-World Impact  

**High accuracy & decision support**  
- Achieved up to 99% forecasting accuracy (SMAPE).  
- Delivered actionable insights to decision-makers, supporting strategic allocation on both national and regional scales.  

**Longer-term banknote management planning**  
- Produced 12-month forecasts with confidence intervals, helping decision-makers prepare for seasonal demand patterns in advance.  
- Ongoing train/validation/test monitoring ensured reliable results, building confidence in forecasts used for cash management planning.  

**Operational & policy relevance**  
- Forecasts supported not only distribution planning (cash logistics) but also upstream needs such as banknote production, supply chain preparation, and long-term stock management.  
- As circulation volume is a key driver of monetary liquidity, accurate demand forecasts provided critical input for broader monetary policy planning.

**Simplicity with real-world impact**  
- Delivered accurate forecasts using only the banknote demand series itself — without requiring additional macroeconomic or external variables.  
- This makes the system easy to apply in practice: fast setup, no dependency on uncertain external forecasts, yet high accuracy in predicting future cash demand.  




## Key Highlights
- Developed 48 models covering national and regional levels.
- Achieved up to 99% accuracy using SMAPE metric.
- Implemented early stopping, loss monitoring, and data normalization.
- Conducted comparative analysis between AI models and SARIMA.
- Utilized Python, TensorFlow, Keras, Pandas, NumPy, Scikit-learn, Pmdarima, Statsmodels, Matplotlib.

## Visual Results
Below are selected visuals demonstrating the forecasting performance and evaluation results of the AI-based system across different models, denominations, and regions.

### Evaluation Metrics – National vs Regional (SMAPE %)
- Evaluation of 4 models across 6 denominations using SMAPE as the main metric.
- AI models (LSTM, TLNN, FNN) generally outperformed SARIMA at both national and regional levels.

![SMAPE Error](media/evaluate-accuracy.png)

---

### Forecasting Results – National Level
#### Forecasting – National Level (200 TL)
- Trained on historical demand data and projected 12 months ahead.
- FNN and LSTM delivered more accurate projections during the test period (2022), closely tracking real demand.
- TLNN and SARIMA showed weaker generalization during unexpected surges.

![200 TL National](media/200TL_forecasting_national.png)

---

#### Loss Curves & Residual Autocorrelation – National Level (200 TL)
- The 200 TL models show stable convergence in both training and validation losses across all neural networks.
- SARIMA's residuals showed no significant autocorrelation.
- These help assess overfitting and model consistency, with early stopping applied to the neural models to retain optimal performance.

![Loss 200 TL](media/200TL_loss_national.png)

---

#### Forecasting – National Level (50 TL)
- Strong seasonal signals were observed and well tracked by neural models.
- SARIMA captured the overall trend but with less precision and higher uncertainty.

![50 TL National](media/50TL_forecasting_national.png)

---

#### Forecasting – National Level (5 TL)
- All models captured seasonal demand patterns.
- Neural models (LSTM, TLNN, FNN) showed slightly better alignment with actual trends than SARIMA, which had wider forecast uncertainty.

![5 TL National](media/5TL_forecasting_national.png)

---

### Forecasting Results – Regional Level

#### Forecasting – Regional Level (200 TL)
- FNN, LSTM, and TLNN maintained accuracy despite regional volatility.
- SARIMA underperformed in capturing irregular demand fluctuations.

![200 TL Regional](media/200TL_forecasting_regional.png)

---

#### Forecasting – Regional Level (50 TL)
- LSTM and TLNN maintained accuracy despite regional volatility.
- SARIMA and FNN underperformed in capturing irregular demand fluctuations.

![50 TL Regional](media/50TL_forecasting_regional.png)

---

#### Forecasting – Regional Level (5 TL)
- All models followed the regional demand trend with clear seasonality.
- Neural networks closely tracked actual values, though with slight underestimation across most months.
- SARIMA showed higher forecast variance and slightly less stable fit.

![5 TL Regional](media/5TL_forecasting_regional.png)

---

## Implementation
To explore the project in detail, including 12 distinct datasets and 14 Jupyter notebooks used for training and forecasting AI and time series models with national and regional data, please visit the Kaggle repository:

1. [200 TL – National Forecasting (FNN, TLNN, LSTM)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-ai-ann-tr-200)
2. [100 TL – National Forecasting (FNN, TLNN, LSTM)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-ai-ann-tr-100)
3. [50 TL – National Forecasting (FNN, TLNN, LSTM)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-ai-ann-tr-50)
4. [20 TL – National Forecasting (FNN, TLNN, LSTM)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-ai-ann-tr-20)
5. [10 TL – National Forecasting (FNN, TLNN, LSTM)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-ai-ann-tr-10)
6. [5 TL – National Forecasting (FNN, TLNN, LSTM)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-ai-ann-tr-5)
7. [200 TL – Regional Forecasting (FNN, TLNN, LSTM)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-ai-ann-eskisehir-200)
8. [100 TL – Regional Forecasting (FNN, TLNN, LSTM)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-ai-ann-eskisehir-100)
9. [50 TL – Regional Forecasting (FNN, TLNN, LSTM)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-ai-ann-eskisehir-50)
10. [20 TL – Regional Forecasting (FNN, TLNN, LSTM)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-ai-ann-eskisehir-20)
11. [10 TL – Regional Forecasting (FNN, TLNN, LSTM)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-ai-ann-eskisehir-10)
12. [5 TL – Regional Forecasting (FNN, TLNN, LSTM)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-ai-ann-eskisehir-5)
13. [SARIMA – National Forecasting (All Denominations)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-time-series-sarima-tr-data)
14. [SARIMA – Regional Forecasting (All Denominations)](https://www.kaggle.com/code/shakkutlu/vocational-thesis-time-series-sarima-eskisehir)

## Official Publication
The official thesis detailing this project is published on the CBRT website:

[View the full publication (PDF, in Turkish)](https://www.tcmb.gov.tr/wps/wcm/connect/b6bafef0-4d5f-4077-9497-e35e2b38c272/Uzmanl%C4%B1k+Tezi+-+%C4%B0shak+Kutlu.pdf?MOD=AJPERES&CACHEID=ROOTWORKSPACE-b6bafef0-4d5f-4077-9497-e35e2b38c272-oMkQrtC)
