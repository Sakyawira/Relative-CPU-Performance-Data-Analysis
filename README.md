# Linear Regression Analysis of Relative CPU Performance
Sakyawira Nanda Ruslim, August 2020.

## Executive Summary 
The dataset is Relative CPU Performance Data downloaded from UCI Machine Learning Repository. The dataset contains the vendor name: 30 (adviser, amdahl,apollo, basf, bti, burroughs, c.r.d, cambex, cdc, dec,dg, formation, four-phase, gould, honeywell, hp, ibm, ipl, magnuson, microdata, nas, ncr, nixdorf, perkin-elmer, prime, siemens, sperry, sratus, wang), Model Name: many unique symbols, MYCT: machine cycle time in nanoseconds (integer), MMIN: minimum main memory in kilobytes (integer), MMAX: maximum main memory in kilobytes (integer), CACH: cache memory in kilobytes (integer), CHMIN: minimum channels in units (integer), CHMAX: maximum channels in units (integer), PRP: published relative performance (integer), and ERP: estimated relative performance from the original article (integer).

There were no null values in the 209 rows dataset. 

After exploring the data by visualizing the correlation between each numerical variable, MMIN, MMAX, CACH, CHMIN, and CHMAX are highly positively correlated while MYCT are relatively highly negatively correlated.

Linear Regression algorithms have been tested for this train dataset and have a score of 0.922.

## Initial Data Exploration 
The initial exploration of the data began with some summary for each attribute’s minimum, maximum, mean, median, standard deviation, and distinct count. The results were taken from a dataset with 209 entries, as shown here:



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
