#Series #Topology 

> [!definition] Problem 1
> Let $X$ be a set.
> 1. Let $d_{1}$ and $d_{2}$ be distances on $X$. If there exist $a,b>0$ s.t.$$d_{1}(x,y)\leq d_{2}(x,y)^a,\quad d_{2}(x,y)\leq d_{1}(x,y)^b,\quad \forall(x,y)\in X\times X$$ show that the topologies defined by $d_{1}$ and $d_{2}$ are the same.
> 2. Let $d$ be a distance on $X$. Show that: $$\delta(x,y)= \frac{d(x,y)}{1+d(x,y)}$$is a distance on $X$. Show that the topology defined by $\delta$ is the same as the topology defined by $d$. Show that $\delta(x,y)\leq 1$ for all $(x,y)\in X\times X$. 

We have:
1. Let $U\subseteq \mathcal{T}_{d_{1}}$. Then, for any $x\in X$, there exists $r>0$ s.t. $B^1_{<r}(x)\subseteq U$. Consider $B^2_{<r^{1/a}}(x)$. We have:$$B^2_{<r^{1 /a}}=\{ y\in X:d_{2}(x,y)<r^{1/a} \}\subseteq \{ y\in X:d_{1}(x,y)<r \}\subseteq$$