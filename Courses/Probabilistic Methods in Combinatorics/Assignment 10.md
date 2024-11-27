#Series #ProbabilisticMethods 

##### Problem 1
Let $\mathcal{A}:=V_{1}\times V_{2}\times\dots \times V_{r}$. Then, for $A\in \mathcal{A}$, $X_{A}$ is the indicator variable if $A$ is an independent set. Therefore, we want to show that $\mathbb{P}(X_{A})$

By taking out vertices, we may assume that $\left| V_{i} \right|:=\left\lceil 2ed\right\rceil$. Let $X$ be a random set formed by picking an element from each set uniformly randomly. Then, for $e\in E$, let $A_{e}$ denote the event that $e\in X$. Let $e=\{ u,v \}\in E$ where $u\in V_{i}$ and $v\in V_{j}$. $$\mathbb{P}(A_{uv})=\begin{cases}0&i=j\\\left( \frac{1}{\lceil 2ed\rceil } \right)^2  &i\neq j\end{cases}$$ 