# Stochastic-Interest-Rate-model
Implementation of Vasicek and CIR interest rate models with MLE calibration, Monte Carlo simulation, bond pricing, and stress testing using US Treasury yield data.”
Stochastic Interest Rate Modeling: Vasicek vs CIR
Overview
This project implements and compares two classical short-rate models used in quantitative finance:
Vasicek Model
Cox-Ingersoll-Ross (CIR) Model
Using historical US 10-Year Treasury Yield (^TNX) data obtained from Yahoo Finance, the models are calibrated via Maximum Likelihood Estimation (MLE) and subsequently used for:
Monte Carlo simulation of future interest rate paths
Zero-coupon bond pricing
Interest rate stress testing
Comparative analysis of model behavior


⸻


Objectives
The primary objectives of this project are:
Estimate Vasicek and CIR model parameters from historical yield data.
Simulate future short-rate paths using Monte Carlo methods.
Price a one-year zero-coupon bond.
Analyze the impact of interest rate shocks through stress testing.
Compare the strengths and limitations of the two models.


⸻


Data Source
Historical US 10-Year Treasury Yield data was downloaded from Yahoo Finance using the ticker:
^TNX
Period: January 2010 – Present
The yield data is converted from percentage form to decimal form before calibration.


⸻


Models Implemented
Vasicek Model
The Vasicek model assumes that interest rates follow a mean-reverting process:
[
dr_t = a(b-r_t)dt + \sigma dW_t
]
Where:
(a) = speed of mean reversion
(b) = long-run mean level
(\sigma) = volatility
(W_t) = Brownian motion
Advantages
Simple and computationally efficient
Closed-form bond pricing solutions
Limitations
Allows negative interest rates
Assumes constant volatility


⸻


Cox-Ingersoll-Ross (CIR) Model
The CIR model modifies the volatility term:
[
dr_t = a(b-r_t)dt + \sigma\sqrt{r_t}dW_t
]
Advantages
Ensures non-negative interest rates
Volatility increases with interest rate levels
Limitations
More complex calibration
Single-factor framework


⸻


Methodology
1. Data Collection
Download historical Treasury yields
Clean and preprocess data
2. Parameter Estimation
Maximum Likelihood Estimation (MLE)
Estimation of:


Mean reversion speed
Long-run mean
Volatility
3. Monte Carlo Simulation
Simulate 1,000 future interest rate paths
One-year forecasting horizon
Daily time steps
4. Bond Pricing
Estimate one-year zero-coupon bond prices using simulated discount factors
5. Stress Testing
Interest rate scenarios applied:
Scenario
Shift
Base
0 bps
Up 50bps
+0.50%
Down 50bps
-0.50%
Up 100bps
+1.00%
Down 100bps
-1.00%


⸻


Results
Estimated Parameters
Model
Mean Reversion
Long-Run Mean
Volatility
Vasicek
Estimated via MLE
Estimated via MLE
Estimated via MLE
CIR
Estimated via MLE
Estimated via MLE
Estimated via MLE
One-Year Zero Coupon Bond Prices
Model
Bond Price
Vasicek
~0.9586
CIR
~0.9582


⸻


Key Findings
Both models successfully capture mean-reverting behavior.
CIR prevents negative interest rates and provides more realistic rate dynamics.
Vasicek is easier to calibrate and interpret.
Bond pricing results from both models are broadly similar for the sample analyzed.
Stress testing demonstrates expected sensitivity of bond values to changes in long-run interest rate expectations.


⸻


Technologies Used
Python
NumPy
Pandas
SciPy
Matplotlib
yfinance
Jupyter Notebook


⸻


Repository Structure
├── Stochastic_IR.ipynb
├── README.md
└── plots/
    ├── treasury_yield_history.png
    ├── vasicek_paths.png
    ├── cir_paths.png
    └── stress_test_results.png


⸻


Future Improvements
Multi-factor interest rate models
Yield curve calibration
Interest rate derivative pricing
Time-varying parameter estimation
Model performance evaluation using out-of-sample forecasting


⸻


Author
Rachit Agarwal
Project developed as part of quantitative finance and financial engineering studies, demonstrating practical applications of stochastic interest rate modeling, Monte Carlo simulation, and fixed-income valuation.
