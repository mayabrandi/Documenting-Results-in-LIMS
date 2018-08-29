
# Illumina SBS (HiSeq X)


## Step 1 Sort HiSeq X samples (HiSeq X)
The first step of the HiSeq X sequencing workflow is to allocate the samples to the appropriate step. In general, all samples go on to Library Normalization (HiSeq X) unless they need to be pooled for sequencing on one lane in which case they are assigned to Aliquot Samples for Library Pooling (HiSeq X). The samples can also be allocated to the Illumina SBS (HiSeq2500) sequencing workflow if the samples needs to be sequenced on a rapid or high output flow cell. To do that select the HiSeq 2500 check box in the Record details screen. Also remember to select Remove from workflow in the NEXT STEPS view.





From the ice bucket view choose 96-well plate as container.
In the "place sample" view add the samples to the corresponding wells in the sample prep plate and change the name to the plate name. If the samples are prepared in different plates add more plates by pressing the + sign. Place and name the new plates accordingly.
In the NEXT STEP view, samples that are checked to be sent to HiSeq2500, should be assigend with Remove from protocol.
The other samples should either be assigned with Aliquot Samples for Library Pooling or Library Normalization (HiSeq X) 
Press FINISH STEP.




## Step 2.1.1 Aliquote samples for Library Pooling 


All samples that pass the sample prepartion for SureSelext XT moves to the Aliquote samples for Library Pooling step. This step is used to calculate the aliquote of sample to take to make a pool with a specific concentration and with the right composition regarding reads per sample.

Start by selecting the application that the samples are going to be sequenced with from the drop down menu in the top right corner. This will decide the "Number of Reads Expected" and the "Final Concentration (nM)"  depending on what flow cell and how many lanes the pool will be sequenced in. If needed this can be manually changed.
Next enter the total volume of the pool.
The Check Indexes button runs a script to check for duplicated index-sequences in the step. A warning and a info file will be generated if duplicates exist. Abort the step and restart it without colliding indexes.
If samples are moved to the current protocol from RML, press Copy Concentration (nM) - RML. Otherwise, press Copy Concentration (nM) to copy concentration from previous step. 
Press Get Reads to Sequence (M) to get the number of missing reads and populate the "Reads to sequence (M)" field. This is calculated from the amount of reads specified in the application tag minus the reads already sequenced (if the sample is being re-sequenced). If needed adjust manually.
To calculate the EB volume and the individual sample volume press Prepare for Pooling. NB! If the sample volume is below 1 ul there will be a warning. Either increase the Total Volume or dilute the samples and adjust the sample concentration accordingly to increase the volume of the sample.
Make Placement Map generates a placement map :)
When done press NEXT STEPS.






## Step 2.1.2 Library Pooling (HiSeq X)


Samples from step 2.2.1 have to be pooled technically in LIMS. Just drag and drop the samples that are to be pooled onto the tube icon. If more than one pool is made just add a pool#2 and so on. The next step is Cluster Generation (HiSeq X). 



## Step 2.2 Library Normalization (HiSeq X)
In the queue view add samples that are to be sequenced together to the icebucket (most often 8 samples, one per lane). First choose samples that have the priority set to "express" or "priority", then "standard" and lastly "research". If possible always sequence samples belonging to the same family together. Make sure that samples with the C060 tag have 2 available positions, that means only add 7 samples if one sample has C060.
In the "place sample" view name the strip tube (for example after the sequencing instrument and flow cell position, "Rosaly A") and place the samples according to what lane they will be sequenced in. Go to "record details".
If samples are moved from a RML protocol into the current protocol, run Copy UDFs from Library Validation RML. Otherwise run  Copy UDFs from Library Validation.
The Concentration fields should be populated.
Run Calculate Volume to calculate what volume of sample and EB buffer to add to each strip tube well. The preset final concentration is 2.5 nM, but if needed this can be changed in the Final Concentration field (for example if a sample has a lower concentration than 2.5 nM). Make a note of this in the comment field.
Run Make Placement Map. A placement map will occur under files.
Proceed to the NEXT STEP.




## Step 3 Cluster Generation (HiSeq X)
In the queue view add the strip tube containing the samples you want to cluster.
In the "place sample" view drag and drop the samples into the corresponding lane of the patterned flow cell. Don't forget to change the name of the flow cell.
In the "record details" view fill in the appropriate fields and press the blue Generate bcl2fastq Sample Sheet button. This generates a sample sheet that you should download to the local computer for sample sheet generation according to 1038 To create a samplesheet for demultiplexing HiSeq runs.
proceed to the NEXT STEP.

## Step 4 Illumina Sequencing (HiSeq X)


Start this step in LIMS before starting the sequencing on the machine. Only process one flow cell at a time in this step. Several flow cells can be processed in parallel.

The fields in the "record details" view will for the most part be auto populated. Only fill in the RGT numbers for the reagent boxes.
Press the blue save button and leave the page.
When the run has finished resume the step from the lab view in LIMS. The sample table will now be filled in with QC data from the sequencing run.
Check that everything has been filled in or make a note about it in the comment field. Then proceed to the NEXT STEP.

## Step 5 Bcl Conversion & Demultiplexing (Illumina SBS)


Once the flow cell has been demultiplexed the Bcl Conversion & Demultiplexing (Ilumina SBS) can be started. Only process one flow cell at a time in this step.

Fill in the method document for demultiplexing and the document version. Set the "Threshold for % bases >= Q30" to 75.
Press the blue demultiplexing button. This will fetch the number of reads, % perfect index reads and %Q30 from the demultiplexing stats. If the data is not available for LIMS the numbers can be filled in manually.
Then press the blue Set QC button to evalute the %Q30 threshold and set a QC flag.
Proceed to the NEXT STEP.

## Step 6 Sequence Aggregation


This step counts the number of reads a sample has gotten in total and summarizes the Missing Reads for easy evaluation of the need for resequencing or not.

Press the blue Aggregate reads button to add all reads from all flow cells the sample has been sequenced in.
Press the blue Get Rerun Info button to calculate the number of missing reads. Note! The calculation is based on 75% of the total reads from the application tag, if this is reached 0 reads missing will be shown. However, if the sample did not reach this threshold, the actual number of missing reads in relation to 100% of the total reads from the application tag will be shown.
Press the blue Report Sequencing QC to sample button before clicking the NEXT STEPS button. 
This will automatically trigger the "rerun HiSeq X" script that will evalute the missing reads and tick the rerun box if more reads are needed. Press FINISH STEP to automatically send the samples to Delivery and Invoicing (section 2.2.4) or to be requeued in the Sort HiSeq X samples (HiSeq X) step.



