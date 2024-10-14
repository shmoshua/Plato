#Series #Algorithms 

#### 1. Covering Cliques

**Part 1**: We define $z_{e}\in \{ 0,1 \}$ for all $e\in E$ to denote whether $e\in F$. Then, 
$$
\begin{aligned}\text{min}\quad &\sum_{e\in E}^{}z_{e}\\\text{subject to}\quad &\sum_{e\in {V_{i}\choose 2}\cap E}z_{e}\geq s&&\forall i\in [\ell]\\&z_{e}\in \{ 0,1 \}&&\forall e\in E\end{aligned}
$$
describes the problem as an ILP problem.

---
**Part 2**  Let $q:={k \choose 2}$. In our algorithm, let $\{z_e^*\}_{e\in E}$ be the optimal solution given by solving the LP. Then, we construct $F:=\{e\in E: z_e^*\ge \frac{1}{q-s+1}  \}$. 

-  **Claim 1**:  $F$ is feasible, i.e. $\left| {V_{i} \choose 2}\cap F \right|\ge s$ for all $i\in [\ell]$.
  Assume otherwise, i.e. let $i\in[\ell]$ s.t. $\left| {V_{i} \choose 2}\cap F \right|\le s-1$. Then, $$\sum_{e\in {V_{i} \choose 2}\cap E}^{}z^*_{e}< (s-1)\cdot 1+\left(\left|{V_{i} \choose 2}\cap E\right|-s+1\right)\cdot \frac{1}{q-s+1}\le (s-1)+1=s$$which is a contradiction. 


Now, for all $e\in F$, we have that $(q-s+1)z^*_e\ge 1$. Hence, 

$$\mathbb{E}[\left| F \right| ]=\sum_{e\in F}^{}1\leq(q-s+1)\sum_{e\in F}z^*_{e}=(q-s+1)\cdot |F_\text{OPT}|\leq (q+1)\cdot |F_\text{OPT}|$$This shows that our algorithm is a $\text{O}(k^2)$-approximation in expectation. Further, as we have polynomially many constraints, this is a polynomial algorithm.

---
#### 2. Graph Coloring

