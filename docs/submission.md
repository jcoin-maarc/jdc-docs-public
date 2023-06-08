# Submission and Curation

## Core Measures

Below are general submission instructions JCOIN core measure data submissions.

!!! important 

    Please reach out to the MAARC (see the "Contact" section [here](https://jcoin-maarc.github.io/jdc-docs-public/contact/)) or data manager list serve to chart out a hub-specific data management plan, technical assistance, or any other questions. Below are general guidelines. Hub specific procedures are catered towards hub internal workflows and preferences while maintaining data privacy and security standards. __Below is one recommended workflow__

### Individual level data submissions

#### 1. __Harmonize local hub variables with the core measure data elements__ 

The initial step involves mapping and transforming local datasets to the common core measure datasets.

The final datasets (ie the datasets hubs submit to the MAARC) are 2 files: a baseline (ie person-level dataset) and a timepoints file (ie measures taken across all timepoints from baseline to each follow up) for both staff and clients (participants). 

!!! important 
JCOIN submission dataset variable names can be one of:

1. the __original__ variable names (called `custom.original_name`)
 Upon submission, these __original__ names will be automatically remapped to the "new" `name`.
2. the __new__ variable names (called `name` in the data dictionaries/schemas)

!!! note

    For more info on the core measure variables, variable values, and file structure, [__click here__](https://jcoin-maarc.github.io/JCOIN-Core-Measures). 

    For synthetic (ie fake) examples of the to-be submitted core measure datasets, see the "data" folder within the core measure data package [__here__](https://github.com/jcoin-maarc/jdc-utilities/tree/main/data/core-measures-test/data)

!!! note

    Tools are also available in the jdc-utilities repository [see here](https://github.com/jcoin-maarc/jdc-utilities) to facilitate harmonization. The MAARC leverages these tools but during the initial data management plan meeting, the MAARC and data manager can establish how to go about using these.

#### __2. Deidentification: Replace ids and date shifting__

After harmonizing variables, to reduce the risk of disclosure, two additional steps are taken:

- __replace the local participant ids (ie PIDs etc) with a list of MAARC-generated ids.__ These mappings (ie local to JDC ids) should be stored locally. The list of ids will be provided in the initial data management plan meeting(s).

-  __shift all dates__ in datasets by a random number of days between 182 and -182 days (with this number remaining constant/fixed within an individual to allow time interval calculations).

!!! note

    To date, hubs have used a set of utilities built by the MAARC [located here](https://github.com/jcoin-maarc/jdc-utilities). These utilities provide automated version control and produces a local to JDC id mapping key. A specific plan for leveraging these tools is dependent on the hub's data management process and will be discussed in the initial meetings.

#### __3. Submit files to a HIPAA-compliant Box folder.__ 

This will be a folder restricted to approved MAARC personnel and the associated hub's data manager.

### Marginal count data submissions

For studies (or components of a study) that are contractually unable to provide individual level data, we have created templates to gather marginal counts of key demographic variables. 

[__Click here__](https://app.box.com/s/uafa6wyzqxcdgvdl0mfbep0li79xh2ic) to download the current template and instructions. 

!!! note

    A separate template for DSMB reports exists. If hubs prefer to just fill out DSMB templates (which is a little more involved), we can also use these marginal counts to derive the more "de-identified" JDC marginal counts. 

1. Fill out template (from above).
2. Submit files to a HIPAA-compliant Box folder. This will be a folder restricted to approved MAARC personnel and the associated hub's data manager.

## What happens after submission to Box (or other secure file transfer method)?

1. After submission to Box, the MAARC fine-tunes submissions (eg deleting minor inconsistencies such as commas, spaces, small words in the value labels) to ensure the data conform exactly to the data model. Then, the datasets are bundled with metadata (ie., the core measure data dictionaries and study level metadata) and compressed into a zip file.

2. This zip file is then uploaded to the JDC. Additionally, a subset of variables and these zipped files are mapped to the JDC data model to allow researchers to quickly examine enrollment and time point counts as well as to download the zipped data packages. For more information on using the JDC explorer, see the JDC explorer section [here](https://jcoin-maarc.github.io/jdc-docs-public/platform/explorer/)

3. From the explorer, one can download the final core measure data package (**IMPORTANT: only for researchers with permissions**). For questions about this, contact the MAARC (ie Phil Schumm; Mike Kranz). A publicly available test version (with fake/synthetic data) is available in two forms:

(1) a zipped package [click to download](https://github.com/jcoin-maarc/jdc-utilities/blob/main/data/core-measures-test.zip)
(2) unzipped data package directory [click here](https://github.com/jcoin-maarc/jdc-utilities/tree/main/data/core-measures-test)

!!! note 

    TOADD: For more information on the overall workflow, refer to the "Overall workflow" section (these have been socialized at various JCOIN meetings).

### Follow-up and iteration

After the initial submission is complete and for subsequent submissions, the MAARC and the hub collaborate on additions to core measure datasets and any other fine-tuning needed.



