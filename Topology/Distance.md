#Topology #Definition 

> [!definition]
> Let $(X,d)$ be a [[Metric Space|metric space]]. For non-empty $A,B\subseteq X$, the ***distance from $A$ to $B$*** is defined as:
> $$d(A,B)=\inf_{x\in A,y\in B}d(x,y)$$
> If $A$ or $B$ is a singleton set $\{ x \}$, we just write $d(x,B)$ or $d(A,x)$ instead.
---
##### Properties
> [!lemma] Lemma 1
> If $A\subseteq X$ is nonempty, for all $x,y\in X$: $$\left| d(x,A)-d(y,A) \right| \leq d(x,y)$$

> [!proof]-
> $$\begin{align}d(x,A)&=\inf_{z\in A}d(x,z)\\&\leq \inf_{z\in A}[d(x,y)+d(y,z)]\\&=d(x,y)+\inf_{z\in A}d(y,z)\\&=d(x,y)+d(y,A)\end{align}$$
> By repeating it with switched $x,y$, we have: $\left| d(x,A)-d(y,A) \right|\leq d(x,y)$.
---
> [!lemma] Proposition 2
> For any non-empty $A\subseteq X$ and $r>0$, $$V_{r}(A)=\{ x\in X:d(x,A)<r \}$$ is an open neighborhood of $A$.

> [!proof]-
> For any $x\in A$, $d(x,A)\leq d(x,x)=0$. Therefore, $x\in V_{r}(A)$ and $A\subseteq V_{r}(A)$. 
> 
> Now, to show that $V_{r}(A)$ is open, for $x\in V_{r}(A)$, we note that for $y\in B(x,r-d(x,A))$, $$d(y,A)\leq d(y,x)+d(x,A)<r-d(x,A)+d(x,A)=r$$
> Therefore, $B(x,r-d(x,A))\subseteq V_{r}(A)$ and $V_{r}(A)$ is open.
---
