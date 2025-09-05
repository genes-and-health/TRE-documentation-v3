# Explainers

## How is data linked

When volunteers take part in stage 1 of Genes & Health their questionnaire and consent form is labelled with the ID number on the Oragene saliva tube (style: **15001502031604**). These **Oragene IDs** are then used to label genetic samples (e.g. GSA chip or exome seq). They also label the Questionnaire. Some people have taken part twice (or more than twice) over the years in Genes & Health, and will have a different Oragene ID each time.

Genes & Health uses the Questionnaire data to look up a volunteer’s `5236\_cram\_IDlinkage.xlsx` (if not already provided). The NHS number (style: 1234567890 ) is one-way pseudonymised (always in the same way using the same encryption key) and the **pseudoNHS number** (style: 0EDFCE604D373660DDF34CA5CBDB754E3BAA17835530591C0161E459A82C7821) is the identified for all types of health record data. A volunteer should only have one single NHS number in NHS systems (we have found a few exceptions to this rule that we have reported to NHS Digital for consideration of merging).

A file is provided linking Oragene ID to pseudoNHS number (see below). Note that this linkage sometimes changes slightly e.g. if we find a missing NHS number, for new samples, or if we identify an error in previous NHS number lookup.

Recall studies (stage 2\) get their own stage 2 ID. We will provide files linking to **pseudoNHS number**. The primary identifier used for volunteer recall is the NHS number.

Wellcome Sanger Institute has used several other ID types e.g. sanger sample ID, cram file ID, EBI-EGA submission ID. See below. Broad Institute uses the Oragene ID with a prefix (style: GNH-15001502031604).

## Where are the data from

### Raw health data overview (UNDER CONSTRUCTION)

#### **Summary**

