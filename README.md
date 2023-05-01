# VKR
Non-Negative Matrix Factorization Improved Kernel Regression for Side Effect Prediction
ipynb for review of ADRs prediciton study and VKR.


# .ipynb file
The .ipynb files are for generating the results of ADRs prediction using multiple models, including the Naive method (Calculating Mean across drugs as prediction of a ADR), Kernel Regression(KR), Support Vector Machine (SVM) wiith kernel Radial Basis Function (RBF) kernel, Linear kernel and Weighted Generalized T-Student (WGTS) kernel, Linear Neighbourhood Similarity Method (LNSM) with different feature combination methods including Cost Minimization Integration method (CMI) and Similarity Matrix Integration (SMI) method. Further more, we also built .ipynb files for genereting figures, as well as the p-values for methods comparison.


## ADRs Prediction

The code for side effects prediction were built based on different models. Here are the .ipynb files for generating the results of nested CV and the independent test sets 
for the models. 
- KR.ipynb: Kernel Regression, Multi-Kernel Regression for integrating features
- Naive.ipynb: Naive method
- LNSM_RLN.ipynb: LNSM, LNSM-CMI and LNSM-SMI with Regularized Linear Neighbourhood Similarity (RLN)
- LNSM_Jaccard.ipynb: LNSM, LNSM-CMI and LNSMS-SMI with Jaccard Similarty
- SVM_Linear.ipynb: SVM with linear kernel
- SVM_RBF.ipynb: SVM with RBF kernel
- SVM_WGTS.ipynb: SVM with WGTS kernel
- VKR.ipynb: Our VKR method

Each file has sections: 

* 1. Define the functions used
* 2. Nested CV and CV
    * 2.1. Nested CV
    * 2.2. CV to tune hyperparameters for independent test set
    * 2.3. Independent test set
    * \*. Save data for PR and ROC

After the first section ran, you can run the subsection 2.1.-2.3. separately. Section 2.1. is for the nested CV of methods and running this section is time consuming. Section 2.2. is for tuning the hyperparmeters for section 2.2. Section \* is for saving the result of 2.3. used for AUROC and AUPR. Run code in section 2.3. before section \*. 

Input: data/
- intersection_DGIdb_mat.tsv: Drug-gene interaction pairs from DGIdb. Data were generated to the binary matrix form. Drugs are intersection of DGIdb 4.0 and SIDER 4.1.
- intersection_Fingerprint_mat: Fingerprints from PubChem. Data were generated to the binary matrix form. Drugs are intection of PubChem Chemical structure fingerprint and SIDER 4.1.
- side-effect-and-drug_name_upper: Drug-side effect pairs from SIDER 4.1.


## Pairwise Paired T-test

Pvalue.ipynb is for calculating the P-value of pairwise paired t-test. Results from the nested CV is "results/AUPR.csv" and "results/AUPR/csv", which is also the input of Pvalue.ipynb. The output of the P-values are "results/Pvalue_AUPR.csv" and "results/Pvalue_AUROC.csv".


## Figures

"Figs" contains the ipynb generate figures for our study. The input of th

# Data

# Figs

# Results
