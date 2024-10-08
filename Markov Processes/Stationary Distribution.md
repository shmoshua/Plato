#Definition #Markov 

> [!definition]
> A [[Positive Measure|probability measure]] $\pi$ is called a ***stationary probability distribution*** if: $$\pi=\pi P$$where $P$ is the [[Markov Chain|transition matrix]].
- **Remark**: $\pi$ is not unique, i.e. there exists Markov chains with more than one stationary distributions. 
---
##### Properties
> [!lemma] Theorem 1 (Doeblin)
> Let $P$ be the transition matrix of a [[Markov chain]]. If $P$ has the ***Doeblin property***, i.e.  there exists some state $j_{0}\in \mathcal{S}$ and $\varepsilon>0$ s.t. $P_{ij_{0}}\geq \varepsilon$ for all $i\in \mathcal{S}$, then: 
> 1. $P$ has a unique stationary probability distribution $\pi$.
> 2. $\pi_{j_{0}}\geq \varepsilon$ and
> 3. for all initial distributions $\mu$, $$\left\| \mu P^n-\pi \right\|_{1}\leq (1-\varepsilon)^n\left\| \mu-\pi \right\| _{1}\leq 2(1-\varepsilon)^n$$

> [!proof]-
> Let $\rho$ be a row vector with $\left\| \rho \right\|_{1}<+\infty$. Then, 
> 1. Claim 1: $\sum_{j\in \mathcal{S}}^{}(\rho P)_{j}=\sum_{j\in \mathcal{S}}^{}\sum_{i\in \mathcal{S}}^{}\rho_{i}P_{ij}=\sum_{i\in \mathcal{S}}^{}\rho_{i}\sum_{j\in \mathcal{S}}^{}P_{ij}=\sum_{i\in \mathcal{S}}^{}\rho_{i}$
> 2. **Claim 2: if $\sum_{i}^{}\rho_{i}=0$ then $\left\| \rho P^n \right\|_{1}\leq(1-\varepsilon)^n\left\| \rho \right\|_{1}$ for all $n\geq 0$.**
>    If $n=1$, $$\left| (\rho P)_{j} \right|=\left| \sum_{i\in \mathcal{S}}^{}\rho_{i}P_{ij} \right|=\left| \sum_{i\in \mathcal{S}}^{}\rho_{i}P_{ij}- \varepsilon\delta_{jj_{0}}\sum_{i\in \mathcal{S}}^{}\rho_{i} \right| =\left| \sum_{i\in \mathcal{S}}^{}\rho_{i}(P_{ij}-\varepsilon\delta_{jj_{0}}) \right|  $$Then, $$\left\| \rho P \right\|_{1} =\sum_{j\in \mathcal{S}}^{}\left| (\rho P)_{j} \right|\leq\sum_{j\in \mathcal{S}}^{}\left( \sum_{i\in \mathcal{S}}^{}\left| \rho_{i} \right| (P_{ij}-\delta_{jj_{0}}) \right) = (1-\varepsilon)\sum_{i\in \mathcal{S}}^{}\left| \rho_{i} \right| =(1-\varepsilon)\left\| \rho \right\| _{1}$$For $n>1$, we have that by Claim 1 that $\sum_{j}^{}(\rho P^{n-1})_{j}=\sum_{i}^{}\rho_{i}$. Hence: $$\left\| \rho P^n \right\| _{1}=\left\| \rho P^{n-1}P \right\|_{1}\leq(1-\varepsilon)\left\| \rho P^{n-1} \right\| _{1}\leq(1-\varepsilon)^n\left\| \rho \right\| _{1} $$
>  
>  Now, define $\mu_{n}:=\mu P^n$ and note that: 
>  1. $\mu_{n}=\mu_{n-m}P^m$
>  2. $\sum_{i}^{}(\mu_{n-m})_{i}-\mu_{i}=0$
>     
>    Therefore, $$\begin{align}\left\| \mu_{n}-\mu_{m} \right\| _{1}=\left\| \mu_{n-m}P^m-\mu P^m \right\| _{1}\leq \left\| (\mu_{n-m}-\mu)P^m \right\|_{1}\leq(1-\varepsilon)^m \left\| \mu_{n-m}-\mu \right\| _{1} \end{align}$$This shows that $(\mu_{n})_{n}$ is a Cauchy sequence and there exists $\pi:=\lim_{ n \to \infty }\mu_{n}$ in $\ell^1(\mathcal{S})$ and: $$\pi=\lim_{ n \to \infty } \mu P^n=(\lim_{ n \to \infty } \mu P^n)P=\pi P$$and $\pi$ is stationary. Further, $\pi$ is a probability measure. 
>    
>    Lastly, $(\pi)_{j_{0}}=\sum_{i}^{}\pi_{i}P_{ij_{0}}\geq \varepsilon$. 
> 
> ---
>  To show uniqueness, let $\nu$ be an arbitrary probability measure s.t. $$\left\| \nu P^m-\pi \right\| _{1}=\left\| (\nu-\pi)P^m \right\|_{1}\leq(1-\varepsilon)^m\|\nu-\pi\|\leq 2(1-\varepsilon)^m $$
- **Remark**: $\pi$ is a left eigenvector of $P$ and $1$ is a right eigenvector of $P$.
---
> [!lemma] Theorem 2 (Doeblin, extended)
> Let $P$ be the transition matrix of a [[Markov chain]]. If there exists some $M\geq 1$ and $\varepsilon>0$ s.t. $\sup_{j}\inf_{i} (P^M)_{ij}\geq \varepsilon$ for all $i\in \mathcal{S}$, then: 
> 1. $P$ has a unique stationary probability distribution $\pi$.
> 2. $\pi_{j_{0}}\geq \varepsilon$ and
> 3. for all initial distributions $\mu$, $$\left\| \mu P^n-\pi \right\|_{1}\leq (1-\varepsilon)^{\left\lfloor n/M\right\rfloor }\left\| \mu-\pi \right\| _{1}\leq 2(1-\varepsilon)^{\left\lfloor n/M\right\rfloor }$$
- **Corollary**: for any bounded function $f$, we have that: $$\left| \mu P^nf-\pi f \right| =\left| \mu P^nf-\mu \cdot \overline{\pi f} \right| \leq 2(1-\varepsilon)^{\left\lfloor n / M\right\rfloor }\left\| f \right\| _{b}$$and hence $\left\| P^nf-\pi f \right\|_{b}\leq 2(1-\varepsilon)^{\left\lfloor n / M\right\rfloor }\left\| f \right\| _{b}$.
---
> [!lemma] Theorem 3
> Let $P$ be the transition matrix of a [[Markov chain]] and we define: $A_{n}=\frac{1}{n}\sum_{m=0}^{n-1}P^m$. If for $M\in \mathbb{Z}^+$, $j_{0}\in\mathcal{S}$ and $\varepsilon>0$, it holds that $(A_{M})_{ij_{0}}\geq \varepsilon$ for all $i$, then: 
> 1. $P$ has a unique stationary probability distribution $\pi$.
> 2. $\pi_{j_{0}}\geq \varepsilon$ and
> 3. for all initial distributions $\mu$, $$\left\| \mu A_{n}-\pi \right\|_{1}\leq \frac{M-1}{n \varepsilon}$$
---
> [!lemma] Theorem 4 (Mean Ergodic Theorem)
> Let $\{ X_{n} \}_{n\geq 0}$ be a Markov chain with transition probability $P$. Further, let: $$\overline{T}_{j}^{(n)}:=\frac{1}{n}\sum_{m=0}^{n-1}\mathbb{1}_{\{ j \}}(X_{m})$$If for $M\in \mathbb{Z}^+$, $j_{0}\in\mathcal{S}$ and $\varepsilon>0$, it holds that $(A_{M})_{ij_{0}}\geq \varepsilon$ for all $i$, then: 
> 1. it holds that:$$\sup_{j\in \mathcal{S}}\mathbb{E}\left[ \left(\overline{T}^{(n)}_{j}-\pi_{j}\right)^2 \right] \leq \frac{2(M-1)}{n\varepsilon},\quad \forall n\geq 1$$
> 2. for any $f\in \ell^\infty(\mathcal{S})$, $$\mathbb{E}\left[ \left( \frac{1}{n}\sum_{m=0}^{n-1}f(X_{m})-\pi f \right) ^{2} \right] \leq \frac{4(M-1)}{n\varepsilon}\left\| f \right\| ^{2}_{\infty}$$

