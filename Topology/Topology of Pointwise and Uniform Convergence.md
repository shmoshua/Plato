#Definition #Topology 

> [!definition]
> For a set $X$ and a [[Topological Space]] $Y$, consider the function space $\mathcal{F}(X,Y)=\{ f:X\to Y \}$,
> 1. the ***topology of pointwise convergence*** $\mathcal{T}_{p}$ is the product topology on $\prod_{x\in X}^{}Y$, i.e. $U\subseteq \mathcal{F}(X,Y)$ is open if and only if for all $f\in U$, there exists a finite $S\subseteq X$ and open neighborhoods $U_{s}\ni f(s)$ s.t. $$\{ g\in \mathcal{F}(X,Y):g(s)\in U_{s},\forall s\in S \}\subseteq U$$
> 2. for a [[Metric Space]] $Y$, the ***topology of uniform convergence*** $\mathcal{T}_{u}$ has $U\subseteq \mathcal{F}(X,Y)$ is open if and only if for all $f\in U$, there exists $\varepsilon >0$ s.t. $$\{ g\in \mathcal{F}(X,Y):\sup_{x\in X}d(f(x),g(x)) <\varepsilon \}\subseteq U$$
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
##### Examples
> [!h] Example 1
> Let $X=\mathcal{F}(\mathbb{R},\mathbb{C})$ with the topology $\mathcal{T}_{p}$.
> 1. Let $A\subseteq X$ be any subset. Then, $0\in \overline{A}$ if and only if, for any $N\geq 1$, $(x_{n})_{n}\in \mathbb{R}^N$ and $\varepsilon>0$, there exists $f\in A$ s.t. $\left| f(x_{n}) \right|<\varepsilon$ for all $n$.
> 2. Let $A\subseteq X$ be the subset of monic polynomials with real coefficients. Then, $0\notin A$ and that $0\in \overline{A}$. 
> 3. For $A\subseteq X$ the subset of the indicator functions of the complements of finite sets (i.e $f_{S}:=1-\chi_{S}$, with $S$ finite), $0\notin A$ and $0\in \overline{A}$. Further there exists no sequence $(f_{n})_{n}\subseteq A$ s.t. $f_{n}\to 0$.

> [!proof]-
> We have: 
> 1. Let $0\in \overline{A}$. Then, for any neighborhood $U$ of $0$, $U\cap A\neq \varnothing$. Therefore, for any $N\geq 1$, $(x_{n})_{n}\in \mathbb{R}^N$ and $\varepsilon >0$, $\{ g\in \mathcal{F}(\mathbb{R},\mathbb{C}):\left| g(x_{n}) \right| <\varepsilon,\forall n\in [N] \}$ is an open neighborhood of $0$ and there exists $$f\in \{ g\in \mathcal{F}(\mathbb{R},\mathbb{C}):\left| g(x_{n}) \right| <\varepsilon,\forall n\in [N] \}\cap A$$Conversely, suppose for all $N\geq 1$, $(x_{n})_{n}\in \mathbb{R}^N$ and $\varepsilon>0$ there exists $f\in A$ s.t. $\left| f(x_{n}) \right|<\varepsilon$ for all $n$. Let $U$ be any neighborhood of $0$. Then, there exists $(x_{n})_{n}\in \mathbb{R}^N$ and $\varepsilon>0$ s.t. $$V:=\{ f\in \mathcal{F}(\mathbb{R},\mathbb{C}):\left| f(x_{n}) \right| <\varepsilon,\ \forall n\in [N] \}\subseteq U$$By assumption, we have $f\in V\cap A\subseteq U\cap A$. Therefore, $U\cap A\neq \varnothing$ and $0\in\overline{A}$.
> 2. We know that $0$ is not monic by definition, so $0\notin A$. However, for any $N\geq 1$, $(x_{n})_{n}\in \mathbb{R}^N$ and $\varepsilon>0$, $$f(x):=\prod_{n=1}^{N}(x-x_{n})$$is a monic polynomial s.t. $\left| f(x_{n}) \right|<\varepsilon$. Therefore, from 1, $0\in \overline{A}$.
> 3. For the indicator functions, $f_{S}\neq 0$ as $S\subseteq \mathbb{R}$ is finite. Therefore, $0\notin A$.  Further, for any $N\geq 1$, $(x_{n})_{n}\in \mathbb{R}^N$ and $\varepsilon>0$, define $S:=\{ x_{n} \}_{n}$ and $f_{S}(x_{n})=0$ for all $n\in [N]$. This proves the statement.
>    
>    Let $(f_{S_{n}})_{n}$ be a sequence of such indicator functions s.t. $f_{S_{n}}(x)\to 0$ where $S_{n}$ is finite for all $n$. As $f_{S_{n}}(\mathbb{R})\subseteq\{ 0,1 \}$ this means that for each $x\in \mathbb{R}$, there exists $n$ s.t. $x\in S_{n}$ for all $n\geq N$. However, from the finiteness of $S_{n}$, this means we can construct a countable sequence $(x_{n})_{n}=\mathbb{R}$, i.e. $\mathbb{R}$ is countable. Indeed, this is a contradiction. 
---
> [!h] Example 2
> Let $X=\mathcal{F}(\mathbb{C})$ and $A\subseteq X$ be the subset of polynomial functions $f:\mathbb{C}\to \mathbb{C}$. Then,
> 1. $A$ is dense in $(X,\mathcal{T}_{p})$.
> 2. $A^\circ$ is empty in $(X,\mathcal{T}_{p})$.
> 3. for any $f\in X$, the sets $$V_{f,n}:=\{ g\in X:\left| f(x)-g(x) \right| <1/n,\quad \forall x\in \mathbb{C} \}$$for $n\geq 1$ form a countable local base of $f$ in $(X,\mathcal{T}_{u})$.
> 4. $A_{0}:=\{ f\in A:f(0)=0 \}$ is discrete in $(X,\mathcal{T}_{u})$.

