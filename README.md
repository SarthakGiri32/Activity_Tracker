# Activity_Tracker

Human Activity Recognition Using Smartphones


The _script_ for generating the final tidy dataset is in the file [`run_analysis.R`](https://github.com/SarthakGiri32/Activity_Tracker/blob/master/run_analysis.R)

The _variables_ used in the script, along with the _data files_ used, have been explained in the file [`Code_Book.md`](https://github.com/SarthakGiri32/Activity_Tracker/blob/master/Code_Book.md), along with some of the transformations done to get both the `training` and the `test` datasets into the form of a data frame in R (which also includes the steps to **extract only the measurments on the mean and standard deviation for each measurement**, and **appropriately label the data set with descriptive variable names**)

The rest of the analysis is explained below:

1. After the `train` and `test` data frames have been created, two more columns are added to each of them, the `Activity` column, consisting of the class-labels for the activities corresponding to each subject, and the `SubjectNum` column, which specifies the index of each participant corresponding to the activities. The values in the `Activity` column have been extracted from the `Y_test.txt` file for the `test` data frame, and `Y_train.txt` file for the `train` data frame, and the values in the `SubjectNum` column have been extracted from the `subject_train.txt` file for the `train` data frame, and from the `subject_test.txt` file for the `test` data frame.

(**Merging the Test and Training data frames**)  
2. The `train` and `test` data frames are merged to each other using the `rbind()`, and stored in a new `combined` data frame.

(**Using descriptive activity names to name the activities in the data set**)  
3. To change the class-labels used in the `Activity` column of the new `combined` data frame into the actual activity names, it is converted to a factor, by using the `classLabels` column in the `acivityLabels` dataframe as the _levels_ of the factor variable, and the `activityName` column in the `activityLabels` dataframe as the _labels_ for the factor levels, such that the `Activity` column in the `combined` data frame will have the activity names instead of the corresponding class-labels as its values.

4. The `SubjectNum` column in the `combined` data frame is also changed into a factor variable, for the purposes of being used in the new tidy data set, which is also the reason why in the previous step the `Activity` column was also converted into a factor variable.

(**Creating a second, independent, tidy dataset with the average of each variable for each activity and each subject**)  
5. The `combined` data frame is first changed to a _molten_ data frame, where `SubjectNum` and `Activity` are treated as _id variables_, and the rest of the measurement variables in the original `combined` data frame are considered as _measured variables_.
6. The data frame is then _recasted_ into a new data frame, wherein the `SubjectNum` and `Activity` variables are considered as the first two variables, and the rest of the measured variables are first summarized using the `mean()`, with respect to each of the activities for each of the subjects.
7. This new data frame is stored in a new `tidyData.txt` file.
