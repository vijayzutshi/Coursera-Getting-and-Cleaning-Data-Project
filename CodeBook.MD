Introduction 

The script  run_analysis.R performs the 5 steps described in the course project's definition.

•First, all the similar data is merged using the training and the test sets to create one data 
 set using the rbind()  function. This takes into account those files which have the same number of 
 columns and referring to the same entities.

•Then, it extracts only those columns with the mean and standard deviation with measurements from the
 whole dataset. After extracting these columns, they are given the correct names, taken from  features.txt file.

•The next step is to take the activity names and IDs from activity_labels.txt file with activity data 
 values from 1 to 6 and then they are substituted in the dataset. 
   
•Then a correction operation is performed on the entire dataset, which involves the correction of incorrect 
 columns names.

•Finally as per the project requirement, a new dataset with all the average measures for each subject and 
 activity type is created. This output file is named tidy.txt.


Variables used in R script

• x_read_training, y_read_training, x_read_test, y_read_test, subject_read_training and subject_read_test 
  used from the downloaded files.

• x_read_data, y_read_data and subject_read_data merges the previous datasets for further analysis.

• read_features contains the correct names for the  x_read_data dataset and are then applied to the column names 
  stored in  mean and std features file.

• Same thing is done with activity names using the read_activity_names variable.

• bind_all_data then stores merged x_read_data, y_read_data and subject_read_data in a big dataset.

• Finally, new_average_data_set contains the relevant averages which is then stored in a .txt file.
  ddply() from the plyr package is used to apply colMeans() to automate the process.
