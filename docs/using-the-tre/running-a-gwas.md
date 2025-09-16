# Running a GWAS

## GWAS Training Video

Genes & Health have provided a number of training videos to help researchers get started with the Trusted Research Environment (TRE). This is a 45-min tutorial in which GWAS using regenie is demonstrated (300Mb with mp4 format, updated 5 oct 2022). This video is a recording of a live demo session, and the quality may not be perfect. It is recommended to watch the video in full screen mode. 

Please feel free to [download the video](https://dl.dropboxusercontent.com/s/k6h5botp53xk3l6/TRE%20Training-20220928\_160450-Meeting%20Recording.mp4?e=1\&dl=0) and watch it at your convenience.

### GWAS Example

You can find an example regenie script for binary trait GWAS below. Please feel free to adapt and reuse this script.

!!! warning "Caution"
    Please let your script run first on the cheap 2-core machine. Regenie has excellent multithreading capabilities and will perform best on the 64-core high-performance machine, but this option is expensive. The 2-core machine is sufficiently fast on a large multicore machine, allowing you to run it directly from the command line using a single all-chromosome pgen input file, without the need for HPC or splitting by chromosome. Regenie will utilise all available threads minus 1 by default, meaning the 64-core machine will run 63 times faster for the compute steps compared to the 2-core machine. It is fast enough on a large multicore machine to run several phenotypes. If you intend to run 1000 phenotypes, you will need to use Google HPC / WDL.

```bash


## RUN THIS FROM THE FOLDER WITH THE 
## COVAR/PHENO FILES AND WHERE YOU WANT THE OUTPUT

## this is for BINARY TRAITS
## remove the  --bt and firth etc options for quant traits, see the online regenie manual https://rgcgithub.github.io/regenie/options/

## first copy big files to local storage ivm SSD for better i/o than with google storage buckets
## regenie will sometimes crash if reading direct from library-red due to slow i/o
## cp /genesandhealth/library-red/genesandhealth/GSAv3EAMD/Jul2021_44k_TOPMED-r2_Imputation_b38/topmed-r2_merged_version03/chrALLincX.dose.merged_INFO0.3_MAF0.00001_F_MISSING0.2.8bit.sorted.p* /home/ivm/Documents/

## CHANGE THE DATE EACH RUN ## 
daterun=2022_07_20
     
covarfile="/genesandhealth/library-red/genesandhealth/GSAv3EAMD/Jul2021_44k_TOPMED-r2_Imputation_b38/GNH.44190.noEthnicOutliers.covariates.20PCs.tab"
## updated to covarfile with correct FID IID structure 15 July 2022

phenofile="/genesandhealth/library-red/genesandhealth/phenotypes_curated/version005_2022_06/1stoccurrence_3digitICD10_1SNOMEDto1ICD10/2022_06_version005_3digitICD10_1to1_42029withbothICD10andGSAJul2021.txt"

## these are the custom phenotypes: "/genesandhealth/library-red//genesandhealth/phenotypes_curated/version005_2022_06/custom/2022-06-15_big_regenie_phenoFile.txt"

grmfile="/genesandhealth/library-red/genesandhealth/GSAv3EAMD/Jul2021_44k_TOPMED-r2_Imputation_b38/bfile_forSAIGEgrm_44396_chipgenotypes_indep-pairwise_500_50_0.2_LDpruned_NotChrY"

## regenie will run all phenotypes in the phenoFIle if you dont specify --phenoCol or --phenoColList

## beware the .log file does not have phenotype name in its filename (because it is designed for running many phenotypes at once), can get overwritten if run multiple times using same $daterun

## if want to run male-only or female-only analysis, best to use --keep with a list of individuals in Step1 Step2 rather than --sex-specific. Because sex-specific uses the sex in the bed or pgen files not from the covariate file. And sex is NA in the pgen file we have made

regenie   \
  --step 1 \
  --bed "$grmfile" \
  --covarFile "$covarfile" \
  --phenoFile "$phenofile" \
  --phenoExcludeList PseudoNHS_2022_02_08 \
  --phenoCol ICD10__E10,ICD10__E11 \
  --minCaseCount 100 \
  --bsize 1000 \
  --bt \
  --lowmem \
  --lowmem-prefix tmp_rg \
  --gz \
  --verbose \
  --out "$daterun"_fit_binary_out

regenie \
  --step 2 \
  --pgen /home/ivm/Documents/chrALLincX.dose.merged_INFO0.3_MAF0.00001_F_MISSING0.2.8bit.sorted \
  --covarFile "$covarfile" \
  --phenoFile "$phenofile" \
  --bsize 1000 \
  --minMAC 20 \
  --minINFO 0.6 \
  --bt \
  --firth --approx \
  --pThresh 0.01 \
  --pred "$daterun"_fit_binary_out_pred.list \
  --gz \
  --verbose \
  --out "$daterun"_GNH_binary_GWAS_firth

## END ##

```
