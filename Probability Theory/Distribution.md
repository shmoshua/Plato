#Definition #ProbabilityTheory 

> [!definition]
> Here are the list of distributions:
> 1. **Discrete distributions**:
>    1. ***Uniform distribution*** on a finite set $E$: a [[random variable]] $X:\Omega\to E$ is uniformly distributed if: $$\mathbb{P}(X=x)=\left| E \right| ^{-1},\quad \forall x\in X$$
>    2. **Bernoulli distribution** $\text{Ber}(p)$ for $p\in [0,1]$: a random variable $X:\Omega\to \{ 0,1 \}$ is Bernoulli distributed if: $$\mathbb{P}(X=1)=p,\quad \mathbb{P}(X=0)=1-p$$
>    3. **Binomial distribution** $\text{Bin}(n,p)$ for $n\in \mathbb{N}$, $p\in [0,1]$: a random variable $X:\Omega\to \{ 0,\dots,n \}$ is binomially distributed if: $$\mathbb{P}(X=k)={n\choose k}p^k(1-p)^{n-k},\quad \forall k=0,1\dots,n$$
>    4. **Geometric distribution** $\text{Geo}(p)$ for $p\in [0,1]$: a random variable $X:\Omega\to \mathbb{Z}_{\geq 0}$ is geometrically distributed if: $$\mathbb{P}(X=k)=(1-p)p^k,\quad \forall k\in \mathbb{Z}_{\geq 0}$$
>    5. **Poisson distribution** $\text{Poisson}(\lambda)$ with $\lambda>0$: a random variable $X:\Omega\to \mathbb{Z}_{\geq 0}$ is Poisson distributed if: $$\mathbb{P}(X=k)=\frac{\lambda^k}{k!}e^{-\lambda},\quad \forall k \in \mathbb{Z}_{\geq 0}$$
> 2. **Continuous distributions**:
> 	1. ***Uniform distribution*** on $[a,b]$ has [[density]]: $$p=\frac{1}{b-a} \cdot \mathbb{1}_{[a,b]}$$
> 	2. ***Exponential distribution*** $\text{Exp}(\lambda)$ with $\lambda>0$ has density: $$p(x)=\lambda e^{-\lambda x}\mathbb{1}_{\mathbb{R}_{\geq 0}}(x)$$
> 	3. ***Gamma distribution*** $\Gamma(a,\lambda)$ for $a,\lambda>0$ has density:$$p(x)=\frac{\lambda^a}{\Gamma(a)}x^{a-1}e^{-\lambda x}\mathbb{1}_{R_{\geq 0}}(x)$$
> 	4. **Cauchy distribution** with $a>0$ has density: $$p(x)=\frac{1}{\pi} \frac{a}{a^{2}+x^{2}}$$
> 	5. **Gaussian distribution** $\mathcal{N}(m,\sigma^{2})$ for $m\in \mathbb{R},\sigma>0$ has density: $$p(x)=\frac{1}{\sigma \sqrt{ 2\pi }}\exp \left( -\frac{(x-m)^{2}}{2\sigma^{2}} \right) $$

--- 
##### Properties
> [!lemma] Proposition 
> Let $X\sim \text{Exp}(\lambda)$. Then, 
> 1. $\mathbb{P}(X\geq a+b)=\mathbb{P}(X\geq a)\mathbb{P}(X\geq b)$
> 2. Especially, any RV that meets this property is either 0 or exponentially distributed.