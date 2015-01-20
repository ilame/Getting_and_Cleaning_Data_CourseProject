
#CodeBook

The data source

data: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
description of the dataset: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

#Study Design 

(as described in the "README.txt" file  : https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip )

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 

For each record it is provided:

- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.

The dataset includes the following files:

- 'README.txt'

- 'features_info.txt': Shows information about the variables used on the feature vector.

- 'features.txt': List of all features.

- 'activity_labels.txt': Links the class labels with their activity name.

- 'train/X_train.txt': Training set.

- 'train/y_train.txt': Training labels.

- 'test/X_test.txt': Test set.

- 'test/y_test.txt': Test labels.

The following files are available for the train and test data. Their descriptions are equivalent. 

- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 

- 'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis. 

- 'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration. 

- 'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second. 

Notes: 

- Features are normalized and bounded within [-1,1].
- Each feature vector is a row on the text file.

#Transformation details

The script run_analysis.R performs the 5 steps described in the course project's definition.

Step1- all the files having the same number of columns and referring to the same entities are merged using the rbind() function. 
Step2- only columns with the mean and standard deviation measures are extracted from the whole dataset. The corresponding columns are given the correct names, taken from "features.txt".

Step3&4- The activity names and IDs from "activity_labels".txt are substituted in the dataset. On the whole dataset, those column names are corrected.

Step5- A new and independant tidy dataset with the average of each activity and subject (30 subjects * 6 activities = 180 rows). The output file is called "averages_data.txt", and uploaded to this repository.

# Variables

The files contained in the subfolder named "inertial_signals" are not used in this project, because they do not have the same number of columns (variables) as X_train/_test. 

X_train, y_train, x_test, y_test, subject_train and subject_test contain the data from the downloaded files.

X_data, y_data and subject_data merge the previous datasets to further analysis.

features contains the correct names for the X_data dataset, which are applied to the column names stored in mean_and_std_features, a numeric vector used to extract the desired data.

A similar approach is taken with activity names through the activities variable.

"averages_data.txt" contains the relevant averages. ddply() from the plyr package is used to apply colMeans().
