#Definition #DifferentialGeometry 

> [!definition]
> Let $V$ be a finite-dimensional $\mathbb{R}$-[[vector space]]. A ***multilinear $k$-form on $V$*** is a function $\mu:V\times\dots \times V\to \mathbb{R}$ which is linear in each argument.
---
##### Properties
> [!lemma] Lemma 1
> Let $\mu$ be a multilinear $k$-form on $V$. The following are equivalent:
> 1. $\mu(v_{1},\dots,v_{k})=0$ if $v_{i}=v_{j}$ for some $i,j\in[k]$.
> 2. $\mu(v_{1},\dots,v_{i},\dots,v_{j},\dots,v_{k})=-\mu(v_{1},\dots,v_{j},\dots,v_{i},\dots,v_{k})$
> 3. For all $v_{1},\dots,v_{k}\in V$ and $\sigma\in$ [[Symmetry Group|$S_{k}$]]: $\mu(v_{\sigma(1)},\dots,v_{\sigma(k)})=\text{sgn}(\sigma)\mu(v_{1},\dots,v_{k})$
>    
> Any multilinear $k$-form $\mu$ with the above property is called ***alternating***.

> [!proof]-
> We have:
> - 1=>2: $$\begin{align}\mu(v_{1},\dots,v_{j},\dots,v_{i},\dots,v_{k})+\mu(v_{1},\dots,v_{j},\dots,v_{i},\dots,v_{k})&=\mu(2v_{1},\dots,v_{i}+v_{j},\dots,v_{i}+v_{j},\dots,2v_{k})\\&=0\end{align}$$
> - 2=>3: As $\text{sgn}(\sigma)=-1$ if the number of elementary transpositions in $\sigma$ is odd, this makes sense.
> - 3=>1: If $v_{i}=v_{j}$, then: $$\mu(v_{1},\dots,v_{i},\dots,v_{j},\dots,v_{k})=-\mu(v_{1},\dots,v_{i},\dots,v_{j},\dots,v_{k})$$ Therefore, $\mu(v_{1},\dots,v_{k})=0$.
---