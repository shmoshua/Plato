#Roadmap #PAI 

### 1. Probability Recap

#### 1.1 Probability Space
![[Probability Space#^815b6d]]

---
#### 1.2 Random Variables
![[Random Variable#^4b9e44]]
![[Random Variable#^a13060|]]

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
![[Gaussian Distribution#^38c683]]

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
![[Maximum Likelihood Estimation#^6a1148]]

---
![[Maximum A Posteriori Estimation#^010b53]]
![[Maximum A Posteriori Estimation#^935410]]

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
![[Linear Regression#^c649df]]

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
![[Bayesian Network#^62a6d8]]
![[Bayesian Network#^c0cc53|p]]

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
![[Kernel#^cc13be]]

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
![[Gaussian Process#^5ba3f5]]

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
Notice that given the kernel, there are different hyperparameters:
1. $k(x,x')=\sigma^{2}_{f}\exp \left( -\frac{1}{2h^{2}}(x-x')^{2} \right) +\sigma_{n}^{2} \delta_{xx'}$ has that $\theta:=(h,\sigma_{f},\sigma_{n})$.
2. $k(x,x')=\sigma^{2}_{f}\exp \left( -\frac{1}{2}(x-x')^\top M(x-x') \right) +\sigma_{n}^{2} \delta_{xx'}$ has that $\theta:=(M,\sigma_{f},\sigma_{n})$.
---
##### 2.3.4.1 Bayesian Model Selection
There are multiple level of random variables to infer. The hierarchy is given by: 
$$\underset{ \text{parameters} }{ w }\gets \underset{ \text{hyperparameters} }{ \theta }\gets \underset{ \text{model selection} }{ \mathcal{H}_{i} }$$where $\mathcal{H}_{i}$ is a discrete set of models, i.e. choosing between a linear kernel and RBF. 

> [!outlook] Method (Bayesian Model Selection)
> At each level, we can maximize the marginal likelihood of the levels below.
> 1. $\widehat{\theta}:=\underset{ \theta }{ \arg\max }\ p(y_{\text{train}}|x_{\text{train}},\theta)$ where:$$p(y_{\text{train}}|x_{\text{train}},\theta)=\int p(y_{\text{train}}|f,x_{\text{train}},\theta) p(f|\theta)\, d\mathbb{P}_{f}$$

- **Remark**: Let $\mathcal{H}_{\text{simple}},\mathcal{H}_{\text{moderate}},\mathcal{H}_{\text{complex}}$ be the three model candidates (including hyperparameter selections). Then, in the marginal likelihood $\int_{}^{} p(y|f,x,\mathcal{H}_{i}) p(f|\mathcal{H}_{i})\, df$, 
	1. $\mathcal{H}_{\text{simple}}$ has small $p(y|f,x,\mathcal{H}_{\text{simple}})$ for most $f$ and small $p(f|\mathcal{H}_{\text{simple}})$ for most $f$. 
	2. $\mathcal{H}_{\text{complex}}$ has large $p(y|f,x,\mathcal{H}_{\text{complex}})$ for some $f$ and small for most, and small $p(f|\mathcal{H}_{\text{simple}})$ for most $f$. 

	Therefore, we can maximize the marginal likelihood where the most moderate model will be selected.


---
> [!h] Example of Simple and Complex Models
> Consider a 1-dimensional example $y=f+\varepsilon$ where $\varepsilon \sim \mathcal{N}(0,\sigma_{n}^{2})$ and we have Gaussian prior $f \sim \mathcal{N}(0,\sigma_{p}^{2})$. With fixed $\sigma_{n}^{2}$, we have that:
> 1. if $\sigma_{p}^{2}$ is too small, then our model will be simple. (only some data will have high likelihood.)
> 2. if $\sigma_{p}^{2}$ is too larger, then our model will be complex. 

---

> [!lemma] Proposition (Bayesian Model Selection for GP)
> Let $\Theta$ be a set of hyperparameters and $k_{\theta}$ be a covariance function for each $\theta\in \Theta$. Then, with prior $f \sim \text{GP}(0,k_{\theta})$ with $y=f(x)+\varepsilon$ with $\varepsilon \sim \mathcal{N}(0,\sigma^2_{n})$ w.r.t. observed datapoints $y_{1:n}$ at $x_{1:n}\subseteq X$, we have that the ***Bayesian model selection*** $\widehat{\theta}=\underset{ \theta\in \Theta }{ \arg\max } \ p(y_{1:n}|x_{1:n},\theta)$ is given as:
> $$\text{tr}\left( (K_{y,\widehat{\theta}}^{-1}-\alpha \alpha^\top)\frac{ \partial K_{y,\widehat{\theta}} }{ \partial \widehat{\theta}_{j} }  \right)=0$$where $K_{y,\theta}:=K_{AA}^{\theta}+\sigma_{n}^{2}I$ and $\alpha:=K_{y,\widehat{\theta}}^{-1}y_{1:n}$.

> [!proof]-
> We have that for $A:=\{ x_{1},\dots,x_{n} \}$, $y_{1:n}|x_{1:n},\theta \sim \mathcal{N}(0,K_{y,\theta})$ where $K_{y,\theta}:=K_{AA}^{\theta}+\sigma_{n}^{2}I$.  Therefore,   $$\begin{align}\widehat{\theta}&=\underset{ \theta\in \Theta }{ \arg\max } \ p(y_{1:n}|x_{1:n},\theta)\\&=\underset{ \theta\in \Theta }{ \arg\max } \ \frac{1}{\sqrt{ (2\pi)^n \left| K_{y}^\theta \right| }}\exp \left( -\frac{1}{2}y_{1:n}^\top K_{y,\theta}^{-1}y_{1:n}\right) \\&=\underset{ \theta\in \Theta }{ \arg\min } \underbrace{ \left(\log \left| K_{y,\theta} \right| +y_{1:n}^\top K_{y,\theta}^{-1}y_{1:n}\right) }_{ =:\mathcal{L}(\theta) }\end{align}$$where $$\begin{align}\frac{\partial}{\partial\theta_{j}}\mathcal{L}&=\text{tr}\left( K_{y,\theta}^{-1}\frac{ \partial K_{y,\theta} }{ \partial \theta_{j} }  \right)+y^\top_{1:n}\frac{ \partial  }{ \partial \theta_{j} }K_{y,\theta}^{-1}y_{1:n} \\&=\text{tr}\left( K_{y,\theta}^{-1}\frac{ \partial K_{y,\theta} }{ \partial \theta_{j} }  \right)-y^\top_{1:n}K_{y,\theta}^{-1}\frac{ \partial K_{y,\theta} }{ \partial \theta_{j} }\underbrace{ K_{y,\theta}^{-1}y_{1:n} }_{=:\alpha  }\\&=\text{tr}\left( K_{y,\theta}^{-1}\frac{ \partial K_{y,\theta} }{ \partial \theta_{j} }  \right)-\text{tr}\left( \alpha \alpha^\top\frac{ \partial K_{y,\theta} }{ \partial \theta_{j} } \right)\\&=\text{tr}\left( (K_{y,\theta}^{-1}-\alpha \alpha^\top)\frac{ \partial K_{y,\theta} }{ \partial \theta_{j} }  \right)\end{align} $$

- **Remark**: Bayesian model selection has the drawback that it might overfit on the parameters. A solution is to set ***hyperpriors*** -- priors on hyperparameters. Essentially, at each level we can perform Bayesian inference. For example, at level 2: $$p(\theta|y_{1:n}, x_{1:n},\mathcal{H}_{i})=\frac{p(y_{1:n}|x_{1:n},\theta,\mathcal{H}_{i})p(\theta|\mathcal{H}_{i})}{p(y_{1:n}|x_{1:n},\mathcal{H}_{i})}$$Then, we can compute $\widehat{\theta}_{\text{MAP}}$.

---
##### 2.3.4.2 Cross Validation
![[Cross Validation#^dcaf90]]

---

> [!outlook] Method (Cross Validation for Hyperparameters)
> Let $\Theta:=\{ \theta_{i} \}_{i}$ be the set of candidate hyperparameters. Then, we do a two step optimization: 
> 1. $\widehat{f}_{i}:=\underset{ f }{ \arg\max } \ p(y_{\text{train}}|x_{\text{train}},f,\theta_{i})p(f|\theta_{i})$ in other words [[Maximum A Posteriori Estimation|MAP estimate]] of $f$ given $\theta_{i}$. 
> 2. $\widehat{\theta}:=\underset{ \theta_{i}\in \Theta }{ \arg\max }\ p(y_{\text{test}}|x_{\text{test}}, \widehat{f}_{i},\theta_{i})$ in other words the [[Maximum Likelihood Estimation|MLE estimate]] of $\theta$.
---
#### 2.3.5 Fast Gaussian Processes
- **Remark**: To compute $p(f|x_{1:n},y_{1:n})$, from [[Gaussian Process|Conditional Gaussian Process]], we need to compute $(K_{AA}+\sigma^{2}I)^{-1}$. This requires $\Theta(n^{3})$. 
	- Compare this to BLR, where we need to compute $(kI+X^\top X)^{-1}$ where $X\in \mathbb{R}^{n,d}$, hence in $\Theta(nd^{2})$.
- **Remark**: Using GPU we can also compute GP inference in parallel. However, this does not reduce the runtime of each inference!
---
##### 2.3.5.1 Local Methods
> [!outlook] Method 1
> As many covariance functions have the property that $k(x,x')\to 0$ as $x-x'\to \infty$. Therefore, 
> 1. create a cutoff $\tau>0$ s.t. at a prediction point $x$, the prediction is only made based on $$A':=\{ x'\in A: \left| k(x,x') \right| \geq \tau \}$$where we assume that $p(f(x)|x_{A},y_{A}) \approx p(f(x)|x_{A'},y_{A'})$.

- **Remark**: This method is however still expensive if $\left| A '\right|$ is still large.
---
##### 2.3.5.2 Random Fourier Features
![[Gaussian Process#^75577d]]
![[Gaussian Process#^6edada|p]]
![[Gaussian Process#^d6078a]]

- **Remark**: Modulo rescaling all the data with $\mu(\mathbb{R}^n)$, **we may assume that wlog $\mu$ is a probability measure**, i.e. $\widehat{k}$ is a probability density function.

---
> [!h] Example (Gaussian Kernel)
> For Gaussian/RBF kernel, $$k(x)=\exp \left( -\|x\|^{2} / h^{2} \right) $$Then, 
> 1. $\widehat{k}(\omega)=h\sqrt{ \frac{(2\pi)^n}{2} }\exp \left( -\frac{h^2}{4}\|\omega\|^{2} \right)$ which can be normalized further s.t. $\widehat{k}(\omega)$ is a probability density. 

> [!proof]-
> We have:
> 1. $$\int_{\mathbb{R}^n}^{} \left| \exp \left( -\frac{\|x\|^{2}}{h^{2}} \right)  \right|  \, dx=\left( \int_{\mathbb{R}}^{} \exp \left( -\frac{x_{i}^{2}}{h^{2}} \right)   \, dx  \right)^n=(\pi h^{2})^{n / 2}  $$Hence, $k\in L^1(\mathbb{R}^n)$. 
> 2. Further, $$\widehat{k}(\omega)=\int_{\mathbb{R}^n}\exp \left( -\frac{\|x\|^2}{h^{2}} -i \omega^\top x\right)  \, dx= h\sqrt{ \frac{(2\pi)^n}{2} }\Phi_{X}(-\omega)$$where $X\sim \mathcal{N}(0,(h^{2} / 2)I)$. Therefore, $$\widehat{k}(\omega)=h\sqrt{ \frac{(2\pi)^n}{2} }\exp \left(-\frac{h^{2}}{4} \|\omega\|^{2}\right) $$

---
> [!lemma] Theorem (Random Fourier Features)
> Let $k$ be a real scaled continuous, integrable covariance function. Then, $$k(x,x')=\mathbb{E}_{\omega \sim \widehat{k}, b \sim \mathcal{U}([0,2\pi])}[z_{\omega,b}(x)z_{\omega,b}(x')] $$where $z_{\omega,b}:X\to \mathbb{R}, x\mapsto  \sqrt{ 2 }\cos(\omega^\top x+b)$.

> [!proof]-
> Let $\widehat{k}$ be a pdf (cf. Remark from Bochner). Then, $$\begin{align}k(x-x')&=\int_{\mathbb{R}^n}\widehat{k}(\omega)\exp \left( i\omega^\top(x-x') \right)  \, d\omega\\&= \mathbb{E}[\exp \left( i\omega^\top(x-x') \right) ]\\&= \mathbb{E}[\cos \left( \omega^\top(x-x') \right) ]\end{align}$$as $k$ is a real function. Hence, $$\begin{align}k(x-x')&=\mathbb{E}[\cos(\omega^\top x-w^\top x')]\\&=\mathbb{E}[\mathbb{E}_{b \sim \mathcal{U}([0,2\pi])}[\cos((\omega^\top x+b)-(w^\top x'+b))]]\\&=\mathbb{E}[\mathbb{E}_{b \sim \mathcal{U}([0,2\pi])}[\cos(\omega^\top x+b)\cos(\omega^\top x'+b)+\sin(\omega^\top x+b)\sin(\omega^\top x'+b)]]\end{align}$$Now, $$\begin{align}\mathbb{E}_{b \sim \mathcal{U}([0,2\pi])}[\sin(\omega^\top x+b)\sin(\omega^\top x'+b)]&=\frac{1}{2\pi}\int_{0}^{2\pi} \sin(\omega^\top x+b)\sin(\omega^\top x'+b) \, db \\&=\frac{1}{2\pi}\int_{0}^{2\pi} \cos\left( \frac{\pi}{2}-\omega^\top x-b \right)\cos\left(  \frac{\pi}{2}-\omega^\top x'-b \right) \, db\\&=\frac{1}{2\pi}\int_{-\pi /2}^{3\pi / 2} \cos\left( -\omega^\top x-b \right)\cos\left(  -\omega^\top x'-b \right) \, db \\&=\frac{1}{2\pi}\int_{0}^{2\pi} \cos\left( \omega^\top x+b \right)\cos\left(  \omega^\top x'+b \right) \, db \end{align}$$Hence, $k(x-x')=\mathbb{E}[\mathbb{E}_{b \sim \mathcal{U}([0,2\pi])}[2\cdot\cos(\omega^\top x+b)\cos(\omega^\top x'+b)]]$
---
> [!outlook] Methods (Random Fourier Features)
> We can approximate $k(x,x')$ as follows:
> 1. Sample $\omega_{1},\dots,\omega_{d}\sim \widehat{k}$ iid and $b_{1},\dots,b_{d}\sim \mathcal{U}([0,2\pi])$ iid.
> 2. Construct $z:\mathbb{R}^n\to \mathbb{R}^d,x\mapsto \frac{1}{\sqrt{ d }}(z_{\omega_{1},b_{1}}(x),\dots,z_{\omega_{d},b_{d}}(x))$.
> 3. Approximate $k(x,x') \approx z(x)^\top z(x')$
- **Remark**: From Rahimi et al, for a real scaled continuous integrable covariance kernel $k$ on $\mathbb{R}^n$ and its random fourier features $z:\mathbb{R}^n\to \mathbb{R}^d$ and $\varepsilon>0$, $$\mathbb{P}\left( \text{sup}_{x,x'\in B_{\leq r}(0)} \left| k(x,x')-z(x)^\top z(x') \right|\geq \varepsilon \right)\leq 2^8 \left( \frac{\sigma_{p}\cdot r}{\varepsilon} \right) ^{2} \exp \left( -\frac{d \varepsilon^{2}}{8(n+2)} \right)  $$where $\sigma_{p}:=\mathbb{E}_{\omega}[\omega^\top\omega]$ is the second moment. 
- **Remark**: RFF gives uniform convergence between $z(x)^\top z(x)$ and $k(x,x')$.
- **Remark**: By applying Bayesian linear regression with $z$, we have $O(nd^{2}+d^3)$ instead.
---
##### 2.3.5.3 Inducing Points - Data Sampling

> [!outlook] Method (Inducing Points)
> Let $f\sim \text{GP}(0,k)$ and let $U:=\{ y_{1},\dots,y_{k} \}\subseteq X$ be the set of ***inducing points***. Then, for a set $A:=\{ x_{1},\dots,x_{n} \}$,  
> 1. with the assumption that $f(x)$ and $f_{A}$ are conditionally independent on $f_{U}$,
> 
> $$\begin{align}p(f(x),f(x_{1}),\dots,f(x_{n}))&=\int_{\mathbb{R}^k} p(f(x)|f_{y_{1:k}}) p(f_{x_{1: n}}|f_{y_{1: k}})p(f_{y_{1: k}})\, df_{y_{1: k}}\end{align} $$where:
> 1. $p(f(x)|f_{y_{1:k}}) =\mathcal{N}([k(x,y_{i})]_{i}^\top K_{UU}^{-1}f_{y_{1:k}}, k(x,x)-[k(x,y_{i})]_{i}^\top K_{UU}^{-1}[k(x,y_{i})]_{i})$
> 2. $p(f_{x_{1: n}}|f_{y_{1:k}}) =\mathcal{N}(K_{A U} K_{UU}^{-1}f_{y_{1: k}},K_{A A}-K_{A U} K_{UU}^{-1}K_{U A})$. 
- **Remark**: In ***subset of regressors*** we approximate the conditional prior as:
	1. $q_{\text{SoR}}(f(x)|f_{y_{1:k}}) =\mathcal{N}([k(x,y_{i})]_{i}^\top K_{UU}^{-1}f_{y_{1:k}},0)$
	2. $q_{\text{SoR}}(f_{x_{1: n}}|f_{y_{1:k}}) =\mathcal{N}(K_{A U} K_{UU}^{-1}f_{y_{1: k}},0)$. 
- **Remark**: In **fully independent training conditional** we approximate the conditional prior by assuming they are fully independent, i.e.
	1. $q_{\text{FITC}}(f(x)|f_{y_{1:k}}) =\mathcal{N}([k(x,y_{i})]_{i}^\top K_{UU}^{-1}f_{y_{1:k}},\text{diag}(k(x,x)-[k(x,y_{i})]_{i}^\top K_{UU}^{-1}[k(x,y_{i})]_{i}))$
	2. $q_{\text{FITC}}(f_{x_{1: n}}|f_{y_{1:k}}) =\mathcal{N}(K_{A U} K_{UU}^{-1}f_{y_{1: k}},\text{diag}(K_{A A}-K_{A U} K_{UU}^{-1}K_{U A}))$. 
- **Remark**: In inducing point methods, now the inversion has runtime $\Theta(k^3)$ where $k$ is the number of inducing points. $U$ can be chosen uniformly or completely randomly. $U$ can even be treated as hyperparameters for Bayesian learning.
- **Remark**: The inducing points can be:
	1. chosen randomly/greedily/deterministically
	2. chosen with bayesian learning by treating them as hyperparameters.
---
### 3. Approximating Inference
#### 3.1 Lagrange Approximation
![[Laplace Approximation#^746b7c]]

---
![[Laplace Approximation#^166528]]
![[Laplace Approximation#^438021|p]]

---
![[Laplace Approximation#^781bf0]]
![[Laplace Approximation#^57e4b7|p]]
![[Laplace Approximation#^770b24]]
![[Laplace Approximation#^ca4362|p]]

---
#### 3.2 Variational Inference
