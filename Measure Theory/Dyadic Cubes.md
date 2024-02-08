#Definition #Analysis #MeasureTheory 

> [!definition]
> For $k\geq 0$, the set of ***dyadic cubes*** is defined as $\bigcup_{k=1}^{\infty}\mathcal{D_{k}}$ where:
> $$\mathcal{D_{k}} =\left\{  \prod_{i=1}^{n}\left[ \frac{a_{i}}{2^k},\frac{a_{i}+1}{2^k} \right) : a_{i}\in \mathbb{Z} \right\}$$
> For example, $\mathcal{D}_{0}$ is the set of cubes with edge 1 and vertices at points with integer coordinates.

- ***Remark***: By bisecting each edge in a cube in $\mathcal{D}_{k}$, we obtain $2^n$ sub-cubes of edge length $\frac{1}{2^k}$ that belongs in $\mathcal{D}_{k+1}$. 
---
##### Properties
> [!lemma] Lemma 1
> We have the following:
> 1. For any $k\geq 0$, $\mathbb{R}^n=\bigcup_{Q\in \mathcal{D}_{k}}^{}Q$.
> 2. For $h<k$, if $P\in \mathcal{D}_{h}$ and $Q\in \mathcal{D}_{k}$, then either $Q \subseteq P$ or $Q \cap P=\varnothing$.
> 3. If $Q\in \mathcal{D}_{k}$, then [[Volume Function|$\text{vol}(Q)$]] $=2^{-kn}$

> [!proof]-
> We have: 
> 1. $\supseteq$ is trivial. For $\subseteq$, let $x\in \mathbb{R}^n$. Then, we have $a_{i}=\lfloor x_{i}2^k\rfloor$. Then, $$a_{i}\leq x_{i}2^k< a_{i}+1$$
> 2. Let $P\in \mathcal{D}_{h}$ and $Q\in \mathcal{D}_{k}$. If $Q\cap P=\varnothing$, then we are done. Therefore, assume that there exists $x\in Q\cap P$. Then, we have: 
> 	$$Q:=\prod_{i=1}^{n}\left[ \frac{a_{i}}{2^k},\frac{a_{i}+1}{2^k} \right) $$
>    where $a_{i}:=\lfloor x_{i}2^k\rfloor$. However, $$P:=\prod_{i=1}^{n}\left[\frac{b_{i}}{2^h},\frac{b_{i}+1}{2^h}  \right) $$with $b_{i}:=\lfloor x_{i}2^h\rfloor$. Then, for any $q\in Q$, Then, we have:
>    1. $2^{k-h}\lfloor x_{i}2^h\rfloor\leq\lfloor x_{i}2^k\rfloor$ and $b_{i} / 2^h\leq a_{i} / 2^k$. 
>    2. Analogously.
>   
> 	  Therefore, $Q \subseteq P$.
> 3. Obvious.
---
> [!lemma] Lemma 2
> Any open set $V\subseteq \mathbb{R}^n$ can be represented as a countable union of disjoint dyadic cubes.

> [!proof]-
> Let $\varnothing \neq V \subseteq \mathbb{R}^n$ be an open set. We define the sets $\{ S_{k} \}_{k\geq 0}$ with:
> 1. $S_{0}:=\{ Q\in \mathcal{D}_{0}:Q\subseteq V \}$
> 2. $S_{k}:= \{ Q\in \mathcal{D}_{k}:Q \subseteq V \backslash \bigcup_{j=0}^{k-1} S_{j}\}$
> 
> Let $\mathcal{S}:=\bigcup_{k=0}^{\infty}S_{k}$. Then, we claim that $V=\bigcup_{Q\in\mathcal{S}}^{}Q$. The inclusion $\supseteq$ is trivial from definition. For any point $x\in V$, as $\mathbb{R}^n=\bigcup_{Q\in \mathcal{D}_{k}}^{}Q$, for any $k\geq 0$, there exists $Q_{k}\in \mathcal{ D}_{k}$ s.t. $x\in Q_{k}$. We will now show that for all $\varepsilon>0$, there exists $k'$ s.t. $Q_{k'}\subseteq B(x,\varepsilon)$. Let $x_{k}$ be the center of $Q_{k}$. Then, for any point $y\in Q_{k}$, we have: $$\left| x -y \right|\leq \left| x-x_{k} \right| +\left| x_{k}-y \right|\leq \frac{\sqrt{ n }}{2^{k+1}} +\frac{\sqrt{ n }}{2^{k+1}} =\frac{\sqrt{ n }}{2^{k}}  $$Therefore, for $k' > \log \frac{\sqrt{ n }}{\varepsilon}$, we have that $Q_{k'}\subseteq B(x,\varepsilon)$. It follows that $Q_{k'}$ is either in $S_{k'}$ or $S_{h}$ where $h < k'$, which proves that $x\in \bigcup_{Q\in\mathcal{S}}^{}Q$.
---