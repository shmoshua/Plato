#Definition #Topology 

> [!definition]
> A ***metric space*** is a pair $(X,d)$ for a set $X$ and a real function $d:X\times X \to \mathbb{R}$ called the ***metric*** such that:
> 1. **Non-negativity**: $d(x,y) \geq 0$ for all $x,y\in X$  
> 2. **Non-degeneracy**: $d(x,y)=0$ if and only if $x=y$.
> 3. **Symmetry**: $d(x,y)=d(y,x)$ for all $x,y\in X$
> 4. **Triangle Inequality**: $d(x,z)\leq d(x,y)+d(y,z)$ for all $x,y,z\in X$ (Triangle inequality)
> 
- **Related Definition**: $(X,d)$ is ***complete***, if every [[Cauchy Sequence| Cauchy sequence]] of points in $X$ has a limit that is also in $X$.
---
##### Properties
> [!lemma] Proposition 1
> Let $(X,d)$ be a complete metric space. For a subset $A \subseteq X$, the following are equivalent: 
> 1. the closure $\overline{A}$ of $A$ is compact.
> 2. $A$ is totally bounded, i.e. for all $\varepsilon>0$, there exists a finite set $F \subseteq A$ s.t. $$A\subseteq \bigcup_{x\in F}^{}\overline{B(x,\varepsilon)}$$

> [!proof] Proof Missing
---
##### Related Definitions
- [[Topology of Metric Spaces]]
---
##### Examples
- [[Discrete Metric Space|Discrete metric space]]
