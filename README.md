# RsqMed (updated Sep 22, 2019)
R package designed for calculating the Rsq measure for high-dimensional mediation analysis. 
* works under on linux R, R version > 3.5.0

Required R package:
* GMMAT: GMMAT can be found at https://github.com/hanchenphd/GMMAT. The current used version is 1.1. Details of the installation steps are provided in https://cran.r-project.org/web/packages/GMMAT/vignettes/GMMAT.pdf.
* SIS: more in https://cran.r-project.org/web/packages/SIS/SIS.pdf


# How to install RsqMed
* Step 1: download the 'RsqMed_0.1.1.tar.gz' file into the local folder.
* Step 2: open R, and set the directory to this local folder 
 ```r
 setwd('local folder')
 ```
 
* Step 3: install the two required R packages, GMMAT and SIS. 
 ```r
 #install SIS
install.packages('SIS')

#install GMMAT
install.packages('devtools')
install_github('hanchenphd/GMMAT')
 ```
* Step 4: install the package in R
```r
install.packages('RsqMed_0.1.1.tar.gz',repos=NULL,type='source')
```

# Example  
## Impute data
The data "example" is a simulated sample with 100 observations, which can be accessed by the following code.
```{r, echo=FALSE}
require(RsqMed)
str(example)
```
The example is saved with the package. X can be regarded as independent variable, Y is the outcome variable, Cov is the covariate matrix, M is the putative mediator matrix.
$$Y_i = 2X + M\beta + Cov\beta_{cov} + r_2$$
$r_1$ and $r_2$ are the residuals, $\alpha_i$ is the element of alpha, $\beta$ is the beta vector, $\beta_{cov}$ is the Cov.beta.

### Calculating point estimates 
```{r, warning=FALSE, eval=F}
Rsq.measure(p=1/2, outcome=example$Y,med=example$M,covar=example$Cov,indp=example$X, method='iSIS',iter.max=1, screening=F,init.cutoff=0.1)$output
```
Use ?Rsq.measure to read more about the input and output of the Rsq.measure function. We added a prescreening step in this function, which is not presented in the paper. It may decrease computation burden in some cases and we suggest using a generous cut-off point.

### Calculate the confidence intervals using bootstrap
```{r, message=FALSE, warning=FALSE, eval=F}
CI.Rsq.measure(p=1/2, outcome=example$Y[1:50],med=example$M[1:50,1:10],covar=example$Cov[1:50,],indp=example$X[1:50], method='ALL', B=2)$CI
```
Use ?CI.Rsq.measure to read more about the input and output of the CI.Rsq.measure function.

# Reference
Yang T, Chen H *, Niu J * , Wei P, Estimation of total mediation effect for high-dimensional omics mediators. bioRxiv 774877; doi: https://doi.org/10.1101/774877

Chen H, Wang C, Conomos MP, Stilp AM, Li Z, Sofer T, Szpiro AA, Chen W, Brehm JM, Celedón JC, Redline S. Control for population structure and relatedness for binary traits in genetic association studies via logistic mixed models. The American Journal of Human Genetics. 2016 Apr 7;98(4):653-66.
