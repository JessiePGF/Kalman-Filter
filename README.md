# Kalman Filter - TAIEX

# Introduction
The TAIEX, a market capitalization-weighted index, was introduced in 1967 by the Taiwan Stock Exchange (TWSE) as the first benchmark index for the Taiwanese stock market.
This project applies the **Kalman Filter** to model and estimate the hidden state processes underlying the TAIEX return dynamics.

# How to do
1. Set starting values of hidden states based refernce.
2. Estimate parameters that maximize the likelihood function.
3. Found out model is really sensitive to initial values - even small changes can push the MLE to very different parameters spaces.
4. Use rt as a proxy for μt, and Δdt as a proxy for gt to run OLS regression.
5. Use regression result as the initial values.
6. Rerun Kalman filter with updated parameters to estimate hidden processes μ and g
7. Calculate the R square and plot

# Data
**Source：**[MacroMicro]  
**Frequency：**Monthly  
**Time Period：**2000-01-01 ~ 2025-08-31

# Reference
JULES H. van BINSBERGEN, RALPH S. J. KOIJEN(2010), Predictive Regressions: A Present-Value Approach, The Journal of Finance Vol. 65, No. 4 pp. 1439- 1471

# Result
- **R^2**  
  - R^2 = -14
  - Kalman Filter shows poor fit under the current specification
- **μ_t filtered**  
![μ_t result](plots/mu_t%20filtered.png)
- **g_t filtered**
![g_t result](plots/g_t%20filtered.png)