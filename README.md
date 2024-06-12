



# PWC-Call Centre Dashboard


## Problem Statement

In this project,Create a dashboard for the call centre manager that reflects relevant KPI's and metrics in the dataset.

Possible KPIS include

.Overall customer satisfaction

.Overall calls answered/abandoned

.Calls by time

.Average speed of answer

.Agent’s performance quadrant -> average handle time (talk        duration) vs calls answered


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : In this dataset,it has 10 columns and 5000 rows.
- Step 5 : Removed unneccessary rows and columns.
- Step 6 :Each of the column were validated under the correct data type.
- Step 7 :Close and load into PowerBI.

 Following DAX expression was written;

 CallAnswered = CALCULATE(COUNT('call centre trends'[Call Id]),FILTER('call centre trends','call centre trends'[Answered (Y/N)]="Y"))

 CallResolved = CALCULATE(COUNT('call centre trends'[Call Id]),FILTER('call centre trends','call centre trends'[Resolved]="Y"))

Calls Abandoned = COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "N"), 'call centre trends'[Answered (Y/N)])
 Total calls=CALCULATE('call centre trends'[Answered] + 'call centre trends'[Calls Abandoned])

 Target value satisfaction=4.5
 
 Count satisfaction rating = count('call centre trends'[Satisfaction rating])



 

       
        


 
 # Report Snapshot (Power BI DESKTOP)

 
![image](https://github.com/SuganyaNammalvar/Test/assets/142667989/ae82efd5-8ed7-4724-8281-8324765eed71)

# Insights

.The call center handled a total of 5000 calls in the specified period.
.A high percentage of calls were answered (4054 out of 5000), indicating good availability.
.However, 946 calls were abandoned, which could indicate potential issues in handling peak times or long wait times.
.Martha handled the highest speed of answering calls, followed by  Jim and Dan.
.The average speed of answer varies slightly among agents, but Stewart has the lowest speed.

#Improvement Areas

.Reducing the number of abandoned calls should be a focus to improve overall customer satisfaction.

.Investigate why some agents have lower satisfaction ratings and provide additional training or resources as needed.




# Test
