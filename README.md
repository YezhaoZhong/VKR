# VKR

.ipynb for review of ADRs prediciton study and VKR in 'Non-Negative Matrix Factorization Improved Kernel Regression for Side Effect Prediction'.



# .ipynb file
The .ipynb files are for generating the results of ADRs prediction using multiple models, including the Naive method (Calculating Mean across drugs as prediction of a ADR), Kernel Regression(KR), Support Vector Machine (SVM) wiith kernel Radial Basis Function (RBF) kernel, Linear kernel and Weighted Generalized T-Student (WGTS) kernel, Linear Neighbourhood Similarity Method (LNSM) with different feature combination methods including Cost Minimization Integration method (CMI) and Similarity Matrix Integration (SMI) method. Further more, we also built .ipynb files for genereting figures, as well as the p-values for methods comparison.


## Side Effects Prediction

The code for side effects prediction were built based on different models. Here are the .ipynb files for generating the results of nested CV and the independent test sets 
for the models. 
- [KR.ipynb](https://github.com/YezhaoZhong/VKR/blob/main/KR.ipynb): Kernel Regression, Multi-Kernel Regression for integrating features
- [Naive.ipynb](https://github.com/YezhaoZhong/VKR/blob/main/Naive.ipynb): Naive method
- [LNSM_RLN.ipynb](https://github.com/YezhaoZhong/VKR/blob/main/LNSM_RLN.ipynb): LNSM, LNSM-CMI and LNSM-SMI with Regularized Linear Neighbourhood Similarity (RLN)
- [LNSM_Jaccard.ipynb](https://github.com/YezhaoZhong/VKR/blob/main/LNSM_Jaccard.ipynb): LNSM, LNSM-CMI and LNSM-SMI with Jaccard Similarty
- [SVM_Linear.ipynb](https://github.com/YezhaoZhong/VKR/blob/main/SVM_Linear.ipynb): SVM with linear kernel
- [SVM_RBF.ipynb](https://github.com/YezhaoZhong/VKR/blob/main/SVM_RBF.ipynb): SVM with RBF kernel
- [SVM_WGTS.ipynb](https://github.com/YezhaoZhong/VKR/blob/main/SVM_WGTS.ipynb): SVM with WGTS kernel
- [VKR.ipynb](https://github.com/YezhaoZhong/VKR/blob/main/VKR.ipynb): Our VKR method

Each file has sections: 

* 1. Define the functions used
* 2. Nested CV and CV
    * 2.1. Nested CV
    * 2.2. CV to tune hyperparameters for independent test set
    * 2.3. Independent test set
    * \*. Save data for PR and ROC

After the first section ran, you can run the subsection 2.1.-2.3. separately. Section 2.1. is for the nested CV of methods and running this section is time consuming. Section 2.2. is for tuning the hyperparmeters for section 2.2. Section \* is for saving the result of 2.3. used for AUROC and AUPR. Run code in section 2.3. before section \*. 

Input: [/data/](https://github.com/YezhaoZhong/VKR/tree/main/data)
- [intersection_DGIdb_mat.tsv](https://github.com/YezhaoZhong/VKR/blob/main/data/intersection_DGIdb_mat.tsv): Drug-gene interaction pairs from DGIdb. Data were generated to the binary matrix form. Drugs are intersection of DGIdb 4.0 and SIDER 4.1.
- [intersection_Fingerprint_mat.tsv](https://github.com/YezhaoZhong/VKR/blob/main/data/intersection_Fingerprint_mat.tsv): Fingerprints from PubChem. Data were generated to the binary matrix form. Drugs are intection of PubChem Chemical structure fingerprint and SIDER 4.1.
- [side-effect-and-drug_name_upper.tsv](https://github.com/YezhaoZhong/VKR/blob/main/data/side-effect-and-drug_name_upper.tsv): Drug-side effect pairs from SIDER 4.1.

Organized output for nested CV: [/results/](https://github.com/YezhaoZhong/VKR/tree/main/results)
- [AUPR.csv](https://github.com/YezhaoZhong/VKR/blob/main/results/AUPR.csv)
- [AUROC.csv](https://github.com/YezhaoZhong/VKR/blob/main/results/AUROC.csv)

Output for independent set: [/Figs/](https://github.com/YezhaoZhong/VKR/tree/main/Figs)
- \*.csv

Required modules:
- pandas
- networkx
- numpy
- sklearn
- time
- scipy
- joblib
- itertools


## Pairwise Paired T-test

Pvalue.ipynb is for calculating the P-value of pairwise paired t-test. 

Input: [/results/](https://github.com/YezhaoZhong/VKR/tree/main/results)
- [AUPR.csv](https://github.com/YezhaoZhong/VKR/blob/main/results/AUPR.csv)
- [AUROC.csv](https://github.com/YezhaoZhong/VKR/blob/main/results/AUROC.csv)

Output: [/results/](https://github.com/YezhaoZhong/VKR/tree/main/results)
- Pvalue_AUPR.csv
- Pvalue_AUROC.csv

(Shown after Pvalue.ipynb ran)

Required modules:
- pandas
- numpy
- pingouin

## Figures

[/Figs/](https://github.com/YezhaoZhong/VKR/tree/main/Figs) contains the .ipynb generate figures for our study and the output of independent test set, which is also the input of the '/Figs/\*.ipynb'.

- [DGI_Chem.ipynb](https://github.com/YezhaoZhong/VKR/blob/main/Figs/DGI_Chem.ipynb): Generate Figure S 5.
- [KR_VKR.ipynb](https://github.com/YezhaoZhong/VKR/blob/main/Figs/KR_VKR.ipynb): Genrate Figure S 4.
- [Overall.ipynb](https://github.com/YezhaoZhong/VKR/blob/main/Figs/Overall.ipynb): Generate Figure 2.

Input: 
- /Figs/\*.csv (After code in sections '\*. Save data for PR and ROC' ran)
Ouput: 
- /Figs/\*.jpg

Required modules：
- pandas
- matplotlib
- sklearn
- numpy



## Author
Yezhao Zhong
Cathal Seoighe
Haixuan Yang

## License

This project is licensed. See [LICENSE](https://github.com/YezhaoZhong/VKR/blob/main/LICENSE) file for details.
