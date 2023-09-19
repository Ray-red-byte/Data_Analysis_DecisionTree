# Data Analysis Using Decision Tree from scratch
## Dataset1 : wine data 
### Data exploration (overview) <br />
  •	Data : 1023 instances (train), 244 instances (test) <br />
  •	Phrase : top phrase “going to a house party and…” <br />
  •	Target : 5 classes (3, 4, 5, 6, 7, 8) <br />
  •	The count of each features are not the same <br />
  =>	Dataset1 may contain duplicated data → cause bias, waste of time <br />
  =>	Dataset1 may contain missing value   → cause bias 
  ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/d9a860bd-442b-4918-8f8c-55726582cdc6)
  ▲ Fig.1 Summary of continuous features (Raw train) 
  
  ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/5720904b-2be2-4fa2-a103-d579970b7b6d)
  ▲ Fig.2 Summary of continuous features (Raw test) 
 
### Data exploration (univariate) <br />
•	The free_sulfur_dioxide, total_sulfur, and sulphates are positive skew. <br />
•	The class 5 and 6 dominate data → cause imbalanced data <br />
![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/ac7429f6-8d72-416e-8d6a-0786529c95ad)
▲ Fig.3 Class distribution     

![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/2a4e8494-1e8c-431e-a927-78a35e88dd06)
▲ Fig.4 Class distribution in each features  
 
### Data exploration (univariate) <br />
•The residual_sugar and chlorides have the most outlier <br />
  → affect the mean of the data, the variance of data ,then cause error. <br />
  
![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/7d523d5e-0933-47a8-baad-33eda9653a4a)
▲ Fig.5 Outliers in each features (boxplot) 
 
### Data exploration (bivariate) <br />
•The heatmap below show (citric_acid and fixed_acidity)(0.68), (fixed_ acidity and density)(0.67), (fixed_ acidity and pH)(-0.68) are high correlation. <br />
•The class and alcohal are the higest correlation, 0.49, there are no features highly   	correlated to target, so put all features training. <br />
  ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/d4ad0b34-809d-424c-a5c8-b6066ebf5f10)
▲ Fig.6 Relationship in each features (scatterplot) 

  ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/6bb309b5-494d-4d4e-bacc-fd54533f9b0d)
▲ Fig.7 Relationship in each features (heatmap)  


### Data cleaning <br />
• Drop duplicated data and imputation <br />
1.	Dataset1 imputation is based on group mean <br />
2.	After dropping, the missing value ratio among each feaures are all around 5%, it’s 
 	acceptable <br />
  ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/dceafb3d-8c22-4d65-8f80-2836a08b70ac)
▲ Fig.8 Missing value of features (After drop duplicated)

 
  • Remove the outliers, which are not in   <br />
1.	Lower : mean – 1.5*std <br />
2.	Upper : mean + 1.5*std <br />
   
  ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/1c3228c6-1272-4bbc-bba0-56df000b3a75)
▲ Fig.10 Summary of continuous features(After imputation, drop duplicated, and remove outliers)

### Evaluation <br />
•	Stratified sampling <br />
  Since imbalanced target, need to stratified sample based on target <br />
•	Calculate f1-score in each class  <br />
  Class 5, 6 are top 2 highest. Need to find another method to classify those two class. <br />
•	I think the low accuracy is that the data size is small, cause to underestimate. <br />
•	Two criterion show no difference   <br />
   1. Entropy (accuracy) = 0.56 <br />
   2. 2. Gini (accuracy) = 0.56 <br />
   ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/f1cb5422-0d5b-400d-8c57-2187aa66f140)
▲ Fig.11 Evaluation report of two criterion  

   
