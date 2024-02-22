#Definition #FunctionalAnalysis 

> [!definition]
> A **$\mathbb{C}$-algebra** is a $\mathbb{C}$-vector space $A$ endowed with a bilinear map $\cdot:A\times A\to A, (x,y)\mapsto xy$ s.t. 
> 1. **associativity**: $(xy)z=x(yz)$ for all $x,y,z\in A$

- **Related definition**: An algebra $A$ is ***unital***, if there exists $0\neq e\in A$ s.t. $xe=ex=x$ for all $x\in A$.
- **Related definition**: An algebra $A$ is ***abelian***, if $xy=yx$ for all $x,y\in A$. 
- **Related defintion**: An element $x$ in an unital $\mathbb{C}$-algebra $A$ is ***invertible*** if there exists $y\in A$ s.t. $xy=yx=e$. Then, $y$ is denoted $x ^{-1}$. We denote the set of invertible elements of $A$ as $G(A)$.
---
##### Properties
> [!lemma] Proposition 1 (Embedding a non-unital algebra to unital)
> Let $A$ be a non-unital algebra. Then, we have for $A_{I}:=A\times \mathbb{C}$ with:
> $$\begin{array}{cccc} &{A_{I}\times A_{I}}&\to&{A_{I}}\\&{((x,\lambda),(y,\mu))} &\mapsto & {(xy+\mu x+\lambda y, \lambda \mu)} \end{array}{}$$ Then,
> 1. $A_{I}$ is unital with $(0,1)$ as unit.
> 2. The map: $$\begin{array}{cccc} {\varphi:}&{A}&\to&{A_{I}}\\&{a} &\mapsto & {(a,0)} \end{array}{}$$is an injective algebra homomorphism.

> [!proof]-
> We have:
> 1. $$(x,\lambda)(0,1)=(x,\lambda),\quad (0,1)(x,\lambda)=(x,\lambda)$$
> 2. Injectivity is clear. Then,$$\varphi(xy)=(xy,0)=(x,0)(y,0)=\varphi(x)\varphi(y)$$
---
> [!lemma] Lemma 2
> Let $A$ be a unital $\mathbb{C}$-algebra and $x\in A$. If $x$ is invertible, $x ^{-1}$ is unique.
> 2. $G(A)$ forms a group with product.