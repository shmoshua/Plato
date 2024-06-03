#Definition #LieGroups 

> [!definition]
> For a [[Lie group]] $G$, a ***representation*** on a $\mathbb{K}$-vector space $V$ is a smooth [[group representation]], i.e. it is a Lie group homomorphism $\pi:G\to \text{GL}(V)$.
- **Remark**: By [[Exponential Map|Proposition 2]], $\pi \circ \exp= \exp \circ\  d_{e}\pi$.
- **Related definition**: for a vector subspace $W\subseteq V$ and $v\in V$,
	1. $\text{Stab}(W):=\{ g\in G:\pi(g)W\subseteq W \}$.
	2. $\text{Stab}(v):=\{ g\in G:\pi(g)v=v \}$, the [[Orbit and Stablizer|stabilizer]] of $\pi$.
- **Remark**: Both stabilizers are closed subgroups of $G$ and by [[Lie Group|Closed Subgroup Theorem]] Lie groups.
---
##### Properties
> [!lemma] Proposition 1
> Let $W$ be a closed subspace of $V$ and $v\in V$. Then,
> 1. $\mathfrak{stab}(W)=\{x\in \mathfrak{g} :d_{e}\pi(x)W\subseteq W\}$
> 2. $\mathfrak{stab}(v)=\{ x\in \mathfrak{g}:d_{e}\pi(x)v=0 \}$

> [!proof]-
> We have:
> 1. By [[Lie Group|Cartan's Theorem Corollary]], $$\begin{align}\mathfrak{stab}(W)&=\{ x\in \mathfrak{g}: \exp(tx)\in  \text{Stab}(W),\forall t\in \mathbb{R} \}\\&=\{ x\in \mathfrak{g}: \pi(\exp(tx))W\subseteq W,\forall t\in \mathbb{R} \}\\&=\{ x\in \mathfrak{g}: \exp(t\cdot d_{e}\pi(x))W\subseteq W,\forall t\in \mathbb{R} \}\end{align}$$Then, for $A\in \mathfrak{gl}(V)$, $\exp(tA)W\subseteq W$ for all $t\in \mathbb{R}$ if and only if $A(W)\subseteq W$. Indeed, for any $v\in W$, $$Av=\lim_{ t \to 0 } \frac{\exp(tA)v-v}{t}\in W$$Similarly, the converse follows from the exponential series definition.
> 2. By [[Lie Group|Cartan's Theorem Corollary]], $$\begin{align}\mathfrak{stab}(v)&=\{ x\in \mathfrak{g}: \exp(tx)\in  \text{Stab}(v),\forall t\in \mathbb{R} \}\\&=\{ x\in \mathfrak{g}: \pi(\exp(tx))v= v,\forall t\in \mathbb{R} \}\\&=\{ x\in \mathfrak{g}: \exp(t\cdot d_{e}\pi(x))v=v,\forall t\in \mathbb{R} \}\end{align}$$Then, for $A\in \mathfrak{gl}(V)$, if $\exp(tA)v=v$ for all $t\in \mathbb{R}$, $Av=0$ from above and if $Av=0$, then: $$\exp(tA)v=\sum_{n=0}^{\infty}\frac{A^nt^n}{n!}=v$$This proves the statement.
> 
---
![[Lie Algebra Representation#^c6ed8f]]