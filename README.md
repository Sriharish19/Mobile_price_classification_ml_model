# **Mobile Price Range Prediction**

# Problem Statement:

In the competitive mobile phone market companies want to understand sales data of mobile phones and factors which drive the prices. Mobile phones come in all sorts of prices, features, specifications etc and estimating the price of mobile phones is an important part of consumer strategy.

The objective of this project is to find out some relation between features of a mobile phone and its selling price. In this problem, we do not have to predict the actual prices but a price range indicating how high the price is. The dataset contains 2000 records of mobile phone information with 20 features which is a mix of categorical features and numerical features.

# Data Description:

The dataset contains 2000 records and 21 features which consists of:

● Battery_power: Total energy a battery can store in one time measured in mAh.

● Blue: Has bluetooth or not

● Clock_speed: Speed at which the microprocessor executes instructions

● Dual_sim: Has dual sim support or not

● Fc: Front camera megapixels

● Four_g: Has 4G access or not

● Int_memory: Internal memory in gigabytes

● M_dep: Mobile depth in cm

● Mobile_wt: Weight of mobile phone

● N_cores: Number of cores of processor

● Pc: Primary camera megapixels

● Px_height: Pixel resolution height

● Px_width: Pixel resolution width

● Ram: Random Access Memory in megabytes

● Sc_h: Screen height of mobile in cm

● Sc_w: Screen width of mobile in cm

● Talk_time: Longest time that a single battery charge will last when you are talking over phone

● Three_g: Has 3G access or not

● Touch_screen: Has touch screen or not

● Wifi: Has wifi or not

● Price_range: This is the target variable with values of 0(low cost), 1(medium cost), 2(high cost) and 3(very high cost).

# Data Exploration:

The distribution of the target variable shows us that the classes are almost balanced as the difference between the classes is minimal. Thus, we know that there’s no class imbalance problem here. All the classes have around 450 records.

The distribution of the categorical features are almost similar to each other except the feature ‘three_g’ which contains very few mobile phones which do not have 3G access. We can infer that almost all phones have 3G access if not 4G.

Most of the numerical features follow an uniform distribution except a few features like fc, px_height, and sc_w follow a right skewed distribution.

The distribution of categorical features across different price ranges stays the same. There is a slight increase in the count of mobile phones in the very high cost category for each categorical feature. Thus we can infer that the more we pay, the more choices we can get.

The distribution of the numerical features across different price ranges shows us that only the features RAM, battery power, px_height and px_width increase with an increase in price. These features are the most influential in determining the price ranges.

RAM has the strongest correlation with the target variable followed by battery power, px_height and px_width. Rest of the numerical features have a very low correlation with the target variable.

# Modeling:

We have used several classification models to predict the mobile price range and compare their performances.

|Models	|Accuracy|	Precision	|Recall	|ROC-AUC|
|---|---|---|---|---|
|Logistic Regression	|96.43%|	96.45%|	96.43%|	99.75%|
|SVM	|96.15%	|96.16%	|96.15%|	99.87%|
|KNN	|91.76%	|91.76%	|91.76%|	97.75%|
|XGBoost	|90.66%|	90.75%	|90.66%|	99.09%|
|Random Forest	|89.56%	|89.58%|	89.56%|	98.88%|
|Gradient Boosting	|89.28%	|89.24%|	89.28%	|98.79%|


All the algorithms have provided us with a good result for predicting the mobile price range. As our target classes are balanced, we can consider accuracy as an important metric to measure and compare our models. The accuracy achieved by most of the models is above 90% which proves that the models have classified the data well.

Logistic Regression along with SVM has performed the best out of all the models as they have achieved an accuracy of 96% and also scored well in precision, recall and roc auc. The tree based methods have performed poorly in comparison to the other classification models implemented.


