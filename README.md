# BIOS626Midterm1 - Anqi

# Introduction
In this question, we are trying to use the sensor signal data from different part of body movement to identify the type of activities. Six activities are considerd, including three static postures (standing, sitting, lying) and three dynamic activities (walking, walking downstairs, and walking upstairs). Postural transitions that occurred between the static postures are also recorded, including stand-to-sit, sit-to-stand, sit-to-lie, lie-to-sit, stand-to-lie, and lie-to-stand.


# Data descrption and import
In the dataset provided, there are 561 signal features treated as variables, a column of the test subject, and a column of the outcome activity level treated as respond variable. 
When import the data, noted that in our case the header are seperated by multiple spaces while the data are seperated by tab. 


# Task 1: binary classifier
We built a binary classifier to classify the activity of each time window into static (0) and dynamic (1). For this task, we considered postural transitions as static (0). Hence, we first need to reassign the activity level 4-12 as 0 and reassign the activity level 1-3 as 1.

Then we are applying the Generalized Linear Model algorithm, which links linear combination of the explanatory variable to the response variable. The family was set as binomial since the outcome in this task was binary. 

After built the GLM model based on training data, we applied the model on test data to make predictions. Assign those response variable larger than 0.5 as 1 and assign those response variable larger than 0.5 as 0. Export the result as txt file for accuracy checking.

# Task 2: multi-class classifier
We built a refined multi-class classifier to classify walking (1), walking_upstairs (2), walking_downstairs (3), sitting (4), standing (5), lying (6), and static postural transition (7). Hence, we first need to reassign all the activity levels from 7 to 12 as 7, and turn the activity levels into factors.

Then we are applying the Support Vector Machines algorithm, which works by finding a hyperplane that separates the input data into different classes. After finding a hyperplane that maximizes the margin between the two classes, the support vectors are obtained as the data points closest to the hyperplane and are used to define the margin. The SVM algorithm then uses these support vectors to make predictions on new data points.

In this case, we specify that we want to use SVM for classification by set type = "C-classification". Also, to make sure that the model will separate the data using a linear boundary, we set kernel = "linear" which specifies that we want to use a linear kernel.

After built the SVM model based on training data, we applied the model on test data to make predictions. Export the result as txt file for accuracy checking.
