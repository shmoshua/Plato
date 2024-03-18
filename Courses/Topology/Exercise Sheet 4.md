#Series #Topology 

> [!def] Problem 1
> Let $X$ be a topological space. Show that $X$ is Hausdorff if and only if, for every $x\in X$, we have $$\bigcap_{x\in U}^{}\overline{U}=\{ x \}$$ where $U$ runs over all neighborhoods of $x$.

Assume that $X$ is Hausdorff. Indeed, $\{ x \}\subseteq \bigcap_{x\in U}^{}\overline{U}$ is trivial. Let $y\in \bigcap_{x\in U}^{}\overline{U}$ and assume $y\neq x$. Then, there exists disjoint open neighborhoods $U,V$ of $x,y$, respectively. However, $y\in \overline{U}$ by assumption and it follows that $U\cap V\neq\varnothing$, which is a contradiction. This shows the inclusion.

Conversely, assume that the condition holds. We will show that $X$ is Hausdorff. Let $x,y\in X$ s.t. $x\neq y$. Then, as $\bigcap_{x\in U}^{}\overline{U}=\{ x \}$, there exists open $U\ni x$ s.t. $y\notin\overline{U}$, i.e. there exists an open neighborhood $V$ of $y$ s.t. $U\cap V=\varnothing$. This proves the statement.

---
> [!def] Problem 2
> Let $X$ be a topological space. 
> 1. If $X$ is a Hausdorff space, show that a filter $\mathcal{F}$ on $X$ which converges has a unique limit.
> 2. Conversely, suppose a convergent filter $\mathcal{F}$ on $X$ always has a unique limit. Show that $X$ is a Hausdorff space. 

We have: 
1. Assume that $X$ is Hausdorff and that $\mathcal{F}$ converges to $x$ and $y$ s.t. $x\neq y$. Let $U,V$ be the disjoint open neighborhoods of $x,y$ and by convergence, there exists $W\in \mathcal{F}$ s.t. $W\subseteq U$ and $W\subseteq V$. (this is given as the filter is closed under intersection). As $\varnothing\notin \mathcal{F}$, we have that $U\cap V\neq \varnothing$, which is a contradiction.