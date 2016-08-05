Getting and Cleaning Data Project

Description

Additional information about the variables, data and transformations used in the course project for the Getting and Cleaning Data course.

The data source:

Original data: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
Original description of the dataset: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Dataset Information:

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

Variables:

For each record in the dataset it is provided:

Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
Triaxial Angular velocity from the gyroscope.
A 561-feature vector with time and frequency domain variables.
Its activity label.
An identifier of the subject who carried out the experiment.

For each record in the tidy dataset
All variables are the mean of a measurement for each subject and activity. This is indicated by the initial Mean in the variable name. All values are floating point numbers.

Time domain body acceleration mean along X, Y, and Z:
MeanTimeBodyAccMeanX
MeanTimeBodyAccMeanY
MeanTimeBodyAccMeanZ
Time domain body acceleration standard deviation along X, Y, and Z:
MeanTimeBodyAccStdDevX
MeanTimeBodyAccStdDevY
MeanTimeBodyAccStdDevZ
Time domain gravity acceleration mean along X, Y, and Z:
MeanTimeGravityAccMeanX
MeanTimeGravityAccMeanY
MeanTimeGravityAccMeanZ
Time domain gravity acceleration standard deviation along X, Y, and Z:
MeanTimeGravityAccStdDevX
MeanTimeGravityAccStdDevY
MeanTimeGravityAccStdDevZ
Time domain body jerk mean along X, Y, and Z:
MeanTimeBodyAccJerkMeanX
MeanTimeBodyAccJerkMeanY
MeanTimeBodyAccJerkMeanZ
Time domain body jerk standard deviation along X, Y, and Z:
MeanTimeBodyAccJerkStdDevX
MeanTimeBodyAccJerkStdDevY
MeanTimeBodyAccJerkStdDevZ
Time domain gyroscope mean along X, Y, and Z:
MeanTimeBodyGyroMeanX
MeanTimeBodyGyroMeanY
MeanTimeBodyGyroMeanZ
Time domain gyroscope standard deviation along X, Y, and Z:
MeanTimeBodyGyroStdDevX
MeanTimeBodyGyroStdDevY
MeanTimeBodyGyroStdDevZ
Time domain gyroscope jerk mean along X, Y, and Z:
MeanTimeBodyGyroJerkMeanX
MeanTimeBodyGyroJerkMeanY
MeanTimeBodyGyroJerkMeanZ
Time domain gyroscope jerk standard deviation along X, Y, and Z:
MeanTimeBodyGyroJerkStdDevX
MeanTimeBodyGyroJerkStdDevY
MeanTimeBodyGyroJerkStdDevZ
Time domain body acceleration magnitude mean:
MeanTimeBodyAccMagMean
Time domain body acceleration magnitude standard deviation:
MeanTimeBodyAccMagStdDev
Time domain gravity acceleration magnitude mean:
MeanTimeGravityAccMagMean
Time domain gravity acceleration magnitude standard deviation:
MeanTimeGravityAccMagStdDev
Time domain body jerk magnitude mean:
MeanTimeBodyAccJerkMagMean
Time domain body jerk magnitude standard deviation:
MeanTimeBodyAccJerkMagStdDev
Time domain gyroscope magnitude mean:
MeanTimeBodyGyroMagMean
Time domain gyroscope magnitude standard deviation:
MeanTimeBodyGyroMagStdDev
Time domain gyroscope jerk magnitude mean:
MeanTimeBodyGyroJerkMagMean
Time domain gyroscope jerk magnitude standard deviation:
MeanTimeBodyGyroJerkMagStdDev
Frequency domain body acceleration mean along X, Y, and Z:
MeanFrequencyBodyAccMeanX
MeanFrequencyBodyAccMeanY
MeanFrequencyBodyAccMeanZ
Frequency domain body acceleration standard deviation along X, Y, and Z:
MeanFrequencyBodyAccStdDevX
MeanFrequencyBodyAccStdDevY
MeanFrequencyBodyAccStdDevZ
Frequency domain body jerk mean along X, Y, and Z:
MeanFrequencyBodyAccJerkMeanX
MeanFrequencyBodyAccJerkMeanY
MeanFrequencyBodyAccJerkMeanZ
Frequency domain body jerk standard deviation along X, Y, and Z:
MeanFrequencyBodyAccJerkStdDevX
MeanFrequencyBodyAccJerkStdDevY
MeanFrequencyBodyAccJerkStdDevZ
Frequency domain gyroscope mean along X, Y, and Z:
MeanFrequencyBodyGyroMeanX
MeanFrequencyBodyGyroMeanY
MeanFrequencyBodyGyroMeanZ
Frequency domain gyroscope standard deviation along X, Y, and Z:
MeanFrequencyBodyGyroStdDevX
MeanFrequencyBodyGyroStdDevY
MeanFrequencyBodyGyroStdDevZ
Frequency domain body acceleration magnitude mean:
MeanFrequencyBodyAccMagMean
Frequency domain body acceleration magnitude standard deviation:
MeanFrequencyBodyAccMagStdDev
Frequency domain body jerk magnitude mean:
MeanFrequencyBodyAccJerkMagMean
Frequency domain body jerk magnitude standard deviation:
MeanFrequencyBodyAccJerkMagStdDev
Frequency domain gyroscope magnitude mean:
MeanFrequencyBodyGyroMagMean
Frequency domain gyroscope magnitude standard deviation:
MeanFrequencyBodyGyroMagStdDev
Frequency domain gyroscope jerk magnitude mean:
MeanFrequencyBodyGyroJerkMagMean
Frequency domain gyroscope jerk magnitude standard deviation:
MeanFrequencyBodyGyroJerkMagStdDev

Transformations:

Section 1. Merge the training and the test sets to create one dataset.

1) Use setwd() function to set the source directory for the files;
2) Use read.table() function to read files below into tables;
3) Assign column names;
4) Use cbind() and rbind() function to combine training and test sets to create one dataset

features.txt
activity_labels.txt
subject_train.txt
x_train.txt
y_train.txt
subject_test.txt
x_test.txt
y_test.txt
Assign column names and merge to create one data set.

Section 2. Extract only the measurements on the mean and standard deviation for each measurement.

1) Use the grepl() function to create a logical vector that contains TRUE values for the ID, mean and stdev columns and FALSE values for the others;
2) Subset the dataset using the the logical vector developed above to keep only the necessary columns.

Section 3. Use descriptive activity names to name the activities in the data set

Use the merge() function to merge data subset with the activityType table to include the descriptive activity names

Section 4. Appropriately label the data set with descriptive activity names.

Use gsub function for pattern replacement to clean up the data labels.

Section 5. Create a second, independent tidy data set with the average of each variable for each activity and each subject.
1) Use the aggregate() function to calculate the average of each veriable for each activity and subject
Use the write.table() funcation to produce the final tidy dataset
