#Definition #Topology 

> [!definition]
> For a set $X$ and a [[topological space]] $Y$, consider the function space $\mathcal{F}(X,Y)=\{ f:X\to Y \}$,
> 1. the ***topology of pointwise convergence*** $\mathcal{T}_{p}$ is the product topology on $\prod_{x\in X}^{}Y$, i.e. $U\subseteq \mathcal{F}(X,Y)$ is open if and only if for all $f\in U$, there exists a finite $S\subseteq X$ and open neighborhoods $U_{s}\ni f(s)$ s.t. $$\{ g\in \mathcal{F}(X,Y):g(s)\in U_{s},\forall s\in S \}\subseteq U$$
> 2. for a [[metric space]] $Y$, the ***topology of uniform convergence*** $\mathcal{T}_{u}$ has $U\subseteq \mathcal{F}(X,Y)$ is open if and only if for all $f\in U$, there exists $\varepsilon >0$ s.t. $$\{ g\in \mathcal{F}(X,Y):\sup_{x\in X}d(f(x),g(x)) <\varepsilon \}\subseteq U$$
- **Remark**: $S(x,U):=\{ g\in \mathcal{F}(X,Y):g(x)\in U \}$ is a subbasis of  $\mathcal{T}_{p}$, where $x\in X$ and $U\subseteq Y$ open.
- **Remark**: If $Y$ is metric, $\mathcal{T}_{p}\subseteq \mathcal{T}_{u}$.
- **Remark**: $C(X)\subseteq \mathcal{F}(X)$  is closed in $\mathcal{T}_{u}$ but not in general for $\mathcal{T}_{p}$.
---
##### Properties
> [!lemma] Lemma 1
> Let $Y$ be a metric space. Then, 
> 1. $f_{n}\to f$ in $\mathcal{T}_{p}$ if and only if $f_{n}(x)\to f(x)$ for all $x\in X$.
> 2. $f_{n}\to f$ in $\mathcal{T}_{u}$ if and only if $f_{n}(x)\to f(x)$ uniformly.
> 3. $\mathcal{T}_{p}\subseteq \mathcal{T}_{u}$.

> [!proof]-
> We have that:
> 1. Suppose that $f_{n}\to f$ in $\mathcal{T}_{p}$. For $x\in X$, let $U\subseteq Y$ be an open neighborhood of $f(x)$. Then, $S(x,U)$ is open and especially is a neighborhood of $f$. Therefore, there exists $N\in \mathbb{N}$ with $f_{n}\in S(x,U)$ for $n\geq N$. This shows that $f_{n}(x)\in U$ for $n\geq N$. Hence, $f_{n}(x)\to f(x)$.
>    
>    Conversely, if $f_{n}(x)\to f(x)$ for all $x\in X$. Let $U$ be an open neighborhood of $f$ in $\mathcal{F}(X,Y)$. Then there exists a finite $S\subseteq X$ and $U_{s}\ni f(s)$ s.t.$$\{ g\in\mathcal{F}(X,Y):g(s)\in U_{s},\forall s\in S \}\subseteq U$$Let $N_{s}\in \mathbb{N}$ s.t. $f_{n}(s)\in U_{s}$ for all $n\geq N_{s}$. Then, by taking $N:=\max_{s\in S}N_{s}$, we have that $f_{n}\in U$ for all $n\geq N$.
> 2. Analogous.
> 3. Let $U\subseteq \mathcal{T}_{p}$. Then for $f\in U$, there exists $\varepsilon>0$ s.t. $$\{ g\in \mathcal{F}(X,Y): \sup_{x\in X}d(f(x),g(x))<\varepsilon \}\subseteq \{ g\in \mathcal{F}(X,Y):g(s)\in U_{s},\forall s\in S \}\subseteq U$$
---
