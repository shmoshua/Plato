#Definition #FunctionalAnalysis 

> [!definition]
> For $d>2$, let $T_{d}:=(V,E)$ be a $d$-regular tree and let $\delta:V\times V\to \mathbb{N}$ be the distance function between two vertices. Let $K:V\times V\to \mathbb{C}$. 
> 1. $K$ is called ***point-pair invariant***, if there exists $k:\mathbb{N}\to \mathbb{C}$ s.t. $K(v,w)=k(\delta(v,w))$ for all $v,w\in V$
> 
> Then, consider the following space:
>  $$L^1(V)^\natural:=\left\{  K:V\times V\to \mathbb{C}\left|K\text{ is point-pair invariant s.t. }\left\| K \right\|_{1}:=\sum_{w\in V}^{}\left| K(v,w) \right|<+\infty   \right.\right\}$$
- **Remark**: $L^1(V)^\natural$ is a new type of Banach algebra, in the sense that there is no group $\Gamma$ s.t. $\ell^1(\Gamma)\cong L^1(V)^\natural$.
- **Remark**: This is similar to hyperbolic planes: $\mathbb{H}^2:=\{ z\in \mathbb{C}: y>0 \}$ then $\text{SL}(2,\mathbb{R})$ acts on it. acts similarly. Given $(z_{1},z_{2})$ and $(w_{1},w_{2})$ with $d(z_{1},z_{2})=d(w_{1},w_{2})$, there exists $g\in \text{SL}(2,\mathbb{R})$ s.t. $g(z_{1})=w_{1}$ and $g(z_{2})=w_{2}$.
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

> [!proof]-
> 2=>1 is clear. So we will show the converse.
> 1. **Showing that $\text{Aut}(T_{d})$ acts transitively on $V$**:
> 	Let $v,w\in V$. Then one can find the shortest path that goes through $v$ and $w$. Then, there exists $h\in \text{Aut}(T_{d})$ that translates the path by one along the path. In other words, $h^{\delta(v,w)}(v)=w$. 
> 2. Now if $\delta(v_{1},w_{1})=\delta(v_{2},w_{2})$, choose $h\in \text{Aut}(T_{d})$ s.t. $h(v_{1})=v_{2}$. Then, $w_{2},h(w_{1})\in S_{n}(v_{2})$ where $n=\delta(v_{1},w_{1})$.
> 3. **Showing that $\{ g\in \text{Aut}(T_{d}):g(v_{2})=v_{2} \}$ acts transitively on $S_{n}(v_{2})$**:
>    We will show a stronger statement. Namely, for any $n\in \mathbb{N},u\in V$ and $v,w\in S_{n}(u)$, there exists $g\in \text{Aut}(T_{d})$ s.t.
>    1. $g(u)=u$
>    2. $g(v)=w$
>    3. $g(x)=x$ if $p(x,u)\cap (p(v,u)\cup p(w,u))=\{ u \}$.
>    
>    If $n=1$, one can easily see that this is true. For $n>1$, let $v',w'\in S_{n-1}(u)$ s.t. $v'$ is on the shortest path between $u$ and $v$, and $w'$ is on the shortest path between $u$ and $w$.
>    
>    Then, there exists $g\in \text{Aut}(T_{d})$ s.t. $g(v')=w'$ and $g(u)=u$. Further, there exists $h\in \text{Aut}(T_{d})$ s.t. $h(v)=g^{-1}(w)$ and $h(u)=u$ as $v,g^{-1}(w)\in S_{1}(v')$. This shows that:
>    1. $g(h(v))=w$ and 
>    2. $g(h(u))=u$
>    3. for $x\in V$ with $p(x,u)\cap (p(v,u)\cup p(w,u))=\{ u \}$, $g(h(x)))=g(x)=x$
>    
>    This proves the statement.

---
> [!lemma] Proposition 3
> We define the product on $L^1(V)^\natural$ as follows: $$(K_{1}*K_{2})(u,v)=\sum_{w\in V}^{}K_{1}(u,w)K_{2}(w,v)$$
> Then, 
> 1. $K_{1}*K_{2}$ is point-pair invariant. 
> 2. $\left\| K_{1}*K_{2} \right\|_{1}\leq \left\| K_{1} \right\|_{1}\left\| K_{2} \right\|_{1}$ and $K_{1}*K_{2}\in L^1(V)^\natural$
> 3. $K_{1}*K_{2}=K_{2}*K_{1}$
> 4. With $K^{*}(x,y)=\overline{K(x,y)}$, $L^1(V)^\natural$ is an [[C*-Algebra|involutive Banach algebra]].

> [!proof]-
> We have:
> 1. **Showing $K_{1}*K_{2}$ is point-pair invariant**:
>    Let $g\in \text{Aut}(T_{d})$. Then, 
> 	$$\begin{align}(K_{1}*K_{2})(u,v)&=\sum_{w\in V}^{}K_{1}(u,g^{-1}(w))K_{2}(g^{-1}(w),v)\\&=\sum_{w\in V}^{}K_{1}(g(u),w)K_{2}(w,g(v))\\&=(K_{1}*K_{2})(g(u),g(v))\end{align}$$Therefore, by Lemma 2, $K_{1}*K_{2}$ is point-pair invariant.
> 2. **Showing $K_{1}*K_{2}\in L^1(V)^\natural$**:
> 	$$\begin{align}\left\| K_{1}*K_{2} \right\| _{1}&=\sum_{v\in V}^{}\left| \sum_{w\in V}^{}K_{1}(u,w)K_{2}(w,v) \right|\\&\leq\sum_{v\in V}^{}\sum_{w\in V}^{}\left| K_{1}(u,w)| |K_{2}(w,v) \right|\\&=\left\| K_{2} \right\| _{1}\left\| K_{1} \right\| _{1}\end{align} $$
> 3. **Showing $K_{1}*K_{2}=K_{2}*K_{1}$**:
> 	$$\begin{align}(K_{1}*K_{2})(u,v)&=\sum_{w\in V}^{}K_{1}(u,w)K_{2}(w,v)\\&=\sum_{w\in V}^{}K_{2}(v,w)K_{1}(w,u)\\&=(K_{2}*K_{1})(v,u)\\&=(K_{2}*K_{1})(u,v)\end{align}$$
> 4. Clear from the properties shown.

---

