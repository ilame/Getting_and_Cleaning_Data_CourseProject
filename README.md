# Getting_and_Cleaning_Data_CourseProject


#Steps to work on this repo

This repository hosts the R code and documentation files for the "Getting and Cleaning data" course project, extracted from the link below:

Source: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones


1-Download the data source and put into a folder on your local drive. You'll have a "UCI HAR Dataset" folder.

2-Put run_analysis.R in the same folder, then set it as your working directory using setwd() function.

3-Run source("run_analysis.R"), then it will generate a new file in your working directory called "averages_data.txt" that contains a tidy data set with the average of each variable for each activity and each subject.


#Files

The code takes for granted all the data is present in the same folder. 

"CodeBook.md" describes the variables and any transformations or work that was performed to clean up the data.

"run_analysis.R" contains all the code to perform the analyses described in the 5 steps. This R script does the following: 

-Step 1.Merges the training and the test sets to create one data set.

-Step 2.Extracts only the measurements on the mean and standard deviation for each measurement. 

-Step 3.Uses descriptive activity names to name the activities in the data set

-Step 4.Appropriately labels the data set with descriptive variable names. 

-Step 5.From the data set in step 4, creates a second, independent tidy data set called "averages_data.txt" with the average of each variable for each activity and each subject.


