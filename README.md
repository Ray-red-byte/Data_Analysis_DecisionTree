# Data Analysis Using Decision Tree from scratch
## Introduction
  This project use Dataset (wine data & rotten tomatos data), but these datasets are imbalanced data and missing value.
  As a result, contain 4 parts to improve f1-score <br />
  1. data exploaration <br />
  2. data cleaning <br />
  3. data visualization <br />
  4. train / test / prediction (Decision Tree) <br />
  

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


## Dataset2 : Rotten Tomatos reviews
### Data exploration (overview): <br />
•	Data : 124848 instances (train) <br />
•	Phrase : top phrase “going to a house party and…” <br />
•	Sentimental : 5 classes (0, 1, 2, 3, 4) <br />
  ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/f6b04a83-b0f5-4b87-9a59-8b184178721e)
  ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/1f3136dc-654d-4186-9a56-7ca5778b1471) <br />
▲ Fig.12 Summary of phrase data and sentimental outcome(train) 
 
•	Data : 31211 insatnces (train) <br />
•	Phrase : top phrase “finds a way to make J.K. Rowling’s marvelo…” <br />
  ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/1f53dc1a-18c0-449b-b3cc-85fb6ddedccc)
▲ Fig.13 Summary of phrase data and sentimental outcome(test) 
 
 
### Data exploration (class distribution): <br />
•	The positive contain the most different length  <br />
•	The neutral contain the most intensive phrase length <br />
  ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/7bd9dd4b-2744-4ca9-83b8-50f131d69dfa)
▲ Fig.14 Class distribution of different phrase length 
 
•	Class 2 is the largest amount, followed by class 3 <br />
 → imbalanced data cause bias  <br />
  ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/3ec8ff28-9d8b-4fa0-966e-3aa48d18d61c)
▲ Fig.15 Class distribution 
 
 
### Data cleaning  <br />
•	Remove HTML tags using BeautifulSoup <br />
•	Keep only alphabetic characters using a regular expression <br />
•	Tokenize the text into individual words <br />
•	Remove stopwords (NLTK library) <br />
•	Perform lemmatization on the words (NLTK library) <br />
→There are 156059 words in the whole dataset2(Train and Test data) <br />
 
 
### Data transformation  <br />  
•	Use TF-IDF(term frequency-inverse document frequency) from scikit-learn TfidfVectorizer to give each words a score that how   
  important to documents. <br />
  ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/fb2e6916-3218-44de-ba67-af2c500b0c95)
  (picture: https://medium.com/%E6%B7%B1%E6%80%9D%E5%BF%83%E6%80%9D/ml-
%E7%94%A8%E5%9C%A8nlp-%E7%9A%84-tf-idf-51dac088a79) <br />
•	Set max_features=1000, remain top 1000 important words <br />
→ new data rows :instances(156059), columns :words(1000) <br />
• Top 50 important words that the total score to all docs are highest <br />
  ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/8005a364-189d-4ff7-8be9-6b5091b59c05)
▲ Fig.16 Top 50 important words  
 
 
### Evaluation <br />
•	Stratified sampling <br />
  Since imbalanced target, need to stratified sample based on target <br />
•	Calculate f1-score in each class <br />
  Class 2 (neutral) is highest. Because class 2 dominate the train data, lots of other class prediction are class 2 in confusion matrix <br />
•	I think the low accuracy is that only consider importance to documents in eeah words is not enough, need to find the relationship in each words and sequences. <br />
•	Two criterion show no difference <br />
1.	Entropy (accuracy) = 0.51 <br />
2.	Gini (accuracy) = 0.51 <br />
   ![image](https://github.com/Ray-red-byte/Data_Analysis_DecisionTree/assets/72739609/e21bf34c-18d2-4702-912a-86e0fbe13a3d)
▲ Fig.17 Evaluation report of two criterion  


   
