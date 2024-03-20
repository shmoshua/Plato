#Definition #Analysis 
> [!definition]
> For a $\mathbb{K}$-[[Vector Space|vector space]] $V$ with an ***inner product*** on $V$ is a map: $\braket{ \cdot , \cdot }:V\times V\to\mathbb{K}$ s.t. 
> 1. $u\mapsto \braket{ u , v }$, for all $v\in V$ is $\mathbb{K}$-linear.
> 2. $\braket{ u , v }= \overline{\braket{ v , u }}$ for all $u,v\in V$.
> 3. $\braket{ u , u }\geq 0$ with equality if and only if $u=0$.
> 
> Then, $(V,\braket{ \cdot , \cdot })$ is called an ***inner product space***.

- **Remark**: 2 implies that for all $u\in V$, $\braket{ u , u }\in \mathbb{R}$. 

- **Related definition**: If $(V,\|\cdot\|)$ is [[Banach Space|Banach]], $V$ is a [[Hilbert space]].

---
##### Properties
> [!lemma] Theorem 1 (Cauchy-Schwarz)
> For an inner product space $V$ and all $x,y\in V$: $$\left| \braket{ x , y } \right|\leq \|x\|\cdot\|y\|$$

> [!proof]-
> If $x=0$ or $y=0$, the proof is obvious. Otherwise, choose $\alpha\in \mathbb{C}$ s.t. $\left| \alpha \right|=1$ and $\alpha \braket{ x , y }=-\left| \braket{ x , y } \right|$. Then, for all $\lambda\in \mathbb{R}$:$$\begin{align}0\leq\left\| \lambda x +\alpha y\right\|^2&=\braket{ \lambda x+\alpha y , \lambda x+\alpha y }\\&=\lambda^{2}\|x\|^{2}+\braket{ \lambda x , \alpha y }+\braket{ \alpha y , \lambda x } +\left\| y \right\| ^{2}\\&=\lambda^{2}\|x\|^{2}+\lambda \braket{ x , \alpha y }+\lambda \braket{ \alpha y , x } +\left\| y \right\| ^{2} \\&=\lambda^{2}\|x\|^{2}+2\lambda \left| \braket{ x , y }  \right| +\|y\|^{2}\end{align}$$Therefore, $\lambda^{2}\|x\|^{2}+\|y\|^{2}\geq -2\lambda \left| \braket{ x , y } \right|$. Notice that $f:\lambda\mapsto \lambda^{2}\|x\|^{2}+2\lambda \left| \braket{ x , y }  \right| +\|y\|^{2}$ has its minimum at $\lambda= -\frac{\left| \braket{ x , y } \right|}{\|x\|^{2}}$. Then, $$f(\lambda)=-\frac{\left| \braket{ x , y }  \right| ^{2}}{\|x\|^{2}}+\|y\|^{2}\geq 0$$This proves the statement.
---
> [!lemma] Theorem 2 (Inner Product Space is Normed)
> An inner product space $V$ is a [[normed space]] with $\|v\|^{2}=\braket{ v , v }$ for all $v\in V$.

> [!proof]-
> We have that: 
> 1. **Absolute homogeneity**:$$\left\| \lambda v \right\| ^{2}=\braket{ \lambda v , \lambda v } =\left| \lambda \right| ^{2}\braket{ v , v } =\left| \lambda \right| ^{2}\|v\|^{2}$$
> 2. **Triangle inequality**:$$\begin{align}\|v+w\|^{2}&=\braket{ v+w , v+w } \\&=\braket{ v , v } +\braket{ v , w } +\braket{ w , v } +\braket{ w , w } \\&=\|v\|^{2}+2\text{Re}\braket{ v , w } +\|w\|^{2}\\&\leq\|v\|^{2}+2\left| \braket{ v , w }  \right|  +\|w\|^{2}\\&\leq(\|v\|+\|w\|)^{2}\end{align}$$
> 3. **Positive definiteness**:$$\|v\|^{2}=\braket{ v , v } =0 \iff v=0$$
---
> [!lemma] Theorem 3 (Parallelogram Law)
> A [[normed space]] $V$ is an inner product space if it satisfies the parallelogram law: $$\left\| x-y \right\| ^{2}+\left\| x+y \right\| ^{2}=2(\|x\|^{2}+\left\| y \right\| ^{2})$$

> [!proof]- Proof (Incomplete)
> For an inner product space $V$, 
> $$\begin{align}\left\| x-y \right\| ^{2} +\left\| x+y \right\| ^{2}&=\braket{ x-y , x-y } +\braket{ x+y , x+y } \\&=\|x\|^{2}-\braket{ x , y } -\braket{ y , x } +\left\| y \right\| ^{2}+\|x\|^{2}+\braket{ x , y } +\braket{ y , x } +\left\| y \right\| ^{2}\\&=2(\|x\|^{2} +\|y\|^{2})\end{align}$$
> Conversely, if a normed space satisfies the parallelogram law, 
> $$$$
- **Corollary (Pythagoras)**: If $\braket{ x,y  }=0$, then $\|x-y\|=\|x+y\|$ and $\|x+y\|^{2}=\|x\|^{2}+\|y\|^{2}$.
---
> [!lemma] Proposition 3 (Polarization Identities)
> Let $V$ be a $\mathbb{C}$-inner product space. Then, for all $x,y\in V:$$$\braket{ x,y  }=\frac{1}{4}\left( \left\| x+y \right\| ^{2}+i \left\| x+iy \right\| ^{2}-\left\| x-y \right\| ^{2}-i \left\| x-iy \right\| ^{2} \right)  $$If $V$ is a $\mathbb{R}$-inner product  space, then: $$\braket{ x , y } =\frac{1}{4}\left( \left\| x+y \right\| ^{2}-\left\| x-y \right\| ^{2} \right) $$

