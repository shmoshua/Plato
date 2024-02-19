#Definition #FunctionalAnalysis 

> [!definition]
> A **$\mathbb{C}$-algebra** is a $\mathbb{C}$-vector space $A$ endowed with a bilinear map $\cdot:A\times A\to A, (x,y)\mapsto xy$ s.t. 
> 1. **associativity**: $(xy)z=x(yz)$ for all $x,y,z\in A$

- **Related definition**: An algebra $A$ is ***unital***, if there exists $0\neq e\in A$ s.t. $xe=ex=x$ for all $x\in A$.
- **Related definition**: An algebra $A$ is ***abelian***, if $xy=yx$ for all $x,y\in A$. 
---
##### Properties
> [!lemma] Proposition 1 (Embedding a non-unital algebra to unital)
> Let $A$ be a non-unital algebra. Then, we have for $A_{I}:=A\times \mathbb{C}$ with $(x,\lambda)(y,\mu)=(xy+\mu x+\lambda y, \lambda \mu)$,
> 1. $A_{I}$ is unital with $(0,1)$ as unit.
> 2. The map: $$\begin{array}{cccc} {}&{A}&\to&{A_{I}}\\&{a} &\mapsto & {(a,0)} \end{array}{}$$is an injective algebra homomorphism.
