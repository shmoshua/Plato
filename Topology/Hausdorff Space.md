#Definition #Topology 
> [!definition]
> A [[topological space]] $(X,\mathcal{T})$ is ***Hausdorff***, if for all $x,y\in X$ with $x\neq y$, there exist disjoint open neighborhoods of $x,y$.
---
##### Properties
> [!lemma] Proposition 1 (Equivalent Conditions of Hausdorff)
> For a topological space $X$, TFAE:
> 1. $X$ is Hausdorff.
> 2. for every $x\in X$, $\bigcap_{U\in \mathcal{F}_{x}}^{}\overline{U}=\{ x \}$ where $\mathcal{F}_{x}$ is the [[filter]] of all neighborhoods of $x$.
> 3. every convergent filter $\mathcal{F}$ on $X$ has a unique limit.
> 4. the diagonal $\Delta:=\{ (x,x): x\in X \}\subseteq X\times X$ is closed.

> [!proof]-
> We have:
> 1. (1=>2): Assume that $X$ is Hausdorff. Indeed, $\{ x \}\subseteq \bigcap_{x\in U}^{}\overline{U}$ is trivial. Let $y\in \bigcap_{x\in U}^{}\overline{U}$ and assume $y\neq x$. Then, there exist disjoint open neighborhoods $U,V$ of $x,y$, respectively. However, $y\in \overline{U}$ by assumption and it follows that $U\cap V\neq\varnothing$, which is a contradiction. This shows the inclusion.
> 2. (2=>1): Assume that the condition holds. We will show that $X$ is Hausdorff. Let $x,y\in X$ s.t. $x\neq y$. Then, as $\bigcap_{x\in U}^{}\overline{U}=\{ x \}$, there exists open $U\ni x$ s.t. $y\notin\overline{U}$, i.e. there exists an open neighborhood $V$ of $y$ s.t. $U\cap V=\varnothing$. This proves the statement.
> 3. (1=>3): Let $\mathcal{F}$ be a convergent filter to $x,y\in X$ where $x\neq y$. Let $U,V$ be the disjoint open neighborhoods of $x,y$ and by convergence, there exists $W\in \mathcal{F}$ s.t. $W\subseteq U$ and $W\subseteq V$. (this is given as the filter is closed under intersection). As $\varnothing\notin \mathcal{F}$, we have that $U\cap V\neq \varnothing$, which is a contradiction.
> 4. (3=>1): Let $x,y\in X$ with $x\neq y$. We first consider the following set: $$\mathcal{F}:=\{\varnothing\neq A\subseteq X: A\supseteq V\cap W \text{ for some open neighborhood }V\text{ of }x \text{ and }W\text{ of }y \}$$Then, by definition $\varnothing \notin \mathcal{F}$ and for $A\in \mathcal{F}$ and $A\subseteq B$, $B\in \mathcal{F}$ with the same $V\cap W$. Lastly, consider $A,B\in \mathcal{F}$ with $V_{1},W_{1}$ and $V_{2},W_{2}$ as open neighborhoods. Then, $V_{1}\cap V_{2}$, $W_{1}\cap W_{2}$ are open neighborhoods of $x,y$ respectively and $A \cap B\supseteq (V_{1}\cap V_{2})\cap(W_{1}\cap W_{2})$. Therefore, $A\cap B\in \mathcal{F}$ and $\mathcal{F}$ is a filter. 
>    
>    Assume for all open neighborhoods $V,W$ of $x,y$ respectively, we have $V\cap W\neq \varnothing$. Then, for all open neighborhood $U$ of $x$, then $\varnothing \neq U\cap W\subseteq U$ for any open neighborhood $W$ of $y$. It follows that $\mathcal{F}$ converges to $x$ and by symmetry to $y$. This is a contradiction to $\mathcal{F}$ having a unique limit. Therefore, $X$ is Hausdorff.
>  5. (1=>4): Assume $X$ is Hausdorff. We show that $U:=X\times X \backslash\Delta$ is open. Let $(x,y)\in U$. By definition $x\neq y$ and there exist disjoint open neighborhoods $V,W$ of $x,y$ respectively, i.e. $V\times W\subseteq X\times X \backslash \Delta$. 
>  6. (4=>1): assume that $\Delta$ is closed and let $x,y\in X$ with $x\neq y$. Then, $(x,y)\in X\times X \backslash \Delta$ and there exists open neighborhoods $V,W$ of $x,y$ respectively s.t. $V\times W\subseteq X \times X \backslash \Delta$, i.e. $V\cap W=\varnothing$. 

---
##### Examples
> [!h] Example 1
> Any [[metric space]] is Hausdorff.

> [!proof]-
> Let $x\neq y$. Then, $\delta:=d(x,y)>0$. Therefore, $B_{< \delta /2}(x),B_{< \delta /2}(y)$ are the two desired open sets.
---
> [!h] Example 2
> The [[topology of pointwise and uniform convergence]] is Hausdorff.
---
###### Non-Hausdorff Spaces
> [!h] Non-example 1
> Let $X$ be infinite and: $$\mathcal{T}:=\{ U\subseteq X:X \backslash U\text{ is finite or }U=\varnothing \}$$Then, $(X,\mathcal{T})$ is not Hausdorff.

> [!proof]-
> Let $x,y\in X$ and $U\ni x$ open. Then, $X \backslash U$ is finite. Similarly, $V\ni y$ open with $X \backslash V$ finite. Then, $$X \backslash(U\cap V)=X \backslash U\cup X \backslash V$$which is finite. Therefore, $U\cap V\neq \varnothing$. 

