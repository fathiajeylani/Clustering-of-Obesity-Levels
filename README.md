# Prediction-of-Obesity-Levels

This project will use K Nearest Neighbor (KNN) algorithm to predict different obesity level categories. In addition to a KNN model, Pycaret will be used to evaluate the best model to use for the data. 


The data incudes the following variables that are associated with different obesity levels. 

- gender
- age
- height
- weight
- family history
- consumption of high calorie foods
- number of vegetables
- number of meals
- snacks
- smoking
- total water
- monitoring of calroies
- physical activity
- use of technology
- use of alcohol
- transportion mode

The variables mentioned will be used to clasify each data point into the following categories for the target variable

- Insufficient Weight
- Underweight
- Normal
- Overweight I
- Overweight II
- Obesity I
- Obesity II
- Obesity III

Initially looking at the data to evaluate the variables with the highest correlation to the target variable using a correlation matrix and heatmap. Both showed the variables age, weight, and family history to have the highest positive correaltions and the variables snacks and physical activity to the highest negative correlations. 

![image](https://github.com/fathiajeylani/Prediction-of-Obesity-Levels/assets/99691983/6d729f7b-c9b4-4115-8f44-714b99426f5d)


The KNN model yielded an accuracy of about 87% using K = 3 after evaluating the optimal k value. 

![image](https://github.com/fathiajeylani/Prediction-of-Obesity-Levels/assets/99691983/7a076931-77bc-4697-a125-a89b556993b1)

From plotting a confusion matrix, it showed the KNN model to have a total of 383 correct predictions. 

![image](https://github.com/fathiajeylani/Prediction-of-Obesity-Levels/assets/99691983/618af201-79df-4791-b48c-f96146e964ef)

Feature importance using the Lasso algorithm showed weight, family history, number of meals, physical activity and snacks to have the most importance. This was interesting to see because the heatmap showed age to also be included in variables with high correlation to the target variable but not included in the feature importance. 

 ![image](https://github.com/fathiajeylani/Prediction-of-Obesity-Levels/assets/99691983/bd25a914-5d52-48cd-9a61-c2fe161c0551)

Removing the variables that weren't important to the target variable didn't help with the accuracy of the KNN model but rather decreased it. This yeilded a 76% accuracy. 

Using Pycaret to determine the best model for our data, showed the Light Gradient Boosting Machine (LGBM) to have yield the best accuracy of 97%. 

Using the LGBM model for our data yielded an almost 98% accuracy. 

The confusion matrix for this model showed to have 793 correct predictions. This was much higher thant the KNN model. 

![image](https://github.com/fathiajeylani/Prediction-of-Obesity-Levels/assets/99691983/9af2de1a-2e1a-435c-bac6-87af739bb4ec)

Also looking at the feature importance for this model and excluding any of those ones that had a lower importance yielded a lower accuracy of 96%. 

![image](https://github.com/fathiajeylani/Clustering-of-Obesity-Levels/assets/99691983/0568301a-e291-48fc-9a68-77a6b8e1a7e2)

Overall, the LGBM model was better with performance compared to the KNN model. 

Future considerations would be to find a similar data set and compare how the model performs when introducing new but similar data. 


References:
Ali, M. (2021, November). PyCaret Tutorial: A beginner's guide for automating ML workflows using PyCaret. Datacamp. https://www.datacamp.com/tutorial/guide-for-automating-ml-workflows-using-pycaret?utm_source=google&utm_medium=paid_search&utm_campaignid=19589720830&utm_adgroupid=157156377071&utm_device=c&utm_keywor

Brownlee, J. (2021, January 5). Multi-Class Imbalanced Classification. Machine Learning Mastery. https://machinelearningmastery.com/multi-class-imbalanced-classification/

Data Normalization with Pandas. (n.d.). GeeksforGeeks. https://www.geeksforgeeks.org/data-normalization-with-pandas/

Mondal, A. (2023, August 17). Complete guide on how to Use LightGBM in Python. https://www.analyticsvidhya.com/blog/2021/08/complete-guide-on-how-to-use-lightgbm-in-python/

Obesity and overweight (2021, June 9). World Health Organization. https://www.who.int/news-room/fact-sheets/detail/obesity-and-overweight

Sathpathy, S. (2023, November 17). SMOTE for Imbalanced Classification with Python. Analytics Vidhya. https://www.analyticsvidhya.com/blog/2020/10/overcoming-class-imbalance-using-smote-techniques/#h-smote-synthetic-minority-oversampling-technique

Shafi, A. (2023, February). K-Nearest Neighbors (KNN) Classification with scikit-learn. Datacamp. https://www.datacamp.com/tutorial/k-nearest-neighbor-classification-scikit-learn?utm_source=google&utm_medium=paid_search&utm_campaignid=19589720830&utm_adgroupid=157156377311&utm_device=c&utm_keyword

Shetye, A. (2019, February 10). Feature Selection with sklearn and Pandas. Medium. https://towardsdatascience.com/feature-selection-with-pandas-e3690ad8504b

Zafar, A. (2022, February 15). Handling Outliers in Pandas. Medium. https://medium.com/@arsalan_zafar/handling-outliers-in-pandas-5cd872eef508#id_token=eyJhbGciOiJSUzI1NiIsImtpZCI6ImY4MzNlOGE3ZmUzZmU0Yjg3ODk0ODIxOWExNjg0YWZhMzczY2E4NmYiLCJ0eXAiOiJKV1QifQ.eyJpc3MiOiJod
