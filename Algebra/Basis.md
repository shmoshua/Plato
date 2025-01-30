#Definition #Algebra

> [!definition]
> Let $M$ be a finitely-generated $R$-[[module]]. 
> 1. A ***basis*** of $M$ is a family $(m_{1},\dots,m_{n})\subseteq M$ s.t. $$R^n\to M,\quad (a_{1},\dots,a_{n})\mapsto a_{1}m_{1}+\dots+a_{n}m_{n}$$is an isomorphism.

^937cda

- **Related definition**: If $M$ has a basis, it is called a ***free module***. ^2b5c98
- **Related definition**: the ***rank*** of a free module $M$, $\text{rk }M$ is defined as the number of elements in the basis.  ^99a3cc

---
##### Properties
> [!lemma] Proposition 1
> Let $R$ be an [[integral domain]]. Let $I\unlhd R$ be non-zero. TFAE:
> 1. $I$ is principal.
> 2. $I$ is a free $R$-module.

^350fd6

> [!proof]-
> We have that:
> 1. (1=>2): Let $I=(b)$. Consider the map: $$\varphi:R\to I,\quad a\mapsto ab$$Then, this is well-defined and $\varphi\in \text{Hom}_{R}(R,I)$. Further, it is bijective as $R$ is an integral domain. Hence, $b$ is a basis of $I$. 
> 2. (2=>1): Let $(m_{1},\dots,m_{n})$ be a basis of $I$ with isomorphism $\varphi$, i.e. $$\varphi:R^{n}\to I,\quad (a_{1},\dots,a_{n})\mapsto a_{1}m_{1}+\dots+a_{n}m_{n}$$Then, if $n\geq 2$, $\varphi(m_{2},-m_{1}, 0\dots,0)=m_{2}m_{1}-m_{1}m_{2}=0=\varphi(0,\dots,0)$ which is a contradiction to $\varphi$ being injective. Hence, $n=1$ and $I=(m_{1})$.

^a4ee9e

---
> [!lemma] Proposition 2 (Modules and Linear Algebra)
> Let $M,N$ be a free $R$-module. 
> 1. $\text{rk }R$ is well-defined.
> 2. $\text{Hom}_{R}(M,N)\cong \text{Mat}(n\times m,R)$ where $n=\text{rk }N$ and $m=\text{rk }M$.

^1b2e6b

> [!proof]-
> We have that:
> 1. let $M\cong R^n$ as $R$-modules. Let $I\unlhd R$ be a maximal ideal. Then, $M / IM$ is a $R / I$-module from [[Module|Example 5]]. As $R / I$ is a field, $M / IM$ is a vector space and: $$\text{dim}_{R / I}M / IM=\text{dim}_{R / I} R^n / IR^n=\text{dim}_{R / I}(R / I)^n=n$$Hence, it is well-defined. 

^aaa83f

---
##### Examples
> [!h] Example 1 
> Let $I$ is a non-trivial ideal in $R$. Then,
> 1. $R / I$ is not free. 

^425e0f

> [!proof]-
> Consider the map: $$\varphi:R^n \to R / I,\quad (a_{1},\dots,a_{n})\mapsto a_{1}m_{1}+\dots+a_{n}m_{n}$$for some $m_{1},\dots,m_{n}\in R / I$. Then, $\varphi(0,\dots,0)=\varphi(a,0,\dots,0)$ for every $a\in I$ and $\varphi$ can never be an isomorphism.

^44d267
