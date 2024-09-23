#Definition #Algorithms 

> [!definition]
> Let $\mathcal{U}:=\{ e_{1},\dots,e_{n} \}$ and $S_{1},\dots,S_{m}\subseteq \mathcal{U}$ with costs $c_{i}:=\text{cost}(S_{i})>0$. 
> 1. The ***minimum vertex cover problem*** aims to find a collection of subsets with union $\mathcal{U}$that has minimum total cost, i.e. $\arg\min_{J\subseteq[m],\bigcup_{j\in J}^{}S_{j}=\mathcal{U}}\sum_{j\in J}^{}c_{j}$

^2ed1e3

- **Remark**: We can represent the problem into a bipartite graph where on the left we have the sets $S_{1},\dots,S_{m}$ and $\mathcal{U}$ on the right, indicating the element relation. 
---
> [!lemma] Theorem 1 (Greedy Algorithm)
> The greedy algorithm works as:
> 1. Pick the set $S_{i}$ that minimizes price per item, i.e. $\text{ppi}(S_{i}):=\frac{c_{i}}{\left| S_{i} \right|}$.
> 2. Remove elements in $S_{i}$ from the universe. 
> 3. Repeat until all elements are covered (with recomputation of $\text{ppi}$)
> 
> The greedy algorithm gives 

> [!proof]+
> Let $\text{OPT}\subseteq [m]$ be the optimal solution where $O_{1},\dots,O_{r}$ denotes the sets $S_{i}$ in the chosen order. Then, 
> 1. **Claim 1: $\text{ppi}(O_{1})\leq \text{cost}(\text{OPT}) / n$.**
> 	Assume otherwise. Then, for any set $S_{i}$, $\text{ppi}(S_{i})> \text{cost}(\text{OPT}) / n$. Let $\mathcal{V_{i}}\subseteq \text{OPT}$ be the subsets that contain $e_{i}$ (which is non-empty by assumption), then: $$\text{cost}(\text{OPT})=\sum_{i\in [n]}^{} \frac{1}{\left| \mathcal{V}_{i} \right| }\sum_{O_{j}\in \mathcal{V_{i}}}^{}\frac{\text{cost}(O_{j})}{\left| O_{j} \right| } \geq \text{ppi}(S_{i})$$
>2. **Claim 2: Greedy picks a solution with cost $\leq H_{n}\cdot \text{cost}(\text{OPT})$** where $H_{n}$ is the $n$-th Harmonic number, i.e. $H_{n}:=\sum_{i=1}^{n}1 / i=\ln n+O(1)$.
> 	  1. If $n=1$, the claim holds.
> 	  2. If $n>1$, then let the greedy algorithm pick a set $S_{i}$ of size $k$. Then, $$\begin{align}\text{cost}(\text{GREEDY})&\leq k\cdot \frac{\text{cost}(\text{OPT})}{n}+\text{cost}(\text{GREEDY}')\\&\leq \frac{k}{n}\text{cost}(\text{OPT})+H_{n-k}\cdot  \underbrace{ \text{cost}(\text{OPT}(P')) }_{ \leq \text{cost}(\text{OPT}) }\\&\leq\text{cost}(\text{OPT})\left( k / n+H_{n-k} \right) \\&\leq \text{cost}(\text{OPT})\cdot H_{n}\end{align}$$

- **Remark**: It is $\mathcal{NP}$-hard to find a $$