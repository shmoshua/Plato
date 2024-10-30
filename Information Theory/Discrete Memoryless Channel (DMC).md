#Definition #InformationTheory 

> [!definition]
> Let $\mathcal{X}$ and $\mathcal{Y}$ be finite sets. A ***discrete memoryless channel (DMC)*** from $\mathcal{X}$ to $\mathcal{Y}$ is a $\mathcal{X}\times \mathcal{Y}$[[Markov Chain|transition matrix]] $W$ where 
> 1. for every $x\in \mathcal{X}$, $\sum_{y\in \mathcal{Y}}^{}W_{xy}=1$
- **Related definition**: A rate $R$ is ***achievable*** on a DMC $W$ if for any block length $n$ and $\mathcal{M}_{n}:=\{ 1,\dots,2^{nR} \}$ there exists $f:\mathcal{M}_{n}\to \mathcal{X}^n$ and $\phi:\mathcal{Y}^n\to \mathcal{M}_{n}$ s.t. $$\lim_{ n \to \infty } \max_{m\in \mathcal{M}_{n}}\sum_{\begin{subarray}{c}y_{1:n}\in \mathcal{Y}^n\\ \phi(y_{1:n})\neq m\end{subarray}}\prod_{i=1}^{n}W_{f(m)_{i},y_{i}}=0$$ 
- **Related definition**: The ***capacity*** of a DMC is $C:=\sup\{ R:R\text{ is achievable} \}$.
---
##### Properties
> [!lemma] Theorem 1 (Data Processing Inequality for Relative Entropy)
> Let $p,q$ be probability measures on $\mathcal{X}$. 
> $$D(p\|q)\geq D(pW\|qW)$$

> [!proof]-
> We have: $$\begin{align}D(pW\|qW)&=\sum_{y\in \mathcal{Y}}^{}(pW)_{y}\log \frac{(pW)_{y}}{(qW)_{y}}\\&=\sum_{y\in \mathcal{Y}}^{}\left( \sum_{x\in \mathcal{X}}^{}p_{x}W_{x,y} \right) \log \frac{\sum_{x}^{}p_{x}W_{x,y}}{\sum_{x}q_{x}W_{x,y}}\\&\leq\sum_{y\in \mathcal{Y}}^{}\sum_{x\in \mathcal{X}}^{}p_{x}W_{x,y}  \log \frac{p_{x}W_{x,y}}{q_{x}W_{x,y}}\\&=\sum_{x\in \mathcal{X}}^{}\sum_{y\in \mathcal{Y}}^{}p_{x}W_{x,y}  \log \frac{p_{x}}{q_{x}}\\&=\sum_{x\in \mathcal{X}}^{}p_{x}  \log \frac{p_{x}}{q_{x}}\\&=D(p\|q)\end{align}$$
---
> [!lemma] Theorem 2
> We have that:
> 1. for any $W$, $q\mapsto I(q;W)$ is a concave function.
> 2. for any $q$, $W\mapsto I(q;W)$ is a convex function.

> [!proof]-
> We have that:
> 1. $I(q;W)=H(q)-H(q|W)$
---
> [!lemma] Theorem 3 (Shannon)
> For a DMC $W$, we have that:
> 1. $C=\max_{q \text{ pmf on }\mathcal{X}}I(q,W)$.
---
> [!lemma] Proposition 4
> For $\mathcal{X},\mathcal{Y}$ and a DMC $W$ from $\mathcal{X}$ to $\mathcal{Y}$, let $W'$ be another DMC from $\mathcal X\times \mathcal{X}$ to $\mathcal{Y}\times \mathcal{Y}$ s.t. $$W'_{(x_{1},x_{2}),(y_{1},y_{2})}=W_{x_{1},y_{1}}W_{x_{2},y_{2}}$$
> Then, 
> 1. a rate $R$ is achievable on $W$ if and only if $2R$ is achievable on $W'$.

> [!proof]-
> We have:
> 1. Assume that $R$ is achievable on $W$. Let $f'_{n}:=f_{2n}$ and $\phi'_{n}:=\phi_{2n}$. Then, for any $m\in \mathcal{M}_{2n}:=\{ 0,1,\dots,2^{2nR} \}$, $$\lambda_{m}:=\sum_{\begin{subarray}{c}y_{1:2n}\in \mathcal{Y}^{2n}\\ \phi_{2n}(y_{1:2n})\neq m\end{subarray}}\prod_{i=1}^{n}W_{f_{2n}(m)_{2i-1,2i},y_{2i-1,2i}}=\sum_{\begin{subarray}{c}y_{1:2n}\in \mathcal{Y}^{2n}\\ \phi_{2n}(y_{1:2n})\neq m\end{subarray}}\prod_{i=1}^{2n}W_{f_{2n}(m)_{i},y_{i}}$$ Therefore, $\lim_{ n \to \infty }\max_{m\in \mathcal{M}_{2n}}\lambda_{m}=0$ and $2R$ is achievable on $W'$.
> 2. Analogous.
---
##### Examples
> [!h] Example 1 (Binary Symmetric Channel)
> The ***binary symmetric channel*** for $\varepsilon$, $\text{BSC}(\varepsilon)$ is given as: $$W:=\begin{bmatrix}1-\varepsilon&\varepsilon\\\varepsilon&1-\varepsilon\end{bmatrix}$$
---
> [!h] Example 2 (Z-channel)
> For $\mathcal{X}=\mathcal{Y}=\{ 0,1 \}$, the ***$Z$-channel*** is given as: $$W:=\begin{bmatrix}1&0\\ \frac{1}{2}& \frac{1}{2}\end{bmatrix}$$

> [!proof]+
> Let $p=(\varepsilon,1-\varepsilon)$. We have that: $$H(Y|X=0)=$$
> 
> We have that: $$\begin{align}I(p,Q)&=I(X;Y)=H(X)-H(Y|X)\\&=-\varepsilon \log \varepsilon-(1-\varepsilon)\log(1-\varepsilon)\end{align}$$