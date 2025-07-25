#Definition #AlgebraicTopology 

> [!definition]
> A ***graded group*** is a [[group]] $G$ s.t. $G=\bigoplus_{i\in \mathbb{Z}}G_{i}$ for groups $G_{i}$.

^1e4733

- **Related definition**: For graded groups $A$ and $B$ with a homomorphism $f:A_{i}\to B_{i}$, $f$ is ***graded of degree*** $d\in \mathbb{Z}$ if $f(A_{i})\subseteq B_{i+d}$ for all $i$. We write $\left| f \right|:= d$. ^40ff8e
- **Related definition**: For $d\in \mathbb{Z}$, $\mathcal{A}[d]$ is a graded group with $\mathcal{A}[d]_{i}:=A_{i+d}$.
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

---
> [!lemma] Proposition 2
> Let $A\overset{ f }{ \to } A'\overset{ f' }{ \to } A''$ and $B\overset{ g }{ \to } B'\overset{ g' }{ \to } B''$ be graded homomorphisms between graded abelian groups. Then, 
> 1. $(f'\circ f)\otimes(g' \circ g)=(-1)^{\left| f \right|\left| g' \right|}(f'\otimes g')\circ(f\otimes g)$.

^47da0d

> [!proof]-
> We have that: 
> 1. For $a\in A_{i}$ and $b\in B_{j}$, $$\begin{aligned}(f'\circ f)\otimes(g' \circ g)(a\otimes  b)&=(-1)^{\left| g'\circ  g \right| \left| a \right| }(f'\circ  f)(a)\otimes  (g'\circ  g)(b)\\&=(-1)^{(\left| g' \right|+\left| g \right| ) \left| a \right| }(f'\circ  f)(a)\otimes  (g'\circ  g)(b)\end{aligned}$$ and $$\begin{aligned}(f'\otimes g')\circ(f\otimes g)(a\otimes  b)&=(-1)^{\left| g \right| \left| a \right| }(f'\otimes  g')(f(a)\otimes  g(b))\\&=(-1)^{\left| g \right| \left| a \right|+\left| g' \right| \left| f(a) \right|  }(f'\circ  f)a\otimes  (g'\circ  g)(b)\\&=(-1)^{\left| g \right| \left| a \right|+\left| g' \right| \left| a \right|+\left| g' \right| \left| f \right|   }(f'\circ  f)a\otimes  (g'\circ  g)(b)\end{aligned}$$This proves the statement.

^6b0b32
