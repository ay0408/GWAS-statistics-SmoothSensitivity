# Differentially Private GWAS Statistics based on Smooth Sensitivity

This contains Python codes used in our experiments on differentially private (DP) GWAS statistics based on their ${\it smooth\ sensitivities}$.

This study focuses on key statistics in GWAS: $\chi^2$-statistics based on a contingency table and TDT statistics for family-based association studies.

"Accuracy" folder contains the experimental results on differences between the original and DP statistics.
In addition to the results provided in our paper, those for smaller ($N=1,000$) and larger ($N=5,000$) cohorts are also provided.
These results indicate that our methods are much more useful than the original DP methods based on global sensitivity especially for larger cohorts.

"RunTime" folder contains the results on the execution time to compute the ${\it smooth\ sensitivity}$ of each statistic when $N = 1,000$, $2,000$, and $5,000$. These results indicate that our method can be performed within practical time even for a large cohort. 

The procedure to generate simulation data for the above experiments can be found in "SimulationData" folder.

"StatsFeature" folder contains the codes for analyses on the characteristics of each statistics. The detailed explanation and discussion are provided in Section 4 of the main document.

## Important future directions

・Covering all statistical analysis in GWAS, e.g., Cochran-Armitage trend test and EIGENSTRAT.

・Improving the selection of random variables in Algorithm 1.

・Investigating other important characteristics and possibilities of ${\it smooth\ sensitivity}$.

・Developing highly accurate methods for publishing top $K$ data based on ${\it smooth\ sensitivity}$. 

## Note

For details of our methods, please see our paper entitled "Privacy-Preserving Publication of GWAS statistics using Smooth Sensitivity" (to appear at PST 2023).

### Contact
Akito Yamamoto

Division of Medical Data Informatics, Human Genome Center,

the Institute of Medical Science, the University of Tokyo

a-ymmt@ims.u-tokyo.ac.jp
