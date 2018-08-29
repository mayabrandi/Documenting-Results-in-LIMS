
# Illumina SBS (HiSeq 2500)

## Sort HiSeq Samples 

## Aliquote samples for Library Pooling 


All samples that pass the sample prepartion for SureSelext XT moves to the Aliquote samples for Library Pooling step. This step is used to calculate the aliquote of sample to take to make a pool with a specific concentration and with the right composition regarding reads per sample.

Start by selecting the application that the samples are going to be sequenced with from the drop down menu in the top right corner. This will decide the "Number of Reads Expected" and the "Final Concentration (nM)"  depending on what flow cell and how many lanes the pool will be sequenced in. If needed this can be manually changed.
Next enter the total volume of the pool.
The Check Indexes button runs a script to check for duplicated index-sequences in the step. A warning and a info file will be generated if duplicates exist. Abort the step and restart it without colliding indexes.
If samples are moved to the current protocol from RML, press Copy Concentration (nM) - RML. Otherwise, press Copy Concentration (nM) to copy concentration from previous step. 
Press Get Reads to Sequence (M) to get the number of missing reads and populate the "Reads to sequence (M)" field. This is calculated from the amount of reads specified in the application tag minus the reads already sequenced (if the sample is being re-sequenced). If needed adjust manually.
To calculate the EB volume and the individual sample volume press Prepare for Pooling. NB! If the sample volume is below 1 ul there will be a warning. Either increase the Total Volume or dilute the samples and adjust the sample concentration accordingly to increase the volume of the sample.
Make Placement Map generates a placement map :)
When done press NEXT STEPS.

<p align="center"><img height="600" width="800" src="img/Illumina_SBS_HiSeq_2500/1.png"></p>




## Library Pooling (Illumina SBS)


Samples from step 2.2.1 have to be pooled technically in LIMS. Just drag and drop the samples that are to be pooled onto the tube icon. If more than one pool is made just add a pool#2 and so on. A check for index collisions is run at the exit of the pooling step and will stoop you from continuing if duplicate index sequences are present. The next step is Cluster Generation (Illumina SBS).



## Cluster Generation (Illumina SBS)
In the queue view add the pools that you want to cluster and in the icebucket view under container select the "Illumina Flow cell Rapid Mode" if sequencing in rapid mode and the "Illumina Flow Cell" if sequencing in high output mode. If clustering on the HiSeq 2500 make sure to have 2 replicates of the pool to place in the flow cell in the "place sample" view.
In the "place sample" view drag and drop the pools into the corresponding lane of the flow cell. Don't forget to change the name of the flow cell.
In the "record details" view fill in the appropriate fields and press Generate SampleSheet CSV. This generates a sample sheet that you should download to the local computer for sample sheet generation according to 1038 To create a samplesheet for demultiplexing HiSeq runs.
proceed to theNEXT STEP.

## Illumina Sequencing (Illumina SBS)


Start this step in LIMS before starting the sequencing on the machine. Only process one flow cell at a time in this step. Several flow cells can be processed in parallel.

The fields in the "record details" view will for the most part be auto populated. Only fill in the RGT numbers for the reagent boxes.
Press the blue save button and leave the page.
When the run has finished resume the step from the lab view in LIMS. The sample table will now be filled in with QC data from the sequencing run.
Check that everything has been filled in or make a note about it in the comment field. Then proceed to the next step.

## Bcl Conversion & Demultiplexing (Illumina SBS)


Once the flow cell has been demultiplexed the Bcl Conversion & Demultiplexing (Ilumina SBS) can be started. Only process one flow cell at a time in this step.

Fill in the method document for demultiplexing and the document version. Set the "Threshold for % bases >= Q30" to 80.
Press the blue demultiplexing button. This will fetch the number of reads, % perfect index reads and %Q30 from the demultiplexing stats. If the data is not available for LIMS the numbers can be filled in manually.
Then press the blue Set QC button to evalute the %Q30 threshold and set a QC flag.
Proceed to the NEXT STEP.

## Sequence Aggregation


This step counts the number of reads a sample has gotten in total and summarizes the Missing Reads for easy evaluation of the need for resequencing or not.

In the "record details" view press the blue Copy UDFs button to fetch the number of reads.
Press the blue Aggregate reads button to add all reads from all flow cells the sample has been sequenced in.
Press the blue Get Rerun Info button to calculate the number of missing reads. Note! The calculation is based on 75% of the total reads from the application tag, if this is reached 0 reads missing will be shown. However, if the sample did not reach this threshold, the actual number of missing reads in relation to 100% of the total reads from the application tag will be shown.
Press the blue Report Sequencing QC to sample button before clicking the NEXT STEPS button. 
This will automatically trigger the "rerun HiSq2500" script that will evalute the missing reads and tick the rerun box if more reads are needed. Press FINISH STEP to automatically send the samples to Delivery and Invoicing (section 2.2.4) or to be requeued in the Aliquote samples for library pooling step.
Workflow: RML


Ready made libraries are a little special in the sense that the samples being multiplexed are pre-pooled when they are handed in to the facility. To facilitate Library Validation QC the pools need to be constructed in the LIMS system before recording the measurements. The RML workflow therefore begin with a pooling step (after reception control). 
