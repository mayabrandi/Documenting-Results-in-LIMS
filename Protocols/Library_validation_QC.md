# Library validation QC

## Step 1 qPCR QC (Library Validation)


This step is pre set to only allow samples from the same plate to be handled at the same time. What this means is that a sample placed in A1 in library preparation plate will be assumed to be placed in A1 in the qPCR calculation, Sample placed in B1 in library preparation plate will be assumed to be placed in B1 in the qPCR calculation and so on.

If samples are in a tube format there is no such pre set and samples from different library preps can be mixed.







Fill in all the required fields
Upload the quantification summary sheet obtained from the qPCR (1). The sheet need to be opened from homer locally and be saved on a macbook before uploading.
Calculate concentration and obtain QC flags by pressing the blue button (2).
The size adjusted concentration will automatically be calculated and filled in under concentration (nM) for each sample. If outlyers are found in any of the dilution-series these are removed before the calculations are done. 
A log file is generated. Open it to see details about witch dilution messurements were used when the calculations were performed.
Once done press the green NEXT STEP button in upper right corner.
If a sample has a red flag select still proceed with the sample to the NEXT STEP.

## Step 2 Aggregate QC (Library validation)
In the upper right corner, select preset: PCR free (WGS) 
Press the blue button "Aggregate QC flags and copy fields.
Concentration (nM) is copied from CG002 - qPCR QC (Library Validation).
Press the blue button Report Library QC to sample. This is important to remember so the results are reported to the submitted sample and can be used in following protocols.
Press the green NEXT STEPS in the upper right corner
If the sample has a red flag and needs to be reprepped chose "Rework from an earlier step". This can only be done by clicking the drop down menu of individual samples.
