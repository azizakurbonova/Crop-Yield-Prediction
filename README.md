# Crop-Yield-Prediction
Authors: Aziza Kurbonova, Florjon Haxhija

We built an ML model that provides a recommendation for farmers on the most suitable crops to grow on a particular farm based on various parameters, such as soil composition and climate data. There is existing research literature that works on this problem as well as a Kaggle problem dataset, defining the most suitable crop as the one that returns the greatest yield. The data that all of this literature works on are limited to India. We intend to replicate the methods used in the literature, with some modifications to the problem scope. First, we intend to curate a similar dataset with the same parameters as found in the literature based in the United States, using publicly available datasets from the U.S. Department of Agriculture. Second, we want to explore adding additional parameters to what constitutes the most suitable crop.


We intend to curate recommendations for the most suitable crop that gives the highest crop yield to farmers in their respective regions. These regions will include the entirety of the United States, specifically demonstrating our results state by county level. We’re also intending to give the highest accuracy report on the most suitable crop with a given specific data region. 


Before delving into the machine learning model, we must make sure that we’re using a suitable dataset for our model. We chose to use the U.S. Department of Agriculture Natural Resource Conservation Service to pull data, roughly 1 million randomly selected data points, and collapse certain features that weren’t needed. 


Due to the Natural Resource Conservation Service having empty columns (features), we decided to strip those from our finalized dataset as well with any null values in other categorical columns. The dataset also presented us with two types of yield data, yield with irrigation of the soil, and yield without irrigation. To combine these two types of data into our dataset, we chose to concatenate the yield of the two different states of soil. We also changed the units of all crop yields to be of metric tons, standardized numeric features in our dataset, and created variables in our dataset for our crop name and month. Through all of these efforts, we dwindled our amount of instances in the dataset to 291840 points. A sample of our dataset is shown here: 

Moving on to the technical details of the machine learning models, we created a train test split of 2/3 for training and 1/3 for testing. We decided to have a total of 3 different models tested with our dataset, a Linear Regression model with Ridge + Lasso Regularization & MAE/MSE Loss Functions, a Decision Tree Regression model w/ MAE, and a Random Forest Regressor model. To get the lowest possible error between our train and test split, we had to do hyperparameter tuning for each model. For our decision tree model, we chose the lowest error that occurred when the max depth was 20 with a minimum sample split of 5 which also had the lowest MAE at 0.01; Furthermore, for our random forest regressor, we chose our n estimators to be 70, max depth to be 12 and a minimum sample split of 2 which had the lowest test MSE at 0.045. 

Works Cited:

Dahiphale, Devendra; Shinde, Pratik; Patil, Koninika; Dahiphale, Vijay (2023). Smart Farming: Crop 
Recommendation using Machine Learning with Challenges and Future Ideas. TechRxiv. 

Preprint. https://doi.org/10.36227/techrxiv.23504496.v1
Hasan M, Marjan MA, Uddin MP, Afjal MI, Kardy S, Ma S and Nam Y (2023) Ensemble machine 
learning-based recommendation system for effective prediction of suitable agricultural 
crop cultivation. Front. Plant Sci. 14:1234555. doi: 10.3389/fpls.2023.1234555

S. M. PANDE, P. K. RAMESH, A. ANMOL, B. R. AISHWARYA, K. ROHILLA and K. SHAURYA, "Crop 
Recommender System Using Machine Learning Approach," 2021 5th International 
Conference on Computing Methodologies and Communication (ICCMC), Erode, India, 
2021, pp. 1066-1071, doi: 10.1109/ICCMC51019.2021.9418351.
