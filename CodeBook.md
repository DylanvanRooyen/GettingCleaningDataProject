###The run_analysis.R script performs the 5 steps in the course project’s definition.

###Steps

##Download the dataset
Dataset downloaded and extracted under the folder called UCI HAR Dataset

##Assign each data to variables
features <- features.txt
activities <- activity_labels.txt
subject_test <- test/subject_test.txt
x_test <- test/X_test.txt
y_test <- test/y_test.txt
subject_train <- test/subject_train.txt
x_train <- test/X_train.txt
y_train <- test/y_train.txt

##Merges the training and the test sets to create one data set
X is created by merging x_train and x_test using rbind() function
Y is created by merging y_train and y_test using rbind() function
Subject is created by merging subject_train and subject_test using rbind() function
Merged_Data is created by merging Subject, Y and X using cbind() function

##Extracts only the measurements on the mean and standard deviation for each measurement
TidyData is created by subsetting Merged_Data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement

##Uses descriptive activity names to name the activities in the data set
Entire numbers in code column of the TidyData replaced with corresponding activity taken from second column of the activities variable

##Appropriately labels the data set with descriptive variable names
code column in TidyData renamed into activities
All Acc in column’s name replaced by Accelerometer
All Gyro in column’s name replaced by Gyroscope
All BodyBody in column’s name replaced by Body
All Mag in column’s name replaced by Magnitude
All start with character f in column’s name replaced by Frequency
All start with character t in column’s name replaced by Time

##A second, independent tidy data set with the average of each variable for each activity and each subject
FinalData is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.
Exported FinalData into FinalData.txt file.
