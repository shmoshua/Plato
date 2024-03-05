#Definition #Topology 

> [!definition]
> For a set $X$ and the function space $\mathcal{F}(X)=\{ f:X\to \mathbb{C} \}$,
> 1. the ***topology of pointwise convergence*** $\mathcal{T}_{p}$ has $U\subseteq \mathcal{F}(X)$ is open if and only if for all $f\in U$, there exists $x_{0}\in X$ and $\varepsilon >0$ s.t. $$\{ g\in \mathcal{F}(X):\left| f(x_{0})-g(x_{0}) \right| <\varepsilon \}\subseteq U$$
> 2. the ***topology of uniform convergence*** $\mathcal{T}_{u}$ has $U\subseteq \mathcal{F}(X)$ is open if and only if for all $f\in U$, there exists $\varepsilon >0$ s.t. $$\{ g\in \mathcal{F}(X):\sup_{x\in X}\left| f(x)-g(x) \right| <\varepsilon \}\subseteq U$$
- **Remark**: $\mathcal{T}_{p}\subseteq \mathcal{T}_{u}$
- **Remark**: $C(X)\subseteq \mathcal{F}(X)$  is closed in $\mathcal{T}_{u}$ but not in general for $\mathcal{T}_{p}$.
---
##### Properties
> [!lemma] Lemma 1
> For $(f_{n})_{n}\subseteq \mathcal{F}(X)$, 
> 1. $f_{n}\to g$ in $\mathcal{T}_{p}$ if and only if $f_{n}(x)\to g(x)$ for all $x\in X$.
> 2. $f_{n}\to g$ in $\mathcal{T}_{u}$ if and only if $f_{n}(x)\to g(x)$ uniformly.

> [!proof]-
> We have:
> 1. Suppose that $f_{n}\to g$ in $\mathcal{T}_{p}$. Then, for $x\in X$ and $\varepsilon>0$, $$V_{\varepsilon}:=\{ f\in \mathcal{F}(X):\left| f(x)-g(x) \right| <\varepsilon \}$$is an open neighborhood of $g$. Therefore, there exists $N\geq 0$ s.t. $f_{n}\in V_{\varepsilon}$ for all $n\geq N$, i.e. $\left| f_{n}(x)-g(x) \right|<\varepsilon$. 
> 	
> 	Conversely, assume that $f_{n}(x)\to g(x)$ for all $x\in X$. For a neighborhood $U$ of $g$, there exists $\{ f\in \mathcal{F}(X):\left| f(x_{0})-g(x_{0}) \right|<\varepsilon \}\subseteq U$ for some $\varepsilon>0$ and $x_{0}\in X$. Then, as $f_{n}(x_{0})\to g(x_{0})$, there exists $N\in \mathbb{N}$ s.t. $f_{n}\in U$ for all $n\geq N$.
> 2. Analogous.
---