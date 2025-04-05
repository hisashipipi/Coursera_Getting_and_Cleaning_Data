# Human Activity Recognition Using Smartphones

This repository contains the scripts and files used to perform analysis on the Human Activity Recognition Using Smartphones dataset (input dataset). The goal of this project was to demonstrate the ability to collect, work with, and clean a dataset in preparation for later analysis.

## Project Structure

-   **`README.md`**: An overview introducing files in this repository, how scripts work, and data content.

-   **`run_analysis.R`**: This script was applied to process and analyze input dataset to generate output data.

-   **`tidy_data.txt`**: This output data set showing the average of each variable for each activity and each subject.

-   **`CodeBook.md`**: This codebook describes the data, the variables, and any transformations or work that have been performed to clean up the data.

## Objective

The objective of this project is to merge, clean, and analyze data collected from the input dataset. The steps performed in the analysis are as follows:

**1. Merges the training and the test sets to create one data set.** Integrates and combines training and test data into one data with `subject`, `activity`, and all the measured variables.

**2. Extracts only the measurements on the mean and standard deviation for each measurement.** Subsets data by selecting the variables measuring the mean and standard deviation for each measurement.

**3. Uses descriptive activity names to name the activities in the data set.** Modify the `activity` column by replacing the activity codes with descriptive activity names

**4. Appropriately labels the data set with descriptive variable names.** Modify the names of all variable columns by to make them easier to understand.

**5. Creates an independent tidy data set with the average of each variable for each activity and each subject** Group dataset by both `subject` and `activity` and analyze the average of each variable for each activity and each subject.

## Script Explanation

**0. Load necessary libraries**: This script uses the `dplyr` to handle data manipulation tasks.

**1. Load data:** Data were downloaded to the working directory. `subject`, `activity`, and variables from both training and test groups were read using `read.table()`.

**2. Integrate data:** `subject`, `activity`, and variables were integrated into one dataset for both training and test data using `data.frame()`.

**3. Merge data:** Training and test data were combined into one dataset using `rbind()`.

**4. Subset data:** Specific variables (measurements) were selected using `grep()` and `select()`.

**5. Rename activity labels:** Replace the numeric activity labels with descriptive activity names using `recode()`.

**6. Rename variable names:** The column names are cleaned and organized by `gsub()` to make them descriptive and consistent.

**7. Creating a tidy dataset**: The script generates a tidy dataset where each variable is averaged for each subject and each activity using `group_by()`, `summarize()`, and `across()`.

**8. Writing the final dataset**: The tidy dataset is written to a file `tidy_data.txt` by `write.table()`.

## How to Use

1.  Download the input dataset and clone the repository or download the project files.

2.  Open the `run_analysis.R` script in an R environment (e.g., RStudio).

3.  Run the script to generate the tidy dataset (`tidy_data.txt`).

4.  Check the generated tidy dataset and ensure that it contains the average of each measurement for each subject and activity.

5.  Check `CodeBook.md` for details about the variables and data.

## Dependencies

`dplyr` is required to run the `run_analysis.R` script.

To install the required packages, run the following commands in R: `install.packages("dplyr")`
