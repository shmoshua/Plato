#Definition #InformationTheory 

> [!definition]
> Let $\mathcal{X}$ be a finite set and $p\in \Delta(\mathcal{X})$. For $\xi\in \mathcal{X}^n$, 
> 1. $\xi$ is ***of type*** $p$ if $p=\frac{1}{n}\sum_{i=1}^{n}\delta_{\xi_{i}}$.
> 2. $\xi$ is ***$\varepsilon$-strongly typical*** w.r.t. $p$ for $\varepsilon>0$ if: $$\left| \frac{1}{n}\sum_{i=1}^{n}\delta_{\xi_{i}}-p \right| \leq \varepsilon \cdot p$$
> 	The set of $\varepsilon$-strongly typical $n$-length sequences is denoted as $T^{n}_{\varepsilon}(p)\subseteq \mathcal{X}^n$.
> 3. $\xi$ is ***$\varepsilon$-weakly typical*** w.r.t. $p$ for $\varepsilon>0$ if: $$2^{-n(H(p)+\varepsilon)}\leq \prod_{i=1}^{n}p(\xi_{i})\leq 2^{-n(H(p)-\varepsilon)}$$The set of $\varepsilon$-weakly typical $n$-length sequences is denoted as $\mathcal{A}^{n}_{\varepsilon}(p)\subseteq \mathcal{X}^n$.
---
##### Properties
> [!lemma] Theorem 1 (AEP)
> Let $X_{1},\dots,X_{n}$ i.i.d random variables with distribution $p$. Then, for all $\varepsilon>0$ $$\lim_{ n \to \infty } \mathbb{P}((X_{1},\dots,X_{n})\in \mathcal{A}^n_{\varepsilon}(p))=1$$
> Further, it holds that:
> 1. $\left| \mathcal{A}^n_{\varepsilon}(p) \right|\leq 2^{n(H(p)+\varepsilon)}$ and
> 2. for large enough $n$, $\left| \mathcal{A}_{\varepsilon}^n(p) \right|\geq (1-\varepsilon)2^{n(H(p)-\varepsilon)}$

> [!proof]+
> Fix $\varepsilon>0$. We have that: $$(X_{1},\dots,X_{n})\in \mathcal{A}^n_{\varepsilon}(p)\iff \left| \frac{1}{n}\sum_{i=1}^{n}\log \frac{1}{p(X_{i})}-H(p) \right| \leq \varepsilon$$where we have that: $$\mathbb{E}\left[ \log \frac{1}{p(X_{i})} \right]=H(p)$$Hence, by the weak law of large numbers, $$\lim_{ n \to \infty } \mathbb{P}((X_{1},\dots,X_{n})\in \mathcal{A}^n_{\varepsilon}(p))=1 $$
> For the rest:
> 1. We have: $$1\geq \mathbb{P}(X\in \mathcal{A}^n_{\varepsilon}(p))=\sum_{\xi\in \mathcal{A}^n_{\varepsilon}(p)}^{}\mathbb{P}(X=\xi)=\sum_{\xi\in \mathcal{A}^n_{\varepsilon}(p)}^{}\prod_{i=1}^{n}p(\xi_{i})\geq 2^{-n(H(p)+\varepsilon)}\cdot \left| \mathcal{A}^n_{\varepsilon} (p)\right| $$
> 2. For $n$ large enough, $$1-\varepsilon\leq \mathbb{P}(X\in \mathcal{A}^n_{\varepsilon}(p))=\sum_{\xi\in \mathcal{A}^n_{\varepsilon}(p)}^{}\prod_{i=1}^{n}p(\xi_{i})\leq 2^{-n(H(p)-\varepsilon)}\cdot \left| \mathcal{A}^n_{\varepsilon} (p)\right| $$
---
> [!lemma] Theorem 2
> 