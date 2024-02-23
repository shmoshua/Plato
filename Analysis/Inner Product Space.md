#Definition #Analysis 
> [!definition]
> For a $\mathbb{K}$-vector space $V$ with an [[Inner Product of a Vector Space|inner product]]:$$\braket{ \cdot  , \cdot  } :V\times V \to \mathbb{K}$$
> is called an ***inner product space*** $(V,\braket{ \cdot , \cdot })$. 

- **Remark**: $\|\cdot \|:V \to \mathbb{K}, x \mapsto \sqrt{ \braket{ x , x } }$ defines a [[Norm|norm]] on $V$.
- **Related definition**: If $(V,\|\cdot\|)$ is [[Banach Space|Banach]], $V$ is a [[Hilbert space]].

---
##### Properties
> [!lemma] Theorem 1 (Cauchy-Schwarz)
> For all $x,y\in V$: $\left| \braket{ x , y } \right|\leq \|x\|\cdot\|y\|$

> [!proof]-
> If $x=0$ or $y=0$, the proof is obvious. Otherwise, choose $\alpha\in \mathbb{C}$ s.t. $\left| \alpha \right|=1$ and $\alpha \braket{ x , y }=-\left| \braket{ x , y } \right|$. Then, for all $\lambda\in \mathbb{R}$:$$\begin{align}\left\| \lambda x +\alpha y\right\|^2&=\braket{ \lambda x+\alpha y , \lambda x+\alpha y }\\&=\lambda^{2}\|x\|^{2}+\braket{ \lambda x , \alpha y }+\braket{ \alpha y , \lambda x } +\left\| y \right\| ^{2}\\&=\lambda^{2}\|x\|^{2}+\lambda \braket{ x , \alpha y }+\lambda \braket{ \alpha y , x } +\left\| y \right\| ^{2} \\&=\lambda^{2}\|x\|^{2}+2\lambda \left| \braket{ x , y }  \right| +\|y\|^{2} \geq 0\end{align}$$Therefore, $\lambda^{2}\|x\|^{2}+\|y\|^{2}\geq -2\lambda \left| \braket{ x , y } \right|$
---
> [!lemma] Theorem 2
> A normed space $(V,\|\cdot\|)$ is an inner product space if it satisfies the parallelogram law: $$\left\| x-y \right\| ^{2}+\left\| x+y \right\| ^{2}=2(\|x\|^{2}+\left\| y \right\| ^{2})$$

> [!proof]+
> For an inner product space $(V,\braket{ \cdot , \cdot })$, 
> $$\begin{align}\left\| x-y \right\| ^{2} +\left\| x+y \right\| ^{2}&=\braket{ x-y , x-y } +\braket{ x+y , x+y } \\&=\|x\|^{2}-\braket{ x , y } -\braket{ y , x } +\left\| y \right\| ^{2}+\|x\|^{2}+\braket{ x , y } +\braket{ y , x } +\left\| y \right\| ^{2}\\&=2(\|x\|^{2} +\|y\|^{2})\end{align}$$
> Conversely, if a normed space satisfies the parallelogram law, 
> $$$$
---
> [!lemma] Proposition 3 (Polarization Identities)
> Let $V$ be a $\mathbb{C}$-vector space. Then, for all $x,y\in V:$$$\braket{ x,y  }=\frac{1}{4}\left( \left\| x+y \right\| ^{2}+i \left\| x+iy \right\| ^{2}-\left\| x-y \right\| ^{2}-i \left\| x-iy \right\| ^{2} \right)  $$If $V$ is a $\mathbb{R}$-vector space, then: $$\braket{ x , y } =\frac{1}{4}\left( \left\| x+y \right\| ^{2}-\left\| x-y \right\| ^{2} \right) $$

> [!proof]-
> We have that: $$\begin{align}\left\| x \pm y \right\| ^{2}&=\|x\|^{2}+\|y\|^{2}\pm 2 \text{Re}\braket{ x , y } \\\left\| x\pm iy \right\| ^{2}&=\|x\|^{2}+\|y\|^{2}\mp 2i\text{Im} \braket{ x , y } \end{align}$$
---
> [!lemma] Proposition 4 (Ptolemy's inequality)
> For all $x,y,z\in V$, it holds that: $$\left\| x-y \right\|\|z\|+\|y-z\|\|x\| \geq \|x-z\|\|y\|$$

> [!proof]-
> The proof is trivial if one of $x,y,z$ is zero. Therefore, assume that none are. Consider $$x'=\frac{x}{\|x\|^{2}},\quad y'=\frac{y}{\|y\|^{2}},\quad z'=\frac{z}{\|z\|^{2}}$$Then, $$\left\| x'-y' \right\| ^{2}=\left\| x' \right\| ^{2}+\left\| y' \right\| ^{2}-2\text{Re}\braket{ x' , y' }=\frac{1}{\|x\|^{2}}+\frac{1}{\|y\|^{2}}-\frac{2\text{Re}\braket{ x , y } }{\|x\|^{2}\|y\|^{2}} =\frac{\left\| x-y \right\| ^{2}}{\|x\|^{2}\|y\|^{2}}$$Then, $$\frac{\| x-z \|}{\|x\|\|z\|} \leq \frac{\left\| x-y \right\| }{\|x\|\|y\|}+\frac{\left\| y-z \right\|} {\|y\|\|z\|}$$
---
> [!lemma] Lemma 5 (Inner Product is continuous)
> Let $V$ be an inner product space. Then, the inner product $\braket{ \cdot , \cdot }:V\times V\to \mathbb{K}$ is continuous.
---
##### Examples
> [!h] Example 1
> For a measure space $(X,\mathcal{F},\mu)$,
> 1. $L^2(X)$ is an inner product space.
> 2. $\ell^2(\mathbb{N})$ is an inner product space.

> [!proof]+
---
> [!h] Example 2
> $C([0,1],\|\cdot\|_{2})$  is an inner product space.
---

