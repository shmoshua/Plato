#Definition #Algorithms 

> [!definition]
> Let $\mathcal{U}:=\{ e_{1},\dots,e_{n} \}$ and $\mathcal{S}=\{ S_{1},\dots,S_{m} \}\subseteq \mathcal{P}(\mathcal{U})$ with a cost function $c:\mathcal{S}\to \mathbb{R}_{>0}$. costs $c_{i}:=\text{cost}(S_{i})>0$. 
> 1. The ***minimum vertex cover problem*** aims to find a collection of subsets $\mathcal{}$ with union $\mathcal{U}$that has minimum total cost, i.e. $\arg\min_{J\subseteq[m],\bigcup_{j\in J}^{}S_{j}=\mathcal{U}}\sum_{j\in J}^{}c(S_{j})$
> 2. Let $G=(V,E)$ be a [[graph]] with vertex weights $c:V\to \mathbb{R}_{>0}$. the ***minimum vertex cover*** aims to find: $$S_{\text{OPT}}\in\underset{ S\subseteq V,\forall e\in E: e\cap S\neq \varnothing }{ \arg\min }c(S)$$

^2ed1e3

- **Remark**: We can represent the problem into a bipartite graph where on the left we have the sets $S_{1},\dots,S_{m}$ and $\mathcal{U}$ on the right, indicating the element relation.  ^0eb03c
---
> [!lemma] Theorem 1 (Greedy Algorithm)
> The greedy algorithm works as:
> 1. Pick the set $S_{i}$ that minimizes price per item, i.e. $\text{ppi}(S_{i}):=\frac{c_{i}}{\left| S_{i} \right|}$.
> 2. Remove elements in $S_{i}$ from the universe. 
> 3. Repeat until all elements are covered (with recomputation of $\text{ppi}$)
> 
> The greedy algorithm gives a $H_{n}$-approximation for $H_{n}:=\sum_{i\in [n]}^{}1 / i=\ln n+O(1)$.

^eb92be

> [!proof]-
> Let $\text{OPT}\subseteq [m]$ be the optimal solution where $O_{1},\dots,O_{r}$ denotes the sets $S_{i}$ in the chosen order. Then, 
> 1. **Claim 1: $\text{ppi}(O_{1})\leq \text{cost}(\text{OPT}) / n$.**
> 	Assume otherwise. Then, for any set $S_{i}$, $\text{ppi}(S_{i})> \text{cost}(\text{OPT}) / n$. Let $\mathcal{V_{i}}\subseteq \text{OPT}$ be the subsets that contain $e_{i}$ (which is non-empty by assumption), then: $$\text{cost}(\text{OPT})=\sum_{i\in [n]}^{} \frac{1}{\left| \mathcal{V}_{i} \right| }\sum_{O_{j}\in \mathcal{V_{i}}}^{}\frac{\text{cost}(O_{j})}{\left| O_{j} \right| } \geq \text{ppi}(S_{i})$$
>2. **Claim 2: Greedy picks a solution with cost $\leq H_{n}\cdot \text{cost}(\text{OPT})$**.
> 	  1. If $n=1$, the claim holds.
> 	  2. If $n>1$, then let the greedy algorithm pick a set $S_{i}$ of size $k$. Then, $$\begin{align}\text{cost}(\text{GREEDY})&\leq k\cdot \frac{\text{cost}(\text{OPT})}{n}+\text{cost}(\text{GREEDY}')\\&\leq \frac{k}{n}\text{cost}(\text{OPT})+H_{n-k}\cdot  \underbrace{ \text{cost}(\text{OPT}(P')) }_{ \leq \text{cost}(\text{OPT}) }\\&\leq\text{cost}(\text{OPT})\left( k / n+H_{n-k} \right) \\&\leq \text{cost}(\text{OPT})\cdot H_{n}\end{align}$$

^d320dd

- **Remark** (Steurer): It is $\mathcal{NP}$-hard to find a $(1-\varepsilon)\cdot H_{n}$-approximation for any constant $\varepsilon>0$.  ^4d9187

---
> [!lemma] Theorem 2 (Linear Programming)
> Let $\{ x_{v} \}_{v\in V}\subseteq \mathbb{R}$ be the solution of the optimization problem $$\begin{align}\text{min}\quad&\sum_{v\in V}^{}x_{v}\cdot c(v)\\\text{subject to}\quad &x_{u}+x_{v}\geq 1 &&\forall \{ u,v \}\in E\\&0\leq x_{v}\leq 1&&\forall v\in V \end{align}$$Then, let $y_{v}\in \{ 0,1 \}$ where $y_{v}=\mathbb{1}_{\left\{  x_{v}\geq \frac{1}{2}  \right\}}$. We have:
> 1. $\{ y_{v} \}_{v\in V}$ is also feasible in the LP.

> [!proof]+
> We have that:
> 1. **Claim 1**: $y_{v}\leq 2x_{v}$ for all $v\in V$. 
> 
> Therefore, $$\sum_{v\in V}^{}y_{v}\cdot c(v)\leq 2\cdot \sum_{v\in V}^{}x_{v}\cdot c(v)\leq 2\cdot c(S_{\text{OPT}})$$