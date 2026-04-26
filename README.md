# -Decline-Curve-Analysis-DCA-for-Oil-Well-Production

📌 Overview

This project applies Decline Curve Analysis (DCA) to historical oil production data to model production behavior and forecast future performance of a well.

Using a hyperbolic decline model, the project estimates key reservoir parameters and predicts future oil rates, along with the Estimated Ultimate Recovery (EUR).

🎯 Objectives
Analyze historical production data for a selected well
Fit a decline curve model to production data
Forecast future oil production
Estimate total recoverable oil (EUR)
Visualize production trends and model performance

🧠 Methodology
1. Data Preparation
Imported production data (oil, water, gas, time)
Filtered data for a specific well
Converted dates into numerical time steps for modelling

2. Decline Curve Model

The hyperbolic decline model used:

q(t) = q1 / (1 + b * Di * t)^(1/b)

Where:

q(t) = oil rate at time t (STB/day)
q1 = initial production rate
Di = initial decline rate
b = decline exponent (controls curve shape)

3. Curve Fitting
Used scipy.optimize.curve_fit to estimate:
Initial rate (q1)
Decline rate (Di)
Decline exponent (b)
The model minimizes the difference between:
Actual production data
Predicted production

4. Forecasting
Extended the model beyond historical data
Predicted future production rates over time

5. EUR Calculation

Estimated Ultimate Recovery (EUR) was calculated as:

EUR = Past Production + Forecasted Production
Past production → cumulative oil
Future production → integrated using numerical methods (np.trapezoid)

📊 Results
The model successfully captured the declining trend of the well
Early-time production showed steep decline, influencing model parameters
Forecast shows continued decline in production rate

⚠️ A sharper-than-expected forecast decline was observed due to:

High estimated decline rate (Di)
Influence of early production data
Lack of parameter constraints during curve fitting

📈 Visualization

The plot includes:

Scatter points → actual production data
Solid line → fitted DCA model
Dashed line → forecasted production