> [!proof]+
> We have that:
> 1. $\tilde{f}:= f-\pi f\in \ell^\infty(\mathcal{S})$. Therefore, $$\begin{align}\left( \frac{1}{n}\sum_{m=0}^{n-1}f(X_{m})-\pi f \right) ^{2}&=\frac{1}{n^{2}}\left( \sum_{m=0}^{n-1}\tilde{f}(X_{m})\right) ^{2}\\&=\frac{2}{n^{2}}\sum_{0\leq k\leq \ell< n}^{}\tilde{f}(X_{k})\tilde{f}(X_{\ell})-\frac{1}{n^{2}}\sum_{k=0}^{n-1}\tilde{f}(X_{k})^{2}\\&\leq\frac{2}{n^{2}}\sum_{0\leq k\leq \ell< n}^{}\tilde{f}(X_{k})\tilde{f}(X_{\ell})\end{align}$$Hence, $$\begin{align}\mathbb{E}\left[ \left( \frac{1}{n}\sum_{m=0}^{n-1}f(X_{m})-\pi f \right) ^{2} \right] &\leq \frac{2}{n^{2}}\sum_{0\leq k\leq \ell<n}^{}\mathbb{E}[\tilde{f}(X_{k})\tilde{f}(X_{\ell})]\\&=\frac{2}{n^{2}}\sum_{k=0}^{n-1}\mathbb{E}\left[\tilde{f}(X_{k})\sum_{\ell=k}^{n-1}\tilde{f}(X_{\ell})\right]\\&=\frac{2}{n^{2}}\sum_{k=0}^{n-1}\mathbb{E}\left[\tilde{f}(X_{k})\sum_{\ell=0}^{n-k-1}\tilde{f}(X_{k+\ell})\right]\\&=\frac{2}{n^{2}}\sum_{k=0}^{n-1}\mathbb{E}\left[\mathbb{E}\left[\left.\tilde{f}(X_{k})\sum_{\ell=0}^{n-k-1}\tilde{f}(X_{k+\ell})\right| X_{k}\right]\right]\end{align}$$