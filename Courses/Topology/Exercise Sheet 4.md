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
2. Let $x,y\in X$ with $x\neq y$. We first consider the following set: $$\mathcal{F}:=\{\varnothing\neq A\subseteq X: A\supseteq V\cap W \text{ for some open neighborhood }V\text{ of }x \text{ and }W\text{ of }y \}$$Then, by definition $\varnothing \notin \mathcal{F}$ and for $A\in \mathcal{F}$ and $A\subseteq B$, $B\in \mathcal{F}$ with the same $V\cap W$. Lastly, consider $A,B\in \mathcal{F}$ with $V_{1},W_{1}$ and $V_{2},W_{2}$ as open neighborhoods. Then, $V_{1}\cap V_{2}$, $W_{1}\cap W_{2}$ are open neighborhoods of $x,y$ respectively and $A \cap B\supseteq (V_{1}\cap V_{2})\cap(W_{1}\cap W_{2})$. Therefore, $A\cap B\in \mathcal{F}$ and $\mathcal{F}$ is a filter. 
   
   Assume for all open neighborhoods $V,W$ of $x,y$ respectively, we have $V\cap W\neq \varnothing$. Then, for all open neighborhood $U$ of $x$, then $\varnothing \neq U\cap W\subseteq U$ for any open neighborhood $W$ of $y$. It follows that $\mathcal{F}$ converges to $x$ and by symmetry to $y$. This is a contradiction to $\mathcal{F}$ having a unique limit. Therefore, $X$ is Hausdorff.
---
> [!def] Problem 3
> Let $X,Y$ be topological spaces. Define a topology on $X\times Y$ by saying that $U\subseteq X\times Y$ is open if and only if, for every $(x,y)\in U$, there exist neighborhoods $V$ and $W$ of $x$ and $y$ respectively such that $V\times W\subseteq U$ (this is the product topology).
> 1. Check that this is a topology on $X\times Y$.
> 2. Show that $X$ is a Hausdorff space if and only if the diagonal $$\Delta:=\{ (x,x)|x\in X \}\subseteq X\times X$$ is closed in $X\times X$ (with the above topology for $Y=X$).
> 
> In the following points, let Y be a Hausdorff space.
>1. For any topological space $X$ and any continuous maps $f:X\to Y$ and $g:X\to Y$, show that the sets $$\{ (x,y): \}$$ are closed in X × X and in X, respectively. 