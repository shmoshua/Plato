#Definition #RepresentationTheory 

> [!definition]
> For a monoid $M$, a ***$M$-graded algebra*** is an [[associative algebra]] $A$ that admits the following decomposition, $A=\bigoplus_{m\in M}A_{m}$ s.t. it holds that: $$A_{m}\cdot A_{n}\subseteq A_{m+n}$$
- **Related definition**: If $A_{n}$ is finite-dimensional, one considers the ***Hilbert series*** defined as: $$h_{A}(t):=\sum_{n= 0}^{\infty}\text{dim}(A_{n})t^n$$
---
##### Examples
> [!h] Example 1
> For a field $K$, 
> 1. $A:=K[X]$ has the Hilbert series: $$h_{A}(t)=1+t+\dots+t^n+\dots=\frac{1}{1-t}$$
> 2. $A:=K\langle x_{1},\dots,x_{m}\rangle$ has the Hilbert series: $$h_{A}(t)=1+mt+\dots+m^nt^n+\dots=\frac{1}{1-mt}$$
> 3. $A$ is the [[exterior algebra]] $\land_{K}[x_{1},\dots,x_{m}]$ generated over some field $K$ by $x_{1},..,x_{m}$ with the defining relations $x_{i}x_{j}+x_{j}x_{i}=0$ and $x^{2}_{i}=0$ for all $i,j$.
> 	$$h_{A}(t)=1+mt+{m\choose 2}t^{2}+\dots=(1+t)^m$$
> 4. $A$ is the [[path algebra]] $P_{Q}$ of a [[quiver]] $Q$. Let $M_{Q}\in \mathbb{R}^{\left| I \right|\times \left| I \right|}$ be the adjacency matrix of $Q$. Then, 
> 	$$h_{A}(t)=\sum_{n=0}^{\infty}\text{tr}(OM_{Q}^n)t^n=\text{tr}\left( O\sum_{n=0}^{\infty}M_{Q}^n t^n\right) =\text{tr}(O(I-M_{Q}t)^{-1})$$where $O$ is a matrix filled with ones.
---
