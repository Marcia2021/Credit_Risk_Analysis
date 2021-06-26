# Credit Risk Analysis - Machine Learning

## Overview 

Machine Learning is a very powerful tool by building models against large amounts of data for prediction. There are variety of models that could be use for different data type and purpose. In this project, we are going to use imbalanced-learn and scikit-learn libraries in Python to build, train and evaluate models using resampling with unbalanced class to predict credit risk. 

-	Oversample using RandomOverSampler and SMOTE
-	Undersample using ClusterCentroids
-	Combinatorial approach of over- and undersampling using SMOTEENN
-	Additional machine learning models that reduce bias: BalancedRandomForestClasifier and EasyEnsembleClassifier

## Results

1.	Oversampling – RandomOverSampler

    ![inst1](https://user-images.githubusercontent.com/79289806/123520394-80334880-d67e-11eb-9339-5a43dc2aed01.png)

    The accuracy score is around 66% for this model. Examined the classification report to assess the results further. 

    ![inst2](https://user-images.githubusercontent.com/79289806/123520396-80cbdf00-d67e-11eb-8bf9-d8aedbe4abc2.png)

    The precision (“pre” column) is only 1% for high-risk, which is much lower than the precision of low-risk. The recall (“rec” column) of the high-risk and low-risk are in         line with each other. The high-risk also has low F1 score compared to low-risk. 

2.	Oversampling – SMOTE

    ![inst3](https://user-images.githubusercontent.com/79289806/123520397-80cbdf00-d67e-11eb-877c-df571ccb9dad.png)

    The accuracy score is around 63% for this model.

    ![inst4](https://user-images.githubusercontent.com/79289806/123520398-80cbdf00-d67e-11eb-817f-01797915f98e.png)

    In the imbalanced classification report, the results are very similar as the RandomOverSampler model. High-risk has only 1% of precision while low-risk has 100% of               precision. The recall between the two population is in line with each other. The high-risk with very low precision has only 2% of F1 score. 

3.	Undersampling – ClusterCentroids

    ![inst5](https://user-images.githubusercontent.com/79289806/123520399-80cbdf00-d67e-11eb-9a31-cddebaa66444.png)

    For this model, the accuracy score is around 63%.

    ![inst6](https://user-images.githubusercontent.com/79289806/123520400-81647580-d67e-11eb-9ff5-90c56c073500.png)

    Similar as the other model, the high-risk has very low precision (1%), which the low-risk has 100% of precision. The recall for high-risk (59%) is higher than the low-risk       population (43%). The F1 score dropped to 1% for high-risk compared to the previous models.

4.	Combination (Over and Under) Sampling – SMOTEENN

    ![inst7](https://user-images.githubusercontent.com/79289806/123520401-81647580-d67e-11eb-8640-3498f72791ed.png)

    For this model, the accuracy score is only around 51%.

    ![inst8](https://user-images.githubusercontent.com/79289806/123520402-81647580-d67e-11eb-8edd-ff4a72e0259c.png)
  
    The precision for high-risk (1%) and low-risk (100%) is the same compared to other models. The recall for high-risk increased to 70%, which is higher than 57% in low-risk.       The F1 score for high-risk is still very low at 2%.

5.	Ensemble Learners – Balanced Random Forest Classifier

    ![inst9](https://user-images.githubusercontent.com/79289806/123520403-81647580-d67e-11eb-85ee-e44bf9c55179.png)

    The accuracy score increased to almost 79% in this model compared to the previous ones.

    ![inst10](https://user-images.githubusercontent.com/79289806/123520404-81647580-d67e-11eb-9e6c-3cd032b232b8.png)

    The precision for low-risk kept the same at 100%. However, the precision for high-risk increased to 4% with increased of F1 score to 7% as well compared to the previous         models. The recall in low-risk is 91% which is much higher than 67% in high-risk population.

6.	Ensemble Learners – Easy Ensemble AdaBoost Classifier

    ![inst11](https://user-images.githubusercontent.com/79289806/123520405-81647580-d67e-11eb-99b4-c71cb9cfa05d.png)

    In this model, the accuracy score increased to over 92%, which is the highest among all the models. 

    ![inst12](https://user-images.githubusercontent.com/79289806/123520406-81647580-d67e-11eb-9a3c-cf0c391c0a25.png)        

    The precision for low-risk remains the same at 100%. The precision for high-risk increased to 7% with 14% of F1 score. The recall values for both high-risk and low-risk are     over 90%, and they are lined up. 

## Summary

For all 6 models we used for this analysis, all of them with 100% precision for low-risk, and with lower than 10% of precision for high-risk. In the meantime, almost all of the recall values for both high-risk and low-risk are over 50%.

In machine learning, there is a fundamental tension between precision and sensitivity. Highly sensitive tests and algorithms will be better at detecting the intended targets, while highly precision tests and algorithms will be better at predicting true positives. 

For credit risk analysis, it is more important to detect potentially risk, so sensitivity might be more important. Based on the results from all 6 models, Easy Ensemble AdaBoost Classifier model has the highest precision among all the models, and over 90% of sensitivity for both high-risk and low-risk. Easy Ensemble AdaBoost Classifier model might be a good model to use. 
