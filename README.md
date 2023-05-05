# Differentially Private GWAS statistics using Smooth Sensitivity

This contains Python codes used in our experiments on differentially private (DP) GWAS statistics using their ${\it smooth\ sensitivities}$.

This study focuses on key statistics in GWAS: $\chi^2$-statistics based on a contingency table and TDT statistics for family-based association studies.

The procedure to generate simulation data can be found in "Simulation Data" file.

"Accuracy" file contains the experimental results on differences between the original and DP statistics.
In addition to the results provided in our paper, those for smaller ($N=1,000$) and larger ($N=5,000$) cohorts are also provided.
These results indicate that our methods are much more useful than the original DP methods based on global sensitivity especially for larger cohorts.

"Run Time" file contains the results on the execution time to compute the ${\it smooth\ sensitivity}$ of each statistic when $N = 1,000$, $2,000$, and $5,000$. These results indicate that our method can be performed within practical time even for a large cohort. 

"Proof.pdf" provides the proofs of our Theorems 5 and 6 for calculating the Hamming distance.

## Note

For details of our methods, please see our paper entitled "Privacy-Preserving Publication of GWAS statistics using Smooth Sensitivity".

### Contact
Akito Yamamoto

Division of Medical Data Informatics, Human Genome Center,

the Institute of Medical Science, the University of Tokyo

a-ymmt@ims.u-tokyo.ac.jp
