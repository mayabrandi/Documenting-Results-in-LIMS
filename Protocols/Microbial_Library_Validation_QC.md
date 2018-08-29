# Microbial Library Validation QC




## Tapestation Microbial QC  


Fill in all required fields.
Enter the Size (bp) for the samples that has been messured.
Run Set Average Size (bp). This will calculate the average size and apply it to all samples.
Run Assign QC flag. 
Go to NEXT STEP and FINISH STEP. If sample has not passed the QC step, select leave in QC protocol if you want to proceed with it.










## Quantit QC (Library Validation)


Fill in all required fields.
Upload the result file from the Plate reader with concentrations.
Run Get concentrations from result file to set the Concentration UDFs.
Go to NEXT STEP and FINISH STEP. If sample has not passed the QC step, select leave in QC protocol if you want to proceed with it.










## Aggregate QC (Library Validation)


Run Aggregate QC Flags and Copy Fields. Concentration and Average Size (bp) are copied from previous steps, for all samples. 

Run Calculate Concentration (nM) and Report Library QC to sample.

If some samples shouldn't not go through Normalization of microbial samples for sequencing, check Skip Normalization for these samples. 
Go to NEXT STEP.
Select Remove from protocol for the samples that should skip Skip Normalization.
Select Mark protocol as complete for the other samples.
Klick FINISH STEP.
