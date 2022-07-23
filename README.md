# Risk Assessment & Capitalization Rate Prediction
As per the note of risk assessment in any portfolio of clients, financial institutions are expected to hold capital reserves sufficient to withstand unlikely circumstances but potentially catastrophic loss events. Sometimes it is hard to forecast such events and on account of this, the reserve for risky loans is higher than the reserve for a safer loan. However, the loss calculations are too cumbersome to be scrutinized every time someone seeks a loan. 

The purpose of this project is to estimate those loss calculations, with a machine learning approach that could be fast enough to utilize during lending, but adequately accurate to avoid under- or over-pricing loans. As per given datasets, one is for development or training for the model and another to test or evaluate the target variables. The variables comprise both numerical and categorical data types. 

**Target Variable Description**
| Column | Description |
| :------: | :------: |
| Capital - EL Tail Risk Contribution (Capped) | The capital amount required to cover exposure losses for the instrument in the case of an extraordinary loss event in the portfolio. |
| Capitalization Rate - EL Tail Rist Contribution | Proportion of Capital and MTM Exposure. |

> Capitalization Rate (%) = Capital (<span>$</span>) / MTM Exposure (<span>$</span>)


**Outline**

The different data visualization methods were implemented with target variables to analyze the relation. The heatmap of correlation portrays a close correlation between MTM exposure and book exposure. It results in the highest correlation of target variables with MTM exposure, book exposure, and commitment variables. The insignificant categorical variables were dropped. The approach of feature scaling was used on instrument subtype and converted into binary by label encoding. I found the indexes of outliers from the time to maturity variable and dropped it for significant performance. Basically, I started with linear regression and achieved quite a good accuracy from the ridge model. Then I made a pipeline to execute PCA with all concerned models and data standardized by a standard scaler. A dictionary pool having all the models with the considerable random state was used with a loop to perform and compare the results of given models with PCA. The decision tree model gave the highest accuracy above all and visualized the feature's importance through a horizontal bar graph which conveys precise features. As per my insights, I tried the ExtraTrees regressor and it yielded pretty good performance, the lowest MAE and considerable accuracy go with it.


**Evaluation and Conclusion**

| Model Name | MAE | R2 Score |
| :-----: | :-----: | :-----: |
| Decision Tree | 5422.17 | 0.82 |
| Random Forest | 4140.78 | 0.73 |
| Gradient Boosting | 6948.01 | 0.66 |
| XGBoost | 4428.25 | 0.64 |
| Extra Trees | 3904.1 | 0.76 |
| Neural Network | 13398.22 | 0.46 |

The calculation of the loss function is more important when lending a loan to analyze the risk factor and handle the reserve funds for any circumstances. The purpose of this project is to estimate those loss calculations, with a machine learning approach that could be fast enough to utilize while lending loans or bonds. In the dataset, there are 10 numeric variables and 6 categorical variables which excludes two target-dependent variables. In the wake of implementing and assessing, I observed that the best performing models are Random Forest, Decision Tree, and Extra Trees. Furthermore, we implemented feature scaling and PCA technique but the results were not as significant as individual performance. To sum up, test evaluation and outright insights can be implemented in financial institutions that will help to assist the smooth lending process quickly and precisely.

For software requirements, the system should be exposed to [anaconda environment](https://www.anaconda.com/products/distribution) and required libraries should be installed.

Copyrights © 2022 by Neel Patel.
All rights are reserved.
