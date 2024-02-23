#Definition #FunctionalAnalysis 

> [!definition]
> For $d>2$, let $T_{d}:=(V,E)$ be a $d$-regular tree and let $\delta:V\times V\to \mathbb{N}$ be the distance function between two vertices. Let $K:V\times V\to \mathbb{C}$. 
> 1. $K$ is called ***point-pair invariant***, if there exists $k:\mathbb{N}\to \mathbb{C}$ s.t. $K(v,w)=k(\delta(v,w))$ for all $v,w\in V$
> 
> Then, consider the following space:
>  $$L^1(V)^\natural:=\left\{  K:V\times V\to \mathbb{C}\left|K\text{ is point-pair invariant s.t. }\left\| K \right\|_{1}:=\sum_{w\in V}^{}\left| K(v,w) \right|<+\infty   \right.\right\}$$
---
##### Properties
> [!lemma] Proposition 1
> $\left\| K \right\|_{1}$ is well-defined, i.e. if $\sum_{w\in V}^{}K(v,w)$ converges, then the value is independent of $v$.

> [!proof]-
> Let $S_{n}(v)$ denote the sphere of radius $n$ from $v$, i.e. 
> $$S_{n}(v):=\{ w\in V:\delta(v,w)=n \}$$
> Then, for any $v\in V$, one can slayfully see that $\left| S_{n}(v) \right|=d(d-1)^{n-1}$. 
> 
> It follows that: $$\begin{align}\sum_{w\in V}^{}K(v,w)&=\sum_{w\in V}^{}k(\delta(v,w))=\sum_{n=0}^{\infty}\sum_{w\in S_{n}(v)}^{}k(n)=\sum_{n=0}^{\infty}\left| S_{n}(v) \right| \cdot k(n)=k(0)+\sum_{n=1}^{\infty}k(n)\cdot d(d-1)^{n-1}\end{align}$$Therefore, it is independent of $v\in V$.
---
> [!lemma] Lemma 2
> Given $(v_{1},w_{1})$ and $(v_{2},w_{2})$ pairs of vertices, The following are equivalent:
> 1. $\delta(v_{1},w_{1})=\delta(v_{2},w_{2})$.
> 2. there exists $g\in \text{Aut}(T_{d})$ s.t. $g(v_{1})=v_{2}$ and $g(w_{1})=w_{2}$
> 
> where an automorphism is a bijective map $g:V\to V$ that preserves adjacency.

> [!proof]+
> 2=>1 is clear. So we will show the converse.
> 1. **Showing that $\text{Aut}(T_{d})$ acts transitively on $V$**:
> 	Let $v,w\in V$. Then one can find the shortest path that goes through $v$ and $w$. Then, there exists $h\in \text{Aut}(T_{d})$ that translates the path by one along the path. In other words, $h^{\delta(v,w)}(v)=w$. 
> 2. Now if $\delta(v_{1},w_{1})=\delta(v_{2},w_{2})$, choose $h\in \text{Aut}(T_{d})$ s.t. $h(v_{1})=v_{2}$. Then, $w_{2},h(w_{1})\in S_{n}(v_{2})$ where $n=\delta(v_{1},w_{1})$.
> 3. **Showing that $\{ g\in \text{Aut}(T_{d}):g(v_{2})=v_{2} \}$ acts transitively on $S_{n}(v_{2})$**:
>    We will show a stronger statement. Namely, for any $n\in \mathbb{N},u\in V$ and $v,w\in S_{n}(u)$, there exists $g\in \text{Aut}(T_{d})$ s.t.
>    1. $g(u)=u$
>    2. $g(v)=w$
>    3. $g(w)=u$
>    4. $g(x)=x$ for all $S_{n}(u) \backslash \{ v,w \}$
>    
>    If $n=0$, then $\text{id}$ is such automorphism. Now, let $n>0$. Then, for $v,w\in S_{n}(v_{2})$ there exists $v',w'\in S_{n-1}(v_{2})$ s.t. 
> - (2=>1): clear.
> - (1=>2): 
---
> [!lemma] Proposition 2
> We define the product on $L^1(V)^\natural$ as follows: $$(K_{1}*K_{2})(u,v)=\sum_{w\in W}^{}K_{1}(u,w)K_{2}(w,v)$$
> Then, 
> 1. $K_{1}*K_{2}\in L^1(V)^{\natural}$ 
> 2. $\left\| K_{1}*K_{2} \right\|_{1}\leq \left\| K_{1} \right\|_{1}\left\| K_{2} \right\|_{1}$
> 3. $K_{1}*K_{2}=K_{2}*K_{1}$

> [!proof]+
> We have:
> 1. **Showing $K_{1}*K_{2}$ is point-pair invariant**:
> 	$$\begin{align}(K_{1}*K_{2})(u,v)&=\sum_{w\in W}^{}K_{1}(u,w)K_{2}(w,v)\\&=\sum_{w\in W}^{}k_{1}(\delta(u,w))k_{2}(\delta(w,v))\\&=\sum_{n=0}^{\infty}\sum_{w\in S_{n}(v)}^{}k_{1}(n)k_{2}(\delta(w,v))\\&=\sum_{n=0}^{\infty}k_{1}(n)\sum_{w\in S_{n}(v)}^{}k_{2}(\delta(w,v))\end{align}$$
> 
> Let $L^1(V)^\natural:=\left\{  K:V\times V\to \mathbb{C}|K\text{ is point-pair invariant s.t. }\left\| K \right\|_{1}:=\sum_{w\in V}^{}\left| K(v,w) \right|<+\infty   \right\}$: $$(K_{1}*K_{2})(u,v)=\sum_{w\in W}^{}K_{1}(u,w)K_{2}(w,v)$$
> Then:
> 1. $K_{1}*K_{2}\in L^1(V)^{\natural}$ and $\left\| K_{1}*K_{2} \right\|_{1}\leq \left\| K_{1} \right\|_{1}\left\| K_{2} \right\|_{1}$ and
> 2. $K_{1}*K_{2}=K_{2}*K_{1}$
>    
> $g\in\text{Aut}(T_{d})$ is a bijection $g:V\to V$ preserving adjacency, i.e. $g$ is a isometry of $(V,\delta)$. 
> 
> There is no group $\Gamma$ s.t. $\ell^1(\Gamma)\cong L^1(V)^\natural$

> [!lemma]+
> Given $(v_{1},w_{1})$ and $(v_{2},w_{2})$ pairs of vertices, TFAE:
> 1. $\delta(v_{1},w_{2})=\delta(v_{2},w_{2})$ and
> 2. there exists $g\in \text{Aut}(T_{d})$ s.t. $g(v_{1})=v_{2}$ and $g(w_{1})=w_{2}$

---
$\mathbb{H}^2:=\{ z\in \mathbb{C}: y>0 \}$ then $\text{SL}(2,\mathbb{R})$ acts on it. acts similarly. Given $(z_{1},z_{2})$ and $(w_{1},w_{2})$ with $d(z_{1},z_{2})=d(w_{1},w_{2})$, there exists $g\in \text{SL}(2,\mathbb{R})$ s.t. $g(z_{1})=w_{1}$ and $g(z_{2})=w_{2}$.
