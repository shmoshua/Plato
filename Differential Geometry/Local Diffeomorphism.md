#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]]. A map $f:M\to N$ is called a ***local diffeomorphism*** if 
> 1. every $p\in M$ has a neighborhood $U\ni p$ s.t. $f(U)$ is open and $f|_{U}$ is a [[diffeomorphism]].
---
##### Properties

> [!lemma] Theorem 1 (Inverse Function Theorem for Manifolds)
> Let $M,N$ be smooth manifolds and $F\in C^\infty(M,N)$. Further, let $p\in M$. If $d_{p}F$ is invertible, 
> 1. there exist connected neighborhoods $U_{0}\ni p$ and $V_{0}\ni F(p)$ s.t. $F|_{U_{0}}:U_{0}\to V_{0}$ is a [[diffeomorphism]]. 

> [!proof]+
> We naturally have that $m=n$ as $d_{p}F$ is invertible. Choose chart $(U,\varphi)$ and $(V,\psi)$ at $p$ and $F(p)$ with $F(U)\subseteq V$. Let $x_{0}:=\varphi(p)$ and $y_{0}:=\psi(F(p))$. Then, we have that:  
> $$d_{x_{0}}(\psi \circ F\circ \varphi ^{-1})=d_{F(p)}\psi\circ d_{p}F\circ d_{x_{0}}\varphi ^{-1}$$
> is invertible at $x_{0}$. Therefore, by [[Smooth Function|Inverse Function Theorem]], there exists an open neighborhood $x_{0}\in \tilde{U}\subseteq\varphi(V)$ and a diffeomorphism $\alpha:\tilde{U}\to\alpha(\tilde{U})$. By setting $U:=\varphi ^{-1}(\tilde{U})$, we have that: $$F=\psi ^{-1}\circ  \alpha \circ \varphi$$is a diffeomorphism.