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
NAs by coercion. To fix this for assignment 2 I have found a new 'cleaner' function. The NAs still persists from 
rows 11372 onward because the data stopped being recorded so those need to be removed as well. The initial plot 
looks good, we can see that the fish had high oxygen consumption immediately after the maximum exercise test, 
and slowly recovered to a resting rate as time progressed.