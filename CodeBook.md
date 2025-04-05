# CodeBook for analyzing the dataset "Human Activity Recognition Using Smartphones"

## Codebook Description

This codebook describes the data, the variables, and any transformations or work that have been performed to clean up the data.

------------------------------------------------------------------------

## Human Activity Recognition dataset

The input dataset from the study "Human Activity Recognition Using Smartphones"" were collected from 30 participants (**subjects**) wearing the Samsung Galaxy S smartphone while performing six **activities**, including walking, walking upstairs, walking downstairs, sitting, standing, and laying. 70% of the participants was selected for generating the training data and 30% the test data. The sensor signals detected by the accelerometer and gyroscope of the Samsung Galaxy S smartphone were pre-processed and sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated into body acceleration and gravity. From each window, a vector of measurement (**variable**) was obtained by calculating variables from the time and frequency domain. [Raw data source.](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)

------------------------------------------------------------------------

## Data

### Summary

The average of each **variable** for each **activity** and each **subject**.

### Subject and activity (the first two columns)

| Column Name | Description | Type | Values |
|------------------|------------------|------------------|------------------|
| `subject` | Identifier for each subject (participant) who carried out the experiment | Integer | 1, 2, 3, ..., 30 |
| `activity` | The type of activity | Character | Walking, Walking_upstairs, Walking_downstairs, Sitting, Standing, Laying |

### Variables (column number 3 to 68)

-   Variables are types of measurements collected from the input dataset.
-   Variable columns are numeric, with values representing the **average** of **each variable** for **each activity and each subject**.
-   The input variable values have already been normalized and bounded within [-1,1] before this analysis.
-   Only the variables of the input dataset with original names containing "mean()" or "std()" were selected for analysis.
-   Abbreviations and explanation for the description of variable names: `mean`: mean value, `std`: standard deviation, `Acc`: Acceleration, `Gyro`: gyroscope, `Mag`: magnitude, `_X`, `_Y`, `_Z`: 3-axial raw signals.

------------------------------------------------------------------------

## Data Transformation Steps

1.  **Merging the Test and Training Data**: The training and test data from the input dataset were integrated and combined into one dataset, with `subject` and `activity` as the first and second columns and with variables as the remaining columns.

2.  **Extracting Mean and Standard Deviation**: Among the variable columns, only the variables representing the mean and standard deviation of the measurements were kept.

3.  **Descriptive Activity Names**: The `activity` column was mapped from numeric labels to descriptive activity names like "Walking", "Laying", etc.

4.  **Descriptive Variable Names**: Column names were cleaned up and made more descriptive to make the data easier to understand (e.g., changing "tBodyAcc-mean()-X" to "timeDomainBodyAcc_mean_X").

5.  **Calculating the average**: A tidy output dataset was created by aggregating the data to get the mean of each variable for each activity and subject.

------------------------------------------------------------------------

## How to Use This Codebook

This codebook should be used to understand the structure and contents of the output dataset. The subject, activity, and variables are described in detail. If you are working with the data, refer to this codebook to understand the transformations and the meaning of each column.

For further details on how the code was written, refer to the **run_analysis.R** script available in the repository.
