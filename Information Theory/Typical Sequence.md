#Definition #InformationTheory 

> [!definition]
> Let $\mathcal{X}$ be a finite set and $p\in \Delta(\mathcal{X})$. For $\xi\in \mathcal{X}^n$, 
> 1. $\xi$ is ***of type*** $p$ if $p=\frac{1}{n}\sum_{i=1}^{n}\delta_{\xi_{i}}$.
> 2. $\xi$ is ***$\varepsilon$-strongly typical*** w.r.t. $p$ for $\varepsilon>0$ if: $$\left| \frac{1}{n}\sum_{i=1}^{n}\delta_{\xi_{i}}-p \right| \leq \varepsilon \cdot p$$
> 	The set of $\varepsilon$-strongly typical $n$-length sequences is denoted as $T^{n}_{\varepsilon}(p)\subseteq \mathcal{X}^n$.
> 3. $\xi$ is ***$\varepsilon$-weakly typical*** w.r.t. $p$ for $\varepsilon>0$ if: $$2^{-n(H(p)+\varepsilon)}\leq \prod_{i=1}^{n}p(\xi_{i})\leq 2^{-n(H(p)-\varepsilon)}$$The set of $\varepsilon$-weakly typical $n$-length sequences is denoted as $\mathcal{A}^{n}_{\varepsilon}(p)\subseteq \mathcal{X}^n$.

^a981a4

- **Related definition**: For $k:=k(n)\in \mathbb{N}$, a ***scheme*** is given by a  pairs of maps $(f_{n},\phi_{n})_{n}$ where $f_{n}:\mathcal{X}^n\to \{ 0,1 \}^{k}$ and $\phi_{n}:\{ 0,1 \}^k\to \mathcal{X}^n$. ^331f26
- **Related definition**: Let $\mathcal{X}\times \mathcal{Y}$ be a product of finite sets and $p\in \Delta(\mathcal{X}\times \mathcal{Y})$.  For $(\xi,\eta)\in \mathcal{X}^n\times \mathcal{Y}^n$, $(\xi,\eta)$ is $\varepsilon$-***weakly joint typical*** if:  ^1b4717
	1. $2^{-n(H(p_{XY})+\varepsilon)}\leq \prod_{i=1}^{n}p_{XY}(\xi_{i},\eta_{i})\leq 2^{-n(H(p_{XY})-\varepsilon)}$ and
	2. $\xi\in \mathcal{A}^n_{\varepsilon}(p_{X})\subseteq \mathcal{X}^n$ and 
	3. $\eta\in \mathcal{A}^n_{\varepsilon}(p_{Y})\subseteq \mathcal{Y}^n$.
---
##### Properties
> [!lemma] Theorem 1 (AEP)
> Let $X_{1},\dots,X_{n}$ i.i.d random variables with distribution $p$. Then, for all $\varepsilon>0$: $$\lim_{ n \to \infty } \mathbb{P}((X_{1},\dots,X_{n})\in \mathcal{A}^n_{\varepsilon}(p))=1$$
> Further, it holds that:
> 1. $\left| \mathcal{A}^n_{\varepsilon}(p) \right|\leq 2^{n(H(p)+\varepsilon)}$ and
> 2. for large enough $n$, $\left| \mathcal{A}_{\varepsilon}^n(p) \right|\geq (1-\varepsilon)2^{n(H(p)-\varepsilon)}$

^997b29

> [!proof]-
> Fix $\varepsilon>0$. We have that: $$(X_{1},\dots,X_{n})\in \mathcal{A}^n_{\varepsilon}(p)\iff \left| \frac{1}{n}\sum_{i=1}^{n}\log \frac{1}{p(X_{i})}-H(p) \right| \leq \varepsilon$$where we have that: $$\mathbb{E}\left[ \log \frac{1}{p(X_{i})} \right]=H(p)$$Hence, by the weak law of large numbers, $$\lim_{ n \to \infty } \mathbb{P}((X_{1},\dots,X_{n})\in \mathcal{A}^n_{\varepsilon}(p))=1 $$
> For the rest:
> 1. We have: $$1\geq \mathbb{P}(X\in \mathcal{A}^n_{\varepsilon}(p))=\sum_{\xi\in \mathcal{A}^n_{\varepsilon}(p)}^{}\mathbb{P}(X=\xi)=\sum_{\xi\in \mathcal{A}^n_{\varepsilon}(p)}^{}\prod_{i=1}^{n}p(\xi_{i})\geq 2^{-n(H(p)+\varepsilon)}\cdot \left| \mathcal{A}^n_{\varepsilon} (p)\right| $$
> 2. For $n$ large enough, $$1-\varepsilon\leq \mathbb{P}(X\in \mathcal{A}^n_{\varepsilon}(p))=\sum_{\xi\in \mathcal{A}^n_{\varepsilon}(p)}^{}\prod_{i=1}^{n}p(\xi_{i})\leq 2^{-n(H(p)-\varepsilon)}\cdot \left| \mathcal{A}^n_{\varepsilon} (p)\right| $$

^d52844

---
> [!lemma] Theorem 2 (Almost Lossless Source Coding Theorem)
> Let $p\in \Delta(\mathcal{X})$ and $X_{1},\dots,X_{n}\sim p$ i.i.d. Then, for some $\varepsilon>0$:
> 1. if $\frac{k}{n}>H(p)+\varepsilon$ then there exists a scheme $(f_{n},\phi_{n})_{n}$ s.t. $\lim_{ n \to \infty }\mathbb{P}(\phi(f(X_{1: n}))=X_{1:n})=1$
> 2. if $\frac{k}{n}<H(p)-2\varepsilon$ then for sufficiently large $n$, for any scheme $(f_{n},\phi_{n})_{n}$, $\lim_{ n \to \infty }\mathbb{P}(\phi(f(X_{1: n}))=X_{1:n})=0$.

