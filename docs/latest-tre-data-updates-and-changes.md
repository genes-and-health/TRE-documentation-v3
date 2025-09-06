# Latest TRE data updates and changes {#latest-tre-data-updates-and-changes}

(newest shown first)

## 2025-MAY-20 by DVH  
>  Begun release of 55k exome ExWAS to Consortium1 partners. Quant traits initially, to be followed by binary traits.
>  ```
>  gs://qmul-production-library-consortiumpriorityperiod-red
>  └── Callsets
>      └── 2024_05_55kCallset
>          └── release_2025-JUN-16_ExWAS/
>  ```

## 2025-MAY-05 by DVH  
>  Released 51k GSA-TOPMEDr3 GWAS results for v010 quant traits
>  ```
>  gs://qmul-production-library-red
>  └── genesandhealth
>      └── GSAv3EAMD
>          └── Jan2024_51k_TOPMED-r3_Imputation_b38
>              └── 2025_05_v010_quantpy_GSATOPMEDr3_GWAS/
>  ```

## 2025-APR-28 by RK  
>  Improved the file dialog that allows users to upload files to the red bucket. Users can now upload files to the red bucket in the directory of their choice and create a new directory in the red bucket if they wish.

## 2025-APR-24 by DVH  
>  More Barts Health datafiles from 2024_09 release redaacted and put in the TRE
>  ```
>  gs://qmul-production-library-red
>  └── genesandhealth
>      └── phenotypes_rawdata
>          └── DSA__BartsHealth_NHS_Trust
>              └── 2024_09_ResearchDataset/
>  ```

## 2025-APR-24 by DVH  
>  New quant traits v010 uploaded:
>  ```
>  gs://qmul-production-library-red
>  └── genesandhealth
>      └── phenotypes_curated
>          └── version010_2025_04/
>  ```

## 2025-MAR-26 by DVH  
>  Uploaded new NHS England (ex Digital) HES data. More datasets still to come.  
>  ```
>  gs://qmul-production-library-nhsdigital-sublicence-red
>  └── DSA__NHSDigitalNHSEngland
>      └── 2025_03/
>  ```

## 2025-MAR-26 by DVH  
>  Uploaded new folder of gvcf files from exome sequencing. These are the input to variant joint calling. They are unfiltered samples and genotypes, do not use for genetic association studies!
>  ```
>  gs://qmul-production-library-consortiumpriorityperiod-red
>  └── gvcfs/
>  ```

## 2025-MAR-25 by DVH  
>  Removal of some files in previous Barts Health phenotypes_raw datasets, and replacement with more highly redacted versions:  
>  
>  **Deleted:**  
>  ```
>  gs://qmul-production-library-red
>  └── genesandhealth
>      └── phenotypes_rawdata
>         └── DSA__BartsHealth_NHS_Trust
>             └── 2024_09_ResearchDataset
>                 └── RDE_Measurements.ascii.redacted.tab
>  ``` 
>  **Replaced with:**   
>  ```
>   gs://qmul-production-library-red
>   └── genesandhealth
>       └── phenotypes_rawdata
>           └── DSA__BartsHealth_NHS_Trust
>               └── 2024_09_ResearchDataset
>                   └── RDE_Measurements.ascii.redacted2.tab
>  ```
>  ---
>  **Deleted:**  
>  ```
>  gs://qmul-production-library-red
>  └── genesandhealth
>      └── phenotypes_rawdata
>         └── DSA__BartsHealth_NHS_Trust
>             └── 2023_12_ResearchDatasetv1.6
>                 └── GandH_Measurements__20240423.ascii.redacted.tab
>  ```
>  **Replaced with:**  
>  ```
>  gs://qmul-production-library-red
>  └── genesandhealth
>      └── phenotypes_rawdata
>         └── DSA__BartsHealth_NHS_Trust
>             └── 2023_12_ResearchDatasetv1.6
>                 └── GandH_Measurements__20240423.ascii.redacted2.tab
>  ```
>  ---
>  **Deleted:** - we do not think this file is used at all, so have not replaced.
>  ```
>  gs://qmul-production-library-red
>  └── genesandhealth
>      └── phenotypes_rawdata
>         └── DSA__BartsHealth_NHS_Trust
>             └── 2023_12_ResearchDatasetv1.6
>                 └── in-beta-testing
>                     └── GH_RAW_Pathology__20231211.ascii.redacted.tab
>  ```
>  ---
>  **Deleted:**  
>  ```
>  gs://qmul-production-library-red
>  └── genesandhealth
>      └── phenotypes_rawdata
>         └── DSA__BartsHealth_NHS_Trust
>             └── 2024_09_ResearchDataset
>                 └── RDE_Pathology.ascii.nohisto.redacted.csv
>  ```
>  **Replaced with:**  
>  ```
>  gs://qmul-production-library-red
>  └── genesandhealth
>      └── phenotypes_rawdata
>         └── DSA__BartsHealth_NHS_Trust
>             └── 2024_09_ResearchDataset
>                 └── RDE_Pathology.ascii.nohisto.redacted2.csv
>  ```
>  ---
>  **Deleted:**  
>  ```
>  gs://qmul-production-library-red
>  └── genesandhealth
>      └── phenotypes_rawdata
>         └── DSA__BartsHealth_NHS_Trust
>             └── 2023_12_ResearchDatasetv1.6
>                 └── GH_Pathology__20231218.ascii.nohisto.redacted.tab
>  ```
>  **Replaced with:**
>  ```
>  gs://qmul-production-library-red
>  └── genesandhealth
>      └── phenotypes_rawdata
>          └── DSA__BartsHealth_NHS_Trust
>              └── 2023_12_ResearchDatasetv1.6
>                  └── GH_Pathology__20231218.ascii.nohisto.redacted2.tab
>  ```
