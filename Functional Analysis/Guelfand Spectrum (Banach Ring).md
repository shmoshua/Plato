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
> 1. We first show that $\text{ker }x$ is an ideal. Let $f,g\in \text{ker }x$. Then, $$0\leq x(f+g)\leq x(f)+x(g)=0$$Further, for any $h\in A$, $x(fh)=x(f)x(h)=0$. Hence, $\text{ker }x$ is an ideal.
>    
>    Let $x(fg)=0$. Then, $0=x(fg)=x(f)x(g)$ and $x(f)=0$ or $x(g)=0$. This shows that $\text{ker }x$ is prime. Further, let $f\in A \backslash \text{ker }x$. Then, $x(f)>0$ and by choosing $r:=x(f) / 2$, we have that: $$N(f,r)\subseteq A \backslash \text{ker }x$$Indeed, for any $x(f-g)<r$, we have that: $$x(f)\leq x(f-g)+x(g)\leq x(f) / 2+x(g)$$and $0<x(f) / 2\leq x(g)$ and $g\in A \backslash \text{ker } x$. 
>    
>    
> 2. Then, $\text{ker }x=\{ f\in A:x(f)=0 \}$. 
> 
---
