---
{"dg-publish":true,"permalink":"/learning/programming/c-and-t/learnbay/statistics-and-machine-learning/doubt-clearing-session/","dg-note-properties":{}}
---


## 1, March/2024 for class of 24Jan and 11th Feb recorded videos that i watched :
systematic sampling at 31:30 minutes in the recorded 24 jan recorded video
Why is he creating two data columns **number** and **number_values**
Why is the N being disordered
in youtube it shows to start from a random number

skewness at 38 minutes in the recorded 11 Feb recorded video
38 - 44 minutes - While explaining beta and gamma, He says if mean(23.12) is greater than the median(25) it will result in +ve skewness so why i am getting a -ve skewness here. I don't understand how 23.12 is greater then 25?
Then he starts to explain the formula $\Large{\frac{\mu_3^2}{\mu_2^3}}$ it can be negative because denominator is a cube


## 20th, March/2024 for class of 16,17th march :
In the notes: [Site Unreachable](https://drive.google.com/drive/folders/13z6nzqckPUQc2Yg-DerdfNgma5N6s97E)
![doubt clearing session-20240320053525780.png](/img/user/attachments/doubt%20clearing%20session-20240320053525780.png)
The video for 16th march [lms.learnbay.co/myaccount/#/course/98128/classrecords?class\_id=263014&lesson=989077&section=266893&subject=263014](https://lms.learnbay.co/myaccount/#/course/98128/classrecords?class_id=263014&lesson=989077&section=266893&subject=263014) at 2:54:40
Why is `model.test(x_train)` has `x_train` as the input values(questions) and why all of the training data ( We are doing class test right) . Shouldn't be using like 20% of the known data becuase if we are using the all the data again the error will be same or the regression line would be same and no > Because What does training means as per video: [17th march video Learnvista Private Limited](https://lms.learnbay.co/myaccount/#/course/98128/classrecords?class_id=263014) at 3:10:10 the predicted is on the line and the actual can be not on the line so there is only one line that will be found out during the training that will result in minimum error.
> Now, if we feed the all of these data points to the class test. It will do the same thing i.e find the one line with minimum error and that line will be same as before <span style="color:#FF0000">so there is not difference between class test(analogy) and the training(analogy) here</span>
> ![doubt clearing session-20240320062319182.png](/img/user/attachments/doubt%20clearing%20session-20240320062319182.png)


|      | fixed acidity | volatile acidity | citric acid | residual sugar | chlorides | free sulfur dioxide | total sulfur dioxide | density | pH   | sulphates | alcohol |
| ---- | ------------- | ---------------- | ----------- | -------------- | --------- | ------------------- | -------------------- | ------- | ---- | --------- | ------- | 
| 0    | 7.4           | 0.700            | 0.00        | 1.9            | 0.076     | 11.0                | 34.0                 | 0.99780 | 3.51 | 0.56      | 9.4     |       
| 1    | 7.8           | 0.880            | 0.00        | 2.6            | 0.098     | 25.0                | 67.0                 | 0.99680 | 3.20 | 0.68      | 9.8     |      
| 2    | 7.8           | 0.760            | 0.04        | 2.3            | 0.092     | 15.0                | 54.0                 | 0.99700 | 3.26 | 0.65      | 9.8     |       
| 3    | 11.2          | 0.280            | 0.56        | 1.9            | 0.075     | 17.0                | 60.0                 | 0.99800 | 3.16 | 0.58      | 9.8     |    
  
There is a correlation between 'free sulfur dioxide' and 'free sulfur dioxide' of 0.7 based on `sns.heatmap()`. I am doing RandomForest Modeling on this data. Shall i ignore this or remove one of the columns ?

![doubt clearing session-20240424163230934.png](/img/user/attachments/doubt%20clearing%20session-20240424163230934.png)![doubt clearing session-20240424163256149.png](/img/user/attachments/doubt%20clearing%20session-20240424163256149.png)

|      | fixed acidity | volatile acidity | citric acid | residual sugar | chlorides | free sulfur dioxide | total sulfur dioxide | density | pH   | sulphates | alcohol | quality |
| ---- | ------------- | ---------------- | ----------- | -------------- | --------- | ------------------- | -------------------- | ------- | ---- | --------- | ------- | ------- |
| 0    | 7.4           | 0.700            | 0.00        | 1.9            | 0.076     | 11.0                | 34.0                 | 0.99780 | 3.51 | 0.56      | 9.4     | 5       |
| 1    | 7.8           | 0.880            | 0.00        | 2.6            | 0.098     | 25.0                | 67.0                 | 0.99680 | 3.20 | 0.68      | 9.8     | 5       |
| 2    | 7.8           | 0.760            | 0.04        | 2.3            | 0.092     | 15.0                | 54.0                 | 0.99700 | 3.26 | 0.65      | 9.8     | 5       |
| 3    | 11.2          | 0.280            | 0.56        | 1.9            | 0.075     | 17.0                | 60.0                 | 0.99800 | 3.16 | 0.58      | 9.8     | 6       |
| 5    | 7.4           | 0.660            | 0.00        | 1.8            | 0.075     | 13.0                | 40.0                 | 0.99780 | 3.51 | 0.56      | 9.4     | 5       |

wine dataframe looks like above
x = wine.loc[:, wine.columns != 'quality'] # training data
y = wine.loc[:, wine.columns == 'quality'] # test data

x = wine.loc[:,wine.columns[:-1]]
y = wine.loc[:,[wine.columns[-1]]]

I am removing the outliers from the x dataframe like this
x[~(x.apply(zscore, axis=0) > 2)]

Now how do i join x with the corresponding values of the target variable y.


