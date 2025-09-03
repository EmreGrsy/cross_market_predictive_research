# Cross-Market Predictive Research: FX, Commodities & Equities

## Project Overview
This project explores **predictive relationships across FX, commodity futures, and equity markets**.  
The aim was to test whether **machine learning models** can uncover signals that could later be used for **algorithmic trading strategies**.

The workflow followed the same steps as in a trading desk research environment:
- Generating trading ideas from cross-market data  
- Building and tuning models  
- Backtesting predictive performance with realistic validation  
- Ranking instruments by signal strength  

---

## Approach
- **Data**: FX pairs, Gold Futures (JPX), LME metals, and global equities  
- **Model**: Gradient boosting (XGBoost) with GPU acceleration  
- **Tuning**: Automated hyperparameter search with Optuna  
- **Validation**: Walk-forward style (TimeSeriesSplit) to avoid lookahead bias  
- **Metric**: Root Mean Squared Error (RMSE) as a proxy for forecast accuracy  

---

## Results
The models identified **strong predictive links between Gold Futures and major FX pairs**.

**Top 10 Targets by Predictive Accuracy (lowest RMSE):**

| Rank | Target | RMSE |
|------|--------|------|
| 1 | FX_EURUSD – JPX_Gold_Standard_Futures_Close | **0.00989** |
| 2 | FX_GBPUSD – JPX_Gold_Standard_Futures_Close | 0.01020 |
| 3 | FX_USDCHF – JPX_Gold_Standard_Futures_Close | 0.01055 |
| 4 | JPX_Gold_Standard_Futures_Close – FX_USDJPY | 0.01061 |
| 5 | JPX_Gold_Standard_Futures_Close – FX_NOKGBP | 0.01075 |
| 6 | FX_EURNZD – JPX_Gold_Standard_Futures_Close | 0.01134 |
| 7 | US_Stock_VT_adj_close | 0.01269 |
| 8 | LME_CA_Close – FX_NOKEUR | 0.01272 |
| 9 | FX_NOKEUR | 0.01279 |
| 10 | FX_EURJPY – JPX_Gold_Standard_Futures_Close | 0.01308 |

---

## Visualization
The chart below shows the **Top 10 Predictive Targets**, ranked by RMSE:

![Top 10 Targets](best_performers.pdf)

---

## Key Insights
- There is **clear predictive structure** between Gold Futures and FX pairs — suggesting potential cross-market trading signals.  
- The framework can be **re-used and extended** to test energy commodities (power, gas, oil) with the same approach.  

---
