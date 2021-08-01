# Fundamental-Factor-Model
This notebook is an experiment of creating factor models based on company fundamental data, such as revenue, EBIT, operation expense, asset, liabilities, and equity. The idea of this method was derived from the valuation model, such as DCF or DDM models when equity analysts trying to determine the intrinsic value of a company.  

The financial report data (10-K) of 500 large-cap companies from 2011 to 2021 was collected and utilized to created investment factors. The weight of each factor was optimized by a linear regression model, a random forest model, and an XGBoost model. A portfolio composite with the 20 stocks with the highest factor score was created for backtesting purposes. The return was calculated based on the real return data of each year. The backtested cumulative returns from the three models were also compared with that of the S&P500. The result turned out to be that the factors generated by the random forest model could provide the highest Sharpe ratio and cumulative return until the beginning of 2021 (the end date of the dataset). 

![image](https://user-images.githubusercontent.com/64211104/127787892-62a29707-ff38-49e2-8f90-47f9770bfae9.png)

The portfolio was rebalanced dynamically on the first trading day of the current year based on the factor generated from the companies' financial performance in the previous year. To make the factor better fit with market expectation, the rating from equity analyst was also involved in creating the factors.

The random forest model also provided details about the weights assigned to each category of fundamental data, listed as below:

![image](https://user-images.githubusercontent.com/64211104/127787993-d7696d77-58a2-4fb2-a0ac-a906f50905ea.png)

The results proved that the tree-based model could perform better than the linear model in creating a dynamic portfolio based on company financial performance.
