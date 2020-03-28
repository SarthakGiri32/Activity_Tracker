# Getting and Cleaning Data Course Project


## Description

### Variables used:

1. packages: This variable is used to store the names of the packages used in the script
2. path: It stores the absolute path to the current working directory which is being used by R
3. url: Stores the url from where the zip file containing the datasets and there metadata will be downloaded
4. activityLabels: It is a data frame that stores the class labels (1 to 6) in its first column and the associated activity names (Walking, Walking_Up, Walking_Down, and so on) in its second column
5. features: It is a data frame that stores the names of the features being measured (like body acceleration, tilt, and many more) in its first column, and the corresponding indexes in the second column
6. featuresWanted: It is a numeric vector data consisting of the indexes of the feature-names that calculate the mean and standard deviation of the corresponding measured-feature in the "features" data frame
7. measurements: It is a character vector that stores the names of the festures selected from the "fectures" data fram with respect to the indices in the "featuresWanted" vector
8. train: It is the data frame that consists of the data collected from the training data set
9. trainActivities: It is a single-column dataset consisting of the class labels for the various activity names considered in the dataset
10. trainSubjects: It is a single-column dataset consisting of the subject-numbers who had been selected for the training dataset
11. 
