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
![[Variational Inference#^baa2ac]]
![[Variational Inference#^b6c367]]
![[Variational Inference#^473bab|p]]

---
![[Variational Inference#^8f7c5f]]
![[Variational Inference#^26b614|p]]

---
![[Variational Inference#^e5c51e]]
![[Variational Inference#^e82d58|p]]
![[Variational Inference#^719723]]

---
![[Variational Inference#^cd942b]]
![[Variational Inference#^0bbd4c]]

---
#### 3.3 Markov Chain Monte Carlo (MCMC)
![[Markov Chain#^a66180]]
- **Related definition**: A Markov chain is ***ergodic***, if there exists $n\geq 0$ s.t. for any $i,j\in \mathcal{S}$, $i\to j$ in exactly $n$ timesteps.
---
![[Stationary Distribution#^e89f70]]
- **Remark**: An ergodic MC has a unique positive stationary distribution. 
---
![[Markov Chain#^61259e]]
![[Markov Chain#^f23581|p]]

---
##### 3.3.1 Markov Chain Monte Carlo
![[Markov Chain Monte Carlo#^265dad]]

---
![[Markov Chain Monte Carlo#^487412]]
![[Markov Chain Monte Carlo#^658ceb|p]]
![[Markov Chain Monte Carlo#^137832]]

---
![[Markov Chain Monte Carlo#^1e7ebe]]
![[Markov Chain Monte Carlo#^cc3fbd|p]]

---
![[Markov Chain Monte Carlo#^28271d]]
- **Related definition**: The ***Metropolis adjusted Langevin algorithm (MALA)*** uses: $$R(x'|x):=\mathcal{N}(x';x-\tau \nabla_{x}f,2\tau I)$$Similarly, this can be formulated as: $x'\gets x-\tau \nabla_{x}f+\varepsilon$ for $\varepsilon \sim \mathcal{N}(0,2\tau I)$.
- **Related definition**: The ***unadjusted Langevin algorithm (ULA)*** uses MALA proposal, but with $\alpha=1$.
---
> [!outlook] Outlook (MALA for Posterior Distribution)
> Let the posterior $p:=p(\cdot|x_{1:n},y_{1:n})$ be the distribution we want to sample with. Then, 
> 1. $p(\cdot|x_{1:n},y_{1:n})$ is a Gibbs distribution, i.e. $$p(\theta|x_{1:n},y_{1:n})=\frac{1}{z}p(y_{1:n}|x_{1:n},\theta)p(\theta )=\frac{1}{z}\exp(-f(\theta))$$ for $f(\theta):=-\sum_{i=1}^{n}\log p(y_{i}|x_{i},\theta)-\log p(\theta)$.
> 2. The MALA algorithm is given by: $$\theta'\gets \theta-\tau \nabla_{\theta}f+\varepsilon=\theta+\tau \left( \nabla_{\theta}\log p(\theta)+\sum_{i=1}^{n}\nabla_{\theta}\log p(y_{i}|x_{i},\theta) \right) +\varepsilon$$where $\varepsilon \sim \mathcal{N}(0,2\tau I)$.
> 3. **(Stochastic gradient Langevin dynamics,SGLD)** Uses ULA with Monte Carlo methods for the gradient, i.e. $$\theta'\gets \theta-\tau \nabla_{\theta}f+\varepsilon=\theta+\tau \left( \nabla_{\theta}\log p(\theta)+\frac{n}{m}\sum_{j=1}^{m}\nabla_{\theta}\log p(y_{i_{j}}|x_{i_{j}},\theta) \right) +\varepsilon$$where $\varepsilon \sim \mathcal{N}(0,2\tau I)$ and $i_{1},\dots,i_{m}\sim \text{Unif}([n])$ independently
- **Remark**: If we use dynamic learning rates $\tau_{t}=\Theta(t^{-1 / 3})$, then SGLD is guaranteed to converge to the posterior. 
---
#### 3.4 Application: Bayesian Deep Learning
![[Neural Network#^1d6c4a]]

---
##### 3.4.1 Heteroscedastic Noise
> [!definition]
> A noise is called:
> 1. ***homoscedastic*** if it is uniform across the domain. 
> 2. ***heteroscedastic*** if otherwise.
---
> [!outlook] Modelling heteroscedastic noise
> We use a neural network with two outputs $f:\mathbb{R}^d\to \mathbb{R}^2$ and define: 
> 1. $p(y|x,\theta)=\mathcal{N}(y;\mu(x;\theta),\sigma^{2}(x;\theta))$ where 
> 2. $\mu(x;\theta):=f_{1}(x;\theta)$ and
> 3. $\sigma^{2}(x;\theta):=\exp(f_{2}(x;\theta))$ where the exponential is used to make it non-negative. 
> 
> For example, the MAP estimate of $\theta$ becomes with Gaussian prior $\theta \sim \mathcal{N}(0,\sigma^{2}_{p}I)$, $$\begin{align}\widehat{\theta}_{\text{MAP}}&:=\arg\max_{\theta\in \Theta}\log p(\theta)+\sum_{i=1}^{n}\log p(y_{i}|x_{i},\theta)\\&=\arg\max_{\theta\in \Theta}\left( -\frac{\|\theta\|^{2}_{2}}{2\sigma^{2}_{p}}+\sum_{i=1}^{n}\left(-\frac{1}{2}\log \sigma^{2}(x_{i},\theta) -\frac{(y_{i}-\mu(x_{i},\theta))^{2}}{2\sigma^{2}(x_{i},\theta)} \right) \right)\\&=\arg\min_{\theta\in \Theta}\left( \frac{\|\theta\|^{2}_{2}}{\sigma^{2}_{p}}+\sum_{i=1}^{n}\log \sigma^{2}(x_{i},\theta) +\sum_{i=1}^{n}\frac{(y_{i}-\mu(x_{i},\theta))^{2}}{\sigma^{2}(x_{i},\theta)} \right) \end{align}$$
- **Remark**: This can be used to model the aleatoric uncertainty, but not the epistemic uncertainty as this is a MAP estimate, i.e. a point estimate. 
---
##### 3.4.2 Variational Inference with Bayesian Neural Networks
> [!outlook] Variational Inference on Bayesian NN
> Using $\mathcal{Q}$ as the Gaussian distributions, 
> 1. Use the reparametrization trick to find $\lambda$ s.t. $$\begin{align}q_{\lambda}&:=\text{argmax}_{q\in \mathcal{Q}}\mathbb{E}_{\theta \sim q}[\log p(y_{1:n}|x_{1:n},\theta)]-D(q\| p(\cdot))\\&\approx \text{argmax}_{q\in \mathcal{Q}}\mathbb{E}_{\varepsilon \sim \mathcal{N}(0,I)}[\log p(y_{1:n}|x_{1:n},\Sigma^{1/2}\varepsilon+\mu)]-D(q\| p(\cdot))\end{align}$$
> 2. Then, for a new point $x^{*}\in \mathbb{R}^d$, $$\begin{align}p(y^{*}|x^{*},x_{1:n},y_{1:n})&=\int_{\Theta}^{} p(y^{*}|x^{*},\theta)p(\theta|x_{1:n},y_{1:n}) \, d\theta\\&=\mathbb{E}_{\theta \sim p(\cdot |x_{1:n},y_{1:n})}[p(y^{*}|x^{*},\theta)]\\&\approx \mathbb{E}_{\theta \sim q_{\lambda}}[p(y^{*}|x^{*},\theta)] \\&\approx \frac{1}{m}\sum_{j=1}^{m}p(y^{*}|x^{*},\theta^{(j)}) \\&= \frac{1}{m}\sum_{j=1}^{m}\mathcal{N}(y^{*};\mu(x^{*};\theta^{(j)}),\sigma^{2}(x^{*};\theta^{(j)})) \end{align}$$where $\theta^{(1)},\dots,\theta^{(m)}\sim q_{\lambda}$ independently. 
> 3. The mean is given by: $$\mathbb{E}[y^{*}|x^{*},x_{1:n},y_{1:n}]\approx \frac{1}{m}\sum_{j=1}^{m}\mu(x^{*};\theta^{(j)})=:\overline{\mu}(x^{*})$$
> 4. The variance is given by: $$\begin{align}\text{Var}[y^{*}|x^{*},x_{1:n},y_{1:n}]&=\mathbb{E}_{\theta}[\text{Var}_{y^{*}}[y^{*}|x^{*},\theta]]+\text{Var}_{\theta}[\mathbb{E}_{y^{*}}[y^{*}|x^{*},\theta]]\\&=\mathbb{E}_{\theta}\left[ \sigma^{2}(x^{*};\theta)\right]+\text{Var}_{\theta}(\mu(x^{*};\theta))\\&\approx \frac{1}{m}\sum_{j=1}^{m}\sigma^{2}(x^{*};\theta^{(j)})+\frac{1}{m-1}\sum_{j=1}^{m}(\mu(x^{*};\theta^{(j)})-\overline{\mu}(x^{*}))^{2}\end{align}$$where the first term corresponds to the aleatoric uncertainty and the second term corresponds to epistemic.
---
##### 3.4.3 MCMC with BNN
> [!outlook] MCMC with BNN
> The challenges of MCMC with BNN is that:
> 1. we cannot afford to store all $T$ samples (e.g. in SGLD)
> 2. we need to drop the first few samples to avoid burn-in period.
> 
> The workaround are as follows:
> 1. **Subsampling**: Keep track of $m$ snapshots of the weights according to some schedule and use it for inference.
> 2. **Gaussian approximation**: We approximate: $\theta \sim \mathcal{N}(\mu,\Sigma)$ where: $$\mu=\frac{1}{T}\sum_{i=1}^{T}\theta^{(i)},\quad \Sigma=\frac{1}{T-1}\sum_{i=1}^{T}(\theta^{(i)}-\mu)(\theta^{(i)}-\mu)^\top$$This can be done by the following iterations: 
> 	1. $\mu^{(t+1)}:= \frac{1}{t+1}(t\mu^{(t)}+\theta^{(t)})$.
> 	2. $A^{(t+1)}:=\frac{1}{t+1}(tA^{(t)}+\theta^{(t)}\theta^{(t)\top})$
> 
> 	Then, $$\Sigma=\frac{1}{T-1}\sum_{i=1}^{T}(\theta^{(i)}-\mu)(\theta^{(i)}-\mu)^\top=\frac{T}{T-1}(A^{(T)}-\mu^{(T)} \mu^{(T)\top})$$
---
##### 3.4.4 Dropout and Dropconnect

> [!outlook] Dropout and Dropconnect
> For a neural network $f$,
> 1. in ***dropout*** method some vertices in the computation graph are randomly dropped.
> 2. in ***dropconnect*** method some edges in the computation graph are randomly dropped.
>    
>  Suppose we drop each edge independently with probability $p$. Then, dropconnect can be treated as variational inference with: $$\mathcal{Q}:=\left\{\prod_{j=1}^{d}q_{j}(\theta_{j}|\lambda_{j})\right\}$$where $q_{j}(\theta_{j}|\lambda_{j}):=p\delta_{0}(\theta_{j})+(1-p)\delta_{\lambda_{j}}(\theta_{j})$. 
---
##### 3.4.5 Ensembles
> [!outlook] Ensembles
> Let $\mathcal{D}:=\{ x_{i},y_{i} \}_{i\in[n]}$ be the dataset.
> 1. Pick $D_{j}$ as $n$ inputs from $\mathcal{D}$ with replacement uniformly at random.
> 2. Perform MAP estimate on $D_{j}$ to find $\theta^{(j)}$.
> 3. $p(y^{*}|x^{*},x_{1:n},y_{1:n})\approx \frac{1}{m}\sum_{j=1}^{m}p(y^{*}|x^{*},\theta^{(j)})$.
---
##### 3.4.6 Calibration
- **Definition**: A model is ***well-calibrated*** if its confidence coincides with its accuracy across many predictions.

> [!outlook] Methods for Calibration
> We have the following methods:
> 1. **Evidence**: For training set $x^{\text{train}}_{1:n}$ and validation set $x_{1:m}^{\text{test}}$, we have: $$\begin{align}\log p(y^\text{val}_{1:m}|x^\text{val}_{1:m},x^\text{train}_{1:n},y^\text{train}_{1:n})&=\log \int_{\Theta} p(y^\text{val}_{1:m}|x^\text{val}_{1:m},\theta)p(\theta|x^\text{train}_{1:n},y^\text{train}_{1:n}) \, d\theta \\&\approx\log \int_{\Theta} \prod_{i=1}^{m}p(y^\text{val}_{i}|x^\text{val}_{i},\theta)q_{\lambda}(\theta) \, d\theta \\&=\log \mathbb{E}_{\theta \sim q_{\lambda}}\left[\prod_{i=1}^{m}p(y^\text{val}_{i}|x^\text{val}_{i},\theta)\right]\\&\geq \mathbb{E}_{\theta \sim q_{\lambda}}\left[\sum_{i=1}^{m}\log p(y^\text{val}_{i}|x^\text{val}_{i},\theta)\right]\\&\approx \frac{1}{k}\sum_{j=1}^{k}\sum_{i=1}^{m}\log p(y^\text{val}_{i}|x^\text{val}_{i},\theta^{(j)})\end{align}$$where $\theta^{(j)}\sim q_{\lambda}$ iid.
> 2. **Reliability diagram**: Let the validation set be split into $B_{1},\dots,B_{M}$ of similar size. For simplicity, assume the classification problem with two labels $\{ \pm 1 \}$.
> 	1. $\text{freq}(B_{m}):=\frac{1}{\left| B_{m} \right|}\sum_{i\in B_{m}}^{}\mathbb{1}_{Y_{i}=1}$.
> 	2. $\text{conf}(B_{m}):=\frac{1}{\left| B_{m} \right|}\sum_{i\in B_{m}}^{}\mathbb{P}(Y_{i}=1|x_{i})$
> 	
> 	Then, a model is well-calibrated if $\text{freq}(B_{m})\approx \text{conf}(B_{m})$ for all $m$. 
---
### 4. Active Learning
#### 4.1 Active Learning for Regression
In active learning, we consider the following setting. Let $\mathcal{X}$ be the domain of possible observation of an unknown function $f:\mathcal{X}\to \mathbb{R}$, s.t. the observation at each point $x\in \mathcal{X}$ is given by: $$y_{x}:=f(x)+\varepsilon_{x},\quad \varepsilon\sim \mathcal{N}(0,\sigma^{2}_{n}I)$$Let $S:=\{ x_{1},\dots,x_{n} \}\subseteq \mathcal{X}$ now be a set of observations. Then, $y_{S}:=f_{S}+\varepsilon$ where: 
1. $y_{S}:=(y_{x_{1}},\dots,y_{x_{n}})$ and 
2. $f_{S}:=(f_{x_{1}},\dots,f_{x_{n}})$ and 
3. $\varepsilon \sim \mathcal{N}(0,\sigma^{2}_{n}I)$

For a subset $S\subseteq \mathcal{X}$, then define $I(S):=I(f;y_{S})=H(f)-H(f|y_{S})$ given by the [[mutual information]]. Hence, our goal is to find: $$S^{*}:=\underset{ S\subseteq \mathcal{X} }{ \arg\max }\ I(S)$$This is known to be an NP-hard problem

---
> [!lemma] Proposition 1 (Monotone Submodularity of Mutual Information)
> Let $I:2^\mathcal{X}\to \mathbb{R}, S\mapsto H(f)-H(f|y_{S})$ described as above. Then,
> 1. $I(S\cup x)-I(S)=H(y_{x}|y_{S})-H(\varepsilon_{x})$ for $S\subseteq \mathcal{X}$ and $x\in \mathcal{X}$.
> 1. $I:2^\mathcal{X}\to \mathbb{R}$ is a [[Monotone Submodular Function|monotone submodular function]].

> [!proof]-
> We have that: 
> 1. Notice that: $$\begin{align}I(S\cup x)-I(S)&=I(f;y_{S\cup x})-I(f;y_{S})\\&=H(f|y_{S})-H(f|y_{S\cup x})\\&=I(f;y_{x}|y_{S})\\&=H(y_{x}|y_{S})-H(y_{x}|f,y_{S})\\&=H(y_{x}|y_{S})-H(\varepsilon_{x})\end{align}$$
> 1. To show the submodularity, let $S\subseteq T\subseteq \mathcal{X}$ and $x\in\mathcal{X}$. Then, we have to show that:$$I(S\cup x)-I(S)\geq I(T\cup x)-I(T)$$We have that: $$\begin{align}I(S\cup x)-I(S)=H(y_{x}|y_{S})-H(\varepsilon_{x})\geq H(y_{x}|y_{T})-H(\varepsilon_{x})=I(T\cup x )-I(T)\end{align}$$from [[Entropy|Lemma 1.4]]
>    
> 	For monotonicity, let $S\subseteq T$. Then, $$\begin{align}I(T)-I(S)&=H(f|y_{S})-H(f|y_{T})\\&= I(f;y_{T \backslash S}|y_{S})\\&\geq 0\end{align}$$by [[Mutual Information|Lemma 1.2]].
---
> [!lemma] Proposition 2 (Greedy)
> ```pseudo
> \begin{algorithm}\caption{GreedyMutualInfoMax}
> \begin{algorithmic}
> \State $S\gets \varnothing$
> \For{$t=1,\dots,T$}
> \State $x_{t}\gets \arg\max_{x\in \mathcal{X}} I(S\cup x)$
> \State $S\gets S\cup \{ x_{t} \}$
\EndFor
> \Return $S$
> \end{algorithmic}
> \end{algorithm}
> ```
> outputs a $\left( 1-\frac{1}{\varepsilon} \right)$-[[approximation algorithm]].

> [!proof]-
> Given by [[Monotone Submodular Function]]. 

---
> [!Outlook] Gaussian setting
> We have that:
> 1. With homoscedastic noise, $I(S\cup x)-I(S)=H(y_{x}|y_{S})-H(\varepsilon_{x})=\frac{1}{2}\log\left( 1+\frac{\sigma_{S}^{2}(x)}{\sigma^{2}_{n}} \right)$ where $\sigma^{2}_{S}(x)$ denotes the variance of $y_{x}$ given $y_{S}$, i.e. the epistemic uncertainty. Therefore, $$\arg\max_{x\in \mathcal{X}} I(S\cup x)=\arg\max_{x\in \mathcal{X}} \sigma^{2}_{S}(x)$$
> 2. With heteroscedastic noise, we have that $$I(S\cup x)-I(S)=H(y_{x}|y_{S})-H(\varepsilon_{x})=\frac{1}{2}\log\left( 1+\frac{\sigma_{S}^{2}(x)}{\sigma^{2}_{n}(x)} \right)$$Hence, finding the maximum is not as helpful in reducing the epistemic uncertainty!
- **Remark**: One can of course derive other criteria to reduce uncertainty s.t. entropy, trace or eigenvalue etc, instead of mutual information. Typically more expensive, but comes with other benefits.

---
#### 4.2 Active Learning for Classification
We can use the following formula: $$x_{t+1}:=\underset{ x\in \mathcal{X} }{ \arg\max }\ H(y_{x}|x_{1:t},y_{1:t})$$
However, this also leads to a problem of not being able to distinguish between epistemic and aleatoric uncertainty.

---
> [!outlook] Bayesian active learning by disagreement (BALD)
> Let our model be parametrized with $\theta$. We can distinguish the uncertainties by: $$\begin{align}x_{t+1}&:=\underset{ x\in \mathcal{X} }{ \arg\max }\ I(\theta;y_{x}|x_{1:t},y_{1:t})\\ &=\underset{ x\in \mathcal{X} }{ \arg\max }\  H(y_{x}|x_{1:t},y_{1:t})-H(y_{x}|\theta,x_{1:t},y_{1:t})\\ &=\underset{ x\in \mathcal{X} }{ \arg\max }\  H(y_{x}|x_{1:t},y_{1:t})-\mathbb{E}_{\theta |x_{1:t},y_{1:t}}[H(y_{x}|\theta,x_{1:t},y_{1:t})]\\ &=\underset{ x\in \mathcal{X} }{ \arg\max }\  H(y_{x}|x_{1:t},y_{1:t})-\mathbb{E}_{\theta |x_{1:t},y_{1:t}}[H(y_{x}|\theta)]\end{align}$$where the last equality holds due to $y_{x}{\bot}x_{1:t},y_{1:t}|\theta$. Then, 
> 1. the first term looks for points where *the average prediction is not confident*. This can be approximated by the predictive distribution of an approximated posterior using variational inference.
> 2. the second term looks for points where sampled models are confident in their predictions. This can also be approximated using MCMC or variational inference.
---
### 5. Bayesian Optimization
We also consider a setting where acquiring new observations is expensive. Given some function $f:\mathcal{X}\to \mathbb{R}$ we would like to find: $$x^{*}\in \underset{ x\in \mathcal{X} }{ \arg\max }\ f(x)$$where $f$ is unknown. For every point $x\in \mathcal{X}$, we get the observation $y_{x}:=f(x)+\varepsilon_{x}$ where $\varepsilon_{x}\sim \mathcal{N}(0,\sigma^{2}_{n})$

---
> [!definition] Definition (Regret)
> For time horizon $T$, the ***regret*** is defined as:$$R_{T}:=\sum_{t=1}^{T}(\max_{x\in \mathcal{X}}f(x)-f(x_{t}))$$
- **Remark**: The goal is to find sublinear regret, i.e. $R_{T} / T\to 0$, which means we have balanced exploration and exploitation.
---
#### 5.1 Acquisition Function
Assume the setting where for the objective function $f^{*}$ we use a Gaussian Process $f$. For an acquisition function $F$, we can use the following algorithm:
```pseudo
\begin{algorithm}\caption{BayesianOptimization}
\begin{algorithmic}
\State initialize $f\sim \text{GP}(\mu_0,k_0)$
\For{$t=1,...,T$}
\State choose $x_t\gets \argmax_x F(x;\mu_{t-1},k_{t-1})$
\State observe $y_t=f(x_t)+\varepsilon_t$
\State update to get $\mu_t$ and $k_t$.
\EndFor
\end{algorithmic}
\end{algorithm}
```

---
##### 5.1.1 Upper Confidence Bound
> [!outlook] UCB
> In UCB, we find the next point using: $$x_{t+1}:=\underset{ x\in \mathcal{X} }{ \arg\max }\ \mu_{t}(x)+\beta_{t+1}\sigma_{t}(x)$$where $\beta_{t+1}$ is the regularizer. 
> 1. If $\beta_{t}=0$ then the algorithm is purely exploitative and for $\beta_{t}\to 0$ the algorithm is purely explorative. 
> 2. To find the optimum $x_{t+1}$, in lower dimensions we can use Lipschitz optimization and gradient ascent in higher dimensions. 
---
> [!lemma] Theorem 1 (Bayesian Confidence Intervals)
> Let $0<\delta<1$ and assume $f^{*}\sim \text{GP}(\mu_{0},k_{0})$ and Gaussian noise $\varepsilon_{t}\sim \mathcal{N}(0,\varepsilon^2_{n})$, 
> 1. if $\beta_{t}(\delta)=O(\sqrt{ \log(\left| \mathcal{X} \right|t / \delta) })$ then $$\mathbb{P}(f^{*}(x)\in C_{t}(x), \forall x\in \mathcal{X},t\geq 1)\geq 1-\delta$$ where $C_{t}(x):=[\mu_{t-1}(x)\pm \beta_{t+1}\sigma_{t}(x)]$.
---
> [!lemma] Theorem 2
> If $\beta_{t}(\delta)$ is chosen correctly, i.e. $\mathbb{P}(f^{*}(x)\in C_{t}(x),\forall x\in \mathcal{X},t\geq 1)\geq 1-\delta$, then UCB has regret: $$R_{T}=O(\beta_{T}(\delta)\sqrt{ \gamma_{T}T })$$where: $\gamma_{T}=\max_{S\in {\mathcal{X} \choose T}}I(f;y_{S})=\max_{S\in {\mathcal{X} \choose T}} \frac{1}{2}\log \det(I+\sigma_{n}^{-2}K_{SS})$. Further we have that:
> 1. Linear kernel: $\gamma_{T}=O(d \log T)$.
> 2. Gaussian kernel: $\gamma_{T}=O((\log T)^{d+1})$
> 3. Matérn kernel for $\nu> \frac{1}{2}$: $\gamma_{T}=O(T^{\frac{d}{2\nu+d}}(\log T)^{\frac{2\nu}{2\nu+d}})$
---
##### 5.1.2 Thompson Sampling
> [!outlook] Thompson Sampling
> In UCB, we find the next point using: $$x_{t+1}:=\underset{ x\in \mathcal{X} }{ \arg\max }\ \tilde{f}_{t+1}(x)$$where $\tilde{f}_{t+1}\sim p(\cdot|x_{1:t},y_{1:t})$.
> 1. The randomness in the sampling is enough to explore and exploit. 
---
### 6. Markov Decision Processes
#### 6.1 MDP
![[Markov Decision Process#^676f65]]
![[Markov Decision Process#^6aea89]]
![[Markov Decision Process#^48753c|p]]
![[Markov Decision Process#^282b3a|p]]
![[Markov Decision Process#^060a16|p]]
![[Markov Decision Process#^0704ec|p]]

---
![[Markov Decision Process#^8cd5fc]]
![[Markov Decision Process#^310f46|p]]

---
![[Markov Decision Process#^f95d00]]
![[Markov Decision Process#^26bdee|p]]
![[Markov Decision Process#^9ca6be]]

---
![[Markov Decision Process#^950b56]]

---
![[Markov Decision Process#^0cea46]]

---
![[Markov Decision Process#^5dd8bf]]
![[Markov Decision Process#^08b195|p]]
![[Markov Decision Process#^bcf061]]

---
#### 6.2 POMDP
![[Partially Observable Markov Decision Process#^a48413]]

---
![[Partially Observable Markov Decision Process#^1bdfe5]]

---
### 7. Reinforcement Learning
> [!definition]
> Let $\mathcal{X}$ be the state space and $\mathcal{A}$ be the action space. 
> 1. A ***trajectory*** is defined as: $$\tau:=(x_{i},a_{i},r_{i},x_{i+1})_{i\geq 0}\subseteq \mathcal{X}\times \mathcal{A}\times \mathbb{R}\times\mathcal{X}$$
---
> [!outlook] Different Branches in RL
> The collection of data can be identified in two settings:
> 1. in ***episodic setting***, the agent performs a sequence of “training” rounds called episodes where in the beginning of each episode, the agent is reset to some initial state.
> 2. in ***non-episodic setting***, the agent learns online where every action, every reward, and every state transition counts.
> 
> Further, each RL method can be identified as:
> 1. ***on-policy methods***: when the agent has control over its own actions, in other words, the agent can freely choose to follow any policy.
> 2. ***off-policy methods*** when the agent cannot freely choose its actions. Hence, with off-policy methods the agents can utilize purely observational data, e.g. collected by a different agent or by a fixed policy. 
> 
> There are also the following distinctions:
> 1. ***Model-based*** where the method aims to learn the underlying MDP, especially $P$ and $r$. 
> 2. ***Model-free*** where the method learns the value function directly.
- **Remark**: Off-policy methods are hence more sample-efficient. 
---
#### 7.1 Tabular Setting
This refers to the case where $\mathcal{X}$ and $\mathcal{A}$ are small so we can keep track of all the values.

---
##### 7.1.1 Model-based Tabular Approaches
- **Remark**: In general has the disadvantage that the whole transition matrix needs to be saved, i.e. $O(\left| \mathcal{X} \right|^{2}\left| \mathcal{A} \right|)$.
- **Remark**: Model-based approaches are inherently off-policy.
---

###### 7.1.1.1 MLE Approximation of MDP
> [!outlook] MLE Approximation
> We can learn the underlying MDP using the following method. Let $N(x'|x,a)$ be the number of transitions from $x$ to $x'$ with action $a$ and $N(a|x)$ the number of times $a$ is played from state $x$ in the trajectory. Then, $$\widehat{P}(x'|x,a):=\frac{N(x'|x,a)}{N(a|x)},\quad \widehat{r}(x,a):=\frac{1}{N(a|x)}\sum_{t}r_{t}\cdot \mathbb{1}_{x_{t}=x}\cdot \mathbb{1}_{a_{t}=a}$$
- **Remark**: This will work only if each tuple $(x,x',a)$ is visited multiple times (at least once to be well-defined). We can use Hoeffding to figure out how much data we need.
---
###### 7.1.1.2 $\varepsilon$-Greedy Algorithm
> [!outlook] Eps-Greedy
> ```pseudo
> \begin{algorithm}\caption{$\varepsilon$-Greedy($(\varepsilon_{t})_{t\geq 0}$)}
> \begin{algorithmic}
> \For{$t\geq 0$}
> \State with probability $\varepsilon_{t}$, pick action uniformly at random. 
> \State otherwise, pick the best action.
\EndFor
\end{algorithmic}
\end{algorithm}
> ```
> If it holds that $\sum_{t=0}^{\infty}\varepsilon_{t}=+\infty$ but $\sum_{t=0}^{\infty}\varepsilon_{t}^{2}<+\infty$, then the algorithm converges to optimal policy almost surely. 
- **Remark**: Picking an action uniformly at random can be improved to use past knowledge to decide where to explore. 
---
###### 7.1.1.3 $R_{\text{max}}$-algorithm
> [!outlook] Rmax Algorithm
> ```pseudo
> \begin{algorithm}\caption{$R_{\text{max}}$ Algorithm}
> \begin{algorithmic}
> \State add the fairy-tale state $x^{*}$ to the MDP
> \State $\widehat{r}(x,a)\gets R_{\text{max}}$ for all $x\in \mathcal{X}$ and $a\in \mathcal{A}$ where $R_{\text{max}}$ is the given upper bound for reward.
> \State $\widehat{P}(x^{*}|x,a)\gets 1$ for all $x\in \mathcal{X},a\in \mathcal{A}$
> \State compute the optimal policy $\widehat{\pi}$ w.r.t. $\widehat{P}$ and $\widehat{r}$
> \For{$t\geq 0$}
> \State execute $\widehat{\pi}$ for some steps and generate trajectory.
> \State update $\widehat{r}$ and $\widehat{P}$ using the result (c.f. MLE approximation)
> \State recompute $\widehat{\pi}$ using the updated $\widehat{r}$ and $\widehat{P}$
\EndFor
\end{algorithmic}
\end{algorithm}
> ```
> We need $N(a|x)\geq \frac{R^{2}_{\text{max}}}{2\varepsilon^{2}}\log \frac{2}{\delta}$ s.t. the approximation error is below $\varepsilon$ with probability $\geq 1-\delta$ for $a\in \mathcal{A}$ and $x\in \mathcal{X}$. Then,
> 1. it can be shown that every $T$ timesteps, the algorithm either obtains a near-optimal reward or visited at least one unknown state-action pair w.h.p.
> 2. with probability at least $1-\delta$, the algorithm reaches an $\varepsilon$-optimal policy in $\text{poly}\left( \left| \mathcal{X} \right|,\left| \mathcal{A} \right|,T, \frac{1}{\varepsilon}, \frac{1}{\delta},R_{\text{max}} \right)$
- **Remark**: The algorithm computes an optimal policy $O(nm)$ times, which can be quite costly.
---
##### 7.1.2 Model-free Tabular Approaches
###### 7.1.2.1 On-Policy Value Estimation
Notice that for the value estimation using: $$V^\pi_{\text{new}}(x)=r(x,\pi(x))+\gamma \sum_{x'}^{}P(x'|x,\pi(x))\cdot V^\pi_{\text{old}}(x')$$which can be represented as an expected value. However, we cannot use Monte Carlo methods as after one sample we will have moved on to a different state. Hence, we crudely approximate the value with the one pair. Further, as we don't know the next state we will move to, we will just iteratively update $V^\pi$ for the current state. 
> [!outlook] Temporal Difference Learning
> ```pseudo
> \begin{algorithm}\caption{Temporal-Difference Learning($(\alpha_{t})_{t\geq 0}$)}
> \begin{algorithmic}
> \State initialize $V^\pi\gets 0$
> \For{$t\geq 0$}
> \State follow a policy $\pi$ to get the transition $(x,a,r,x')$
> \State $V^\pi(x)\gets (1-\alpha_{t})V^\pi(x)+\alpha_{t}(r+\gamma V^\pi(x'))$
\EndFor
\end{algorithmic}
\end{algorithm}
> ```
> We have that:
> 1. if $\sum_{t=0}^{\infty}\alpha_{t}=\infty$ and $\sum_{t=0}^{\infty}\alpha^{2}_{t}<\infty$ and all pairs $(x,a)$ are chosen infinitely often, then $V^\pi$ converges to the actual value function for $\pi$ almost surely. 
---
> [!outlook] SARSA
> ```pseudo
> \begin{algorithm}\caption{SARSA($(\alpha_{t})_{t\geq 0}$)}
> \begin{algorithmic}
> \State initialize $Q^\pi\gets 0$
> \State follow a policy $\pi$ to get the transition $(x,a,r,x')$
> \For{$t\geq 0$}
> \State follow a policy $\pi$ to get the transition $(x',a',r',x'')$
> \State $Q^\pi(x,a)\gets (1-\alpha_{t})Q^\pi(x,a)+\alpha_{t}(r+\gamma Q^\pi(x',a'))$
> \State $(x,a,r,x')\gets(x',a',r',x'')$
\EndFor
\end{algorithmic}
\end{algorithm}
> ```
> We have that:
> 1. if $\sum_{t=0}^{\infty}\alpha_{t}=\infty$ and $\sum_{t=0}^{\infty}\alpha^{2}_{t}<\infty$ and all pairs $(x,a)$ are chosen infinitely often, then $Q^\pi$ converges to the actual Q-function for $\pi$ almost surely. 

---
###### 7.1.2.2 Off-Policy Value Estimation

> [!outlook] Off Policy SARSA
> ```pseudo
> \begin{algorithm}\caption{SARSA($(\alpha_{t})_{t\geq 0}$)}
> \begin{algorithmic}
> \State initialize $\widehat{Q}^\pi\gets 0$
> \For{$t\geq 0$}
> \State observe the transition $(x,a,r,x')$
> \State $\widehat{Q}^\pi(x,a)\gets (1-\alpha_{t})\widehat{Q}^\pi(x,a)+\alpha_{t}\left( r+\gamma \sum_{a'\in \mathcal{A}}^{}\pi(a'|x')\widehat{Q}^\pi(x',a') \right)$
\EndFor
\end{algorithmic}
\end{algorithm}
> ```
> We have that:
> 1. if $\sum_{t=0}^{\infty}\alpha_{t}=\infty$ and $\sum_{t=0}^{\infty}\alpha^{2}_{t}<\infty$ and all pairs $(x,a)$ are chosen infinitely often, then $\widehat{Q}^\pi$ converges to $Q^\pi$ almost surely. 
---

> [!outlook] Q-learning
> ```pseudo
> \begin{algorithm}\caption{Q-learning($(\alpha_{t})_{t\geq 0}$)}
> \begin{algorithmic}
> \State initialize $\widehat{Q}^{*}\gets 0$
> \For{$t\geq 0$}
> \State observe the transition $(x,a,r,x')$
> \State $\widehat{Q}^{*}(x,a)\gets (1-\alpha_{t})\widehat{Q}^{*}(x,a)+\alpha_{t}\left( r+\gamma \max_{a'\in \mathcal{A}}\widehat{Q}^{*}(x',a') \right)$
\EndFor
\end{algorithmic}
\end{algorithm}
> ```
> We have that:
> 1. if $\sum_{t=0}^{\infty}\alpha_{t}=\infty$ and $\sum_{t=0}^{\infty}\alpha^{2}_{t}<\infty$ and all pairs $(x,a)$ are chosen infinitely often, then $\widehat{Q}^{*}$ converges to $Q^{*}$ almost surely. 
> 2. With probability at least $1-\delta$, the algorithm converges to a $\varepsilon$-optimal policy in $\text{poly}(\log \left| \mathcal{X} \right|,\log \left| \mathcal{A} \right|, 1 / \varepsilon, \log(1 / \delta))$ steps.
---
> [!outlook] Optimistic Q-learning
> ```pseudo
> \begin{algorithm}\caption{Optimistic Q-learning($(\alpha_{t})_{t\geq 0}, R_{\text{max}},T_{\text{init}}$)}
> \begin{algorithmic}
> \State initialize $\widehat{Q}^{*}\gets (1-\gamma)^{-1}R_{\text{max}}\prod_{t\in [T_{\text{init}}]}^{}(1-\alpha_{t})^{-1}$
> \For{$t\geq 0$}
> \State get current state $x$.
> \State pick $a_{t}:=\arg\max_{a\in \mathcal{A}}\widehat{Q}^{*}(x,a)$observe the transition $(x,a,r,x')$
> \State $\widehat{Q}^{*}(x,a)\gets (1-\alpha_{t})\widehat{Q}^{*}(x,a)+\alpha_{t}\left( r+\gamma \max_{a'\in \mathcal{A}}\widehat{Q}^{*}(x',a') \right)$
\EndFor
\end{algorithmic}
\end{algorithm}
> ```
> We have that:
> 1. if $\sum_{t=0}^{\infty}\alpha_{t}=\infty$ and $\sum_{t=0}^{\infty}\alpha^{2}_{t}<\infty$ and all pairs $(x,a)$ are chosen infinitely often, then $\widehat{Q}^{*}$ converges to $Q^{*}$ almost surely. 
> 2. With probability at least $1-\delta$, the algorithm converges to a $\varepsilon$-optimal policy in $\text{poly}(\log \left| \mathcal{X} \right|,\log \left| \mathcal{A} \right|, 1 / \varepsilon, \log(1 / \delta))$ steps.
---
