#Roadmap #PAI 

### 1. Probability Recap

#### 1.1 Probability Space
![[Probability Space#^815b6d]]

---
#### 1.2 Random Variables
![[Random Variable#^4b9e44]]
![[Random Variable#^a13060|q]]

![[Density#^fe3835]]

---
#### 1.3 Distributions
![[Distribution#^fcd59b]]

---
#### 1.4 Conditional Probability
![[Conditional Probability#^22a6cd]]

---
#### 1.5 Independence
![[Independence#^48b93f]]

---
#### 1.6 Gaussian Distribution
![[Gaussian Distribution#^a29bbb]]
![[Gaussian Distribution#^38c683|q]]

---

![[Gaussian Distribution#^6f6281]]
![[Gaussian Distribution#^6af1ff|p]]

---
![[Gaussian Distribution#^e649b0]]

---
![[Gaussian Distribution#^061ea5]]
![[Gaussian Distribution#^89a1c5|p]]

---
### 2. Linear Regression

![[Linear Regression#^e4d197]]

---
#### 2.1 MLE and MAP

![[Maximum Likelihood Estimation#^fe8cee]]
![[Maximum Likelihood Estimation#^6a1148|q]]
![[Maximum A Posteriori Estimation#^010b53]]
![[Maximum A Posteriori Estimation#^935410|q]]

---
![[Linear Regression#^985e1b]]
![[Linear Regression#^42a860|p]]
---
![[Linear Regression#^ff972b]]
![[Linear Regression#^c76ffe|p]]
---
#### 2.2 Bayesian Decision Theory

![[Linear Regression#^647c71]]
![[Linear Regression#^8a650d|p]]
![[Linear Regression#^c649df|q]]
---
![[Aleatoric and Epistemic Uncertainty#^265ad5]]

---
![[Bayesian Decision#^64da66]]

---
![[Bayesian Decision#^2d18fd]]
![[Bayesian Decision#^23b6bb|p]]

---
##### 2.2.1 Bayesian Networks and Graphical Models
![[Bayesian Network#^78dc2b]]
![[Bayesian Network#^62a6d8|q]]
![[Bayesian Network#^c0cc53|q]]

---
![[Bayesian Network#^acd87b]]

---
##### 2.2.2 Recursive Bayesian Updates
![[Linear Regression#^cc841a|p]]

---
##### 2.2.3 Kernelized BLR
By using a linearization function $\phi:\mathbb{R}^d\to \mathbb{R}^p$ we can turn non-linear regression into linear regression. 
1. **Example**: $f(x):=ax^{2}+bx+c$ can be represented as $f(x)=[a,b,c]^\top \phi(x)$ where $\phi(x):=(x^2,x,1)$.

However, this has the drawback that the dimension explodes, i.e. $\left| \phi(x) \right|={d+m \choose d}$ by stars and bins. 

In Bayesian Linear Regression with $w \sim \mathcal{N}(0,I)$ and $y_{i}=w^\top\phi(x_{i})+\varepsilon_{i}$, we have that: $$y=\Phi^\top w+\varepsilon \sim \mathcal{N}(0,\Phi \Phi^\top+\sigma^{2}I)$$by setting $\Phi:=[\phi(x_{1})|\dots|\phi(x_{n})]^\top\in \mathbb{R}^{n,p}$ and the distribution only depends on $\{ \braket{ \phi(x_{i}) ,\phi( x_{j} )} \}_{i,j\in [n]}$. 

---
### 2.3 Gaussian Processes
![[Gaussian Process#^fc4049]]
![[Gaussian Process#^cc13be|q]]


