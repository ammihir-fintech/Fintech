# Euro ETF

## Instructions

At any given moment in the exchange-traded fund (ETF) market, there is a price at which sellers are willing to sell, and a price at which buyers are willing to buy. The closest discrepancy between selling and buying prices is referred to as the bid-ask spread.

In this activity, you will analyze the autocorrelation of a ETF bid-ask spread.

1. Open the dataset and parse the `timestamp` column as datetime, and set it as the index.

2. Resample the dataframe at 10-second intervals and obtain the mean. Drop all NaNs.

3. Obtain the autocorrelation value at a lag of 1. If you like, repeat the process for another lag, e.g., 2.

4. Plot the ACF and PACF.

5. How many significant lags do you see in these plots, outside the default confidence interval of 95%?

### Hints

To start the autocorrelation plot at 1 lag (instead of 0), you will want to set the zero parameter to false (`zero=False`). Add this parameter to both the `plot_acf` and `plot_pacf` functions.

---

© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.