#Definition #Topology 

> [!definition]
> Let $X$ be a [[Topological Space]] and $x_{0}\in X$. A ***local basis/fundamental system of neighborhoods*** of $x_{0}$ is a set $\mathcal{V}$ of neighborhoods of $x_{0}$ s.t. 
> 1. for every neighborhood $U$ of $x_{0}$, there exists $V\in \mathcal{V}$ with $V\subseteq U$.
- **Related definition**: We say an ***open local base*** if $\mathcal{V}\subseteq \mathcal{T}$.
---
##### Properties
> [!lemma] Proposition 1
> Let $X$ be a topological space and $x_{0}\in X$ with a local base $\mathcal{V}$ of $x_{0}$. Then,
> 1. there exists a open local base $\mathcal{U}$ of $x_{0}$.
> 2. if $\mathcal{V}$ is countable, there exists a decreasing sequence of open sets $(U_{n})_{n}$ that form a local base of $x_{0}$.

> [!proof]-
> We have:
> 1. For each $V\in \mathcal{V}$ there exists an open set $U\subseteq V$. Take $\mathcal{U}:=\{ U_{\alpha}:V_{\alpha}\in\mathcal{V},U_{\alpha}\subseteq V_{\alpha} \text{ open} \}$. Then, for any neighborhood $W$ of $x_{0}$, there exists $U\in \mathcal{U}$ with $U\subseteq V\subseteq W$.
> 2. Let $(V_{n})_{n}$ be the countable local base of $x_{0}$ from 1. Then, define $U_{n}:=\bigcap_{i=1}^{n}V_{i}$. Then, $U_{n}\supseteq U_{n+1}$ and they are open neighborhoods of $x_{0}$. Now, for a neighborhood $W$ of $x_{0}$, there exists $n\in \mathbb{N}$ s.t. $$U_{n}\subseteq V_{n}\subseteq W$$Therefore, $\{ U_{n} \}_{n}$ is an open local base of $x_{0}$.
---
##### Examples
> [!h] Example 1
> For a metric space $(X,d)$, $\{ B_{<r}(x):r>0 \}$ is a fundamental system of open neighborhood of $x$.
---