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

> [!proof]+
> We have that:
> 1. Notice that: $$\begin{align}-D(p\|q)&=-\mathbb{E}_{p}[\log p / q]=\mathbb{E}_{p}[\log q / p]\leq \log \mathbb{E}_{p}[q / p]=\log\end{align}$$
---

