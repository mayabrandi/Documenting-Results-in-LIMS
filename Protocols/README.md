# Protocols 

Protocols in lims are the equivalent of method documents. They consist of a series of steps where one or more samples are involved in a reaction or analysis. There are two types of protocols “QC protocols” and “Standard protocols”.

* When samples are in QC protocols they are queued in all steps simultaneously and the user choses which QC steps to perform. When one or more QC steps have been completed, the samples are queued in the “Aggregate QC” step, which serves as the gatekeeper of the QC protocol. In the aggregate step, the user either marks the samples to proceed in the workflow, or to remain in the QC protocol. A user can also request manager review, and a system administrator may remove the sample from the workflow. Think of the Aggregate QC step as where the decision to proceed or not in the workflow is made.
* A standard protocol is a protocol where samples move successively through the steps, starting with the first step and finishing with the last. Some steps may be skipped, but the steps carried out must be completed in the order of the protocol. A standard protocol, may have one or several QC steps.
