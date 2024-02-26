#Definition #Topology

> [!definition]
> A ***topological space*** is a pair $(X,\mathcal{T})$ of a set $X$ and a set $\mathcal{ T}$ of subsets of $X$ called **open sets**, s.t.
> 1. for $\{ U_{\lambda} \}_{\lambda\in \Lambda}\subseteq \mathcal{T}$, $\bigcup_{\lambda\in \Lambda}^{}U_{\lambda}\in \mathcal{T}$. (any arbitrary union of open sets is open)
> 2. for $U_{1},U_{2}\in\mathcal{T}$, $U_{1}\cap U_{2}\in \mathcal{T}$ (the intersection of any two open sets is open)
> 4. $\varnothing,X\in \mathcal{T}$.
> 
> Then, $\mathcal{T}$ is the ***topology*** of $X$. 

- **Related definition:** $F \subset X$ is ***closed***, if $X \backslash F\in \mathcal{T}$.
- **Related definition**: $U \subset X$ is a ***neighborhood*** of $x\in X$, if there is an open set $V$ s.t. $x\in V \subseteq U$.
---
##### Examples
> [!h] Example 1 (Euclidean Topology)
> In the Euclidean topology on $\mathbb{R}^n$, $U\subseteq \mathbb{R}^n$ is open if and only if for all $x\in U$, there exists $\varepsilon>0$ s.t. $B_{<\varepsilon}(x)\subseteq U$ by the Euclidean distance.
---
> [!h] Example 2 (Subspace Topology)
> For a topological space $(X,\mathcal{T})$ and $Y\subseteq X$, a set $A\subseteq Y$ is open w.r.t. the ***subspace topology*** on $Y$ if and only if there exists $U\in \mathcal{T}$ s.t. $A=U\cap Y$.

##### Related Definitions
For a topological space $X$,

- For any subset $B\subseteq X$, a point $x\in X$ is:
  - an ***interior point*** of $B$ if $B$ is a neighborhood of $x$.
  - an ***exterior point*** of $B$ if $X\backslash B$ is a neighborhood of $x$.
  - an ***edge point*** of $B$ if neither $B$ or $X\backslash B$ are a neighborhood of $x$.
- The set $\mathring{B}$ of interior points of $B$ is the ***interior*** or the ***open kernel*** of $B$.
- The set $\bar{B}$ of non-exterior points of $B$ is called the ***closed hull*** of $B$.
---
##### Sum of Topological Spaces
> [!definition]
> For topological spaces $(X,\mathcal{ O})$ and $(Y,\tilde{\mathcal{ O}})$, the ***topologic sum*** of $X$ and $Y$ is defined as $(X+Y)$ with the topology $$\{  U+V:U\in\mathcal{ O},V\in \tilde{ \mathcal{O}} \}$$
> where $+$ defines the direct disjoint sum of two sets, i.e. for two sets $A,B$, $A+B:= A\times \{ 0 \}\cup B\times \{ 1 \}$.
---
##### Cartesian Product of Topological Spaces
> [!definition]
> For topological spaces $X,Y$, a subset $W \subseteq X\times Y$ is ***open in the product topology***, if for every point $(x,y)\in W$ there is a neighborhood $U$ of $x$ in $X$ and a neighborhood $V$ for $y$ in $Y$ s.t. $U\times V\subseteq W$. Then, $X\times Y$ is called the ***Cartesian product*** of $X$ and $Y$.
---