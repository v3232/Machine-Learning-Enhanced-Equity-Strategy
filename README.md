# Machine Learning-Enhanced Equity Strategy
This project explores the development of a quantitative equity trading strategy using machine learning to improve predictive performance. It involves gathering historical stock price data, engineering features, training a classifier, and analyzing portfolio returns.

## Project Overview
This notebook covers:

* Downloading and processing historical stock data via yfinance

* Engineering financial indicators and trading signals

* Splitting data into training and testing sets

* Using GradientBoostingClassifier for return prediction

* Evaluating model performance and strategy returns

##  Technologies Used
* Python

* Pandas, NumPy

* yFinance

* Scikit-learn

* HVPlot for visualization

## Machine Learning Model
A Gradient Boosting Classifier is trained to classify expected returns (up/down) based on engineered features. The model’s output is used to construct trading signals for a long/short portfolio.

## Performance Analysis
The notebook evaluates:

* Strategy accuracy

* Classification metrics

* Cumulative returns

* Visual comparison of predicted vs. actual returns