# Getting and Cleaning Data Course Project


## Description

### Variables Used:

1. `packages`: This variable is used to store the names of the packages used in the script
2. `path`: It stores the absolute path to the current working directory which is being used by R
3. `url`: Stores the url from where the zip file containing the datasets and there metadata will be downloaded
4. `activityLabels`: It is a data frame that stores the class labels (1 to 6) in its first column and the associated activity names (Walking, Walking_Up, Walking_Down, and so on) in its second column
5. `features`: It is a data frame that stores the names of the features being measured (like body acceleration, tilt, and many more) in its first column, and the corresponding indexes in the second column
6. `featuresWanted`: It is a numeric vector data consisting of the indexes of the feature-names that calculate the mean and standard deviation of the corresponding measured-feature in the `features` data frame
7. `measurements`: It is a character vector that stores the names of the festures selected from the "fectures" data fram with respect to the indices in the `featuresWanted` vector
8. `train`: It is the data frame that consists of the activity data collected from the training data set, along with the corresponding activity-class labels and the subject numbers 
9. `trainActivities`: It is a single-column dataset consisting of the class labels for the various activity names considered in the training dataset
10. `trainSubjects`: It is a single-column dataset consisting of the subject-numbers who had been selected for the training dataset
11. `test`: It is similar to the `train` data frame, except that it consists of the activity data collected from the test dataset
12. `testActivities`: It is a single-column dataset consisting of the class labels for the various activity names considered in the test dataset
13. `testSubjects`: It is a single-column dataset consisting of the subject-numbers who had been selected for the test dataset
14. `combined`: It is the merged data frame formed by merging the `test` and the `training` data frames

## Data Used:

1. `features.txt`: A text file consisting of a list of the names of various features being measured in the dataset, and their corresponding indices
2. `activity_labels`: A text file consisting of the list of activities considered in the dataset, along with their respcting level indices
3. `X_train.txt` and `X_test.txt`: A text file consisting of the measurement values for each of the features, and for each of the subjects selected for the training and test datasets, respectively
4. `Y_train.txt` and `Y_test.txt`: A text file consisting of the list of activities for each of the measurements made for the training and test datasets, respectively
5. `tidyData.txt`: The final dataset, consisting of the average of each of the feature-measurements, calculated on a per subject as well as a per activity basis

## Transformations:

1. The absolute path to the current working directory is first stored in `path`.
2. The zip file, consisting of the test and training datasets and the corresponding metadat, was downloaded into the file `dataFiles.zip`, which was then unzipped, creating a directory named `UCI HAR Dataset` inside the current working directory.
3. Inside `activityLabels`, the `activity_labels.txt` file is extracted and stored as a data frame, with `classLabels` as the first variable-name, and `activityName` as the second variable name.
4. Inside `features`, the `features.txt` file is extracted and stored as a data frame, with `index` as the first variable-name, and `featureNames` as the second variable-name.
5. In `featuresWanted`, the indices of the feature-names in `features` corresponding to the mean and standard deviation for each measured feature is stored, by using the `grep()`.
6. Then, using `featuresWanted` for the row indices, the required feature-names from the `featureNames` variable in the `fectures` data frame are selected and stored as a character vector in the `measurements` variable.
7. The `measurements` variable is further refined by removing the curved-brackets present in the stored feature-names.
8. In `train`, the `X_train.txt` file, inside the `train` sub-directory, is extracted, and only those columns corresponding to the `featuresWanted` vector are extracted.
9. In `test`, the `X_test.txt` file, inside the `test` sub-directory, is extracted, and only those columns corresponding to the `featuresWanted` vector are extracted.

(_Note: The script is the intellectual property of [Mayank Galarnyk](https://github.com/mGalarnyk)
Link to the original script: [`run_analysis.R`](https://github.com/mGalarnyk/datasciencecoursera/blob/master/3_Getting_and_Cleaning_Data/projects/run_analysis.R)_)
