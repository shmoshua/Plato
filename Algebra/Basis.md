#Definition #Algebra

> [!definition]
> Let $M$ be a finitely-generated $R$-[[module]]. 
> 1. A ***basis*** of $M$ is a family $(m_{1},\dots,m_{n})\subseteq M$ s.t. $$R^n\to M,\quad (a_{1},\dots,a_{n})\mapsto a_{1}m_{1}+\dots+a_{n}m_{n}$$is an isomorphism.

^937cda

- **Related definition**: If $M$ has a basis, it is called a ***free module***. ^2b5c98

---
##### Properties
> [!lemma] Proposition 1
> Let $R$ be an [[integral domain]]. Let $I\unlhd R$ be non-zero. TFAE:
> 1. $I$ is principal.
> 2. $I$ is a free $R$-module.

> [!proof]+
> We have that:
> 1. (1=>2): Let $I=(b)$. Consider the map: $$\varphi:R\to I,\quad a\mapsto ab$$Then, this is well-defined and $\varphi\in \text{Hom}_{R}(R,I)$. Further, it is bijective as $R$ is an integral domain. Hence, $b$ is a basis of $I$. 
> 2. (2=>1): Let $(m_{1},\dots,m_{n})$ be a basis of $I$ with isomorphism $\varphi$, i.e. $$\varphi:R^{n}\to I,\quad (m_{1},\dots,m_{n})\mapsto $$
---
##### Examples
> [!h] Example 1 
> Let $I$ is a non-trivial ideal in $R$. Then,
> 1. $R / I$ is not free. 

> [!proof]-
> Consider the map: $$\varphi:R^n \to R / I,\quad (a_{1},\dots,a_{n})\mapsto a_{1}m_{1}+\dots+a_{n}m_{n}$$for some $m_{1},\dots,m_{n}\in R / I$. Then, $\varphi(0,\dots,0)=\varphi(a,0,\dots,0)$ for every $a\in I$ and $\varphi$ can never be an isomorphism.