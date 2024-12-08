#Definition #Algorithms 

> [!definition]
> For a given cost metric $c$ and an optimal algorithm $\text{OPT}$, a ***fully polynomial time approximation scheme (FPTAS)*** for a minimization problem is an algorithm $\mathcal{A}$ s.t. 
> 1. $c(\mathcal{A}(I,\varepsilon))\leq(1+\varepsilon)\cdot c(\text{OPT}(I))$ for all inputs $I$ and $\varepsilon>0$.
> 2. $\mathcal{A}$ runs in $\text{poly}\left( \left| I \right|, 1/\varepsilon \right)$ time.

^a99681

---
