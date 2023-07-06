# Privacy-Preserving Publication of GWAS statistics using Smooth Sensitivity

This contains Python codes used in our experiments on differentially private (DP) GWAS statistics based on their ${\it smooth\ sensitivities}$.

This study focuses on key statistics in GWAS: $\chi^2$-statistics based on a contingency table and TDT statistics for family-based association studies.

"Accuracy" folder contains the experimental results on differences between the original and DP statistics.
In addition to the results provided in our paper, those for smaller ($N=1,000$) and larger ($N=5,000$) cohorts are also provided.
These results indicate that our methods are much more useful than the original DP methods based on global sensitivity especially for larger cohorts.

"RunTime" folder contains the results on the execution time to compute the ${\it smooth\ sensitivity}$ of each statistic when $N = 1,000$, $2,000$, and $5,000$. These results indicate that our method can be performed within practical time even for a large cohort. 

The procedure to generate simulation data for the above experiments can be found in "SimulationData" folder.

"StatsFeature" folder contains the codes for analyses on the characteristics of each statistics. The detailed explanation and discussion are provided in Section 4 of the main document.

## Important Note

・In this study, for the sake of simplicity in the experiments, we determine the $\chi^2$-statistics based on a contingency table as the values when the number of cases and controls are equal. That is, the equations provided in Section III.B.1 are different from the exact ones. However, we think this approximation is reasonable in this study because **we put emphasis on a validation of the effectiveness of ${\it smooth\ sensitivity}$ on GWAS statistics**; actually, the existing methods compared in our experiments are for the case where the number of cases and controls are equal, and the expected values of them in the simulation data used in Section V are also equal (i.e., the $\chi^2$-statistics can be approximate to the values shown in Section III.B.1; the values can be regarded as psuedo statistics for evaluation (including the analyses in Section IV.A)). Although the analyses and discussions in Section IV are just examples of the procedures for constructing algorithms to calculate ${\it smooth\ sensitivities}$, we will use this study as a starting point for further research on privacy-preserving methods that can be used in more precise and general cases, including rigorous analysis of ${\it global\ sensitivity}$ and ${\it local\ sensitivity}$.

・As for the case when the number of cases and controls are far apart, the ${\it sensitivities}$ of $\chi^2$-statistics are expected to be much larger \[[Yu et al., 2014](https://www.sciencedirect.com/science/article/pii/S1532046414000100)\]; therefore, we should conduct further reseach and analyses on it and develop efficient algorithms to calculate ${\it smooth\ sensitivities}$ (and to reduce noise) for this case.

## Future Directions

・Covering all statistical analysis in GWAS, e.g., Cochran-Armitage trend test and EIGENSTRAT.

・Improving the selection of random variables in Algorithm 1.

・Investigating other important characteristics and possibilities of ${\it smooth\ sensitivity}$.

・Developing highly accurate methods for publishing top $K$ data based on ${\it smooth\ sensitivity}$. 

・Completely eliminating restrictions on the number of cases and controls.

## Note

For details of our methods, please see our paper entitled "Privacy-Preserving Publication of GWAS statistics using Smooth Sensitivity" (to appear at PST 2023).

Errata:  
・Section III.B.1. "The $\chi^2$-statistics based on Talbes I and II are" → "When $p+r+t \approx q+s+u$ and $a+c \approx b+d$, the $\chi^2$-statistics based on Talbes I and II are"  
・Section III.B.1. $\ \chi^2_{3 \times 2}(p,q,r,s,t,u) =$ → $\ \chi^2_{3 \times 2}(p,q,r,s,t,u) \approx$  
・Section III.B.1. $\ \chi^2_{2 \times 2}(a,b,c,d) =$ → $\ \chi^2_{2 \times 2}(a,b,c,d) \approx$  
・The last sentence in Section III.B.1. should be ${\it deleted}$.

### Contact
Akito Yamamoto

Division of Medical Data Informatics, Human Genome Center,

the Institute of Medical Science, the University of Tokyo

a-ymmt@ims.u-tokyo.ac.jp
