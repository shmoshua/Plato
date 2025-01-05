#Definition #Topology 

> [!definition]
> Let $(X_{i})_{i\in I}$ be an indexed family of [[Topological Space|topological spaces]]. Let $x_{i}\in X_{i}$ for all $i\in I$. 
> 1. The ***wedge sum*** of $(X_{i})_{i\in I}$ is given by: $$\bigvee_{i\in I}^{} X_{i}:=\bigsqcup_{i\in I}^{}X_{i} /_{\sim}$$where $\sim$ is the equivalence relation s.t. $x_{i}\sim x_{j}$ for all $i,j\in I$

^56869a

- **Related definition**: For $i\in I$,  ^6c44a6
	1. the ***inclusion*** $i_{i}:X_{i}\to \bigvee_{i\in I}X_{i}$.
	2. the **projection** $p_{i}:\bigvee_{i\in I}X_{i}\to X_{i}$ s.t. for every $x\notin X_{i}$, $p(x)=x_{i}$ and $p_{i}|_{X_{i}}=\text{id}|_{X_{i}}$. 
---
##### Examples
> [!h] Example 1 (Bouquet of Spheres)
> Let $S_{1}^\mathbf{n}\dots,S^n_{k}$ be spheres. Then, 
> 1. $X:=S_{1}^n\vee \dots \lor S^n_{k}$ is called a ***bouquet of $k$ spheres***.

^789a47

---
