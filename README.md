Getting and Cleaning Data Project

Repo for the submission of the course project for the Getting and Cleaning Data course.

Overview

This project serves to demonstrate the collection and cleaning of a dataset that can be used for subsequent analysis. A full description of the data used in this project can be found at The UCI Machine Learning Repository.

The source data for this project can be found here.

How to use the run_analysis.R script:

Once you have obtained and unzipped the source files, you will need to make one modification to the R script before you can process the data. Note that on line 24 of run_analysis.R, you will set the path of the working directory to the location of the source files in your own directory.

Script Summary

The run_analysis.R script completes the following tasks: 1. Merges the training and the test sets to create one data set. 2. Extracts only the measurements on the mean and standard deviation for each measurement. 3. Uses descriptive activity names to name the activities in the data set 4. Appropriately labels the data set with descriptive activity names. 5. Creates a second, independent tidy data set with the average of each variable for each activity and each subject.

Additional Information

You can find additional information about the variables, data and transformations in the CodeBook.MD file.
