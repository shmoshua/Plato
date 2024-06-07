#Definition #DifferentialGeometry 

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]]. A map $f:M\to N$ is called a ***local diffeomorphism*** if 
> 1. every $p\in M$ has a neighborhood $U\ni p$ s.t. $f(U)$ is open and $f|_{U}$ is a [[diffeomorphism]].
---
##### Properties

> [!lemma] Theorem 1 (Inverse Function Theorem for Manifolds)
> Let $M,N$ be smooth manifolds and $F\in C^\infty(M,N)$. Further, let $p\in M$. If $d_{p}F$ is invertible, 
> 1. there exist open neighborhoods $U_{0}\ni p$ and $V_{0}\ni F(p)$ s.t. $F|_{U_{0}}:U_{0}\to V_{0}$ is a [[diffeomorphism]]. 

> [!proof]-
> We naturally have that $m=n$ as $d_{p}F$ is invertible. Choose chart $(U,\varphi)$ and $(V,\psi)$ at $p$ and $F(p)$ with $F(U)\subseteq V$. Let $x_{0}:=\varphi(p)$ and $y_{0}:=\psi(F(p))$. Then, we have that:  
> $$d_{x_{0}}(\psi \circ F\circ \varphi ^{-1})=d_{F(p)}\psi\circ d_{p}F\circ d_{x_{0}}\varphi ^{-1}$$
> is invertible at $x_{0}$. Therefore, by [[Smooth Function|Inverse Function Theorem]], there exists an open neighborhood $x_{0}\in \tilde{U}\subseteq\varphi(U)$ and a diffeomorphism $\alpha:\tilde{U}\to\alpha(\tilde{U})$. By setting $U:=\varphi ^{-1}(\tilde{U})$, we have that: $$F=\psi ^{-1}\circ  \alpha \circ \varphi$$is a diffeomorphism.
- **Corollary**: $F\in C^\infty(M,N)$ is a local diffeomorphism if and only if $d_{p}F$ is invertible for all $p\in M$.
---
> [!lemma] Proposition 2 (Elementary Properties of Local Diffeomorphisms)
> Let $M,N,P$ be smooth manifolds and $f,g:M\to N$, $h:N\to P$ be local diffeomorphisms. Then, 
> 1. $h\circ f$ is a local diffeomorphism.
> 2. $fg$ is a local diffeomorphism.
> 3. $f$ is a local homeomorphism and open.
> 7. for any $U\subseteq M$ open, $f|_{U}$ is a local diffeomorphism.
> 8. a diffeomorphism $F:M\to N$ is a local diffeomorphism.
> 9. if $f$ is bijective, $f$ is a diffeomorphism.
> 10. A map $F:M\to N$ is a local diffeomorphism if and only if for all $p\in M$, there exist charts $(U,\varphi)$ and $(V,\psi)$ at $p$ and $F(p)$ s.t. $\psi F\varphi ^{-1}$ is a local diffeomorphism.

> [!proof]-
> We have:
> 1. The composition of two invertible linear maps is invertible.
> 2. Choose the intersection $U_{p}$ and $V_{p}$ given by $f$ and $g$. 
> 3. A diffeomorphism is clearly a homeomorphism, so a local diffeomorphism is a local homeomorphism. 
>    
>    Let $U\subseteq M$ be an open set. For every $p\in U$, there exists $U_{p}\ni p$ s.t. $F(U_{p})$ is open in $N$ and $F|_{U_{p}}:U_{p}\to F(U_{p})$ is a homeomorphism. In particular, the open subset $U\cap U_{p}\ni p$ is mapped to an open subset $F(U\cap U_{p})\ni F(p)$. As $F(U\cap U_{p})$ is open in $N$. Hence, $F(U)=\bigcup_{p\in U}^{}F(U\cap U_{p})$ is open in $N$ as well. In conclusion, $F$ is an open map.
> 4. The differential of the restriction is still invertible.
> 5. We may take $M$ and $N$ as our open neighborhoods in the definition of a local diffeomorphism.
> 6. Since $f$ is a local diffeomorphism, for each $p\in M$, $f^{-1}$ is smooth at $f(p)$. Therefore, $f^{-1}$ is smooth.
> 7. If the coordinate representation $\psi F\varphi ^{-1}$ around each point is a (local) diffeomorphism, then the map is a local diffeomorphism by 1. The converse direction follows from the inverse function theorem.
---
> [!lemma] Proposition 3
> Suppose $M$ and $N$ are [[Smooth Manifold|smooth manifolds]], and $F:C^\infty(M,N)$ is a map. 
> 1. $F$ is a local diffeomorphism if and only if it is both an immersion and a submersion. 
> 2. If $m=n$ and $F$ is either an immersion or a submersion, then it is a local diffeomorphism.

> [!proof]-
> Suppose first that $F$ is a local diffeomorphism. Given $p\in M$; there is a neighborhood $U\ni p$ such that $F|_{U}$ is a diffeomorphism. Then, by [[Diffeomorphism|remark]], $d_{p}F$ is an isomorphism. Thus, $m=n$ and $F$ is both an immersion and a submersion. 
> 
> Conversely, if $F$ is both an immersion and a submersion, then $d_{p}F$ is an isomorphism at each $p\in M$; and the inverse function theorem for manifolds shows that $p$ has a neighborhood on which $F$ restricts to a diffeomorphism onto its image. This proves 1. 
> 
> To prove 2, note that if $m=n$, then either injectivity or surjectivity of $d_{p}F$ implies bijectivity, so $F$ is a submersion if and only if it is an immersion, and thus 2 follows from 1.
---
