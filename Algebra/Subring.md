#Definition #Algebra

> [!definition]
> Let $R$ be a [[Ring|ring]]. A set $S\subseteq R$ is a ***subring*** of $R$, if:
> 1. $(S,+)\leq (R,+)$, i.e. $S$ is an additive subgroup of $R$ and
> 3. $S$ is closed under multiplication.
- **Related Definition**: For a commutative ring $S$, a subring $R\subseteq S$ and $s_{0}\in S$, we define $R[s_{0}]$ as the smallest subring that contains $R$ and $s_{0}$. (However, generally this is not a [[polynomial ring]]).
- **Remark**: The subring need not have the same multiplicative identity as the ring:  e.g
	  - $R:=\mathbb{R}\oplus \mathbb{R}$ and $S:=\mathbb{R}\oplus \{ 0 \}$. Then, the unity of $S$ is $(1,0)$. 
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> $$R[s_{0}]=\{ \tilde{s}\in S:\tilde{s}=a_{0}+a_{1}s_{0}+a_{2}s_{0}^{2}+\dots+a_{n}s_{0}^n\text{ with }n\in \mathbb{N},a_{i}\in R \}$$

> [!proof]-
> By denoting the right set as $X$, 
> 1. $R[s_{0}]\subseteq X$ as $X$ is a subring that contains $R$ and $s_{0}$. 
> 2. $X\subseteq R[s_{0}]$ as a ring is closed under finite addition and multiplication
---
##### Examples
1. $\mathbb{Z}[i]=\{ z\in \mathbb{C}: z=a+bi\text{ for }a,b\in \mathbb{Z} \}$
2. For $\omega=-\frac{1}{2}+i \frac{\sqrt{ 3 }}{2}$, $\mathbb{Z}\left[ \omega\right]=\{ z\in \mathbb{C}: z=a+b\omega,a,b\in \mathbb{Z}\}$
3. $\mathbb{Z}[e]=\{ z\in \mathbb{C}: z=a_{0}+a_{1}e+\dots+a_{n}e^n \text{ for }a_{i}\in \mathbb{Z},n\in \mathbb{N}\}$
---