# CodeBook for getting and cleaning data project assignment


## Data Source
Human Activity Recognition database built from the recordings of 30 subjects performing activities of daily living (ADL) 
while carrying a waist-mounted smartphone with embedded inertial sensors. This dataset is available [here](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip) for download and use for analysis.
I have downloaded the data through the run_analysis.R script and used for analysis.

## run_analysis.R script perform the below tasks
**1. Download the dataset:** Download the dataset [here](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)
   and extract the files under "UCI HAR Dataset" folder
   
**2. Read and Assign data to Variables:** 
     
     -a. Read data from features.txt file and assing to features variable
     
     -b. Read data from activity_labels.txt file and assing to activities variable
     
     -c. Read data from subject_test.txt file and assing to subject_test variable
     
     -d. Read data from X_test.txt file and assing to x_test variable
     
     -e. Read data from Y_test.txt file and assing to y_test variable
     
     -f. Read data from subject_train.txt file and assing to subject_train variable
     
     -g. Read data from X_train.txt file and assing to x_train variable
     
     -h. Read data from Y_train.txt file and assing to y_train variable

**3. Merge both (test and train) data to create one set of data**
     
     -a. rbind() function is used for merging x_train, x_test, y_train, y_test, subject_train, 
         subject_test data and created new variables X, Y and Subject
     
     -b. cbind() fucntion is used for merging X, Y and Subject data into Merged_Data

**4. Extracts only the mean and standard deviation for each measurement** 
     
     -a. TidyData is created by subsetting Merged_Data 
     
     -b. Selecting only columns: subject, code and the measurements on the mean and standard 
         deviation(std) for each measurement   
         
**5. Use descrtptive activity names for the activities in the data set**
     
     -a. Entire numbers in code column of the TidyData replaced with corresponding activity taken from 
         second column of the activities variable
         
**6. Label the dataset variables with descriptive/meaningful names** 
     
     -a. code column in TidyData renamed to activities
     
     -b. "Acc" in column name replaced by "Accelerometer"
     
     -c. "Gyro" in column name replaced by "Gyroscope"
     
     -d. "BodyBody" in column name replaced by "Body"
     
     -e. "Mag" in column name replaced by "Magnitude"
     
     -f. All start with character f in column’s name replaced by "Frequency"
     
     -g. All start with character t in column’s name replaced by "Time"

**7. From the data set in step 4, creates a second, independent tidy data set with the average of each 
     variable for each activity and each subject**
     
     -a. AnalyzedData is created by sumarizing TidyData taking the means of each 
         variable for each activity and each subject, after groupped by subject and activity.
     
     -b. Export AnalyzedData into AnalyzedData.txt file.
