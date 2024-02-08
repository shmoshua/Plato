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
> If $x=0$ or $y=0$, the proof is obvious. Otherwise, choose $\alpha\in \mathbb{C}$ s.t. $\left| \alpha \right|=1$ and $\alpha \braket{ x , y }=\left| \braket{ x , y } \right|$. Then, for all $\lambda\in \mathbb{R}$:$$\begin{align}\left\| \lambda x +\alpha y\right\|^2&=\braket{ \lambda x+\alpha y , \lambda x+\alpha y }\\&=\lambda^{2}\|x\|^{2}+2\lambda \left| \braket{ x , y }  \right| +\|y\|^{2} \end{align}$$
---
> [!lemma] Theorem 2
> A normed space $(V,\|\cdot\|)$ is an inner product space if it satisfies the parallelogram law: $$\left\| x-y \right\| ^{2}+\left\| x+y \right\| ^{2}=2(\|x\|^{2}+\left\| y \right\| ^{2})$$

> [!proof]+
> For an inner product space $(V,\braket{ \cdot , \cdot })$, 
> $$\begin{align}\left\| x-y \right\| ^{2} +\left\| x+y \right\| ^{2}&=\braket{ x-y , x-y } +\braket{ x+y , x+y } \\&=\|x\|^{2}-\braket{ x , y } -\braket{ y , x } +\left\| y \right\| ^{2}+\|x\|^{2}+\braket{ x , y } +\braket{ y , x } +\left\| y \right\| ^{2}\\&=2(\|x\|^{2} +\|y\|^{2})\end{align}$$
> Conversely, if a normed space satisfies the parallelogram law, 
> $$$$
---
