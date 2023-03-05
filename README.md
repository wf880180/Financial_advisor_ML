# Financial_advisor_ML
Create an algorithmic trading bot that learns and adapts to new data and evolving markets.

## Establish a Baseline Performance 
- Start Day : 2015-04-02 15:00:00
- End Day : 2015-07-02 15:00:00
- SMA :
	- short_window = 4
	- long_window = 100
- cumulative product of the actual returns vs. the strategy returns.</br>
![alt text](https://github.com/wf880180/Financial_advisor_ML/blob/main/README_image/Baseline_cumulative.png)
- Conclusions : </br>
![alt text](https://github.com/wf880180/Financial_advisor_ML/blob/main/README_image/classifier_1.png)

## Evaluate a New Machine Learning Classifier (Backtesting)
- LogisticRegression
	- cumulative product of the actual returns vs. the strategy returns.</br>
	![alt text](https://github.com/wf880180/Financial_advisor_ML/blob/main/README_image/Ls_backtest_cumulative.png)
	
	- Conclusions : </br>
	![alt text](https://github.com/wf880180/Financial_advisor_ML/blob/main/README_image/Ls_classification.png)

	- Did this new model perform better or worse than the provided baseline model? Did this new model perform better or worse than your tuned trading algorithm? </br>
