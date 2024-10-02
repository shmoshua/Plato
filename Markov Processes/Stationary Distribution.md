#Definition #Markov 

> [!definition]
> A [[Positive Measure|probability measure]] $\pi$ is called a ***stationary probability distribution*** if: $$\pi=\pi P$$where $P$ is the [[Markov Chain|transition matrix]].
- **Remark**: $\pi$ is not unique, i.e. there exists Markov chains with more than one stationary distributions. 
---
##### Properties
> [!lemma] Theorem 1 (Doeblin)
> Let $P$ be the transition matrix of a [[Markov chain]]. If there exists some state $j_{0}\in \mathcal{S}$ and $\varepsilon>0$ s.t. $P_{ij_{0}}\geq \varepsilon$ for all $i\in \mathcal{S}$, then: 
> 1. $P$ has a unique stationary probability distribution $\pi$ with $\pi_{j_{0}}\geq \varepsilon$ and
> 2. for all initial distributions $\mu$, $$\left\| \mu P^n-\pi \right\|_{1}\leq (1-\varepsilon)^n\left\| \mu-\pi \right\| _{1}\leq(1-\varepsilon)^n$$

> [!proof]+
> Let $\rho$ be a row vector with $\left\| \rho \right\|_{1}<+\infty$. Then, 
> 1. Claim 1: $\sum_{j\in \mathcal{S}}^{}(\rho P)_{j}=\sum_{j\in \mathcal{S}}^{}\sum_{i\in \mathcal{S}}^{}\rho_{i}P_{ij}=\sum_{i\in \mathcal{S}}^{}\rho_{i}\sum_{j\in \mathcal{S}}^{}P_{ij}=\sum_{i\in \mathcal{S}}^{}\rho_{i}$
> 2. **Claim 2: if $\sum_{i}^{}\rho_{i}=0$ then $\left\| \rho P^n \right\|_{1}\leq(1-\varepsilon)^n\left\| \rho \right\|_{1}$ for all $n\geq 0$.**
>    If $n=1$, $$\left| (\rho P)_{j} \right|=\left| \sum_{i\in \mathcal{S}}^{}\rho_{i}P_{ij} \right|=\left| \sum_{i\in \mathcal{S}}^{}\rho_{i}P_{ij}- \varepsilon\delta_{jj_{0}}\sum_{i\in \mathcal{S}}^{}\rho_{i} \right| =\left| \sum_{i\in \mathcal{S}}^{}\rho_{i}(P_{ij}-\varepsilon\delta_{jj_{0}}) \right|  $$Then, $$\left\| \rho P \right\|_{1} =\sum_{j\in \mathcal{S}}^{}\left| (\rho P)_{j} \right|\leq\sum_{j\in \mathcal{S}}^{}\left( \sum_{i\in \mathcal{S}}^{}\left| \rho_{i} \right| (P_{ij}-\delta_{jj_{0}}) \right) = (1-\varepsilon)\sum_{i\in \mathcal{S}}^{}\left| \rho_{i} \right| =(1-\varepsilon)\left\| \rho \right\| _{1}$$For $n>1$, we have that by Claim 1 that $\sum_{j}^{}(\rho P^{n-1})_{j}=\sum_{i}^{}\rho_{i}$. Hence: $$\left\| \rho P^n \right\| _{1}=\left\| \rho P^{n-1}P \right\|_{1}\leq(1-\varepsilon)\left\| \rho P^{n-1} \right\| _{1}\leq(1-\varepsilon)^n\left\| \rho \right\| _{1} $$
>  
>  Now, define $\mu_{n}:=\mu P^n$ and note that: 
>  1. $\mu_{n}=\mu_{n-m}P^m$
>  2. $\sum_{i}^{}(\mu_{n-m})_{i}-\mu_{i}=0$
>     
>    Therefore, $$\begin{align}\left\| \mu_{n}-\mu_{m} \right\| _{1}=\left\| \mu_{n-m}P^m-\mu P^m \right\| _{1}\leq \left\| (\mu_{n-m}-\mu)P^m \right\|_{1}\leq(1-\varepsilon)^m \left\| \mu_{n-m}-\mu \right\| _{1} \end{align}$$