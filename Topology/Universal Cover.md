#Definition #Topology 

> [!definition]
> Given a [[topological space]] $X$, a ***universal cover*** of $X$ is a [[covering space]] $f:Y\to X$ where $Y$ is [[Simply Connected Space|simply connected]].
---
##### Properties
> [!lemma] Theorem 1 (Universal Cover Theorem)
> Let $X$ be a [[Path-Connected Space|path-connected]], locally path-connected, [[semi-locally simply connected space]]. Then, 
> 1. $X$ has a universal cover $f:Y\to X$.
> 2. if $f_{1},f_{2}$ are universal covers, for any $x\in X$ and $y_{1}\in Y_{1}$ and $y_{2}\in Y_{2}$ with $f_{1}(y_{1})=x$ and $f_{2}(y_{2})=x$, there exists a unique homeomorphism $\varphi:Y_{1}\to Y_{2}$ s.t. $\varphi(y_{1})=y_{2}$ and $f_{2}\circ\varphi=f_{1}$.
> 3. given $x_{0}\in X$, there exists an action $\pi_{1}(X,x_{0}) \curvearrowright Y$ s.t. $Y / \pi_{1}(X,x_{0})$ is homeomorphic to $X$.

> [!proof]+
> Let $x_{0}\in X$ and define: $$\tilde{Y}:=\{ \gamma\in C([0,1],X): \gamma(0)=x_{0}\}$$and $Y:=\tilde{Y} /\sim_{p}$. Then, we claim that the function $f:Y\to X, \gamma\mapsto \gamma(1)$ is a covering space.
> 1. **Claim 1: $f:Y\to X$ is a covering space.**
>    We first define a bijection $f^{-1}(\{ x \})\to \pi_{1}(X,x_{0})$. Let $\gamma\in f^{-1}(x)$ be a fixed curve which exists as $X$ is path-connected. Then, consider: $$f^{-1}(\{ x \})\to \pi_{1}(X,x_{0}),\quad \gamma'\mapsto\gamma \overline{\gamma'}$$is a bijection as it is injective by definition and for $\eta\in \pi_{1}(X,x_{0})$, $\gamma \overline{\overline{\eta}\gamma }=\gamma\overline{\gamma}\eta=\eta$.
> 2. **Claim 2: $Y$ is simply connected.**
> 3. **Claim 3: $\pi_{1}(X,x_{0})$ acts on $Y$ with quotient $X$.**
---
##### Examples
> [!h] Example 1
> We have that:
> 1. $\mathbb{R}\to S^1,t\mapsto \exp(2\pi it)$ is a universal cover.
> 2. $\mathbb{C}\to \mathbb{C}^\times, z\mapsto \exp(z)$ is a universal cover. 
---
> [!h] Example 2 (Simply Connected)
> For a simply-connected space $X$, $\text{id}:X\to X$ is a universal cover.
---