> [!proof]-
> We have:
> 1. let $f\in X$ and $U$ be an open neighborhood of $f$ w.r.t $\mathcal{T}_{p}$. Then there exists $F\subseteq\mathbb{C}$ finite and $\varepsilon>0$ s.t. $$\{ g\in X :\left| g(x)-f(x) \right| <\varepsilon, \forall x\in F\}\subseteq U$$Now there exists a polynomial $p$ that interpolates $\{ (x,f(x)) \}_{x\in F}$. Then, $p\in U\cap A$. Therefore, $f\in \overline{A}$, i.e. $X=\overline{A}$.
> 2. Let $U$ be an open set s.t. $U\subseteq A$. If $f\in U$, then there exists $F\subseteq \mathbb{C}$ finite and $\varepsilon>0$ s.t. $$\{ g\in X:\left| g(x)-f(x) \right|<\varepsilon, \forall x\in F \}\subseteq U$$However, consider $h(x)=\begin{cases}f(x)&x\in F\\0&x\notin F&\end{cases}$. Then, $h\notin A$ but $\left| h(x_{0})-f(x_{0}) \right|=0$. Therefore, this is a contradiction and $U$ has to be empty. As $U$ is arbitrary, $A^\circ=\varnothing$.
> 3. Let $V$ be a neighborhood of $f$ in $(X,\mathcal{T}_{u})$. Then, there is an open set $f\in U\subseteq V$. Therefore, there exists $\varepsilon>0$ and $n\geq 1$ (e.g. $\frac{1}{n}<\varepsilon$) s.t. $V_{f,n}\subseteq\{ g\in X:\sup_{x\in\mathbb{C}}\left| f(x)-g(x) \right|<\varepsilon \}\subseteq U\subseteq V$. Further, the countability is clear.
> 4. Let $f\subseteq A_{0}$. It suffices to show that $\{ f \}$ is open w.r.t. the subspace topology. Let $\varepsilon>0$ and we will show that $\{ f \}:=\{ g\in X:\sup_{x\in \mathbb{C}}\left| f(x)-g(x) \right|<\varepsilon \}\cap A_{0}$. Assume there exists $g\in \{ g\in X:\sup_{x\in \mathbb{C}}\left| f(x)-g(x) \right|<\varepsilon \}\cap A_{0}$. As $g$ is a polynomial, $f-g$ is a polynomial and from $\left| (f-g)(x) \right|<\varepsilon$, by Liouville, $f-g$ is constant, i.e. $f(x)=g(x)+k$ for some $k$ for all $x\in \mathbb{C}$. However, as $f(0)=0=g(0)$, $k=0$ and $g=f$. 
>    
>    Indeed, $\{ g\in X:\sup_{x\in \mathbb{C}}\left| f(x)-g(x) \right|<\varepsilon \}$ is open and this shows that $A_{0}$ is discrete.