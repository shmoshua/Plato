#Definition #Topology 

> [!definition]
> Let $X$ be a topological group and $x\in X$. The ***fundamental group*** of $X$ at $x$ is a [[group]] $\Lambda_{x,x}$, where for $x,y\in X$, $\Lambda_{x,y}$ denotes the set of [[Path|path homotopy]] classes of paths from $x$ to $y$ on $X$.
- **Notation**: The fundamental group of $X$ at $x$ is also denoted as $\pi_{1}(X,x)$.
- **Related definition**: For $x\in X$, let $\varepsilon_{x}:[0,1]\to X, t\mapsto x$ be the constant path at $x$.
---
##### Properties
> [!lemma] Proposition 1
> We have for $\gamma\in \Lambda_{x,y}$
> 1. $\gamma_{0}(\gamma_{1}\gamma_{2})=(\gamma_{0}\gamma_{1})\gamma_{2}$ for $\gamma_{0}\in \Lambda_{x,y},\gamma_{1}\in \Lambda_{y,z},\gamma_{2}\in \Lambda_{z,w}$.
> 2. $\varepsilon_{x}\gamma=\gamma$, $\gamma \varepsilon_{y}=\gamma$
> 4. $\gamma\overline{\gamma}=\varepsilon_{x}$, $\overline{\gamma}\gamma=\varepsilon_{y}$

> [!proof]+
> 
- **Corollary**: $\Lambda_{x,x}$ is indeed a group with path composition and path inversion.