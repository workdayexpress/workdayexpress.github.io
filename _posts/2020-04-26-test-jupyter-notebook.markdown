---
layout: post
title:  "Test Jupyter Notebook"
date:   2020-04-25 21:58:30 +0200
categories: jekyll update
---
This is a simple blog to test blogging a jupyter notebook.

# A simple regression

                                OLS Regression Results                            
    ==============================================================================
    Dep. Variable:                      y   R-squared:                       0.231
    Model:                            OLS   Adj. R-squared:                  0.215
    Method:                 Least Squares   F-statistic:                     14.58
    Date:                Sun, 26 Apr 2020   Prob (F-statistic):           2.92e-06
    Time:                        09:20:21   Log-Likelihood:                -23.879
    No. Observations:                 100   AIC:                             53.76
    Df Residuals:                      97   BIC:                             61.57
    Df Model:                           2                                         
    Covariance Type:            nonrobust                                         
    ==============================================================================
                     coef    std err          t      P>|t|      [0.025      0.975]
    ------------------------------------------------------------------------------
    const          1.4828      0.096     15.470      0.000       1.293       1.673
    x1            -0.0268      0.118     -0.227      0.821      -0.262       0.208
    x2             0.6320      0.119      5.302      0.000       0.395       0.869
    ==============================================================================
    Omnibus:                       28.826   Durbin-Watson:                   2.173
    Prob(Omnibus):                  0.000   Jarque-Bera (JB):                5.671
    Skew:                          -0.004   Prob(JB):                       0.0587
    Kurtosis:                       1.833   Cond. No.                         6.23
    ==============================================================================
    
    Warnings:
    [1] Standard Errors assume that the covariance matrix of the errors is correctly specified.


# Double the sample can increase the p-value

                                OLS Regression Results                            
    ==============================================================================
    Dep. Variable:                      y   R-squared:                       0.231
    Model:                            OLS   Adj. R-squared:                  0.223
    Method:                 Least Squares   F-statistic:                     29.60
    Date:                Sun, 26 Apr 2020   Prob (F-statistic):           5.74e-12
    Time:                        09:20:21   Log-Likelihood:                -47.759
    No. Observations:                 200   AIC:                             101.5
    Df Residuals:                     197   BIC:                             111.4
    Df Model:                           2                                         
    Covariance Type:            nonrobust                                         
    ==============================================================================
                     coef    std err          t      P>|t|      [0.025      0.975]
    ------------------------------------------------------------------------------
    const          1.4828      0.067     22.047      0.000       1.350       1.615
    x1            -0.0268      0.083     -0.323      0.747      -0.191       0.137
    x2             0.6320      0.084      7.556      0.000       0.467       0.797
    ==============================================================================
    Omnibus:                       76.837   Durbin-Watson:                   2.173
    Prob(Omnibus):                  0.000   Jarque-Bera (JB):               11.342
    Skew:                          -0.004   Prob(JB):                      0.00344
    Kurtosis:                       1.833   Cond. No.                         6.23
    ==============================================================================
    
    Warnings:
    [1] Standard Errors assume that the covariance matrix of the errors is correctly specified.


**Verify the standard error calculation**
0.118 * np.sqrt((N-3)/(2*N-3))

    0.08280084356714895

# Replicate the data 100 times can make the coefficient of x1 significant

                                OLS Regression Results                            
    ==============================================================================
    Dep. Variable:                      y   R-squared:                       0.231
    Model:                            OLS   Adj. R-squared:                  0.231
    Method:                 Least Squares   F-statistic:                     1517.
    Date:                Sun, 26 Apr 2020   Prob (F-statistic):               0.00
    Time:                        09:20:21   Log-Likelihood:                -2411.8
    No. Observations:               10100   AIC:                             4830.
    Df Residuals:                   10097   BIC:                             4851.
    Df Model:                           2                                         
    Covariance Type:            nonrobust                                         
    ==============================================================================
                     coef    std err          t      P>|t|      [0.025      0.975]
    ------------------------------------------------------------------------------
    const          1.4828      0.009    157.838      0.000       1.464       1.501
    x1            -0.0268      0.012     -2.312      0.021      -0.050      -0.004
    x2             0.6320      0.012     54.095      0.000       0.609       0.655
    ==============================================================================
    Omnibus:                     6618.059   Durbin-Watson:                   2.174
    Prob(Omnibus):                  0.000   Jarque-Bera (JB):              572.767
    Skew:                          -0.004   Prob(JB):                    4.22e-125
    Kurtosis:                       1.833   Cond. No.                         6.23
    ==============================================================================
    
    Warnings:
    [1] Standard Errors assume that the covariance matrix of the errors is correctly specified.