^93c318

> [!proof]-
> We have that:
> 1. Let $\mathcal{A}^n_{\varepsilon}(p)$ be indexed. Then, we have that $\mathcal{A}^n_{\varepsilon}(p)\subseteq \{ 0,1 \}^k$. We construct $(f_{n},\phi_{n})$, where $f_{n}$ maps $\mathcal{A}_{\varepsilon}^n(p)$ to itself and sends the rest to some error term. 
>    
>    Then, $$\lim_{ n \to \infty }\mathbb{P}(\phi(f(X_{1: n}))=X_{1:n})=\lim_{ n \to \infty } \mathbb{P}(X_{1:n}\in \mathcal{A}^n_{\varepsilon}(p))=1 $$
> 2. Let $k / n< H(p)-2\varepsilon$. Then, $$\begin{align}\mathbb{P}(\phi(f(X_{1: n}))=X_{1:n})&\leq \mathbb{P}(\phi(f(X_{1: n}))=X_{1:n}, X_{1:n}\in \mathcal{A}_{\varepsilon}^n(p))+\mathbb{P}(X_{1:n}\notin \mathcal{A}^n_{\varepsilon}(p))\end{align}$$However, $$\begin{align}\mathbb{P}(\phi(f(X_{1: n}))=X_{1:n}, X_{1:n}\in \mathcal{A}_{\varepsilon}^n(p))&=\sum_{\xi\in \mathcal{A}^n_{\varepsilon}(p),\phi(f(\xi))=\xi}^{}\mathbb{P}(X=\xi)\\&\leq\sum_{\xi\in \mathcal{A}^n_{\varepsilon}(p),\phi(f(\xi))=\xi}^{}2^{-n(H(p)-\varepsilon)}\\&\leq2^{-n(H(p)-\varepsilon)}2^{k}\\&< 2^{-n(H(p)-\varepsilon)}2^{n(H(p)-2\varepsilon)}\\&=2^{-n\varepsilon}\end{align}$$Hence, $\lim_{ n \to \infty }\mathbb{P}(\phi(f(X_{1: n}))=X_{1:n}, X_{1:n}\in \mathcal{A}_{\varepsilon}^n(p))=0$. As $\lim_{ n \to \infty }\mathbb{P}(X\notin \mathcal{A}^n_{\varepsilon}(p))=0$ by AEP, we have the statement.

^067ee1

---
> [!lemma] Theorem 3 (AEP for joint typicality)
> Let $(X_{1},Y_{1}),\dots,(X_{n},Y_{n})$ be i.i.d random variables with distribution $p_{XY}$. Then, for all $\varepsilon> 0$, $$\lim_{ n \to \infty } \mathbb{P}((X_{1:n},Y_{1:n})\in \mathcal{A}^n_{\varepsilon}(p_{XY}))=1$$
> 1. ${\left| \mathcal{A}^n_{\varepsilon}(p_{XY}) \right|}\leq 2^{n(H(p_{XY})+\varepsilon)}$

^012426

> [!proof]-
> Analogous to Theorem 1. 

^d76625

---
> [!lemma] Proposition 4 (Joint Typicality and Independent RVs)
> Let $(X_{1},Y_{1}),\dots,(X_{n},Y_{n})$ be i.i.d random variables with distribution $p_{X}p_{Y}$. Then, $$\mathbb{P}((X_{1:n},Y_{1:n})\in \mathcal{A}^n_{\varepsilon}(p_{XY}))\leq 2^{-n(I(X;Y)-3\varepsilon)}$$

^3cf8af

> [!proof]-
> We have that: $$\begin{align}\mathbb{P}((X_{1:n},Y_{1:n})\in \mathcal{A}^n_{\varepsilon}(p_{XY}))&=\sum_{(\xi,\eta)\in \mathcal{A}^n_{\varepsilon}(p_{XY})}^{}\mathbb{P}(X_{1:n}=\xi,Y_{1:n}=\eta)\\&=\sum_{(\xi,\eta)\in \mathcal{A}^n_{\varepsilon}(p_{XY})}^{}\mathbb{P}(X_{1:n}=\xi) \mathbb{P}(Y_{1:n}=\eta)\\&\leq \sum_{(\xi,\eta)\in \mathcal{A}^n_{\varepsilon}(p_{XY})}^{} 2^{-n(H(p_{X})+H(p_{Y})-2\varepsilon)}\\&\leq2^{-n(H(p_{X})+H(p_{Y})-H(p_{XY})-3\varepsilon)}=2^{-n(I(X;Y)-3\varepsilon)}\end{align}$$

^d9ff78

---
> [!lemma] Lemma 5
> Let $\mathcal{X}$ be finite and $p\in \Delta(\mathcal{X})$. Let $g:\mathcal{X}\to \mathbb{R}_{\geq 0}$. Then, 
> 1. for $\xi\in T^n_{\varepsilon}(p)$ then: $$\frac{1}{n}\sum_{i=1}^{n}g(\xi_{i})\leq(1+\varepsilon)\mathbb{E}_{X\sim p}[g(X)]$$

> [!proof]-
> We have that by strong typicality: $$\frac{1}{n}\sum_{i=1}^{n}g(\xi_{i})=\sum_{a\in \mathcal{X}}^{} \frac{1}{n}N(a|\xi)g(a)\leq \sum_{a\in \mathcal{X}}^{}(1+\varepsilon)p(a)g(a)=(1+\varepsilon)\mathbb{E}[g(X)]$$
---
