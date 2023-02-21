# Problem_Set_7

Problem set 5 is inspired by __The shape of gene expression distributions matter: how incorporating distribution shape improves the interpretation of cancer transcriptomic data__ written by de Torrenté et al in 202

I will include the abstract from the paper below. _Please read this summary_ 

__Background__
In genomics, we often assume that continuous data, such as gene expression, follow a specific kind of distribution. However we rarely stop to question the validity of this assumption, or consider how broadly applicable it may be to all genes that are in the transcriptome. Our study investigated the prevalence of a range of gene expression distributions in three different tumor types from the Cancer Genome Atlas (TCGA).

__Results__
Surprisingly, the expression of less than 50% of all genes was Normally-distributed, with other distributions including Gamma, Bimodal, Cauchy, and Lognormal also represented. Most of the distribution categories contained genes that were significantly enriched for unique biological processes. Different assumptions based on the shape of the expression profile were used to identify genes that could discriminate between patients with good versus poor survival. The prognostic marker genes that were identified when the shape of the distribution was accounted for reflected functional insights into cancer biology that were not observed when standard assumptions were applied. We showed that when multiple types of distributions were permitted, i.e. the shape of the expression profile was used, the statistical classifiers had greater predictive accuracy for determining the prognosis of a patient versus those that assumed only one type of gene expression distribution.

___Conclusions__
Our results highlight the value of studying a gene’s distribution shape to model heterogeneity of transcriptomic data and the impact on using analyses that permit more than one type of gene expression distribution. These insights would have been overlooked when using standard approaches that assume all genes follow the same type of distribution in a patient cohort.

This week we are going to examine a similar gene expression dataset and test for three different distributions. 



## Part 1 - Data formatting & Packages

1. Install and load the package fitdistrplus https://cran.r-project.org/web/packages/fitdistrplus/index.html 
2. Read in the datafile GSE37642-GPL97_series_matrix.EDITED.txt __THIS FILE IS IN CANVAS!__ because it is large but it's REAL!
3. Set the rownames to the column called ID_REF
4. Remove the column called ID_REF

Now you should have a dataframe where each column is a different individual and each row is a different gene


![Screenshot 2023-02-21 162627](https://user-images.githubusercontent.com/47755288/220462238-8101279e-fb39-4e15-83db-9856dd6a3134.png)

## Part 2 - Testing Gene 200000_s_at in Row 1

1. Save the data for the gene in row 1 (aka 200000_s_at) into a new variable
2. Use the function ```unlist()``` on your data for row 1. To use the the fitdist package this must be a numeric vector. If you were to try and use just the row data you would get an error like:

```
Error in fitdist(gene, "norm") : 
  data must be a numeric vector of length greater than 1
  ```
3. Use the ```fitdist``` function to test and save the fit for the normal "nrom" distribution
4. Use the ```fitdist``` function to test and save the fit for the lognormal "lnrom" distribution
5. Use the ```fitdist``` function to test and save the fit for the gamma "gamma" distribution
6. Display the fit of these three models using the ```denscomp``` function
7. Compare the AIC of the three models using the ```gofstat``` function
8. Which model has the best fit? 


### Part 3 - Testing the first 500 genes for best fit distribution 
