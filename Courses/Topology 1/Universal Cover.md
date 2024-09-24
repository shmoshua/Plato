#Definition #Topology 

> [!definition]
> Given a [[Topological Space]] $X$, a ***universal cover*** of $X$ is a [[Covering Space]] $f:Y\to X$ where $Y$ is [[Simply Connected Space|simply connected]].
---
##### Properties
> [!lemma] Theorem 1 (Universal Cover Theorem)
>  Let $X$ be a [[Path-Connected Space|path-connected]], locally path-connected, [[Semi-Locally Simply Connected Space]]. Then,  
> 1. $X$ has a universal cover $f:Y\to X$.
> 2. if $f_{1},f_{2}$ are universal covers, for any $x\in X$ and $y_{1}\in Y_{1}$ and $y_{2}\in Y_{2}$ with $f_{1}(y_{1})=x$ and $f_{2}(y_{2})=x$, there exists a unique homeomorphism $\varphi:Y_{1}\to Y_{2}$ s.t. $\varphi(y_{1})=y_{2}$ and $f_{2}\circ\varphi=f_{1}$.
> 3. given $x_{0}\in X$, there exists an action $\pi_{1}(X,x_{0}) \curvearrowright Y$ s.t. $Y / \pi_{1}(X,x_{0})$ is homeomorphic to $X$.

> [!proof]-
> Let $x_{0}\in X$ and define: $$\tilde{Y}:=\{ \gamma\in C([0,1],X): \gamma(0)=x_{0}\}$$and $Y:=\tilde{Y} /\sim_{p}$. Then, we claim that the function $f:Y\to X, \gamma\mapsto \gamma(1)$ is a covering space.
> 1. **Claim 1: $f:Y\to X$ is a covering space.**
>    We first define a bijection $f^{-1}(\{ x \})\to \pi_{1}(X,x_{0})$. Let $\gamma\in f^{-1}(x)$ be a fixed curve which exists as $X$ is path-connected. Then, consider: $$f^{-1}(\{ x \})\to \pi_{1}(X,x_{0}),\quad \gamma'\mapsto\gamma \overline{\gamma'}$$is a bijection as it is injective by definition and for $\eta\in \pi_{1}(X,x_{0})$, $\gamma \overline{\overline{\eta}\gamma }=\gamma\overline{\gamma}\eta=\eta$.
>    
>    As $X$ is locally path connected and semi-locally simply connected, for any $x\in X$, there exists a neighborhood $U$ of $x$ s.t. $U$ is path-connected and for any loop at $x$ on $U$ is path-homotopic to $\varepsilon_{x}$ in $X$. Then, we define the bijection: $$f^{-1}(U)\to U\times f^{-1}(\{ x \}),\quad \gamma\mapsto(\gamma(1),\gamma \overline{\lambda_{U,\gamma(1)}})$$where $\lambda_{U,\gamma(1)}$ is the path from $x$ to $\gamma(1)$ over $U$. This is well-defined as if $\lambda,\lambda'$ are two such paths, $\lambda\overline{\lambda'}$ is path homotopic to $\varepsilon_{x}$ and $\lambda$ is path homotopic to $\lambda'$. Therefore, if we endow $Y$ with a topology s.t. the bijection is homeomorphic, it proves that $f$ is a covering space.
>    
>    As $Y$ is covered by $f^{-1}(U)$, we just need to show that this homeomorphism is compatible, i.e. for any $U_{1},U_{2}$ with $x_{1},x_{2}$ as base points as above, $$(U_{1}\cap U_{2})\times f(\{ x_{2} \})\to(U_{1}\cap U_{2})\times f(\{ x_{1} \}),(x,\eta)\mapsto (\eta\lambda_{U_{2},x}(1),\eta\lambda_{U_{2},x}\overline{\lambda_{U_{1},x}})=(x,\eta\lambda_{U_{2},x}\overline{\lambda_{U_{1},x}})$$is a homeomorphism. Firstly, this is a bijection from above. Then, this map is continuous  as $\eta\lambda_{U_{2},x}\overline{\lambda_{U_{1}},x}$ is locally constant. The continuity of the inverse holds by symmetry.
> 2. **Claim 2: $Y$ is simply connected.**
> 	   We first show that $Y$ is path-connected. For $\gamma\in \tilde{Y}$, we have that: $$\tilde{\eta}:[0,1]\to \tilde{Y},\quad s\mapsto(t\mapsto\gamma(st))$$ can be lifted to $\eta:[0,1]\to Y, s\mapsto[\tilde{\eta}(s)]$ where $\eta(0)=[\varepsilon_{x_{0}}]$ and $\eta(1)=[\gamma]$. This shows the path-connectedness.
> 	   
> 	   For the simply-connectedness, let $\eta:[0,1]\to Y$ be a loop at $\varepsilon_{x_{0}}$. Now, consider the homotopy: $$h:[0,1]\times[0,1]\to X,\quad (t,s)\mapsto \eta(t)(s)$$Then, $h(0,s)=\eta(0)(s)=x_{0}$ and $h(1,s)=x_{0}$. Further, $h(t,0)=\eta(t)(0)=x_{0}$ and $$h(t,1)=\eta(t)(1)=f\circ \eta(t)$$ Therefore, $h$ is a path-homotopy from $\varepsilon_{x_{0}}$ to $f_{*}(\eta)$. This shows that $f_{*}(\eta)$ is trivial in $\pi_{1}(X,x_{0})$ and by [[Covering Space|Lemma 2]], $\eta$ is trivial in $\pi_{1}(Y,\varepsilon_{x_{0}})$. It shows that $\pi_{1}(Y,\varepsilon_{x_{0}})$ is trivial and $Y$ is simply connected.
> 1. **Claim 3: $\pi_{1}(X,x_{0})$ acts on $Y$ with quotient $X$.**
>    The action is given by: $$\pi_{1}(X,x_{0})\times Y\to Y,\quad (\eta,\gamma)\to \eta\gamma$$By identifying $Y$ with the bijection from above $f^{-1}(U)\to U\times f^{-1}(\{ x_{U} \})$, we get that: $$\eta(x,\gamma)\mapsto(x,\eta\gamma)$$Since $\pi_{1}(X,x_{0})\to f^{-1}(\{ x_{U} \}), \eta\mapsto \eta \gamma_{0}$ is a bijection for a fixed $\gamma_{0}\in f^{-1}(\{ x_{U} \})$ with inverse $\gamma\mapsto \gamma\overline{\gamma_{0}}$, we have that $Y / \pi_{1}(X,x_{0})\cong X$.
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
