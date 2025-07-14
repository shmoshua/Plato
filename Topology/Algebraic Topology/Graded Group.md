#Definition #AlgebraicTopology 

> [!definition]
> A ***graded group*** is a [[group]] $G$ s.t. $G=\bigoplus_{i\in \mathbb{Z}}G_{i}$ for groups $G_{i}$.

^1e4733

- **Related definition**: For graded groups $A$ and $B$ with a homomorphism $f:A_{i}\to B_{i}$, $f$ is ***graded of degree*** $d\in \mathbb{Z}$ if $f(A_{i})\subseteq B_{i+d}$ for all $i$. We write $\left| f \right|:= d$. ^40ff8e
---
##### Properties
> [!lemma] Proposition 1 (Tensor Products of Graded Groups)
> Let $A,B$ be graded groups. 
> 1. The group defined as: $$(A\otimes B)_{n}:=\bigoplus _{i+j=n}A_{i}\otimes  B_{j}$$forms a graded group.
> 2. If $f:A\to A'$ and $g:B\to B'$ are graded homomorphisms, then: $f\otimes g: A\otimes  B\to A'\otimes  B'$ is graded s.t. 
> 	1. $\left| f\otimes g \right|=\left| f \right|+\left| g \right|$ and 
> 	2. $(f\otimes g)(a\otimes b)=(-1)^{\left| g \right|\left| a \right|}f(a)\otimes g(b)$ for all $a\in A_{i}$ and $b\in B_{j}$.

^200a6c

> [!proof]-
> We have that:
> 1. Obvious.
> 2. We have that: $$\begin{aligned}(f\otimes  g)((A\otimes  B)_{n})&=(f\otimes  g)(\bigoplus _{i+j=n}A_{i}\otimes  B_{j})=\bigoplus _{i+j=n}f(A_{i})\otimes  g(B_{j})\\&\subseteq \bigoplus_{i+j=n}A'_{i+\left| f \right| }\otimes  B'_{j+\left| g \right| }\subseteq \bigoplus_{i+j=n+\left| f \right| +\left| g \right| }A'_{i }\otimes  B'_{j}=(A'\otimes B')_{n+\left| f \right| +\left| g \right| }\end{aligned} $$Further, $$(f\otimes  g)(a\otimes  b)=$$

^ddd5d1

