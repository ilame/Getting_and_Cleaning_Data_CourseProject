# Getting_and_Cleaning_Data_CourseProject

This repository hosts the R code and documentation files for the Data Science's track course "Getting and Cleaning data", available in coursera.

The dataset being used is in this link: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

#Files

The code takes for granted all the data is present in the same folder, un-compressed and without names altered.

CodeBook.md describes the variables and any transformations or work that was performed to clean up the data.

run_analysis.R contains all the code to perform the analyses described in the 5 steps. This R script does the following: 
-Step 1.Merges the training and the test sets to create one data set.

-Step 2.Extracts only the measurements on the mean and standard deviation for each measurement. 

-Step 3.Uses descriptive activity names to name the activities in the data set

-Step 4.Appropriately labels the data set with descriptive variable names. 

-Step 5.From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

#Steps to work on this course project

-Download the data source and put into a folder on your local drive. You'll have a "UCI HAR Dataset" folder.

-Put run_analysis.R in the same folder, then set it as your working directory using setwd() function.

-Run source("run_analysis.R"), then it will generate a new file in your working directory called averages_data.txt that contains a tidy data set with the average of each variable Steps to work on this course project.
