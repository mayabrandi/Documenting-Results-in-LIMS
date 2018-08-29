# Library Validation QC (Dev)


## Tapestation  QC (Dev)
Write the average library size in Average Size (bp)  
Write the peak size from the TP data in Peak Size
Use the correct flag for each library using QC- flags
Write any comments in Comments
Press NEXT STEPS to proceed in the protocol.








## qPCR QC (Library Validation) (Dev)
Upload the quantification summary shet obtained from the qPCR. The sheet need to be opened from homer locally and be saved on a macbook before uploading. NB! If running a manual qPCR the calulation will not work. Manully enter the calculations from the method 1031 qPCR procedure for NGS.
Press Calculate Concentration and Assign QC. This will pars the qPCR result file, calculate concentrations in nM, and set the QC flags.
The size adjusted concentration will automatically be calculated and filled in under concentration (nM) for each sample. If outlyers are found in any of the dilution-series these are removed before the calculations are done. 
A log file is generated. Open it to see details about witch dilution messurements were used when the calculations were performed.
The size adjusted concentration will automatically be calculated and filled in under concentration (nM) for each sample
Once done press the green NEXT STEP button in upper right corner.
If a sample has a red flag select still proceed with the sample to the NEXT STEP.










## Qubit QC (Library Validation) (Dev)
Write the assay used in Assay
Write the measured concentrations in Concentration
Write any comments in Comments
Press NEXT STEPS to proceed in the protocol.








## Aggregate QC (Library Validation) (Dev)
Run Aggregate QC Flags and Copy Fields. Concentration, Concentration (nM), Peak Size  and Average Size (bp) are copied from previous steps if they exist there.

Run Calculate Concentration (nM) if  this has not been calculated by qPCR.

Report Library QC to sample.

Go to NEXT STEP, FINISH STEP.
