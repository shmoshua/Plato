#TCS #Definition 

> [!definition]
> Let $G:=(V,E)$ be a finite [[graph|undirected graph]] with adjacency matrix $A$. For $\beta\geq 0$ and $h\in \mathbb{R}$, 
> 1. the ***ferromagnetic ising model*** with inverse temperature $\beta$ and external field $h$, is given by $\mu_{\beta,h}\in \Delta(\{ \pm 1 \}^{V})$ where: $$\mu_{\beta,h}(x) \propto \exp\left( \frac{\beta}{2}x^\top Ax + h\braket{ x , 1 }  \right),\quad \forall x\in \{ \pm 1 \}^V$$

---
##### Properties
###### FPRAS for Partition Function
> [!definition] Definition (Even Subgraphs Representation)
> For $F\subseteq E$, we define: 
> 1. $\textsf{odd}(F):=\{ v\in V:\text{deg}_{F}(v)\text{ is odd} \}$
> 2. For $0\leq\rho\leq 1$ and $\lambda \geq 0$, we define the ***high-temperature expansion***: $$\widehat{\mu}_{\rho,\lambda}(F) \propto \rho^{\left| \textsf{odd}(F) \right| }\lambda^{\left| F \right| },\qquad \forall F\subseteq E$$with the partition function $\widehat{Z}(\rho,\lambda)=\sum_{F\subseteq E}\rho^{\left| \textsf{odd}(F) \right| }\lambda^{\left| F \right| }$