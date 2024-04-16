#Definition #Algebra 

> [!definition]
> For a finite [[group]] $G$, the ***exponent*** of $G$, denoted as $e(G)$ is the least common multiple of the orders of the elements of $G$.
- **Remark**: $e(G)\leq \left| G \right|$ and $e(G)|\left| G \right|$
---
##### Properties
> [!lemma] Proposition 1
> Let $G$ be a finite [[abelian group]]. Then, there exists $g\in G$ s.t. $\text{ord}(g)=e(G)$. 

> [!proof]-
> As $G$ is a [[Finitely Generated Abelian Group|finitely generated abelian group]], $G\cong \mathbb{Z}_{d_{1}}\times\dots \times\mathbb{Z}_{d_{s}}$ where $d_{j}|d_{k}$. If $g\in G$, then $g^{d_{s}}=e$. This shows that $e(G)\leq d_{s}$. 
> 
> However, $G$ has a subgroup which is isomorphic to $\mathbb{Z}_{d_{s}}=\braket{ h  }$ with $\text{ord}(h)=d_{s}$. Therefore, $d_{s}|e(G)$ and $d_{s}\leq e(G)$. This shows that $d_{s}=e(G)$.