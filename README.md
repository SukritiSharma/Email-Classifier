# Email-Classifier
There are set of emails, half of which were written by one person and the other half by another person at the same company. Our objective is to classify the emails as written by one person or the other based only on the text of the email. 

Using three classification algorithm, classifier models have been build. Following analysis is been done on given set of data about accuracy and performance time with fine tuning of paramters of classifier. 
1. Naive Bayes
2. SVM
3. Decision Tree


Data Set :
* Training Set : 15820 emails
* Testing Set : 1758 emails

Classifier | Paramteters | Training Time | Prediction Time | Accuracy
------- | ----------- | ----------- | ---------- | ----------- |
Naive Bayes | Default| 1.351 s | 0.084 s | 97.33%
SVM | kernel="rbf", C=10000| 121.047 s  | 12.255 s | 99.08%
Decision Tree | min_samples_split=40| 51.661 s | 0.015 s| 97.72.04%

