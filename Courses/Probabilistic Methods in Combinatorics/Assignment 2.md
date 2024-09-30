#Series #ProbabilisticMethods 

#### Problem 1
Let $H$ be a hypergraph with $m\leq 4^{n-1} / 3^n$ edges. We will color each vertex uniformly randomly. Then, for an edge $e$, let $A_{e}$ denote the event that $e$ contains all $4$ colors. We have that:
   $$\mathbb{P}(A_{e})=4!\cdot\left\{\begin{matrix}n\\4\end{matrix} \right\}\cdot \frac{1}{4^n}=\frac{1}{4^n}\sum_{r=0}^{4}(-1)^r {4 \choose r } (4-r)^n=\frac{1}{4^n}\left( 4^n-4\cdot 3^n+6\cdot 2^n-4 \right)> 1-\frac{3^n}{4^{n-1}} $$Therefore, $$\mathbb{P}(\exists \text{edge that has }\leq 3\text{ colors})=\mathbb{P}\left( \bigcup_{e\in E}^{}A_{e}^c \right) < m\cdot \frac{3^n}{4^{n-1}} =1$$This shows that the coloring of $H$ is valid with positive probability and hence there exists such a coloring.
---
#### Problem 2
