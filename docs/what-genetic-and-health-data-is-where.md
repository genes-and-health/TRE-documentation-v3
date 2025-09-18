# What genetic and health data is where?

## TRE identifiers

There are two identifiers in the G&H TRE which allow data linkage (e.g. genomic data to binary traits):

1. **PseudoNHS number:** these 64-character alpha-numeric strings serves as a unique identifier for individuals and are used for health data and phenotype identification.
2. **OrageneID**: these 14-digit strings serves as an identifier for saliva tube DNA IDs.

!!! warning
    Multiple samples may be collected from the same individual, resulting in a many-to-one relationship between Oragene ID and PseudoNHS number.

### GSA and Exome data identifiers (assay IDs)

Genetic assays, such as exome sequencing or GSA chip analysis, are assigned assay IDs. 

For GSA chip analysis, the assay ID consists of the OrageneID concatenated with the Illumina chip ID and row position, e.g. **12345678901234_201234567890_R00C00**.

Exome sequencing assay IDs follow the format **GNH-12345678901234_2**, with the suffix accommodating multiple assays of a single Oragene ID. Multiple or repeated assays may be conducted on the same Oragene ID.

### Linking genetic assays and health data

There is a file linking OrageneIDs/assay IDs (for genetics & questionnaire data) with PseudoNHS numbers (for NHS e-health record data and stage-1 questionnaire data). This file may get updated and re-dated:

```
/library-red
└── genesandhealth
    └── 2025_02_10__MegaLinkage_forTRE.csv
```

!!! info
    Within the TRE community, this file is simply referred to as the MegaLinkage file or even sometime Megalinkage™ 

## TRE folders and what is in them

!!! warning
    This section is quite out of date and needs updating 2025-09-18

Please see the `README` files in each folder for detail.

### Illumina GSAv3EAMD genotyping chip and TOPMed-r2 imputation data:

```
/library-red/genesandhealth/GSAv3EAMD/
```

### Exome sequencing data

As of February 2022 n=5236 low/mid depth samples sequenced at Wellcome Sanger Institute and funded by Wellcome Sanger Institute are available. Both aligned cram files and callset vcfs are available. The file `5236_cram_IDlinkage.xlsx` links Oragene IDs with multiple ID types used by Wellcome Sanger Institute. Industry Consortium funded exome sequencing data on the full 50,000+ Genes & Health volunteer cohort during 9 month post datafreeze priority period will only be available in /consortiumpriorityperiod-library-red/ After the priority period data will go into:

```
/library-red/genesandhealth/exome_seq/ 
```

### Curated phenotypes (aka binary traits)

Phenotypes which have been manually or automatically curated for consistency:

```
/library-red/genesandhealth/phenotypes_curated/ 
```

See also [this document](https://docs.google.com/spreadsheets/d/1ipwdF2j_owfr_QbkDYk1rk0TW3KtdfQYVQn-Vf-o38s/edit?usp=sharing) which has data descriptions, case counts, and phenotype codelists.

### "Raw" phenotype data

'Raw' phenotype and health record data (NHS numbers pseudonymised, and de-identified of names, postcodes, dates of birth etc).

```
/library-red/genesandhealth/phenotypes_rawdata/
```

Data are organised by provider and data sharing agreement. This is so we can easily change access if any of the terms of data sharing change.

!!! warning
    Please note as of Feb 2023, we do not yet have permission from NHS Digital to put their data in the TRE. An amendment is awaited.
    
    A reference for the NHS Digital Data Model and dictionary can be found on [NHS Digital reference](https://digital.nhs.uk/data-and-information/data-tools-and-services/data-services/hospital-episode-statistics/hospital-episode-statistics-data-dictionary).

### Publicly available data

The **genesandhealth** folder contains downloadable data 'publicly' available to users (read-only):

```
/library-green/genesandhealth/
```


