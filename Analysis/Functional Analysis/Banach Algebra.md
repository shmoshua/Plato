#Definition #FunctionalAnalysis 

> [!definition] 
> A ***Banach algebra*** is a [[C-Algebra|$\mathbb{C}$-algebra]] $B$ endowed with a norm $\|\cdot\|$ s.t. 
> 1. $(B,\|\cdot\|)$ is a [[Banach space]] and
> 2. $\left\| xy \right\|\leq\|x\|\|y\|$ for all $x,y\in B$
---
##### Properties
> [!lemma] Proposition 1 
> Let $B$ be a non-unital Banach algebra. Then, 
> 1. $B_{I}:=B\times \mathbb{C}$ per [[C-Algebra|this construction]] with $\left\| (x,\lambda) \right\|=\|x\|+\left| \lambda \right|$ is a unital Banach algebra. 
> 2. The map: $$\begin{array}{cccc} &{B}&\to&{B_{I}}\\&{x} &\mapsto & {(x,0)} \end{array}{}$$is isometric.
---
> [!lemma] Proposition 2
> Let $A$ be a [[C-Algebra|unital algebra]] with a norm $\|\cdot\|$ s.t.
> 1. $(A,\|\cdot\|)$ is a [[Banach space]] and
> 2. $A\times A \to A, (x,y)\mapsto xy$ is continuous in each variable. 
> 
> Then, there exists an [[Equivalence of Norms|equivalent norm]] $\|\cdot\|_{\text{new}}$ on $A$ that makes it a Banach algebra.
- For Hilbert space $\mathcal{H}$, $\mathcal{B}(\mathcal{H})$ is a Banach algebra.