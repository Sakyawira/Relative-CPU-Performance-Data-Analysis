# Linear Regression Analysis of Relative CPU Performance
Sakyawira Nanda Ruslim, August 2020.

## Executive Summary 
The dataset is Relative CPU Performance Data downloaded from UCI Machine Learning Repository. The dataset contains the vendor name, Model Name, MYCT (machine cycle time in nanoseconds), MMIN (minimum main memory in kilobytes), MMAX(maximum main memory in kilobytes), CACH(cache memory in kilobytes), CHMIN(minimum channels in units), CHMAX(maximum channels in units), PRP(published relative performance), and ERP(estimated relative performance from the original article). After exploring the data by visualizing the correlation between each numerical variable, MMIN, MMAX, CACH, CHMIN, and CHMAX are highly positively correlated while MYCT are relatively highly negatively correlated. Linear Regression algorithms have been tested for this train dataset and have a score of 0.738.

## Initial Data Exploration 
The initial exploration of the data began with some summary for each attribute’s minimum, maximum, mean, median, standard deviation, and distinct count. The results were taken from a dataset with 209 entries, as shown here:


<img src="https://github.com/Sakyawira/Relative-CPU-Performance-Data-Analysis/blob/master/Images/description.PNG?raw=true" width="461" height="150" />

It should be noted that all attributes have standard deviations of more than 3.

## Correlation and Relationships
The correlation between the numeric columns were calculated and observed in the below correlation plot. (The right color bar indicated the correlation values. For example, dark red means correlation value is 1 and light beige means correlation value is negative 0.25)


The graph shows that MMIN, MMAX, CACH, CHMIN, and CHMAX have strong positive correlation with the PRP of the CPU. On the other hand MYCT has a strong negative correlation with the PRP of the CPU.

## Analysis
No null values were found in the dataset with 209 entries. All the attributes have the expected data types, so no conversion needs to be done.


Attributes such as Vendor Name and Model Name were dropped because Linear Regression only works with numerical attributes. The ERP is also dropped because it was the author's previous prediction of the "PRP" which will allow for higher correlation but irrelevant for real world application.


In this analysis, a Linear Regression algorithm was used. These algorithms were trained with 70% of the data. Testing the model with the remaining 30% of the data yielded 0.738.

## Conclusion
This analysis has shown that the PRP of a CPU can be confidently predicted from its MMIN, MMAX, CACH, CHMIN, CHMAX, and MYCT. In particular, the Linear Regression algorithm has a score of 74%.
