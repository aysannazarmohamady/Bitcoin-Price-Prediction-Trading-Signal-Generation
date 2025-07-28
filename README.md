#  Bitcoin Price Prediction & Trading Signal Generator

> An end-to-end machine learning solution for Bitcoin price forecasting and automated trading signal generation using deep learning techniques.



##  Project Overview

This project develops a sophisticated Bitcoin price prediction system combining LSTM neural networks with technical analysis to forecast next-day Bitcoin prices and generate actionable trading signals. The solution demonstrates production-ready ML engineering with comprehensive feature engineering, bias correction, and realistic backtesting.

###  Key Features
- **Next-day price prediction** with 9.5% MAPE accuracy
- **Automated trading signals** with confidence scoring
- **Bias-corrected predictions** for improved reliability
- **Realistic backtesting** with transaction costs
- **Technical indicator integration** (RSI, MACD, Bollinger Bands)

##  Results Summary

| Metric | Value |
|--------|-------|
| **MAE** | $7,653 |
| **MAPE** | 9.5% |
| **Directional Accuracy** | 47.6% |
| **Accuracy (5% threshold)** | 35.6% |
| **Model Parameters** | 8.4K |

**Performance vs Bitcoin Volatility:** 220.1% efficiency ratio 

##  Technical Implementation

### Architecture
- **Deep Learning:** Optimized LSTM with 32→16 layer structure
- **Feature Engineering:** 7 selected technical indicators from 47 candidates
- **Time Series:** 30-day sequences for next-day prediction
- **Regularization:** Dropout, early stopping, proper time-series validation

### Data Pipeline
```python
Raw Bitcoin Data → Feature Engineering → Technical Indicators → 
LSTM Model → Bias Correction → Trading Signals → Backtesting
```

##  Installation & Setup

### Prerequisites
```bash
Python 3.8+
TensorFlow 2.x
Pandas, NumPy, Matplotlib, Scikit-learn
```

### Quick Start

1. **Clone the repository:**
```bash
git clone https://github.com/yourusername/bitcoin-price-prediction.git
cd bitcoin-price-prediction
```

2. **Install dependencies:**
```bash
pip install -r requirements.txt
```

3. **Download the dataset:**
   - Visit [Bitcoin Historical Data on Kaggle](https://www.kaggle.com/datasets/adilshamim8/bitcoin-historical-data/data)
   - Download `Bitcoin_history_data.csv`
   - Place in `data/` directory

4. **Run the notebook:**
```bash
jupyter notebook bitcoin_prediction.ipynb
```

##  Dataset Information

**Source:** [Kaggle - Bitcoin Historical Data](https://www.kaggle.com/datasets/adilshamim8/bitcoin-historical-data/data)

**Features:**
- **Date Range:** September 2014 - July 2025
- **Records:** 3,966 daily observations
- **Columns:** Date, Open, High, Low, Close, Volume

**Download Instructions:**
```python
# Using Kaggle API
kaggle datasets download -d adilshamim8/bitcoin-historical-data
```

##  Key Challenges Solved

### 1. **Model Overfitting**
- **Problem:** Initial model showed severe overfitting (training loss: 0.001, validation: 0.21)
- **Solution:** Architectural simplification (154K → 8.4K parameters) + enhanced regularization

### 2. **Feature Redundancy**
- **Problem:** 47 engineered features caused noise and complexity
- **Solution:** Systematic feature selection based on correlation analysis and domain expertise

### 3. **Systematic Bias**
- **Problem:** Model consistently underestimated prices by 5.6%
- **Solution:** Implemented bias correction algorithm for improved signal accuracy

### 4. **Unrealistic Backtesting**
- **Problem:** Initial backtest showed 153% returns (too good to be true)
- **Solution:** Added transaction costs, proper time-series splitting, and conservative thresholds

##  Sample Results

### Recent Trading Signals
```
Date       | Signal | Price    | Predicted | Confidence
-----------|--------|----------|-----------|----------
2025-07-22 | SELL   | $119,995 | $94,438   | 99%
2025-07-23 | SELL   | $118,755 | $94,473   | 100%
2025-07-24 | HOLD   | $118,368 | $94,349   | 85%
```

### Signal Distribution
- **BUY Signals:** 46.2%
- **HOLD Signals:** 17.1%  
- **SELL Signals:** 36.7%

##  Business Applications

- **Risk Management:** Excellent at identifying major market downturns
- **Portfolio Optimization:** Informed position sizing and entry/exit timing
- **Research Foundation:** Baseline for advanced ensemble methods
- **Market Analysis:** Technical pattern recognition and trend analysis

##  Future Enhancements

- [ ] **Ensemble Methods:** Combine LSTM + XGBoost + Linear models
- [ ] **Macro Features:** Include Fed rates, inflation data, market sentiment
- [ ] **Regime Detection:** Adaptive thresholds based on market conditions
- [ ] **Real-time Deployment:** Live trading signal API
- [ ] **Alternative Data:** News sentiment, social media analysis

##  Project Structure

```
bitcoin-price-prediction/
├── README.md                 # Project documentation
├── bitcoin_prediction.ipynb  # Main notebook
├── requirements.txt          # Dependencies
├── data/                     # Dataset directory
├── images/                   # Visualization outputs
├── models/                   # Saved model files
└── src/                      # Source code modules
    ├── data_processing.py
    ├── feature_engineering.py
    ├── model_training.py
    └── trading_signals.py
```


##  Contributing

Contributions are welcome! Please feel free to submit a Pull Request.


---

⭐ **Star this repository** if you found it helpful!
