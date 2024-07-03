# hrv_collab
This repository offers a pipeline to study the physiological effects of an infusion given during an MRI scan on individuals with mood disorders. It enables the collection, processing, and analysis of data like heart rate (HR), helping researchers explore the infusion's impact on physiological parameters related to mood disorder symptoms.

## Study Design and Time points 
Our study is a double-blind crossover study with sub-anethisic dose of ketamine(0.5 mg/kg) and saline as the placebo 
![Study Design](Study_Design.png)
*Each rest scan was for ~ 15 minutes*

## Data Collection
Data(HR and respiratory rate) was collected during MRI scans 

This data was saved using the [bids]([url](https://bids-specification.readthedocs.io/en/stable/modality-specific-files/physiological-and-other-continuous-recordings.html ) format 

**When naming our files we coded**

Baseline - run-01 

Start of Infusion - run-101

End of Infusion - run-201
*See folder of Test_Subjects_Physio_Input* 


We used a Json file with scanning rate (state) and saved our physiological data tab separated file three bare no header numeric columns containing the respitroy rate and heart rate 

*If your scanning rate is consistent for all of the scan you may input the srate manually instead of using json files. Additionally, if your data is saved not using the tab format make sure to reformat your data or edit the code* 

## Python Files 
**Before using the notebooks make sure**
1. environment.yml is downloaded
2. a virtual environment is created
3. and HRV analysis environment is used 

**nk_hrv_singlefile_sample.ipynb** - This notebook can be used to process a single scan, and may be useful when first using the pipeline 

**nk_hrv_loop_sample.ipynb** - This notebook can be used to process all of your scans and to output it into a single CSV file 

For both notebooks the **input** will be phyislogical data file and optional json file 
*See folder of Test_Subjects_Physio_Input* 

For both notebooks the **output** will be Subject_number, Session_date, task, run, echo, state, PPG_Rate_Mean, and many heart rate variability(HRV) measures 
*See folder of Test_Subjects_Physio_Output* 

## R-Markdown 
This file can be used to 
1. See if BMI, age, and gender are available to see if they are confounding variables
2. Combine MADRS(mood rating) scores to HRV_Data_Loop_Test (output file)
3. Do Statistical Analysis for 
4. Plot Mood Rating Before and After Infusion, Average HR at Scan Time Points, Average HRV at Scan Time Points, and Effect of Placebo on HRV, Correlation Between Change in Mood Rating and HR Level at the End of the Infusion, 



