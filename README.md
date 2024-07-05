# Privacy-Preserving Publication of GWAS statistics using Smooth Sensitivity

This contains Python codes used in our experiments on differentially private (DP) GWAS statistics based on their ${\it smooth\ sensitivities}$.

This study focuses on key statistics in GWAS: $\chi^2$-statistics based on a contingency table and TDT statistics for family-based association studies.

"Accuracy" folder contains the experimental results on differences between the original and DP statistics.
In addition to the results provided in our paper, those for smaller ($N=1,000$) and larger ($N=5,000$) cohorts are also provided.
These results indicate that our methods are much more useful than the original DP methods based on ${\it global\ sensitivity}$ especially for larger cohorts.  
(Please also see Important Notes and Errata for the details of the experiments.)

"RunTime" folder contains the results on the execution time to compute the ${\it smooth\ sensitivity}$ of each statistic when $N = 1,000$, $2,000$, and $5,000$. These results indicate that our method can be performed within practical time even for a large cohort. 

The procedure to generate simulation data for the above experiments can be found in "SimulationData" folder.

"StatsFeature" folder contains the codes for analyses on the characteristics of each statistics. The detailed explanation and discussion are provided in Section IV of the main document.

In our experiments on $\chi^2$-statistics based on a $2 \times 2$ contingency table, we consider ${\it neighboring}$ datasets as two datasets that differ only by one or two alleles in the table. This is because when one individual in the dataset varies, at most two alleles' information varies. 

## Important Notes

・In this study, the discussion for the $\chi^2$-statistics based on a contingency table is for the case where the number of cases and controls are almost equal. Therefore, for the sake of simplicity, we defined the statistics as the values when the number of cases and controls are equal. We think this approximation is reasonable in this study because **we put emphasis on the proposal of new algorithm and theorems on smooth sensitivity and a validation of their effectiveness on GWAS statistics**. Actually, the existing methods compared in our experiments are for the case where the number of cases and controls are equal, and the expected values of them in the simulation data used in Section V are also equal (i.e., the $\chi^2$-statistics can be approximate to the values shown in Section III.B.1; the values can be regarded as psuedo statistics for evaluation (including the analyses in Section IV.A)). Under the above experimental settings, the value of ${\it global\ sensitivity}$ for the existing method can be (approximately) fixed, and similarly, the value of ${\it smooth\ sensitivity}$ for our method can be (approximately) calculated; consequently, a fair comparison can be made. 

・The experimental results (regarding the analysis on ${\it global\ sensitivity}$) indicate that, even when the ratio between the number of cases and controls is ${\it approximately}$ fixed, the global sensitivity is almost the same as the value when the ratio is ${\it strictly}$ fixed. Therefore, for more flexible analysis settings and more strict privacy guarantees, we should also consider ${\it neighboring}$ datasets that allow for changes in elements between case and control groups (i.e., that have no ${\it strict}$ restrictions on the ratio) in computing differentially private $\chi^2$-statistics for genomic statistical analysis.

**・In practice, after determining the range of the number of cases and controls for the analyses, it would be recommended to construct a specific algorithm for computing ${\it smooth\ sensitivity}$ in a similar manner to that described in Section IV based on the exact statistics.**

