##README for "run_analysis"

### Introduction
This README describes how function "run_analysis* post processess study data descibed in *ref [1]*.

###Included Files
1. README.md 
2. CodeBook.md -- variable reference
3. TidyData.txt -- Output Data
4. run_analysis.R

###Summary of Functionality
1. Function run_analysis.R reads multiple files of Samsung accelerometer data from the working directory.

2. Data was post-processed to remove extraneous parameters (see Data Selection, below).  

3. Data from training and testing phases of the study were merged into a single set.

4. Numeric data identifiers were replaced with descriptive activity labels.

5. Activity labels, study subject identifiers, and acclerometer data were merged into a single set.

6. Final processing consisted of calculating the mean for each pemutation of activity type, study subject, and measurement parameter. 

7. The activity label, subject identifier, and mean for each permutation was added to the output table.

8. Output table was saved to the working directory as TidyData.txt

###Data Selection
The original Samsung dataset contained 561 parameters. Based on the project instructions *ref [2]*, this data was down selected to represent only the measurements on means and standard deviations.  

This study was entitled "Human Activity Recognition Using Smartphones".  Based on a decription of the study it was decided that only the mean and standard deviation parameters for accelerometer measurements were relevant to "recognizing human activities".  Other "averaging" parameters were neglected as they seemed to describe the signal, rather than the activity.

**Retained parameters:**

- tBodyAcc-mean()-X
- tBodyAcc-mean()-Y
- tBodyAcc-mean()-Z
- tBodyAcc-std()-X
- tBodyAcc-std()-Y
- tBodyAcc-std()-Z

###How to Run
1. Download into your working directory *ref[3]*.  

2. In R, source then run "run_analysis.R"

3. Evaluate, as desired, output file TidyData.txt (see note below)

###Output File
The output file TidyData.txt can be read as a data.frame object *tidyData* into your R environment using the following script: 

```tidyData <- read.table('./TidyData.txt',header = TRUE)```

###References
[1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012

[2] Coursera "Getting and Cleaning Data" Class Project <https://class.coursera.org/getdata-011/human_grading/view/courses/973498/assessments/3/submissions>

[3] Samsung Source Data <https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip>





