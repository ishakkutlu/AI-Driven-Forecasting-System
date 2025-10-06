# AI-Driven Banknote Forecasting System

## 🔍 Overview  

Forecasting banknote demand is a critical challenge for central banks, since banknotes in circulation depend on many external and macroeconomic factors.  

This AI-driven system addresses the problem by using a dual-path forecasting architecture, combining time-series models for structural interpretability with neural networks for adaptive learning.  

Originally developed and validated as a high-impact prototype at the Central Bank of the Republic of Türkiye, it was applied to **48 models** across **real-world national and regional datasets**. Due to confidentiality constraints, only the **24 national-scale models** are shared in this public repository.  

It achieved median-based forecast accuracies up to **97%** (1−SMAPE), delivering strategic insights that supported monetary stability and efficient banknote management.  

---

## ✨ Key Features  

- **Hybrid forecasting architecture (SARIMA + Neural Networks)**  
  Machine learning (LSTM, MLP/FNN, TLNN) and time series (SARIMA) models; applied to six denominations (₺5…₺200) at national scale, resulting in 24 trained and validated models (4 × 6).  
  All models were evaluated under a consistent, leakage-safe protocol with **train / validation / test splits using past-only windows**.  

- **Robustness over single-run performance**  
  Neural networks were trained with multiple random seeds, and results were reported using **median-seed performance** rather than isolated "best runs".  
  This ensured that **model selection favored stability and decision reliability**, not just peak accuracy.  

- **Training & modeling safeguards**  
  Neural networks: early stopping, loss monitoring, learning-rate scheduling, regularization techniques to prevent overfitting, deterministic initializers for reproducibility, and normalization for stable training.  
  Time series: stationarity/seasonality checks, model selection, and residual diagnostics to ensure robustness and validity.  
  Together, these mechanisms ensured **smooth convergence**, **generalization beyond the training period**, and **consistent behavior across multiple runs**.   

 - **Metrics & interpretability**  
  RMSE to assess errors in real-world units (domain-level interpretability).  
  SMAPE as the main reporting metric, also expressed as accuracy (100 − SMAPE) for clear comparison and communication.  
  Additional stability indicators such as NRMSE and seed-based CV/IQR included to reflect consistency rather than isolated peak scores.  

---

## 📊 Real-World Impact  

- **Actionable accuracy & decision support**  
  Median-based forecast accuracies up to 97% (SMAPE), delivering reliable insights for both national and regional allocation decisions.  

- **Practical by design**  
  Forecasts relied only on the banknote demand series itself — no external variables required.  
  This made the system easy to set up and directly usable in practice, while still achieving high accuracy.  

- **Supports both short-term response and long-term planning**  
  Produced 12-month forecasts with confidence intervals, helping decision-makers prepare for seasonal patterns.  
  Supported not only cash logistics but also upstream needs such as banknote production, supply chain preparation, and long-term stock management.  

**SARIMA provided a stable statistical baseline, while neural networks added adaptive gains—especially in volatile denominations—offering more reliable signals for allocation decisions.**  

![SMAPE Error](media/accuracies.PNG)  

---

## 📂 Project Files & Reproduction Guide   

All notebooks are stored in the [`/notebooks`](./notebooks) folder.  
They include **both source code and final outputs (forecasts, validation plots, diagnostics)** — no need to re-run to view results. 

### 🔗 Kaggle Notebooks 

National-scale notebooks can be opened directly on Kaggle — no local setup required. They are fully reproducible with public datasets and run in Kaggle’s hosted Python environment.  

- **Artificial Neural Networks (MLP / TLNN / LSTM)**  
  End-to-end training pipeline is fully reproduced in a single consolidated notebook, including data preprocessing, scaling, model definition, seed-based training loops, validation monitoring and forecast generation:  
  👉 **[Open Reproducible ANN Notebook](https://www.kaggle.com/code/shakkutlu/ai-driven-demand-forecasting-mlp-tlnn-lstm)**

- **SARIMA (classical time-series baseline)**  
  Includes full statistical modeling workflow — order selection, residual diagnostics and confidence interval projection — applied across all denominations at national scale:  
  👉 **[Open Reproducible SARIMA Notebook](https://www.kaggle.com/code/shakkutlu/time-series-demand-forecasting-sarima)**

> *The original prototype also included 24 regional-scale models trained under the same protocol, but these are not included in this public release due to confidentiality constraints.*

---

## ⚙️ Tools & Environment  

- **Language:** Python (tested with 3.7+)  
- **Core libraries:** TensorFlow, Keras, Pandas, NumPy, Scikit-learn  
- **Time series:** Statsmodels, pmdarima  
- **Visualization:** Matplotlib, seaborn    
- **Environment:** Jupyter Notebook  

---

## 🛡️ Disclaimer  

- The notebooks are **anonymized, demonstration-ready versions** prepared for portfolio purposes.  
- **No confidential or sensitive data are included.**  
  - National-level datasets are public.  
  - Regional-level datasets are not shared.  

 ---

## Official Publication
The official thesis detailing this project is published on the CBRT website:

[View the full publication (PDF, in Turkish)](https://www.tcmb.gov.tr/wps/wcm/connect/b6bafef0-4d5f-4077-9497-e35e2b38c272/Uzmanl%C4%B1k+Tezi+-+%C4%B0shak+Kutlu.pdf?MOD=AJPERES&CACHEID=ROOTWORKSPACE-b6bafef0-4d5f-4077-9497-e35e2b38c272-oMkQrtC)
