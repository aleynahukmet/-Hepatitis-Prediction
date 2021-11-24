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
   <img alt="Ekran Resmi 2021-06-28 01 15 28" src="https://user-images.githubusercontent.com/87663976/143287002-04dcdfb6-c57a-4c29-b0fa-5fbf772acf5f.png">
</p>

<p align="center"> 
   <img alt="Ekran Resmi 2021-06-28 01 15 28" src="https://user-images.githubusercontent.com/87663976/143285860-5d36a5f7-a89f-46c3-a92b-454e8f863fa1.png">
</p>

# Correlation 

<p align="center"> 
   <img alt="Ekran Resmi 2021-06-28 01 15 28" src="https://user-images.githubusercontent.com/87663976/143287156-61e789d5-4705-4b72-9c4d-fd4fd99f2995.png">

   # Label Encoding
We had only two categorical columns(category and sex). When it comes to the "category" column, the ordinal column is encoded with the label encoding method. The "sex" column is nominal and it is encoded with the one-hot encoding method. 

# Feature Scaling
I used the Standard Scaler for scaling the column sex with leaving out target column (category).

# Models 
We trained eight different models (KNN, Logistic, Random Forest,Decision Tree, Extra Trees, and Ada Boosting) to see which one is the giving best results. And with Grid Search and Cross Validation we pointed out the best models and parameters.
   



   | Model                | CV  Mean     |      Std     |
   | :------------------: | :----------: | :-----------:|
   |  KNN                 | 0.9878       | 0.0049       |
   |  Logistic            | 0.9979       | 0.0040       |
   |  Decision Tree       | 1.0          | 0.0          |
   |  Extra Trees         | 1.0	        | 0.0          |
   |  AdaBoost            | 1.0          | 0.0          |

   

<p align="center"> 
   <img alt="Ekran Resmi 2021-06-28 01 15 28" src="https://user-images.githubusercontent.com/87663976/143288668-103f9916-ac04-463a-84de-88086d2b1b1c.png">
</p>



