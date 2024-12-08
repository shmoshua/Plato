#Definition #Algorithms 

> [!definition]
> For a given cost metric $c$ and an optimal solution $\text{OPT}$, a ***fully polynomial randomized approximation scheme (FPRAS)*** for a minimization problem is a Monte Carlo algorithm $\mathcal{A}$ s.t. for all inputs $I$ and $\varepsilon>0$,
> 1. $P(\left| c(\mathcal{A}_{\varepsilon}(I))-c(\text{OPT}(I)) \right|\geq \varepsilon \cdot c(\text{OPT}(I)))\leq \frac{1}{4}$
> 2. $\mathcal{A}$ runs in $\text{poly}\left( \left| I \right|, \frac{1}{\varepsilon} \right)$ time.

^a1e36b