This page provides an overview of the raw health data available to Genes and Health TRE users. All files described below are located in genesandhealth/library-red, please see the [page](#folder-structures) describing TRE file structures for further information. File paths described below assume you are starting from genesandhealth/library-red

For complete descriptions of file contents, please see the [raw health data description](#what-do-the-raw-data-look-like).

All folders contain detailed README.txt files, which describe the contents of each data file in more detail (number of rows, number of G\&H volunteers present in the file etc).

### Primary care data

Primary care datasets and linkage are provided by agreement with GP practices, made at the CCG level. As of 2023-04-14 all primary care data are for participants registered with practices in East London only. Data are refreshed periodically to add complete historical records for new participants, and to update existing participants' records with information from clinical contacts made since the previous refresh.

#### **London**

All files are located in **/DSA\_Discovery\_7CCGs**. Subfolders are created for each data refresh. Folder names are the date of the refresh. For refreshes before 2023\_01 data are further split by Clinical Commissioning Group (CCG).

1. **GNH\_thwfnech** are for volunteers registered at practices in Tower Hamlets, Waltham Forest, Newham, City & Hackney CCGs  
     
2. **GNH\_bhr** are for volunteers registered at practices in Barking, Havering, Redbridge and outer east London CCGs

**For refreshes after 2023-01 the data for these two regions are combined.**

As of 2023-01 Genes and Health does not have access to data for volunteers registered with practices in the North West London and South East London CCGS

**Data files**  
Each folder contains the following files, all containing raw, individual level data, with one row per observation.

* **medications\_ord** for normal repeat prescriptions  
    
* **medications\_stmt** for short term medications and treatments  
    
* **observations** for diagnoses, blood test results, clinical measurements, other tests and referrals  
    
* **procedure\_req** for health and medication reviews, screening and vaccination records

All files contain:

* A pseudo nhs number for linkage across all health data, and to the Genes and Health OrageneID number.  
    
* SNOMED concept ID for describing diagnoses, procedures, and prescriptions (useful for generating binary traits)  
    
* value results (for test results e.g. creatinine, height etc where applicable and useful for generating quantitative traits)  
    
* value units (where applicable) describing the unit of measurement (e.g. meters or cm for height)  
    
* Clinical effective date (usually when the SNOMED code was entered into the patient record)

#### **Bradford**

No raw primary care data as of 2023-04-14

#### **Manchester**

No raw primary care data as of 2023-04-14

### Secondary care data

[Hospital Episode Statistics (HES)](https://digital.nhs.uk/data-and-information/data-tools-and-services/data-services/hospital-episode-statistics) data will be available on the TRE soon (pending NHS Digital approval at 2023-04-14), and for most purposes will supersede the regionally sourced secondary care data described below (HES will replicate the majority of data, and because it offers nationwide coverage, will include more G\&H volunteers).

At present, secondary care data are split by location. As of 2023-04-14 secondary care data are available for volunteers in London and Bradford.

#### **London**

All files are located in DSA\_BartsHealth\_NHS\_Trust. Subfolders are created for each data refresh. Folder names are the date of the refresh. Data are retrieved from the Barts Health Trust Data Warehouse and contain information on visits made by Genes and Health volunteers to hospitals in that Trust only.

Barts Trust provides multiple datasets that are unique/ specific to that Trust, including pathology lab data (useful for generating [quantitative traits](https://tre-documentation.pages.dev/docs/explainers/phenotype_curation)), prescribing data, and radiology department reports. Some datasets are only available by special request (e.g. maternity bookings, chemotherapy prescribing). Please see the README.txt in the DSA\_BartsHealth\_NHS\_Trust folder for further details.

Data in the icd\_10\_combined\_redacted.txt and opcs\_combined\_redacted.txt files will have substantial overlap with HES (see note above on availability), and are useful for generating [binary traits](https://tre-documentation.pages.dev/docs/explainers/phenotype_curation)

#### **Bradford**

Data provided by Bradford Teaching Hospitals NHS foundation trust

#### **Manchester**

No raw primary care data as of 2023-04-14

## What do the raw data look like

This section describes the **raw** phenotype files currently available in the TRE, and their location in the TRE file structure. Column headings are replicated directly, brief summaries of file contents and column contents will be updated.

For most users and use cases, this documment should serve as a reference guide only. Members of the GH data team have used the raw files described here to produce curated products, that will in most cases be more useful (and user friendly).

/genesandhealth/library-red/genesandhealth/phenotypes\_rawdata/DSA\_\_BartsHealth\_NHS\_Trust/2021\_04\_PathologyLab/AntiMullerianHormone\_April2021.csv

| PseudoNHSNo | Age At Test | Test Name | Date of Test | Result | Unit |
| :---- | :---- | :---- | :---- | :---- | :---- |
| Type description here | Type description here | Type description here | Type description here | Type description here | Type description here |

## Phenotype Curation (UNDER CONSTRUCTION)

This page provides a few examples of how the raw health data in the TRE have been curated to produce useful output for a range of analyses. The files used in the examples below are all located in genesandhealth/library-red, please see the [page describing TRE file structures](folder-and-bucket-structure.md/#library-red) for further information. An overview of the different datafiles are available in the [raw phenotype data page](#what-do-the-raw-data-look-like)

### Tools

The philosophy of the Genes and Health project is to provide researchers with the tools to generate their own phenotypes as well as providing a curated set of phenotypes.

The curated phenotypes are generated using the tre-tools package, which is a custom package developed by the Data Team. A curated phenotype is a phenotype that has been generated using a set of codelists that have been checked and validated by researchers in Genes and Health.

The code is available at [tre-tools](https://github.com/genes-and-health/tre-tools). We strongly recommend that you use this package to generate your own phenotypes, as the code has been generated by the Data Team using a software engineering approach, and has been thoroughly tested.

### Codelists

There are a number of codelists available in the TRE that can be used to generate phenotypes. These are stored in the library-red folder. The codelists are stored in a folder called codelists and are named according to the phenotype they are used to generate.

Codelists are simple csv files that contain the codes that are used to generate the phenotype. If you wish to use your own codelist, simply utilise the provided clipboard functionality, allowing you to transfer text data, such as CSV files, from your local machine to the TRE.

In order to make sure that analyses are only carried out with codelists that have the expected structure (i.e. the correct format for ICD10), the Data Team have created a set of tools in tre-tools that can be used to check the codelists.

The tool checks that all codes in the codelist conform to the expected format, and that there are no duplicate codes. For example, checking that a SNOMED codelist only contains SNOMED codes which have the format of a numerical value between 6 and 18 digits in length.

### Example code

The following code loads a codelist called Diabetes.

**diabetes.csv**

| code,term"100000001","Type 2 Diabetes""100000002","Diabetic Review" |
| :---- |

| from tretools.codelists.codelist\_types import CodelistTypefrom tretools.codelists.codelist import Codelist\# Load the codelistdiabetes \= Codelist("diabetes.csv", CodelistType.SNOMED.value) |
| :---- |

In the example above, we have loaded a codelist called diabetes.csv which contains two SNOMED codes. The Codelist class is used to load the codelist, and the CodelistType enum is used to specify the type of codelist. In this case, the codelist is a SNOMED codelist. If any of the codes in the codelist do not conform to the expected format, an error will be raised.

For more information on how to use the tre-tools package, please see the tre-tools documentation, and the test files in the tre-tools repository for examples of how to use the package. We welcome any feedback on the package, and are happy to help with any issues you may encounter.

### Binary Traits

Binary traits are those that have two possible outcomes, such as disease status (e.g. diabetes, hypertension). A person either has the disease or they do not.

The raw health data in the TRE is curated to produce binary traits for a range of analyses. The files used in the examples below are all located in genesandhealth/library-red. There is a lengthy readme file in the folder that describes the data in detail, along with timestamps for when the data was last updated. We recommend that you read this file before using the data.

The binary traits data was generated using the tre-tools custom package. The code is available at [tre-tools](https://github.com/genes-and-health/tre-tools). The data has been cleaned and processed for use in a range of analyses. The data includes all the primary care and hospital data for the Genes and Health cohort, and has been processed and saved in a format that is easy to use for different types of analyses. The cleaning processes are described in the README file in the folder but in summary:

* Each data file has been loaded and de-duplicated on the basis of the unique identifier for each patient, date and code.  
* All datasets of the same coding system (for example, ICD10) have been merged into a single dataset for each "time cut" of data received.  
* All datasets have been merged into a single dataset for each coding system.

Binary trait reports are generated using the tre-tools package and use ProcessedDataset and Codelist classes to generate a PhenotypeReport object. The PhenotypeReport object can then be used to generate a range of reports for the binary traits, including Regenie input files.

#### **Example workflow**

#### **Example code**

### Quantitative traits

#### **Codelists**

#### **Example workflow**

#### **Example code**
