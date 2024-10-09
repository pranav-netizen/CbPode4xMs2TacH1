<h1>Problem Statement</h1>

In this problem we are given a dataset (40,000 records) from a call center company where their customers either subscribe or don't subscribe to a product called "term-deposits".
<br>
The ask is to build a model to predict if a customer will subscribe (achieving an accuracy of 81%) and also determine what makes them subscribe. 
<br>

<h1>Methodology</h1>
The solution was implemented in 3 layers where the first 2 are supervised and the last unsupervised (focusing only on the subscribers).
<br>
In the first layer the goal was to reduce the number of calls made that would mostly result in 'No' while preserving the most subscribers.
<br>
In the second layer the goal was to predict subscribers from the filtered dataset in the first layer.
<br>
In the 3rd layer, the goal was to discern what makes someone subscribe by focusing on the subscribers.
<br>
As a first step Exploratory data analysis (box plots, bar charts, pair plots, heat maps etc.) was conducted to gain an intuitive understanding of the underlying pattern.
<br>
In this step, outliers were removed from the dataset to be able to see patterns more clearly
<br>
The first layer goal was achieved manually without any models by simply observing where the most non-subscribers lie (while preserving most subscribers). 
<br>
For the 2nd layer, the following advanced ML techniques were applied in search of the best performing model. "best" means highest recall for the subscriber class with some precision.
<br>
<ol>
  <li>Feature selection on the original dataset</li>
  <li>Transformation of categorical variables using Label Encoding and One-Hot Encoding</li>
  <li>PyCaret</li>
  <li>SMOTE (tomek, ENN)</li>
  <li>Lazy Predict</li>
  <li>Tpot</li>
  <li>Optuna to tune the hyper-parameters of the best model</li>
</ol>
<br>
<h1>Findings/Conclusion</h1>
The overall conclusion of this project is that there is model that can capture 80% subscribers in just 9,312 phone calls, and this is the best model for this project.
<br>
This model is able to reduce 30,000+ calls which translates to 1,500+ hours saved.
<br>
In the first layer it was discovered that the numbers of calls can be reduced significantly by filtering those people whose contact method is "unknown".
<br>
It was discovered that the single most predictive factor is "duration"...people who talk on the phone for longer are more likely to subscribe.
