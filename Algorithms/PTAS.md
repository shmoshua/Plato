#Definition #Algorithms 

> [!definition]
> For a given cost metric $c$ and an optimal algorithm $\text{OPT}$ and a parameter $\varepsilon$, a ***polynomial time approximation scheme (PTAS)*** for a minimization problem is an algorithm $\mathcal{A}_{\varepsilon}$ s.t. 
> 1. $c(\mathcal{A}_{\varepsilon}(I))\leq(1+\varepsilon)\cdot c(\text{OPT}(I))$ for all inputs $I$.
> 2. $\mathcal{A}_{\varepsilon}$ runs in $\text{poly}(\left| I \right|)$ time.

^968d36

---