・As for the cases when the number of cases and controls are far apart, the ${\it sensitivities}$ of $\chi^2$-statistics are expected to be much larger \[[Yu et al., 2014](https://www.sciencedirect.com/science/article/pii/S1532046414000100)\]; therefore, further reseach and analyses on it and develop efficient algorithms for calculating ${\it smooth\ sensitivities}$ (and to reduce noise) for this case might be desired.

・Although the analyses and discussions in Section IV are just simple examples of the procedures for constructing algorithms to calculate ${\it smooth\ sensitivities}$, we will use this study as a starting point for further research on privacy-preserving methods that can be used in more precise and general cases, including rigorous analysis of ${\it global\ sensitivity}$ and ${\it local\ sensitivity}$.

(・Note that the evaluations for the TDT statistics are rigours.)

## Future Directions

・Completely eliminating restrictions on the number of cases and controls for the $\chi^2$-statistics based on a contingnecy table.

・Covering all statistical analysis in GWAS, e.g., Cochran-Armitage trend test and EIGENSTRAT.

・Improving the selection of random variables in Algorithm 1. / Would the idea of comparing multiple random variables also work for cases other than when using the standard Cauchy distribution?

・Investigating and analyzing other important characteristics and possibilities of ${\it smooth\ sensitivity}$, including other noise distributions than the standard Cauchy distribution.  
${\ \ \ }$ ← I expect that it is not so difficult to obtain a more rigorous $(\alpha, \beta)$ - ${admissible}$ property (than was previously reported in [Smooth Sensitivity and Sampling in Private Data Analysis](https://cs-people.bu.edu/ads22/pubs/NRS07/NRS07-full-draft-v1.pdf)) of the general distribution with density $h(z) \propto \frac{1}{1+|z|^\gamma}$ by following our Theorem 1 and its proof. $\biggl($ I assume that the values of $(\alpha, \beta)$ are $\left(\frac{\epsilon}{2 \cdot (\gamma-1)^{\frac{\gamma-1}{\gamma}}}, \frac{\epsilon}{2 (\gamma - 1)}\right)$. $\biggr)$ However, this was not addressed in this study, because we focused on comparing ${\it global\ sensitivity}$ and ${\it smooth\ sensitivity}$, rather than comparing among ${\it smooth \ sensitivity}$-based methods. (Detailed results on this point will be presented in a separate paper.) Moreover, for a quantitative evaluation and comparison among noise distributions, I believe that it is more important to have a closer discussion on inequalities in the proof and accordingly extend and elaborate the concepts of ${admissible}$ and ${smooth\ sensitivity}$ (and differential privacy).

・Developing highly accurate methods for publishing top $K$ data based on ${\it smooth\ sensitivity}$. 

・Constructing a more general and efficient algorithm to compute ${\it smooth\ sensitivity}$.

・Considering the application of ${\it elastic\ sensitivity}$ [[Johnson, Near, and Song, 2018](https://dl.acm.org/doi/10.1145/3177732.3177733)] or ${\it residual\ sensitivity}$ [[Dong and Yi, 2021](https://doi.org/10.1145/3448016.3452813)].

## Note

For details of our methods, please see our paper entitled "Privacy-Preserving Publication of GWAS statistics using Smooth Sensitivity" (https://doi.org/10.1109/PST58708.2023.10320160) presented at PST 2023.

Errata:  
・The last sentence in Section III.B.1. should be ${\it deleted}$ or rewritten as "The global sensitivities analyzed in existing studies were for cases where the number of cases and controls are fixed, and this study is the first to consider cases without such limitations. In particular, we analyzed them approximately where the number of cases and controls are almost equal and not fixed." (Note that Theorems 5 and 6 can be used for any cases without restrictions on the number of cases and controls.)

・Section III.B.1. "The $\chi^2$-statistics based on Talbes I and II are" → "When $p+r+t \approx q+s+u$ and $a+c \approx b+d$, the $\chi^2$-statistics based on Tables I and II are"  
・Section III.B.1. $\ \chi^2_{3 \times 2}(p,q,r,s,t,u) =$ → $\ \chi^2_{3 \times 2}(p,q,r,s,t,u) \approx$  
・Section III.B.1. $\ \chi^2_{2 \times 2}(a,b,c,d) =$ → $\ \chi^2_{2 \times 2}(a,b,c,d) \approx$  

### Contact
Akito Yamamoto

Division of Medical Data Informatics, Human Genome Center,

the Institute of Medical Science, the University of Tokyo

a-ymmt@ims.u-tokyo.ac.jp
