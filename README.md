# RsqMed
R package designed for calculating the Rsq measure for high-dimensional mediation analysis. 
* works under on linux R, R version > 3.4.0

Required R package:
* GMMAT: GMMAT can be found at https://github.com/hanchenphd/GMMAT. The current used version is 0.7. It is also included in this folder. 
* SIS: more in https://cran.r-project.org/web/packages/SIS/SIS.pdf


# How to install RsqMed
* Step 1: download the 'RsqMed_0.0.0.9000.tar.gz' file into the local folder.
* Step 2: open R, and set the directory to this local folder 
 ```r
 setwd('local folder')
 ```
 
* Step 3: install the two required R packages
 ```r
 #install SIS
install.packages('SIS')

#install GMMAT
install.packages('devtools')
install_github('hanchenphd/GMMAT')
#or install by local resources (recommended)
install.packages('GMMAT_0.7-1.tar.gz',repos=NULL,type='source')
 ```
* Step 4: install the package in R
```r
install.packages('RsqMed_0.0.0.9000.tar.gz',repos=NULL,type='source')
```

# Reference
Yang T, Chen H *, Niu J* , Wei P, Estimation of total mediation effect for high-dimensional omics mediators, to be submitted. (Chen and Niu contributed equally)

Chen H, Wang C, Conomos MP, Stilp AM, Li Z, Sofer T, Szpiro AA, Chen W, Brehm JM, Celedón JC, Redline S. Control for population structure and relatedness for binary traits in genetic association studies via logistic mixed models. The American Journal of Human Genetics. 2016 Apr 7;98(4):653-66.
