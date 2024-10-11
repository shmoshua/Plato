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
![[Gaussian Distribution#^bf26eb|p]]

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

---
#### 2.3.1 Kernels and Covariance Function
![[Kernel#^258b99]]
![[Kernel#^cc13be|q]]

---

![[Gaussian Process#^acc53b]]
![[Gaussian Process#^d1890f|p]]

---
![[Kernel#^e4d3ef]]
![[Kernel#^55975d|p]]

---
##### Examples of Kernels
![[Kernel#^12715f]]
![[Kernel#^bf3cb3|p]]

---
![[Kernel#^01b33c]]
![[Kernel#^6bfe78|p]]
- **Remark**: The lower the lengthscale is, the less correlated the points are.
---
![[Kernel#^0f0590]]

---
![[Kernel#^a6cc5d]]

---
![[Kernel#^e66b39]]

---
#### 2.3.2 Making Predictions with Gaussian Processes

![[Gaussian Process#^6676d7]]
![[Gaussian Process#^9b4fed|p]]

- **Remark**: Then, we can use $p(f|y_{1:n},x_{1:n})$ as the posterior distribution! We can use this for spatial prediction or protein engineering.

---
![[Gaussian Process#^ec2539]]
![[Gaussian Process#^f3ea71|p]]
![[Gaussian Process#^5ba3f5|q]]

---

> [!outlook] Outlook (Gaussian Processes on Graphs)
> For arbitrary base space $X$ e.g. $X$ is a [[graph]] $G$, we have the following solutions.
> 1. **Option 1**: Embed $X\hookrightarrow \mathbb{R}^n$ for some $n$.
> 	$\to$ might lose other structural properties of the graph for example.
> 2. **Option 2**: Define $k(x,x'):=k'(d_{G}(x,x'))$ for some $k':\mathbb{Z}_{\geq 0}\to \mathbb{R}$. 
>    $\to$ might not result in a positive semidefinite kernel.
> 3. **Option 3**: Laplacian-based generalizations of Gaussian/Matérn kernels.
>    $\to$ always SPsD and respects the intrinsic geometry of $X$. 

- **Remark**: For other $X$ like a [[topological manifold]], we have geometric kernels.
---
#### 2.3.3 Sampling From a Gaussian Process

> [!outlook] Method 1
> Choose $A:=\{x_{1},\dots,x_{n}\} \subseteq X$ and we would like to sample $f$ at these points. Then, as $f \sim \text{GP}(0,k)$, $$(f(x_{1}),\dots,f(x_{n})) \sim \mathcal{N}(0, K_{AA})$$where $K_{AA}$ is symmetric positive semidefinite. Let $K_{A A}=LL^\top$ be the [[Cholesky decomposition]]. Then, 
> 1. Sample $\varepsilon \sim \mathcal{N}(0,I_{n})$. We then have that: $$(f(x_{1}),\dots,f(x_{n})):=L\varepsilon \sim \mathcal{N}(0, LL^\top)=\mathcal{N}(0, K_{A A})$$
---
> [!outlook] Method 2 (Forward Sampling)
> Let $\{ x_{i} \}_{i}\subseteq X$ be a sequence of points. Then, we utilize that: $$p(f(x_{1}),\dots,f(x_{n}))=p(f(x_{1}))\prod_{i=1}^{n-1}p(f(x_{i+1})|f(x_{1}),\dots,f(x_{i}))$$Therefore, we can sample $f(x_{i})$ in increasing order, where we use the previous samples in the conditional sampling. 
---
#### 2.3.4 Choosing Kernel Hyperparameters
