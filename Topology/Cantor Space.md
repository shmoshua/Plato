#Definition #Topology 

> [!definition]
> The ***Cantor space*** is a [[topological space]] defined as: $C=\{ 0,1 \}^\infty$ with the [[product topology]], i.e. $U\subseteq C$ is open if and only if for every $x\in U$, there exists a finite index set $I\subseteq \mathbb{N}$ s.t. $$\{ y\in C: y_{n}=x_{n},\forall n\in I \}\subseteq U$$
---
##### Properties
> [!lemma] Proposition 1
>  $x^{(n)}\to x$ in $C$ if and only if for all $m\in \mathbb{N}$, $x_{m}^{(n)}=y_{m}$ for all $n\geq N_{m}$.

> [!proof]-
> If $x^{(n)}\to x$, then for $m\in \mathbb{N}$, there exists $N_{m}$ s.t. $$x^{(n)}\in\{ y\in C: y_{m}=x_{m}\},\quad \forall n\geq N_{m}$$Conversely, if $x_{m}^{(n)}=y_{m}$ for all $n\geq N_{m}$, for any neighborhood $U$ of $x$, there exists $I\subseteq \mathbb{N}$ finite s.t. $$\{ y\in C: y_{m}=x_{m},\forall m\in I \}\subseteq U$$Then, by choosing $N:=\max_{m\in I}N_{m}$, $x^{(n)}\in U$ for all $n\geq N$.
---
> [!lemma] Proposition 2
> Consider the map: $$b:C\to[0,1],\quad x\mapsto \sum_{n=1}^{\infty}\frac{x_{n}}{2^n}$$
> 1. $b$ is surjective.
> 1. $b$ is continuous.
> 2. $b$ is not a homeomorphism.
---
> [!lemma] Proposition 3
> Consider the map: $$t:C\to[0,1],\quad x\mapsto \sum_{n=1}^{\infty}\frac{2x_{n}}{3^n}$$Then, 
> 1. $t$ is injective.
> 2. $t$ is not surjective and $t(C)$ is the [[Cantor set]].
> 3. $t$ is continuous and $t:C\to t(C)$ is a homeomorphism.
---