# RedMed
R package designed for calculating the Rsq measure for high-dimensional mediation analysis. 
* works under on linux R, R version > 3.4.0

Needed package:
GMMAT: GMMAT can be found at https://github.com/hanchenphd/GMMAT. The current used version is 0.7
SIS: more in https://cran.r-project.org/web/packages/SIS/SIS.pdf


# How to install aGE
* Step 1: download the 'RsqMed_0.0.0.9000.tar.gz' file into the local folder.
* Step 2: open R, and set the directory to this local folder 
 ```r
 setwd('local folder')
 ```
 
* Step 3: install the two required R packages
 ```r
install.packages('SIS')
install.packages('devtools')
install_github('hanchenphd/GMMAT')
 ```
* Step 3: install the package in R
```r
install.packages('RsqMed_0.0.0.9000.tar.gz',repos=NULL,type='source')
```

# Reference
Yang T, Chen H, Niu J, Wei P, Estimation of total mediation effect for high-dimensional omics mediators, to be submitted.
