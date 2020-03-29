# Activity_Tracker

Human Activity Recognition Using Smartphones


The _script_ for generating the final tidy dataset is in the file [`run_analysis.R`](https://github.com/SarthakGiri32/Activity_Tracker/blob/master/run_analysis.R)

The _variables_ used in the script, along with the _data files_ used, have been explained in the file [`Code_Book.md`](https://github.com/SarthakGiri32/Activity_Tracker/blob/master/Code_Book.md), along with some of the transformations done to get both the `training` and the `test` datasets into the form of a data frame in R (which also includes the step to **extract only the measurments on the mean and standard deviation for each measurement**)

The rest of the analysis is explained below:

1. After the `train` and `test` data frames have been created, two more columns are added to each of them, the `Activity` column, consisting of the class-labels for the activities corresponding to each subject, and the `SubjectNum` column, which specifies the index of each participant corresponding to the activities. The values in the `Activity` column have been extracted from the `Y_test.txt` file for the `test` data frame, and `Y_train.txt` file for the `train` data frame, and the values in the `SubjectNum` column have been extracted from the `subject_train.txt` file for the `train` data frame, and from the `subject_test.txt` file for the `test` data frame.

(**Merging the Test and Training data frames**)
2. The `train` and `test` data frames are merged to each other using the `rbind()`, and stored in a new `combined` data frame.

