#Definition #FunctionalAnalysis #Algebra 

> [!definition]
> Let $A$ be a commutative [[Banach ring]].
> 1. the ***spectrum*** $\widehat{A}$ of $A$ is the set of all [[Banach Ring|bounded]] [[Seminorm|multiplicative seminorms]] of $A$ endowed with the [[initial topology]] of $\{ \varphi_{f} \}_{f\in A}$ where:$$\varphi_{f}:\widehat{A}\to \mathbb{R},\quad \left| \cdot  \right| \mapsto \left| f \right|$$
- **Related definition**: The ***Guelfand transform*** is the map: $$\widehat{}:A\to \prod_{x\in \widehat{A}}^{}H(x),\quad f\mapsto (f(x))_{x\in \widehat{A}}$$where: 
	1. $H(x)$ is the closure of $\text{Quot}(A / \text{ker }x)$ w.r.t the valuation on $A / \text{ker }x$ and 
	2. $f(x)\in H(x)$ is the image of $f\in A$ in $A \to A / \text{ker }x \hookrightarrow \text{Quot}(A / \text{ker }x)\hookrightarrow H(x)$.
---
##### Properties
> [!lemma] Theorem 1
> Let $A$ be a commutative Banach ring. 
> 1. $\widehat{A}$ is a non-empty compact Hausdorff space.

> [!proof]+


---
> [!lemma] Theorem 2 (Guelfand Transform)
> Let $A$ be a commutative Banach ring. Let $x\in \widehat{A}$:
> 1. $\text{ker }x\unlhd  A$ is a closed [[prime ideal]] of $A$.
> 2. $x(f)$ only depends on $[f]\in A / \text{ker }x$.
> 3. the valuation on $A / \text{ker }x$ extends to a valuation on $F:=\text{Quot}(A / \text{ker }x)$.

> [!proof]+
> Let $x\in \widehat{A}$.
> 1. 
> 2. Then, $\text{ker }x=\{ f\in A:x(f)=0 \}$. 
> 
---
