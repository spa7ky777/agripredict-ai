# AgriPredict AI

AgriPredict AI is a browser-based agricultural decision-support prototype that forecasts crop-market variables and recommends crops using expected profitability, waste, and market-volatility signals.

> **Prototype notice:** The dashboard uses bundled sample data for demonstration. Its estimates are not financial or agricultural advice.

## Why it matters

Farmers must balance changing prices, demand, supply, production cost, and the risk of waste. AgriPredict AI brings these factors into a single interactive dashboard so that potential crop choices can be compared more clearly.

## Machine learning and recommendation pipeline

1. **Forecasting:** A client-side linear-regression model learns a trend from each crop's historical price, demand, supply, and cost observations. A lightweight seasonal adjustment produces a 30-day forecast for each signal.
2. **Feature calculation:** Forecast averages are used to estimate expected revenue, production cost, unsold inventory, and net profit.
3. **Risk scoring:** Price and demand volatility are measured with the coefficient of variation.
4. **Recommendation:** Crops are filtered by a waste threshold and ranked by forecasted net profit; the dashboard surfaces the strongest lower-risk option.

This is an introductory machine-learning prototype: it uses a transparent regression model rather than a production-trained deep-learning model. Future work includes integrating verified market data, evaluating predictions against held-out data, and comparing stronger time-series models.

## Features

- Crop price, demand, supply, and cost forecasting
- Profit, expected-waste, and volatility-aware crop ranking
- Interactive Chart.js price-trend visualizations
- English and Kannada user interface
- Responsive dashboard with detailed crop-analysis views

## Tech stack

- HTML5
- CSS3 and Tailwind CSS
- Vanilla JavaScript
- Chart.js

## Run locally

No build step is required.

1. Clone the repository.
2. Open `app.html` in a modern browser.
3. Keep an internet connection available for the CDN-hosted Tailwind CSS, Chart.js, and Google Font resources.

## Project structure

```text
.
├── app.html       # Dashboard markup
├── script.js      # Forecasting, ranking, translation, and UI logic
├── styles.css     # Custom responsive styles
└── logo.png       # Application logo
```

## Data and limitations

The current application includes illustrative historical data for tomatoes, cucumbers, and lettuce. The model uses linear regression plus a simplified seasonal adjustment; its confidence values are heuristic indicators, not statistically validated prediction intervals. Real deployment would require validated regional data, model evaluation, and domain review.

## Future improvements

- Import regional crop-market and weather datasets
- Add train/test evaluation with MAE and RMSE metrics
- Compare regression against validated time-series models
- Let users upload CSV data and inspect recommendation factors

## Resume-ready description

Built an agricultural decision-support dashboard using JavaScript and Chart.js. Implemented linear-regression forecasting with seasonal adjustment to predict crop price, demand, supply, and cost, then ranked crops using forecasted profit, waste, and market-volatility signals.

## License

MIT
