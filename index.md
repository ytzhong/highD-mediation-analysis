## R package: RsqMed 

This page introduce the RsqMed package

### Function to estimate Rsq
Rsq.measure

### Sample code 
```markdown

```r
#simulate the data
library(MASS)
require('RsqMed')
X<-rnorm(100)
alpha<-rnorm(100)
M<-matrix(NA,nrow=100,ncol=100)
for (i in 1:100){
M[,i]<-alpha[i]*X+rnorm(100)
}
beta<-rnorm(100)
Cov <-mvrnorm(n=100,mu=c(0,0), Sigma=diag(c(1,1)))
Cov.beta <-c(1,-1)
Y<- as.vector(2*X + M %*% beta + Cov %*%Cov.beta + rnorm(100))

require(RsqMed)
#call the function
Rsq.measure(p=1/2, outcome=Y,med=M,covar=Cov,indp=X, method='ISIS',seed=1234)
Rsq.measure(p=1/2, outcome=Y,med=M,covar=Cov,indp=X, method='SIS',seed=1234)
```

