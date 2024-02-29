#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]] and $f:M\to N$ [[Differentiable Function|differentiable]] at $p\in M$. For $(U,\varphi)$ at $p$ and $(W,\psi)$ at $f(p)$, the ***rank*** of $f$ at $p$ is the rank of $d_{\varphi(p)}(\psi \circ f\circ\varphi ^{-1}):\mathbb{R}^m\to \mathbb{R}^n$ at $\varphi(p)$.
---
##### Properties
> [!lemma] Theorem 1 
> Let $A_{0}\subseteq \mathbb{R}^n$, $B_{0}\subseteq \mathbb{R}^m$ be open and let $F\in C^r(A_{0},B_{0})$. If $F$ has constant rank $k$ on $A_{0}$, then given $a_{0}\in A_{0}$, there exists open subsets $A\subseteq A_{0},B\subseteq B_{0}$ and $C^r$-diffeomorphisms $G:A\to U\subseteq \mathbb{R}^n$ and $H:B\to V\subseteq \mathbb{R}^m$ s.t. 
> 1. $a_{0}\in A$ and $F(a)\in B$
> 2. $U,V$ are open
> 3. $G(a_{0})=0$ and $H(F(a_{0}))=0$
> 4. we have: $$HFG^{-1}(x_{1},\dots,x_{n})=(x_{1},\dots,x_{k},0, \dots,0)$$

> [!proof]+
> Altering $G,H$ with translations if necessary, we may assume that $a_{0}=0$ as well as $F(a_{0})=0$. 