# GWAS-serum-uric-acid
This repository contains the code for a GWAS of serum uric acid in a Scottish population using a mixed model. 

## Analysis Overview
GWAS was performed on serum uric acid levels using FastGWA and a mixed linear model. FastGWA applied linear regression with SNPs as predictors and age and sex as covariates, while the mixed model accounted for relatedness and population structure via a genomic relationship matrix. Population structure was assessed using Principal Component Analysis, but no significant structure was found. QQ plots were generated for both models to compare observed versus expected p-value distributions, and genomic control was applied to the standard GWAS to assess test statistic inflation. Analyses, quality control, and visualization were conducted using PLINK, GCTA, and RStudio.

## Key Results
Population Structure & Relatedness:
QQ plots of the standard GWAS showed deviation from expected p-values (slope = 1.184, λ = 1.23), indicating confounding due to relatedness or population structure.
After applying a mixed linear model (MLMA) accounting for relatedness, QQ plots showed a good fit (slope = 1, λ = 1.002), confirming confounding was controlled.
PCA of genomic data revealed minimal population structure (first 5 PCs explained only 2.74% of variance, no clustering observed).

GWAS Findings:
Standard GWAS (uncorrected for relatedness): 5 significant SNPs. Standard GWAS with genomic control: 1 significant SNP (rs13129697), effect = -0.32, variance explained ~0.04%, heritability ~3.65%. MLMA GWAS: 2 significant SNPs on chromosome 4, only 67 kb apart, effect estimates -0.33 and -0.35 mg/dL, standard errors 0.06–0.07, heritability ~3.67%. Proximity and similar effect sizes suggest these SNPs may tag a single causal variant.

Interpretation:
Accounting for relatedness improves model accuracy and reduces false positives. The two chromosome 4 SNPs are likely linked to uric acid metabolism.

<img width="745" height="443" alt="image" src="https://github.com/user-attachments/assets/e2a60df9-e2d0-4d22-a3e2-d4d342a79026" />

<img width="747" height="470" alt="image" src="https://github.com/user-attachments/assets/64eb8776-08b3-449d-b24a-8699f582829b" />

<img width="736" height="503" alt="image" src="https://github.com/user-attachments/assets/25a2843c-56c6-400e-9e7e-76094548f82d" />

<img width="858" height="96" alt="image" src="https://github.com/user-attachments/assets/86aecb23-18cd-4497-b7e5-77f017cb6e48" />






