#Definition #InformationTheory 

> [!definition]
> For a finite set $\mathcal{X}$, a ***code*** is a map $C:\mathcal{X}\to \{ 0,1 \}^{+}$.
- **Related definition**: the length is a function $L:\mathcal{\mathcal{X}}\to \mathbb{N}$ given by $L(x)=\left| C(x) \right|$.
- **Related definition**: a code $C$ is ***non-singular*** if $C$ is injective.
- **Related definition**: an ***extension*** of the code $C$ is a map $$\mathcal{X}^+\to \{ 0,1 \}^+,\quad x_{1}\dots x_{n}\mapsto C(x_{1})\dots C(x_{n})$$
	A code $C$ is ***uniquely decodable*** if its extension is non-singular.
- **Related definition**: A code $C$ is ***prefix-free*** or ***instantaneous*** if no codeword is the prefix of another. 

---
##### Properties
> [!lemma] Proposition 1
> For any prefix-free code $C:\mathcal{X}\to \{ 0,1 \}^+$,
> 1. $C$ is uniquely decodable.
> 2. $C$ is equivalent to a binary tree where $\mathcal{X}$ are nodes.

> [!proof]-
> Assume $C$ is not uniquely decodable. Then, there exists $x_{1}\dots x_{n}$, $y_{1},\dots,y_{m}\in \mathcal{X}$ s.t. $$C(x_{1})\dots C(x_{m})=C(y_{1})\dots C(y_{m})$$Wlog we may assume that $x_{1}\neq y_{1}$ and $L(x_{1})\leq L(y_{1})$. Then, $C(x_{1})$ is clearly a prefix of $C(y_{1})$ and $C$ is not prefix-free.
---
> [!lemma] Theorem 2 (Kraft's inequality)
> We have that:
> 1. For a uniquely decodable code $C$, $\sum_{x\in \mathcal{X}}^{}2^{-L(x)}\leq 1$.
> 2. For positive integers $\ell_{1},\dots,\ell_{n}$ s.t. $\sum_{i=1}^{m}2^{-\ell_{i}}\leq 1$, there exists a prefix-free code with $\ell_{1},\dots,\ell_{n}$ as lengths. 
---
> [!lemma] Theorem 3 ()
$$\begin{align}\min\quad &\sum_{i=1}^{n}p_{i}\ell_{i}\\\text{subject to}\quad&\sum_{i=1}^{n}2^{-\ell_{i}}\leq 1\end{align}$$

Then, $$\begin{align}0&=\frac{ \partial  }{ \partial \ell_{i} } \sum_{i=1}^{n}p_i\ell_{i}+\lambda \left( \sum_{i=1}^{n}2^{-\ell_{i}} -1\right)\\&=p_{i}-\lambda \ln 2 \cdot 2^{-\ell_{i}} \end{align}$$Hence, $\ell_{i}=-\log_{2}(p_{i} / \lambda \ln 2)$ and by setting $\ell ^{*}_{i}=\log_{2}(1/ p_{i})$

---
$$\begin{align}L-H(X)=-\sum_{i}^{}p_{i}\log_{2}2^{-\ell_{i}}+\sum_{i}^{}p_{i}\log_{2}p_{i}=\sum_{i}^{}p_{i}\log \frac{p_{i}}{2^{-\ell_{i}}}\geq 0\end{align}$$

---

##### Examples
> [!h] Example 1 (Not Prefix-Free but Uniquely Decodable Code)
> Consider $\mathcal{X}:=\{ a,b,c,d \}$ where: $$\begin{align}a&\mapsto 10\\b&\mapsto 00\\c&\mapsto 11\\b&\mapsto 110\end{align}$$
---
