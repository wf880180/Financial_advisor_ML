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

Base on the higher recall this model is better predict 1 than -1, and the -1's recall almost equal to 0 that the prediction almost did nothing.

## Tune the Baseline Trading Algorithm
- Change the time period :
	- Start Day : 2015-04-02 15:00:00
	- End Day : 2015-10-02 15:00:00
	- SMA :
		- short_window = 4
		- long_window = 100
	- cumulative product of the actual returns vs. the strategy returns.</br>
	![alt text](https://github.com/wf880180/Financial_advisor_ML/blob/main/README_image/6monthCumulative.png)

	- Conclusions : </br>
	![alt text](https://github.com/wf880180/Financial_advisor_ML/blob/main/README_image/Classifier_6month.png)


	Compare to original test case we want to improve the -1 F1 score and recall, and this change did increase. However, the new test case changed the 1's condiction and decrease a lot of 1's precision, recall and F1-score.

	- What impact resulted from increasing or decreasing the training window?
	The -1 test case increased so that -1 F1 score increased. However, the 1 test cases didn't increase too much so that 1's F1 decrease.
- Change SMA input features :
	- Start Day : 2015-04-02 15:00:00
	- End Day : 2015-10-02 15:00:00
	- SMA :
		- short_window = 5
		- long_window = 75
	- cumulative product of the actual returns vs. the strategy returns.</br>
	![alt text](https://github.com/wf880180/Financial_advisor_ML/blob/main/README_image/6monthSMA5_75_cumulative.png)	

	- Conclusions : </br>
	![alt text](https://github.com/wf880180/Financial_advisor_ML/blob/main/README_image/Classifier6monthSMA5_75.png)

	Compare to 6 month test case we want to improve the overall F1 score and recall, and this change did increase overall score. 

	- What impact resulted from increasing or decreasing either or both of the SMA windows?</br>
	Both 1 and -1 accuracy hase increase with this parameter because the 1 and -1 test cases are more balance by decrease the band of SMA.

- The better cumulative result:
	- Start Day : 2015-04-02 15:00:00
	- End Day : 2015-10-02 15:00:00
	- SMA :
		- short_window = 4
		- long_window = 72
	- cumulative product of the actual returns vs. the strategy returns.</br>
	![alt text](https://github.com/wf880180/Financial_advisor_ML/blob/main/README_image/6monthSMA4_72_cumulative.png)	

	- Conclusions : </br>
	![alt text](https://github.com/wf880180/Financial_advisor_ML/blob/main/README_image/Classifier6monthSMA4_72.png)
	
	Compare to 6 month test case we want to improve the overall F1 score and recall, and this change did increase overall score. 

## Evaluate a New Machine Learning Classifier (Backtesting)
- LogisticRegression
	- cumulative product of the actual returns vs. the strategy returns.</br>
	![alt text](https://github.com/wf880180/Financial_advisor_ML/blob/main/README_image/Ls_classification.png)

	- Conclusions : </br>
	![alt text](https://github.com/wf880180/Financial_advisor_ML/blob/main/README_image/Ls_backtest_cumulative.png)
	
	Base on the higher recall this model is better predict 1 than -1, and the -1's recall almost equal to 0 that the prediction almost did nothing.
	- Did this new model perform better or worse than the provided baseline model? Did this new model perform better or worse than your tuned trading algorithm? </br>
	The ls 1's precision is higher than the svc, and ls's F1 score is higher both 1 and -1 than SVC.
