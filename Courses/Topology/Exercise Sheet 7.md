#Series  #Topology 

> [!def] Problem 1
> Let $X=[0,+\infty)$. Define a function $\delta:X\times X\to [0,+\infty),(x,y)\mapsto \left| e^{-x}-e^{-y} \right|$
> 1. Show that $\delta$ is a distance on $X$.
> 2. Show that the topology defined by $\delta$ on $X$ is the euclidean subspace topology.
> 3. Show that $(X,\delta)$ is not complete.
> 4. Show that $X$ is a complete space with the restriction of the euclidean distance.

We have:
1. The non-negativity, symmetry and triangle inequality is inherited from the norm $\left| \cdot  \right|$ in the definition. The non-degeneracy is given by the injectivity of $e^{-x}$. 
2. Let $x\in X$ and $r>0$. We show that $U:=B_{<r}^\delta(x)\cap A$ is open in the euclidean subspace topology. Let $y\in U$. 
3. 
4. Then, $B^\text{eucl}_{<r}(x)\cap X=B_{}$
---
> [!def] Problem 2
> In a metric space $(X,d)$, the diameter of a non-empty subset $Y\subseteq X$ is defined to be $$\text{diam}(Y):=\text{sup}\{ d(x,y):(x,y)\in Y^{2} \}$$ if this supremum exists in $\mathbb{R}$, or $+\infty$ otherwise. Let $X$ be a complete metric space. Let $(C_{n})_{n\geq 1}$ be closed subsets of $X$ such that $C_{n}\supseteq C_{n+1}$ for $n\geq 1$.