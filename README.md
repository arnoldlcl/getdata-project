This readme describes the course project for the 10th iteration of Johns Hopkins University's online course Getting and Cleaning Data. The data for this project can be found [here.] (https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip) 

There is only one script, run_analysis.R, which contains all the steps involved from reading the messy data into R to writing the tidied data to a new .txt file.

run_analysis.R assumes that the working directory is the UCI HAR Dataset folder, which contains the "test" and "train" folders as well as activity_labels.txt, features.txt, features_info.txt and README.txt.

run_analysis.R requires the following libraries:
- plyr
- dplyr

The script goes through the following steps:

1. Read features.txt, which gives the variable names for all 561 columns in the training and test sets
2. Use features.txt to create vectors identifying the columns that measure mean and standard deviation
3. Read the training set into R
4. Select only the mean and standard deviation columns from the training set, and rename them
5. Add a new column to the training set from subject_train.txt, which provides info on which of the 30 subjects corresponds to each observation
6. Add a new column to the training set from y_train.txt, which provides info on which of the 6 activities corresponds to each observation
7. Repeat steps 3-6 for the test set
8. Combine and sort the training and test sets
9. Make the variable names more descriptive
10. Replace the numeric values for the activity column with more descriptive names
11. Create a new dataset with the average of each variable, grouped by each activity and each subject
12. Write this new dataset to a .txt file