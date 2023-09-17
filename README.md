# Data Analysis Using Decision Tree from scratch
## Dataset1 : wine data 
Data exploration (overview) <br />
<pre>
  •	Data : 1023 instances (train), 244 instances (test) <br />
  •	Phrase : top phrase “going to a house party and…” <br />
  •	Target : 5 classes (3, 4, 5, 6, 7, 8) <br />
  •	The count of each features are not the same <br />
  1.	Dataset1 may contain duplicated data → cause bias, waste of time 
  2.	Dataset1 may contain missing value   → cause bias 
</pre>
  ![alt text](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/56d7f234-f618-4c21-a7fb-f8ac4a79576b)
  ▲ Fig.1 Summary of continuous features (Raw train) 
  
  ▲ Fig.2 Summary of continuous features (Raw test) 
 
 
 
 
 
 
 
Data exploration (univariate) 
•	The free_sulfur_dioxide, total_sulfur, and sulphates are positive skew. 
•	The class 5 and 6 dominate data → cause imbalanced data 
      
▲ Fig.3 Class distribution    
 
      
▲ Fig.4 Class distribution in each features  
 
 
 
 
Data exploration (univariate) 
•The residual_sugar and chlorides have the most outlier 
  → affect the mean of the data, the variance of data ,then cause error. 
  
  
▲ Fig.5 Outliers in each features (boxplot) 
 
Data exploration (bivariate) 
•The heatmap below show (citric_acid and fixed_acidity)(0.68), (fixed_ acidity                  	and density)(0.67), (fixed_ acidity and pH)(-0.68) are high correlation. 
•The class and alcohal are the higest correlation, 0.49, there are no features highly   	correlated to target, so put all features training. 
  
▲ Fig.6 Relationship in each features (scatterplot) 
 
  
▲ Fig.7 Relationship in each features (heatmap)  
Data cleaning 
• Drop duplicated data and imputation 
1.	Dataset1 imputation is based on group mean 
2.	After dropping, the missing value ratio among each feaures are all around 5%, it’s 
 	acceptable 
  
▲ Fig.8 Missing value of features (After drop duplicated) 
  
▲ Fig.9 Summary of continuous features (After imputation,drop duplicated) 
 
  • Remove the outliers, which are not in   
1.	Lower : mean – 1.5*std 
2.	Upper : mean + 1.5*std 
   
  
▲ Fig.10 Summary of continuous features  
(After imputation, drop duplicated, and remove outliers)  
Evaluation 
•	Stratified sampling 
 Since imbalanced target, need to stratified sample based on target 
•	Calculate f1-score in each class  
 Class 5, 6 are top 2 highest. Need to find another method to classify those two class. 
•	I think the low accuracy is that the data size is small, cause to underestimate. 
•	Two criterion show no difference   
   1. Entropy (accuracy) = 0.56     2. Gini (accuracy) = 0.56 
   
▲ Fig.11 Evaluation report of two criterion  

   