> [!proof]-
> We have that: $$\begin{align}\left\| x \pm y \right\| ^{2}&=\|x\|^{2}+\|y\|^{2}\pm 2 \text{Re}\braket{ x , y } \\\left\| x\pm iy \right\| ^{2}&=\|x\|^{2}+\|y\|^{2}\pm 2\text{Im} \braket{ x , y } \end{align}$$Therefore, $$\begin{align}\left\| x+y \right\| ^{2}+i \left\| x+iy \right\| ^{2}-\left\| x-y \right\| ^{2}- i \left\| x-iy \right\| ^{2}&=4\text{Re}\braket{ x , y } +4i\text{Im}\braket{ x ,y  }=4\braket{ x , y }  \end{align}$$
---
> [!lemma] Proposition 4 (Ptolemy's inequality)
> For all $x,y,z\in V$, it holds that: $$\left\| x-y \right\|\|z\|+\|y-z\|\|x\| \geq \|x-z\|\|y\|$$

> [!proof]-
> The proof is trivial if one of $x,y,z$ is zero. Therefore, assume that none are. Consider $$x'=\frac{x}{\|x\|^{2}},\quad y'=\frac{y}{\|y\|^{2}},\quad z'=\frac{z}{\|z\|^{2}}$$Then, $$\left\| x'-y' \right\| ^{2}=\left\| x' \right\| ^{2}+\left\| y' \right\| ^{2}-2\text{Re}\braket{ x' , y' }=\frac{1}{\|x\|^{2}}+\frac{1}{\|y\|^{2}}-\frac{2\text{Re}\braket{ x , y } }{\|x\|^{2}\|y\|^{2}} =\frac{\left\| x-y \right\| ^{2}}{\|x\|^{2}\|y\|^{2}}$$Then, $$\frac{\| x-z \|}{\|x\|\|z\|} \leq \frac{\left\| x-y \right\| }{\|x\|\|y\|}+\frac{\left\| y-z \right\|} {\|y\|\|z\|}$$
---
> [!lemma] Lemma 5 (Inner Product is continuous)
> Let $V$ be an inner product space. Then, the inner product $\braket{ \cdot , \cdot }:V\times V\to \mathbb{K}$ is continuous.

> [!proof]-
> We know that $\braket{ x , \cdot },\braket{ \cdot , y }\in V^{*}$. Suppose now $(x_{n},y_{n})\to (x,y)$. Then, $$\begin{align}\left| \braket{ x_{n} , y_{n} } -\braket{ x , y }  \right| &\leq \left| \braket{ x_{n} , y_{n} } -\braket{ x , y_{n} }  \right|+\left| \braket{ x , y_{n} } -\braket{ x , y }  \right| \\&\leq\left\| y_{n} \right\| \left\| x_{n}-x \right\|+\|x\|\left\| y_{n}-y \right\|  \\&\leq 2\left\| x_{n}-x \right\| \left\| y_{0} \right\|  +\|x\|\left\| y_{n}-y \right\| \end{align}$$for $n$ large enough. This proves the statement.
---
##### Examples

> [!h] Example 1
> Following are inner product spaces:
> 1. $\mathbb{R}^n,\mathbb{C}^n$ with the standard inner product.
> 2. any subspace of an inner product space.
---
> [!h] Example 2 (L2 and l2 space)
> For a measure space $(X,\mathcal{F},\mu)$,
> 1. [[Lp Space|$L^2(X)$]] is an inner product space with $\braket{ f , g }:=\int_{X}^{} f\overline{g} \, d\mu$.
> 2. [[Sequence Space over Natural Numbers|$\ell^2(\mathbb{N})$]] is an inner product space with $\braket{ f , g }:=\sum_{n=1}^{\infty}f(n)\overline{g(n)}$.

> [!proof]-
> We have that: 
> 1. The linearly follows from the linearly of multiplication and integral. Then, we have: $$\begin{align}\overline{\braket{ g , f } }&=\int_{X}^{} \overline{g \overline{f}} \, d\mu=\int_{X}^{} f\overline{g} \, d\mu=\braket{ f , g }   \end{align} $$Lastly, if $\braket{ f , f }=0$, then $\|f\|_{2}=0$, which happens if and only if $f=0$ $\mu$-a.e.
> 2. The linearly follows from linearity of addition. Further, $$\overline{\braket{ g , f } }=\sum_{n=1}^{\infty}\overline{g(n)\overline{f(n)}}=\sum_{n=1}^{\infty}f(n)\overline{g(n)}=\braket{ f , g } $$Lastly, if $\braket{ f , f }=0$, then $\sum_{n=1}^{\infty}\left| f(n) \right|^{2}=0$. This is equivalent to $\left| f(n) \right|=0$ for all $n\in \mathbb{N}$.
---
> [!h] Example 2
> $C([0,1],\|\cdot\|_{2})$  is an inner product space.
---

