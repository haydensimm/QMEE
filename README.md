# QMEE

Data Description:
The data set is a part of a project titled "Characterizing the Interactive Effects of Temperature and Salinity 
Acclimation on the Thyroid Axis in Mummichog Killifish, Fundulus heteroclitus." The experimental design included 
acclimating fish to four combinations of saline (isosmotic and high-salinity) and temperature (cold and warm) 
conditions. Specifically, the data is a series of respiromerty experiments at each of the conditions where the 
oxygen content in a chamber containing a fish is continuously measured to quantify the oxygen consumption rate.
In the dataframe, each column represents an individual fish which underwent a maximum exercise chase at the 
beginning of the experiment, and then progresses to a resting rate as the time series continues. 
By measuring oxygen consumption, the metabolic rate of the fish can thereby be determined, to monitor differences 
in metabolic demand across environments. The biological questions this data is seeking to answer are: are there 
differences in the metabolic capacity (resting metabolic rate, maximal metabolic rate and aerobic scope) between 
acclimation treatments, and if certain environments cause reduced metabolic capacity when acutely exposed to 
non-acclimation conditions. I hypothesize that acclimation to high-salinity will prevent the ability to properly 
acclimate to temperature, relative to isosmotic acclimation. I predict that this will be displayed in statistical 
differences in metabolic capacity between treatments because effective acclimation should compensate for the 
differences in metabolic demand across environments. If differences are present, I believe this is indicative of 
multiple stressors causing a breakdown in the ability to acclimate and subsequently reducing ecological fitness. 

Assignment 2 description: 
One of the first issues with the data set is that the software and device information used to collect the data 
itself is listed throughout the first rows, this makes all subsequent %air saturation values be read in as 
characters instead of numerical values. For assignment 1 I solved this problem using a function that introduced 
NAs by coercion. The first script "Assignment_2_Cleaning_Data_Script.Rmd" fixes this and then removes NAs from 
rows 11372 onward because the data stopped being recorded at that point. The initial y~x plot looks good, we can 
see that the fish had high oxygen consumption immediately after the maximum exercise test, and slowly recovered
to a resting rate as time progressed. Overlaying the histograms also showed that the runs all essentially parallel 
so I would count them as valid. The "auto_rate.int()" function also is designed to ignore any 'bad' slopes by 
only including ones with R^2 >0.9 and in the lowest 10th percentile, so I don't think I need to investigate the 
individual slopes themselves. 
The second script "Assignment_2_Separate_Data_Script.Rmd" reads in the clean data and calculates the metabolic 
rate of a fish alone by subtracting background oxygen consumption from an empty "blank" chamber.Both files are 
located within the "main" branch of my QMEE repository.
Overall, I think that the investigation I am going to with my data is very similar to what I am currently doing.
In the end I would like to use the respR package to extra the metabolic rates from each chamber, and then 
perform the appropriate statistical tests to make comparisons between groups. Each .txt file containing data all
used the same software so the chambers names over lap. To break this into replicable components I think each file
will be run separately. 

Assignment 3 description:
Boxplot: the boxplot is trying to show the magnitude of difference between metabolic rates at the two assays 
temperatures used in the experiments. Therefore the groups are separated on the x-axis by this factor. Additionally,
to display the second factor, different shapes are used for the individual data points to correspond to the 
different salinity acclimations. The y-axis is a log scale in order to better display the variance within groups 
since the individuals points of the 10C assay group were relatively indistinguishable otherwise. Horizontal 
grid lines were added to convey the log scale since the distance between them increases with the scale. The graphical 
choices were made to follow the Cleveland Hierarchy. The primary intention was to visualize the metabolic rate so 
this was positioned as the common scale of the y-axis. Then to differentiate between the salinity factor, different 
shapes were chosen to utilize differentiation by angle, which is the next highest in the hierarchy besides length 
which I believe would be confusing because the intention was not to establish an order within the salinity factor.
Area plot: this plot is a poor way to visualize the data. 