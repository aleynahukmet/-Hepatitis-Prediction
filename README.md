# -Hepatitis-Prediction
<p align="center"> 
   <img width="1000" height="400" alt="Ekran Resmi 2021-06-28 01 15 28" src="https://user-images.githubusercontent.com/87663976/143283954-3fb39162-3e77-469a-9ba2-0be5d93c8694.jpg">
</p>

In this project, we are trying to predict whether a person is hepatitis or healthy depending on some other variables. We first, analyzed data and see the relations between features, and then we trained different machine learning models to help us predict hepatitis.

# Dataset

The data set contains laboratory values of blood donors and Hepatitis C patients and demographic values like age.All attributes except Category and Sex are numerical.
Attributes 1 to 4 refer to the data of the patient:
1) X (Patient ID/No.)
2) Category (diagnosis) (values: '0=Blood Donor', '0s=suspect Blood Donor', '1=Hepatitis', '2=Fibrosis', '3=Cirrhosis')
3) Age (in years)
4) Sex (f,m)
Attributes 5 to 14 refer to laboratory data:
5) ALB
6) ALP
7) ALT
8) AST
9) BIL
10) CHE
11) CHOL
12) CREA
13) GGT
14) PROT

The target attribute for classification is Category (2): blood donors vs. Hepatitis C patients 

# Data Preprocessing

Firstly, I checked the duplicated rows and saw there were none. After that, I dropped the unnamed:0 column (which represents the ID of patients) because I did not need it. After that, I filled the missing values with the median method.

# Exploratory Data Analysis

I used some visualization methods to have a better understanding of features' relation, and also their effects on hepatitis.
<p align="center"> 
   <img alt="Ekran Resmi 2021-06-28 01 15 28" src="ttps://user-images.githubusercontent.com/87663976/143285793-eaedbc83-415a-4817-bfff-b7f16e7ac1f0.png">
</p>

<p align="center"> 
   <img alt="Ekran Resmi 2021-06-28 01 15 28" src="https://user-images.githubusercontent.com/87663976/143285860-5d36a5f7-a89f-46c3-a92b-454e8f863fa1.png">
</p>

# Correlation 

<p align="center"> 
   <img alt="Ekran Resmi 2021-06-28 01 15 28" src="https://user-images.githubusercontent.com/87663976/143219223-4451b45d-d5ab-4aaa-86a4-37caf145171a.png">
</p>

As it can be seen on the correlation matrix some features had a high correlation between them. When independent features are highly correlated i.e. have the same nature, then they introduce the element of variance in the model which is called Multi-Collinearity. Multi-Collinearity is not good for our models so I dropped some of the columns to avoid that.

# Label Encoding
We had only two categorical columns. When it comes to the "status" column, the ordinal column is encoded with the label encoding method. The "country" column is nominal and it is encoded with the one-hot encoding method. And I encoded "country" column with one-hot encoding method I dropped one column to avoid Multi-Collinearity.

# Feature Scaling
Robust Scaler is one of the best scaler methods to use when a dataset contains outliers. As seen previously, our dataset had outliers and we did not remove or replace them. Outliers can skew a probability distribution and make data scaling using standardization difficult as the calculated mean and standard deviation will be skewed by the presence of the outliers. Therefore, we choose RobustScaler for our Feature scaling.

# Models 
We trained eight different models (Lasso, Ridge, Random Forest, KNN, Decision Tree, SVR, Gradient Boosting Regressor and Ada Boosting Regregssor) to see which one is the giving best results. Then I checked results after cross validation too and plotted the results.

# R2 Scores


   | Model                | CV R2 Mean   |      Std     |
   | :------------------: | :----------: | :-----------:|
   |  Lasso               | 0.9481       | 0.0143       |
   |  Ridge               | 0.9481       | 0.0143       |
   |  Random Forest       | 0.9611       | 0.0078       |
   |  KNN                 | 0.839148	  | 0.0123       |
   |  Decision Tree       | 0.8926       | 0.0149       |
   |  SVR                 | 0.8328       | 0.0224       |
   |  Gradient Boosting   | 0.9497       | 0.0074       |
   |  Ada Boosting        | 0.8921       | 0.0126       |

<p align="center"> 
   <img alt="Ekran Resmi 2021-06-28 01 15 28" src="https://user-images.githubusercontent.com/87663976/143229476-dfa19181-73d5-4a0b-8919-763ec6d82cc6.png">
</p>
