#Definition #Topology 

> [!definition]
> For a set $X$ and a family $\mathcal{F}=\{ (Y_{i},\varphi_{i}) \}_{i\in I}$ of [[Topological Space|topological spaces]] $Y_{i}$ with $\varphi_{i}: Y_{i}\to X$, the ***final topology*** is the finest topology that makes $\varphi_{i}$ continuous for all $i\in I$.
- **Remark**: Final topology is dual to [[initial topology]].
---
##### Properties
> [!lemma] Proposition 1
> Let $X$ be equipped with final topology.
> 1. $U\subseteq X$ is open/closed if and only if $\varphi_{i}^{-1}(U)$ is open/closed for all $i\in I$.
> 2. $\psi:X\to Z$ is continuous if and only if $\psi \circ\varphi_{i}$ is continuous for all $i\in I$.

> [!proof]-
> We have that:
> 1. Let $U$ be open. Then, as $\varphi_{i}$ is continuous, $\varphi_{i}^{-1}(U)$ is open. Now, notice that: $$\tau :=\{ U\subseteq X:\varphi ^{-1}_{i}(U)\text{ open in }Y_{i}, \forall i\in I \}$$is a topology. Hence, $\tau$ defines the initial topology and if $\varphi ^{-1}_{i}(U)$ is open for all $i\in I$, then so is $U$ in $X$.
> 2. Let $\psi$ be continuous. Then, as $\varphi_{i}$ is continuous so is $\psi \circ \varphi_{i}$. Conversely assume that $\psi \circ\varphi_{i}$ is continuous for all $i\in I$. Then, for $U\subseteq Z$ open, we have that: $\varphi ^{-1}_{i}(\psi ^{-1}(U))$ is open for all $i\in I$ and therefore, $\psi ^{-1}(U)$ is open in $X$.
---
