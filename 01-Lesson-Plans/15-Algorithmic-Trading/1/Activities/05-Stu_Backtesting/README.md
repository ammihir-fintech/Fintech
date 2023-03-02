# The Big Short, Part II

The real estate bubble that led to the 2008 financial crisis resulted in one of the worst economic disasters since the Great Depression. During this period, housing prices plummeted, throwing the US economy into freefall and causing the stock market to crash. Some keen investors profited off of the recession by *shorting* the market or placing bets that the market would fall. Most, however, lost substantial value from their investment portfolios, including much needed retirement and savings accounts.

Now that you have developed a Short Position Dual Moving Average Crossover Trading Strategy and determined that the algorithm could have *made* money during the 2008 financial recession, it is now time to determine *how much* money could have been made.

## Instructions

The pre-requisite steps for developing the Short Position Dual Moving Average Crossover trading strategy have already been provided for you. Therefore, continue onwards to the backtesting parts of the notebook file.

Using the [starter file](Unsolved/the_big_short_part_2.ipynb), complete the following steps:

1. Set an `initial_capital` variable to 100000, representing the simulated starting portfolio value.

2. Set a negative `share_size` value of -500.

3. Create a new column `Position` by multiplying the `share_size` by the values in the `Signal` column.

4. Create a new column `Entry/Exit Position` by using the `diff` function on the `Position` column.

5. Create a new column `Portfolio Holdings` by multiplying the `Close` prices of VNQ by the cumulative sum of the values of the `Entry/Exit Position` column.

6. Create a new column `Portfolio Cash` by subtracting the `initial_capital` by cumulative sum of the product of the `Close` prices of VNQ and the values of the `Entry/Exit Position` column.

7. Create a new column `Portfolio Total` by adding the values of the `Portfolio Cash` and `Portfolio Holdings` columns.

8. Create a new column `Portfolio Daily Returns` by using the `pct_change` function on the `Portfolio Total` column.

9. Create a new column `Portfolio Cumulative Returns` by using the `cum_prod` function on the `Portfolio Daily Returns` column.

10. Use the `figure` and `axes` objects of the `matplotlib` library to plot the Short Position Dual Moving Average Crossover trading strategy against its backtesting results.

## Hint

Remember that shorting a stock means to sell shares of a stock and then buy or cover the shares at a later point in time. Therefore, share sizes relative to backtesting calculations should be negative.

---

© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.