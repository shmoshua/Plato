### 1. Well-Spaced Subsets
1. **Solution 1**: Assume there is a well-spaced subset $S\subseteq V$ s.t. $\left| S \right|=k+1$ wlog. Note that for any $v\in S$, $N(v)\subseteq V \backslash S$ and $N(v)\cap N(w)=\varnothing$ for all $v,w\in S$. However, there are $3k-1$ vertices and $3k+3$ neighbors. Hence, there exists at least one vertex that is common by pigeonhole, contradiction.
   
   **Solution 2**: Let $S$ be a well-spaced subset. Then, $N(S)$ contains exactly $3\left| S \right|$ elements as any two nodes in $v,w\in S$ have disjoint neighborhood. Further, $S\cap N(S)=\varnothing$ by definition. Hence, $4\left| S \right|=\left| S\cap N(S) \right| \leq 4k$.
   
2. We describe the following Greedy algorithm. For any node $v\in V(G)$, we denote $B_{2}(v)$ as the radius $2$-ball of $v$. We construct a well-spaced subset $S$ as follows. 
   
   The key idea is as follows. At each step we choose a vertex.
   
   
   
   Let $B$ denote the set of "blocked" vertices. 
	1. In the beginning, we have $S,B=\varnothing$. Add $s_{1}:=\arg\min_{v\in V(G)}\left| B_{2}(v) \right|$ to $S$ and set $B=B_{2}(s_{1})$. 
	2. At each step, choose $s_{i}:=\arg\min_{v\in D_{1}(B)\backslash B}$
	
	
Let $S=\{ v_{1},\dots,v_{p} \}$ be the vertices in the order they were added. First, we notice that for any $v\in V(G)$, $\left| B_{2}(v) \right|\leq 1+3+6=10$. Hence, we have the following three cases:

3. Case $\left| B_{2}(v_{1}) \right|\leq 9$. Notice that for any $i\geq 2$, $v_{i}\in D_{1}(B)$. Therefore, $\left| B_{2}(v_{i})\cap \bigcup_{1\leq j< i}^{} B_{2}(v_{j})\right|\geq 2$. Further, by the definition we have that: $$\left| B_{2}(v_{i}) \backslash \bigcup_{1\leq j<i}^{}B_{2}(v_{j})\right|\leq 8,\quad \forall i\geq 2 $$Therefore, $$4k= \left| \bigcup_{i}^{}B_{2}(v_{i}) \right| =\sum_{i\in[p]}^{}\left| B_{2}(v_{i}) \backslash \bigcup_{1\leq j<i}^{}B_{2}(v_{j})\right|\leq 8p +1$$However as $4k$ is even and $p$ is an integer, $4k\leq 8p$.
4. Case $\left| B_{2}(v_{1}) \right|=10$. Then, $\left| B_{2}(v) \right|=10$ for every $v\in V(G)$ by the minimum condition. 
---
### 2. Disjoint Reward Maximization
1. (5min) We have the ILP: $$\begin{array}{rl}\text{max}&\sum_{S\in \mathcal{F}}^{}r_{S}x_{S}\\\text{subject to}&\sum_{S:i\in S}^{}x_{S}=1&\forall i\in \mathcal{X}\\&x_{S}\in \{ 0,1 \}&\forall S\in \mathcal{F}\end{array}$$We can relax this into the LP $$\begin{array}{rl}\text{max}&\sum_{S\in \mathcal{F}}^{}r_{S}x_{S}\\\text{subject to}&\sum_{S:i\in S}^{}x_{S}\leq 1&\forall i\in \mathcal{X}\\&0\leq x_{S}\leq 1&\forall S\in \mathcal{F}\end{array}$$
2. (30min) Let $x^{*}_{S}$ be the optimum for the LP. Then, $\sum_{S\in \mathcal{F}}r_{S}x^{*}_{S}\geq \text{OPT}$. Now, let $y_{S}\sim \text{Ber}(x^{*}_{S}\cdot p)$ for all $S\in \mathcal{F}$. Then, we define $\mathcal{G}:=\{ S\in \mathcal{F}:y_{S}=1 \}$. Now, from $\mathcal{G}$, we delete any subsets that are not disjoint. Let this new family be called $\tilde{\mathcal{G}}$.
   
   Now, let $S\in \mathcal{F}$ and $i\in S$. Then, $$\mathbb{E}[\left| \{ T\neq S\in \mathcal{G}:i\in T \} \right| ]=\sum_{T\neq S:T\ni i}^{}px^{*}_{S}\leq p\sum_{T:i\in T}x^{*}_{S}\leq p$$Hence, by Markov, $\mathbb{P}(\exists T\neq S\in \mathcal{G}:i\in T)\leq p$. Union bound over all the elements, we have that $\mathbb{P}(S\text{ has conflict}|S\in \mathcal{G})\leq kp$. Hence, $$\mathbb{P}(S\in {\tilde{\mathcal G}})\geq  (1-kp)p x^{*}_{S}$$Therefore, we have that: $$\mathbb{E}[r(\tilde{\mathcal{G}})]\geq  (1-kp)p\sum_{S\in \mathcal{F}}^{}r_{S }x^{*}_{S}\geq (1-kp)p \text{OPT} $$Hence, we need that $(1-kp) p \geq \frac{1}{4k}$, i.e. $(1-kp)4kp\geq 1$ and $(2kp-1)^{2}\leq 1$ and works by taking $p=\frac{1}{2k}$.

- Every subset S ∈ F has size that is at most k, and has associated with it a positive reward rS.
- **Every subset $S\in\mathcal{F}$ has at most $k$ elements, and a positive reward $r_{S}$ associated with it.**
---
### 3. Sales Tactics

- You can sell to customer j any subset Sj ⊆ [n] of the items, as long as there is no item that the customer could leave off the purchase while still attaining at least rj processing power,

- **You can sell any subset $S_{j}\subseteq[n]$ to customer $j$, as long as removing any item from $S_{j}$ drops the total processing power below $r_{j}$.** 

- There being at most C distinct item types means that there exists some set I of size |I| ≤ C such that (vi , pi) ∈ I for each item i ∈ [n].
- **There being at most $C$ distinct item types means that $I:=\{ (v_{i},p_{i}) \}_{i\in[n]}$ has at most size $C$.**

1. (30m) We have that: $$\text{DP}[i][k_{1},\dots,k_{C}]=\text{maximum value you can sell to customer 1,...,}i\text{ with }k_{a}\text{ items of type }a$$Then, let $S_{j}$ contain$$\text{DP}[i][k_{1},\dots,k_{C}]=\text{max}_{S_{j}\text{ valid}} \text{ DP}[i-1]\left[ k_{1}-\ell_{1}(S_{j}),\dots,k_{C}-\ell_{C}(S_{j})+\sum_{ i\in S_{j}}^{}v_{i} \right]$$where $S_{j}=(\ell_{1}(S_{j}),\dots,\ell_{C}(S_{j}))$. Then, $m\cdot n^{2C}$
2. (2.5hr)

---
### 4. Clumsy Skier
$K$ and $k$.