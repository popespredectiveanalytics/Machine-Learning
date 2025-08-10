# Machine-Learning
This is an example of a machine learning project that I have done in the past. 
#Assignment Overview

For this assignment your objective is to utilize Scikit-learn functions, including constructing a data pipeline, to preprocess data for running a multiple linear regression model. We will create a machine learning model to predict apartment prices using the available features.

This assignment will follow steps outlined in the machine learning checklist provided in the textbook's appendix. It's important to acknowledge that this assignment is meant to stay at a simple, broad overview and in a real-world scenario, extensive data exploration, diverse data refinement techniques, experimentation with multiple models, and meticulous model refinement would be conducted before reaching the final evaluation stage.

#Data

This assignment uses a dataset of advertised apartment rentals in the USA, and the original dataset can be found on UC Irvine's Machine Learning Repository. However, please use the dataset provided in Canvas as some values have been changed and features deleted. The dataset provided through Canvas contains 10,000 instances and 10 columns.

The columns in the file are as follows:

- id : unique identifier of apartment
- latitude : latitude where the apartment is located
- longitude : longitude where the apartment is located
- bathrooms : number of bathrooms
- bedrooms : number of bedrooms
- fee : Y/N does apartment have fee?
- has_photo : Y/N does apartment listing have photo?
- pets_allowed : what pets are allowed dogs/cats etc.
- square_feet : size of the apartment in square feet
- price : rental price of apartment (This will be our target)
Assignment Instructions

Walk through the rest of the assignment, completing the exercises as indicated. As you read through the markdown comments, the provided code, and create your own code, think about how each section fits into the overall machine learning process.

Once you have completed all the tasks, you are ready to submit your assignment to CodeGrade for testing. Please restart your notebook's kernel and run your code from the beginning to ensure there are no error messages. Once you have verified that the code runs without any issues, submit your .ipynb notebook file to CodeGrade for evaluation. Your notebook should be called pipeline_project.ipynb. You have unlimited attempts for this assignment.

Table of Contents

Standard Imports
Get the Data
Explore the Data
Prepare the Data
Model Selection & Evaluation
Final Model Evaluation
Final Model Evaluation

We are now ready to assess our model's performance on the test set, utilizing the previously established Random Forest model. It is necessary that we apply any data transformations we performed on the training data to the testing data. It is crucial to emphasize that we should solely apply transformations to the testing data without using the "fit_transform" method, as we want to exclusively use the information derived from the training data for this transformation process.

Exercise 8: (12.5 points)

Utilizing the previously established preprocessing ColumnTransformer, apply transformations to your X_test data, and label the resulting dataset as X_test_prepared. It is essential that you use the transform method and refrain from using the fit_transform method on your testing data.
With the pre-fitted forest_reg model, make predictions using the X_test_prepared dataset and store these predictions as a variable called final_predictions.
Utilizing Scikit-learn's mean_squared_error function, calculate the root mean squared error (RMSE) by passing your y_test and final_predictions, making sure to set the squared parameter to False. Round the RMSE score to 2 decimal places. Save this score as final_rmse.
### ENTER CODE BELOW ###
X_test_prepared = preprocessing.transform(X_test)

final_predictions = forest_reg.predict(X_test_prepared)

rmse = mean_squared_error(y_test, final_predictions)

final_rmse = round(rmse, 2)

print(final_rmse)
215383.24
Congratulations on successfully completing the assignment! Throughout this task, you acquired and explored your dataset. By implementing pipelines, you streamlined the data preparation process, greatly simplifying the transformation of your test data. You went on to develop and assess two models for predicting apartment prices. Great job, and we hope this assignment has been a valuable learning experience!
