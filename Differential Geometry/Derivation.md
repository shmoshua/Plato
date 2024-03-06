#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]] and $p\in M$. A ***derivation*** of $C^\infty(M)$ at $p$ is a map $\delta\in C^\infty(M)^{*}$ s.t. for all $f,g\in C^\infty(M)$, $$\delta(fg)=\delta(f)g(p)+f(p)\delta(g)$$
> Let $\text{Der}_{p}C^\infty(M)$ be the vector space of derivations at $p$.
---
##### Properties
> [!lemma] Lemma 1
> Let $M$ be a [[smooth manifold]] and $p\in M$. Further, let $\delta\in \text{Der}_{p}C^\infty(M)$ and $g\in C^\infty(M)$ s.t. $g \equiv 1$ in a neighborhood of $p$. Then, $$\delta(f)=\delta(fg), \quad\forall f\in C^\infty(M)$$

> [!proof]-
> By linearity of $\delta$, it suffices to show that $\delta(h)=0$ for $h=f-fg$. Observe that $h$ vanishes on a neighborhood $V$ of $p$. Then, we can construct $\psi\in C^\infty(M)$ s.t. 
> 1. $\text{supp }\psi \subseteq V$
> 2. $\psi(p)\neq 0$
> 
> as follows. 
> 
> 1. **Constructing $\psi$**:
> 	Let $(U,\varphi)$ be a chart at $p$ s.t. $U\subseteq V$. Let $C\subseteq \mathbb{R}^m$ be a hypercube centered at $\varphi(p)$ contained in $\varphi(U)$ and $\beta$ be a smooth function that is $1$ at the hypercube and $0$ outside of the hypercube. Then, we can define $\psi:=\beta \circ\varphi$ that naturally extends to $M$ with $\psi(p)=1$ and $\text{supp }\psi \subseteq U\subseteq V$. 
> 2. **Showing the rest**:
> 	We have that $h\cdot \psi=0$. Therefore, $$0=\delta(h\psi)=\delta(h)\psi(p)+h(p)\delta(\psi)=\delta(h)\psi(p)$$As $\psi(p)\neq 0$, $\delta(h)=0$. This proves the statement.
---
> [!lemma] Lemma 2
> Let $v\in \mathbb{R}^n$ and $U\subseteq \mathbb{R}^n$ a star-shaped neighborhood of $v$. Further, let $f\in C^\infty(U)$.  Then, there are $g_{1},\dots,g_{n}\in C^\infty(U)$ with: 
> 1. $g_{i}(v)=\partial_{i}f(v)$ and
> 2. $f(x)=f(v)+\sum_{i=1}^{n}(x_{i}-v_{i})g_{i}(x)$

> [!proof]-
> Since $U$ is star-shaped w.r.t. $v$, we may write: $$\begin{align}f(x)&=f(v)+\int_{0}^{1} \frac{ \partial f }{ \partial t } (v+t(x-v)) \, dt\\&=f(v)+\sum_{i=1}^{n}(x_{i}-v_{i})\underbrace{ \int_{0}^{1} \frac{ \partial f }{ \partial x_{i} } (v+t(x-v)) \, dt }_{ =:g_{i}(x) } \end{align} $$In particular, $$g_{i}(v)=\int_{0}^{1} \frac{ \partial f }{ \partial x_{i} } (v) \, dt=\partial_{i}f(v) $$

---
> [!lemma] Theorem 3
> Let $M$ be a [[smooth manifold]] and $p\in M$. $$\begin{array}{cccc} {}&{\text{T}_{p}M}&\to&{\text{Der}_{p}C^\infty(M)}\\&{v} &\mapsto & {\delta_{v}:f\mapsto d_{p}f(v)} \end{array}{}$$is a vector space isomorphism.

