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
> [!lemma] Theorem 1
> Let $M$ be a [[smooth manifold]] and $p\in M$. $$\begin{array}{cccc} {}&{\text{T}_{p}M}&\to&{\text{Der}_{p}C^\infty(M)}\\&{v} &\mapsto & {\delta_{v}:f\mapsto d_{p}f(v)} \end{array}{}$$is a vector space isomorphism.

> [!proof]+
> Let $(U,\varphi)$ be a chart at $p$. Choose $\varepsilon>0$ s.t. $\prod_{i=1}^{n}(\varphi(p)_{i}-2\varepsilon,\varphi(p)_{i}+2\varepsilon)\subseteq\varphi(U)$. Now, by the smooth version of the Urysohn lemma, there exists a functon $g\in C^\infty([0,1])$