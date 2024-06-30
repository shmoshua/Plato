#Definition #Algebra 
> [!definition]
> The ***quaternions*** is a vector space $\mathbb{R}^4$ with basis $\{ 1,i,j,k \}$ s.t. 
> 1. $i^{2}=j^{2}=k^{2}=-1$
> 2. $ij=-ji=k$
> 3. $jk=-kj=i$
> 4. $ki=-ik=j$
---
##### Properties
> [!lemma] Proposition 1
> Let $u=(a,b,c,d)$
> 1. $u\overline{u}=\|u\|^{2}=u\overline{u}$ for $\overline{u}:=(a,-b,-c,-d)$.
> 2. for every $u\neq 0$, $u^{-1}=\overline{u} / \|u\|$.
> 3. $\|uv\|=\|u\|\|v\|$

> [!proof]-
> We have:
> 1. for $u\in Q$, $$\begin{align}u\overline{u}&=(a+bi+cj+dk)(a-bi-cj-dk)\\&=a^{2}-abi-acj-adk+abi+b ^{2}-bck+bdj+acj+bck+c^{2}-cdi+adk-bdj+cdi+d^{2}\\&=a^{2}+b ^{2}+c^{2}+d^{2}\end{align}$$
> 2. From 1.
> 3. We have: $$\|uv\|^{2}=(uv)(\overline{uv})=u\cdot v\cdot \overline{v}\cdot \overline{u}=\|v\|^{2}\cdot u\overline{u}=\|v\|^{2}\|u\|^{2}$$as $\overline{uv}=\overline{v}\cdot \overline{u}$.
---
> [!lemma] Proposition 2
> $S^3:=\{ u\in Q:\|u\|=1 \}$ is a group.

> [!proof]-
> We have that:
> 1. $1$ is the neutral element.
> 2. for $u\in S^3$, as $\|u\|=1$, we have $u^{-1}=\overline{u}$. Then, $\|\overline{u}\|=\frac{\|u\overline{u}\|}{\|u\|}=\|u\|^{2}=1$ and $\overline{u}\in S^3$.
> 3.  By 1.3, $uv\in S^3$ if $u,v\in S^3$.
---