> [!proof]-
> Let $(U,\varphi)$ be a chart at $p$. Choose $\varepsilon>0$ s.t. $V:=\prod_{i=1}^{m}(\varphi(p)_{i}-2\varepsilon,\varphi(p)_{i}+2\varepsilon)\subseteq\varphi(U)$. Now, by the smooth version of the Urysohn lemma, there exists a functon $g\in C^\infty(\mathbb{R}^m,[0,1])$ s.t. 
> 1. $g(x)=1$ for $x\in \prod_{i=1}^{m}\left( \varphi(p)_{i}-\frac{\varepsilon}{2},\varphi(p)_{i}+\frac{\varepsilon}{2} \right)$ and 
> 2. $g(x)=0$ for $x\notin \prod_{i=1}^{m}\left( \varphi(p)_{i}-\varepsilon,\varphi(p)_{i}+\varepsilon \right)$
> 
> For $f\in C^\infty(M)$, by Lemma 1, we have $\delta(f)=\delta(f\cdot(g\circ\varphi))$ where we extend $g\circ\varphi$ to $M \backslash U$ with zero. Then, $$\delta(f)=\delta(f\cdot (g\circ \varphi))=\delta(((f\circ \varphi^{-1})\cdot g)\circ \varphi)$$where $(f\circ\varphi ^{-1})\cdot g\in C^\infty(\mathbb{R}^n)$ with support in $\prod_{i=1}^{m}\left( \varphi(p)_{i}-\varepsilon,\varphi(p)_{i}+\varepsilon \right)$.
> 
> Now, for every $F\in C^\infty(V)$ define $\alpha(F):=\delta((F\cdot g)\circ\varphi)$ which is a derivation of $C^\infty(V)$ at $\varphi(p)$ as: $$\begin{align}\alpha(FG)&=\delta((F\cdot G\cdot g)\circ \varphi)\\&=\delta((F\cdot g)\circ \varphi)(G\cdot g)(\varphi(p))+(F\cdot g)(\varphi(p))\delta((G\cdot g)\circ \varphi)\\&=\alpha(F)G(\varphi(p))+ F(\varphi(p))\alpha(G)\end{align}$$Therefore, by Lemma 2, there exists $G_{1},\dots,G_{n}\in C^\infty(V)$ with: 
> 1. $G_{i}(\varphi(p))=\partial_{i}F(\varphi(p))$ and
> 2. $F(x)=F(\varphi(p))+\sum_{i=1}^{n}(x_{i}-\varphi(p)_{i})G_{i}(x)$
>    
> Then, $$\begin{align}\alpha(F)&=\alpha(F(\varphi(p))\cdot 1)+\sum_{i=1}^{n}\alpha(x\mapsto x_{i}-\varphi(p)_{i})G_{i}(\varphi(p))\\&=\sum_{i=1}^{n}\underbrace{ \alpha(x\mapsto x_{i}-\varphi(p)_{i}) }_{ =:v_{i} }\frac{ \partial F }{ \partial x_{i} } (\varphi(p))\end{align}$$Therefore, $$\begin{align}\delta(f)&=\delta(((f\circ \varphi ^{-1})\cdot g)\circ \varphi)\\&=\alpha(f\circ \varphi ^{-1})\\&=\sum_{i=1}^{n}v_{i}\frac{ \partial (f\circ \varphi^{-1}) }{ \partial x _{i}}\varphi(p)\\&=d_{\varphi(p)}(f\circ \varphi ^{-1})(v)\\&=d_{p}f(v)\end{align} $$
---
> [!lemma] Corollary 4
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and let $F:M\to N$ be a [[Smooth Function|smooth map]]. Then, we can define the function: $$\begin{array}{cccc} {F_{*}:}&{\text{Der}_{p}C^\infty(M)}&\to&{\text{Der}_{F(p)}C^\infty(N)}\\&{\delta} &\mapsto & {f\mapsto \delta(f\circ F)} \end{array}{}$$Further, the following diagram commutes:
> $$\begin{CD} \text{T}_{p}M @>d_{p}F>> \text{T}_{F(p)}N\\@V\cong VV&@V\cong VV\\\text{Der}_{p}C^\infty(M) @>>F_{*}>\text{Der}_{F(p)}C^\infty(N)\end{CD}$$

> [!proof]-
> For $\delta\in \text{Der}_{p}C^\infty(M)$ and $g_{1},g_{2}\in C^\infty(N)$, $$\begin{align}F_{*}\delta(g_{1}g_{2})&=\delta((g_{1}\cdot g_{2})\circ F)\\&=\delta(g_{1}\circ F)g_{2}(F(p))+g_{1}(F(p))\delta(g_{2}\circ F)\\&=F_{*}\delta(g_{1})g_{2}(F(p))+g_{1}(F(p))F_{*}\delta(g_{2})\end{align}$$
> Further, for $v\in \text{T}_{p}M$, $$F_{*}(\delta_{v})(f)=\delta_{v}(f\circ F)=d_{p}(f\circ F)v=d_{F(p)}(f)d_{p}F(v)=\delta_{d_{p}F(v)}(f)$$
---
