# Employee-Retention-Analysis
Project devoted to the investigation of the employee retention in the fictitious company Salifort Motors based on the HR survey.

This project is the conclusion of Google Advanced Data Analytics course to demonstrate all skills acquired within the intensive 250-hour long course. 

Project Overview: The dataset from the latest HR survey was used for the project. It included the results from about 15 thousand of employees of the company to reflect their situation (e.g., satisfaction score, last evaluation results, salary level, etc.). This data was a basis for the detailed exploratory data analysis, data cleaning, visualisation and modelling. The resulting random-forest model is able to predict with high f1, recall and precision values, if an employee may be prone to leave the company based on his/her personal survey results.

Business Understanding: The company has observed in recent years that the retention time of employees in the company is not that high, many employees tend to leave the company which costs the company tremendous efforts and finances to recruit and teach new employees. The management of the company together with the HR department would like to understand better what makes the employees resign from the company and would like to use this information to take preventive measures and avoid the potential resignations. The stakeholders would like to see the factors that affect the resignation the most and have a model in their hands which can be used for the future surveys to predict which employees would tend to leave the company.

Data Understanding: The dataset received from HR department contained about 15 thousand of entries. During the exploratory data analysis it turned out, that about 3000 rows were duplicates of other rows. It is very unlikely that some employees could have completely the same results on 10 indicators (some of them had the continuous values, not discrete or categorical). Therefore, these rows were dropped and the later analysis was done on 12 thousand rows. The data was of a surprisingly good quality without any missing values, however there was some imbalance between employees that left and stayed in the company. Most of the employees in the dataset had the tenure of less than 6 years, while the other few percents worked 7 or more years in the company. These were treated as outliers for the logistic regression and were dropped in one of the iterations, however they did not pose any issue for the random forest modelling. Multiple visualisations at the EDA stage helped to dive into valuable insights on which categories of employees tend to resign.

Modelling and Evaluation: Firstly, logistic regression was applied on the dataset with the outliers, then on the one without them. In both cases the results were poor and insufficient for any further application (f1-score of 0.33, the model was predicting quite good those who are definitely not planning to leave the company, so-called true negative values, but it was failing to predict true positive - those who may be leaving the company). Therefore, it was decided to use the random forest modelling for a better prediction. Two iterations were done: one without and one with some feature engineering. The later was used for the prediction on the test dataset. The results were found to be good enough for the future usage (f1-score of 0.89, accuracy of 0.96, meaning that the model predicts the employees who may leave the company quite accurately without missing many of them and without predicting falsely many employees who do not tend to leave as if they would leave). The most important factors affecting if employees leave are: last evaluation result, number of projects, tenure, salary and overtimes.

![image](https://github.com/user-attachments/assets/25c269f0-ce6b-4845-8d80-ee873c364723)


Conclusion: The analysis and modelling have shown that many employees suffer from a great number of projects and extra hours they do, which often results in their resignation. It looks like that either the employees are not aware of the overtime policies or the management is not taking any actions to split the projects better and avoid the distortion of work-life balance. Moreover, there is some salary gap between more and less experienced colleagues which may affect their satisfaction, too. It is recommended for the stakeholders to check these factors.
