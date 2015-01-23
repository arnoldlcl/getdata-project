# Codebook

This dataset is based on data collected from the embedded accelerometer and gyroscope of Samsung Galaxy S II smartphones worn on the waists of 30 volunteers performing six activities. The data is courtesy of the Non-Linear Complex Systems Laboratory at the University of Genoa, Italy.

The dataset contains 180 observations across 68 variables:
- The 'activity' variable describes which of six activities was being performed. This variable was added to the dataset from the original files y_train.txt and y_test.txt.
- The 'subject' variable describes which of 30 subjects was performing. This variable was added to the dataset from the original files subject_train.txt and subject_test.txt.
- The remaining variables measure either the mean or the standard deviation of various signals from the devices, as described in features_info.txt which is bundled with the original data. (For a link to the data, see the README file in this repo)

A typical example of one of the remaining variables is frequencyBodyAcc.mean.Y, which can be broken into several parts:
- the first word can be "frequency" or "time"
- the first section before the period, BodyAcc, describes what exactly was measured
- the function between the periods, either mean or stdev, describes the function that was performed on the measurement
- there may be an X, Y, or Z after the second period, which describes the dimension along which the measurement was taken, if applicable

Each of the 180 observations contains the mean of each variable for each activity and each subject (so, the mean of means or of standard deviations). 30 subjects * 6 activities = 180.

The original data consists of a training set with 7352 observations across 561 variables, and a test set with 2947 observations across 561 variables. Variables that performed functions other than the mean or the standard deviation were removed from the dataset. The training and test sets were then merged, grouped by subject and activity, and summarized with the mean of all observations per subject and activity.

