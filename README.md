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
Decision Tree | min_samples_split=40| 51.661 s | 0.015 s| 97.72%

### Naive Bayes
One particular feature of Naive Bayes is that it’s a good algorithm for working with text classification. When dealing with text, it’s very common to treat each unique word as a feature, and since the typical person’s vocabulary is many thousands of words, this makes for a large number of features. The relative simplicity of the algorithm and the independent features assumption of Naive Bayes make it a strong performer for classifying texts.

Categorizing news, email spam detection, face recognition, sentiment analysis, medical diagnosis, digit recognition and weather prediction are just few of the popular use cases of Naive Bayes algorithm.

### SVM - Support Vector Machine
SVM gives the better accuracy with this training set, but with the trade off of performace time. For the same set of data, in terms of training time Naive bayes runs faster, but SVM give better accuracy. 
Performance tuning of SVM involved playing around kernal function: linear or rbf and C. Linear kernels are best to apply on linearly separable data and have less number of feature. In our case each training set had 3785 features, hence more complex kernel such as rbf (Radial Basis Function) have better accuracy. Second tuning parameter I used was C. C parameter trades off misclassification of training examples against simplicity of the decision surface. A low C makes the decision surface smooth, while a high C aims at classifying all training examples correctly by giving the model freedom to select more samples as support vectors. Increasing the value of C from 10000, was decreasing the accuracy of the model as it was overfitting the training set. 

### Decision Tree
Decision Trees (DTs) are a non-parametric supervised learning method used for classification and regression. The goal is to create a model that predicts the value of a target variable by learning simple decision rules inferred from the data features.
The paramter min_samples_split helps to avoid overfitting of the data. The default value of 2, which means if there is 1 sample left in a node, it cannot split further. When it gets really deep in depth, it overfits the data. Whereas with the increase in the value, depth of the tree increases, this is because it will run out of sample to split. Therefore would reduce overfitting. 


If speed is a major consideration (and for many real-time machine learning applications, it certainly is) then you may want to sacrifice a bit of accuracy if it means you can train/predict faster.
Application such as flagging credit card fraud, and blocking a transaction before it goes through or voice recognition, like Siri Naive bayes would work better. 
Appliations such as predicting the author of an email, classification of images, protein fold and remote homology detection SVM may give better accuracy. 
