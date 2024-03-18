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
> In the following points, let $Y$ be a Hausdorff space.
>1. For any topological space $X$ and any continuous maps $f:X\to Y$ and $g:X\to Y$, show that the sets $$\{ (x,y):f(x)=g(y) \},\quad \{ x\in X:f(x)=g(x) \}$$ are closed in $X\times X$ and in $X$, respectively. 
>2. For any topological space $X$ and any continuous maps $f:X\to Y$ and $g:X\to Y$, show that if $f(x)=g(x)$ for all $x$ in a dense set, then $f=g$.
>3. For any topological space $X$ and any continuous map $f:X\to Y$ , show that the graph $$\text{graph}(f):=\{ (x,y) :y=f(x)\}$$ of $f$ is closed in $X\times Y$.

We have:
1. $\varnothing$ is open by definition. Further, $X\times Y$ is open by taking $X,Y$ as the neighborhoods. For a family of open sets $(U_{\lambda})_{\lambda\in \Lambda}$, we have that for $(x,y)\in \bigcup_{\lambda\in \Lambda}^{}U_{\lambda}$, there exists $\alpha\in \Lambda$ s.t. $(x,y)\in U_{\alpha}$ and there exists neighborhoods $V,W$ of $x,y$ respectively s.t. $$V\times W\subseteq U_{\alpha}\subseteq \bigcup_{\lambda\in \Lambda}^{}U_{\lambda}$$
	Similarly, for $U_{1},U_{2}$ open s.t. $U_{1}\cap U_{2}\neq \varnothing$, let $(x,y)\in U_{1}\cap U_{2}$. Then, there exists open neighborhoods $V_{1},W_{1}$ and $V_{2},W_{2}$  s.t. $V_{1}\cap V_{2}$ and $W_{1}\cap W_{2}$ are open neighborhoods of $x$ and $y$ respectively and: $$(V_{1}\cap V_{2})\times(W_{1}\cap W_{2})\subseteq U_{1}\cap U_{2}$$ This shows that this is indeed a topology.
2. Assume $X$ is Hausdorff. We show that $U:=X\times X \backslash\Delta$ is open. Let $(x,y)\in U$. By definition $x\neq y$ and there exist disjoint open neighborhoods $V,W$ of $x,y$ respectively, i.e. $V\times W\subseteq X\times X \backslash \Delta$. 
   
   Conversely, assume that $\Delta$ is closed and let $x,y\in X$ with $x\neq y$. Then, $(x,y)\in X\times X \backslash \Delta$ and there exists open neighborhoods $V,W$ of $x,y$ respectively s.t. $V\times W\subseteq X \times X \backslash \Delta$, i.e. $V\cap W=\varnothing$. 
3. Let $x,y\in X$ s.t. $f(x)\neq g(y)$. Then, as $Y$ is Hausdorff, there exists $V,W\subseteq Y$ neighborhoods of $f(x),g(y)$ respectively s.t. $V\cap W=\varnothing$. Then, $f^{-1}(V)$ and $g^{-1}(W)$ are neighborhoods of $x,y$ respectively, s.t. $f^{-1}(V)\times g^{-1}(W)\subseteq X\times X \backslash\{ (a,b):f(a)=g(b) \}$. This shows that $\{ (x,y):f(x)=g(y) \}$ is closed.
   
   Similarly, 