#Definition #InformationTheory 

> [!definition]
> Let $p,q$ be distributions on $\mathcal{X}$. 
> 1. The ***relative entropy*** of $p$ and $q$ is defined as:$$D(p\|q):=\mathbb{E}_{x\sim p}\left[ \log \frac{p(x)}{q(x)}\right]$$

^c8e329

- **Remark**: the relative entropy is not symmetric.
---
##### Properties
> [!lemma] Proposition 1 (Information Equality)
> For distributions $p,q$ on $\mathcal{X}$ we have that:
> 1. $D(p\|q)\geq 0$.
> 2. $D(p\|q)=0$ if and only if $p=q$ almost everywhere.

^e6cf2f

> [!proof]-
> We have that:
> 1. Notice that: $$\begin{align}-D(p\|q)&=-\mathbb{E}_{p}[\log p / q]=\mathbb{E}_{p}[\log q / p]\leq \log \mathbb{E}_{p}[q / p]=\log \int_{\text{supp }p} q(x) \, dx \leq \log 1 = 0\end{align}$$
> 2. If $p=q$, then: $D(p\|q)=\mathbb{E}_{p}[0]=0$. Conversely, if $D(p\|q)=0$, then $\log \frac{p(x)}{q(x)}=0$ almost everywhere on $\text{supp }p$. Hence, $p(x)=q(x)$ almost everywhere on $p(x)$.
>    
>    However, as $1=\int_{\text{supp } p} p  \, dx=\int_{\text{supp } p} q  \, dx$, we have that $p=q$ almost everywhere.

^9f110f

---
> [!lemma] Proposition 2 (Convexity)
> Relative entropy is convex, i.e. for $p_{1},p_{2}$ and $q_{1},q_{2}\in\Delta (\mathcal{X})$ and $\lambda\in (0,1)$, $$D(\lambda p_{1}+(1-\lambda)p_{2}\|\lambda q_{1}+(1-\lambda)q_{2})\leq \lambda D(p_{1}\|q_{1})+(1-\lambda)D(p_{2}\|q_{2})$$

^0ed2a9

> [!proof]-
> We have that: 
> $$\begin{align}D(\lambda p_{1}+(1-\lambda)p_{2}\|\lambda q_{1}+(1-\lambda)q_{2})&\leq \sum_{x}^{}(\lambda p_{1}(x)+(1-\lambda)p_{2}(x))\log \frac{\lambda p_{1}(x)+(1-\lambda)p_{2}(x)}{\lambda q_{1}(x)+(1-\lambda)q_{2}(x)}\\&\leq \sum_{ x}^{}\left( \lambda p_{1}(x)\log\frac{p_{1}(x)}{q_{1}(x)} +(1-\lambda)p_{2}(x)\log \frac{p_{2}(x)}{q_{2}(x)}\right)\\&=\lambda D(p_{1}\|q_{1})+(1-\lambda)D(p_{2}\|q_{2}) \end{align}$$where the inequality holds from [[Technical Lemmas|log-sum inequality]].

^ab9003

---
##### Examples
> [!h] Example 1 (Uniform q)
> Let $\mathcal{X}$ be finite and $q\sim \text{Uni}(\mathcal{X})$. Then, 
> 1. $D(p\|q)=\log \left| \mathcal{X} \right|-H(p)$.

^c12de7

> [!proof]-
> We have:
> 1. Notice that: $$D(p\|q)=\sum_{x\in \text{supp }p}^{}p(x)\log (\left| \mathcal{X} \right| \cdot p(x))=\sum_{x\in \text{supp }p}^{}p(x)\log  p(x)+\log \left| \mathcal{X} \right|=\log \left| \mathcal{X} \right| -H(p)$$

^819eb1

---
![[Entropy^]]