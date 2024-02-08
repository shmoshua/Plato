#Definition #LST 

> [!definition]
> Given a system: $$\begin{align}\dot{x}(t)&=f(x(t),u(t),t)\in \mathbb{R}^n\\y(t)&=r(x(t),u(t),t)\in \mathbb{R}^p\end{align}$$where $t\in \mathbb{R}$, $f:\mathbb{R}^n\times \mathbb{R}^m\times \mathbb{R}\to \mathbb{R}^n$ and $r:\mathbb{R}^n\times \mathbb{R}^m\times \mathbb{R}\to \mathbb{R}^p$, such that: 
> 1. $f$ is Lipschitz in $x$, continuous in $u$, piecewise-continuous in $t$.
> 2. $u(\cdot)$ is piecewise-continuous in $t$.
> 3. $r$ is continuous in $x,u$ and piecewise-continuous in $t$.
> 
> Then, for $t_{0}<t_{1}$, the system is ***controllable*** on $[t_{0},t_{1}]$ if for all $x_{0},x_{1}\in\mathbb{R}^n$, there exists $u(\cdot)\in PC([t_{0},t_{1}],\mathbb{R}^m)$ s.t. $$s(t_{1},t_{0},x_{0},u)=x_{1}$$In which case, we say that $u(\cdot)$ ***steers*** $(x_{0},t_{0})$ to $(x_{1},t_{1})$.
- **Remark**: The controllability of a system does not depend on the output.
- **Remark**: A system is controllable if and only if $s(t_{1},t_{0},x_{0},\cdot):PC([t_{0},t_{1}],\mathbb{R}^m)\to \mathbb{R}^n$ is surjective.
---
##### Properties
> [!lemma] Theorem 1 (Relation to Feedback)
> Consider $t_{0},t_{1}\in \mathbb{R}$ with $t_{0}\leq t_{1}$. Then, the following statements are equivalent: 
> 1. $\dot{x}(t)=f(x(t),u(t),t)$ is controllable in $[t_{0},t_{1}]$.
> 2. $\dot{x}(t)=f(x(t),v(t)+F_{S}(x(t),t),t)=f_{S}(x(t),v(t),t)$ is controllable in $[t_{0},t_{1}]$.
> 3. $\dot{x}(t)=f(x(t),w(t)+F_{O}(r(x(t),t),t),t)=f_{O}(x(t),w(t),t)$ is controllable in $[t_{0},t_{1}]$.

> [!proof]+
---
##### Linear Time-Varying Systems
> [!definition]
> The linear time-varying system $$\dot{x}(t)=A(t)x(t)+B(t)u(t)$$ or equivalently, the pair $(A(\cdot),B(\cdot))$ is ***controllable*** on $[t_{0},t_{1}]$ for $t_{0}<t_{1}$ if for all $x_{0},x_{1}\in \mathbb{R}^n$, there exists $u(\cdot)\in L^2([t_{0},t_{1}],\mathbb{R}^m)$ s.t. $$x_{1}=\Phi(t_{1},t_{0})x_{0}+\int_{t_{0}}^{t_{1}} \Phi(t_{1},\tau)B(\tau)u(\tau) \, d\tau $$
> 
> The ***controllability gramian*** of $(A(\cdot),B(\cdot))$ on $[t_{0},t_{1}]$ is the matrix: $$W_{r}(t_{0},t_{1}):=\int_{t_{0}}^{t_{1}} \Phi(t_{1},\tau)B(\tau)B(\tau)^\top\Phi(t_{1},\tau)^\top \, d\tau \in \mathbb{R}^{n,n} $$
---
> [!lemma] Lemma 2
> The following statements are equivalent: 
> 1. $(A(\cdot),B(\cdot))$ is controllable on $[t_{0},t_{1}]$.
> 2. For all $x_{0}\in\mathbb{R}^n$, there exists $u(\cdot)$ that steers $(x_{0},t_{0})$ to $(0,t_{1})$.
> 3. For all $x_{1}\in\mathbb{R}^n$, there exists $u(\cdot)$ that steers $(0,t_{0})$ to $(x_{1},t_{1})$.

> [!proof]-
> - 1=>2,3 is obvious.
> - 2=>1: For arbitrary $x_{0},x_{1}\in \mathbb{R}^n$, let $\hat{x}_{0}:=x_{0}-\Phi(t_{0},t_{1})x_{1}$ and consider $\hat{u}:[t_{0},t_{1}]\to \mathbb{R}^m$ that steers $(\hat{x}_{0},t_{0})$ to $(0,t_{1})$. Then, 
>  $$0=\Phi(t_{1},t_{0})x_{0}-x_{1}+\int_{t_{0}}^{t_{1}} \Phi(t_{1},\tau)B(\tau)\hat{u}(\tau) \, d\tau $$Therefore, $\hat{u}(\cdot)$ steers $(x_{0},t_{0})$ to $(x_{1},t_{1})$.
>  - 3=>1: For arbitrary $x_{0},x_{1}\in \mathbb{R}^n$, let $\hat{x}_{1}:=x_{1}-\Phi(t_{1},t_{0})x_{0}$. Then, there exists $u(\cdot)$ s.t. $$x_{1}-\Phi(t_{1},t_{0})x_{0}=\int_{t_{0}}^{t_{1}} \Phi(t_{1},\tau)B(\tau)u(\tau) \, d\tau $$
---
> [!lemma] Lemma 3
> The controllability gramian $W_{r}(t_{0},t_{1})$ has the following properties:
> 1. Symmetric positive semi-definite: $W_{r}(t_{0},t_{1})=W_{r}(t_{0},t_{1})^\top$
> 2. For all $t'_{0}\leq t_{0}$, $W_{r}(t'_{0},t_{1})\geq W_{r}(t_{0},t_{1})$ i.e. for all $x\in \mathbb{R}^n$:$$x^\top[W_{r}(t'_{0},t_{1})-W_{r}(t_{0},t_{1})]x\geq 0$$

> [!proof]-
> We have that: 
> 1. For symmetry:$$\begin{align}W_{r}(t_{0},t_{1})^\top&=\left[ \int_{t_{0}}^{t_{1}} \Phi(t_{1},\tau)B(\tau)B(\tau)^\top\Phi(t_{1},\tau)^\top \, d\tau  \right] ^\top\\&= \int_{t_{0}}^{t_{1}} \Phi(t_{1},\tau)B(\tau)B(\tau)^\top\Phi(t_{1},\tau)^\top \, d\tau \\&=W_{r}(t_{0},t_{1})\end{align}$$Further, for any $x\in \mathbb{R}^n$:$$x^\top W_{r}(t_{0},t_{1})x=\int_{t_{0}}^{t_{1}} x^\top\Phi(t_{1},\tau)B(\tau)B(\tau)^\top\Phi(t_{1},\tau)^\top x \, d\tau=\int_{t_{0}}^{t_{1}} \|B(\tau)^\top\Phi(t_{1},\tau)^\top x\|^{2} \, d\tau \geq 0$$
> 2. We have that: $$x^\top[W_{r}(t'_{0},t_{1})-W_{r}(t_{0},t_{1})]x=\int_{t'_{0}}^{t_{0}} \left\| B(\tau)^\top\Phi(t_{1},\tau)^\top x \right\|  \, d\tau\geq 0 $$
---
> [!lemma] Theorem 4
> For $t_{0}<t_{1}$, the following statements are equivalent:
> 1. $(A(\cdot),B(\cdot))$ is controllable on $[t_{0},t_{1}]$
> 2. $\text{Im }\mathcal{L}_{r}=\mathbb{R}^n$, where $\mathcal{L}_{r}$ is the [[Reachability|reachability map]]
> 3. $\text{Im }\mathcal{L}_{r}\circ\mathcal{L}_r^{*}=\mathbb{R}^n$
> 4. $\det(W_{r}(t_{0},t_{1}))\neq 0$, i.e. $W_{r}(t_{0},t_{1})$ is positive definite.

> [!proof]-
> We have that: 
> - 1 <=> 2: A linear system is controllable if and only if all states $x_{1}\in \mathbb{R}^n$ are reachable from 0, i.e. $\text{Im }\mathcal{L}_{r}=\mathbb{R}^n$. 
> - 2 <=> 3: By the finite rank lemma.
> - 3 <=> 4: We will show that $(\mathcal{L}_{r}\circ\mathcal{L}_{r}^{*})(x)=W_{r}(t_{0},t_{1})(x)$ for all $x\in \mathbb{R}^n$. We can see that: $$\mathcal{L}_{r}^{*}(x)(\tau)=B(\tau)^\top\Phi(t_{1},\tau)^\top x$$and therefore, $$(\mathcal{L}_{r}\circ \mathcal{L}_{r}^{*})(x)=\int_{t_{0}}^{t_{1}} \Phi(t_{1},\tau)B(\tau)B(\tau)^\top\Phi(t_{1},\tau)^\top x\, d\tau =W_{r}(t_{0},t_{1})x$$Therefore, the linear map has full rank, if and only if the matrix is invertible.
---
> [!lemma] Theorem 5
> Assume that $(A(\cdot),B(\cdot))$ is controllable on $[t_{0},t_{1}]$. Given $x_{0},x_{1}\in \mathbb{R}^n$, define $\tilde{u}:[t_{0},t_{1}]\to \mathbb{R}^m$:$$\begin{align}\tilde{u}(t)&=[\mathcal{L}^{*}_{r}\circ (\mathcal{L}_{r}\circ \mathcal{L}_{r}^{*})^{-1}](x_{1}-\Phi(t_{1},t_{0})x_{0})(t)\\&=B(t)^\top\Phi(t_{1},t)^\top W_{r}(t_{0},t_{1})^{-1}(x_{1}-\Phi(t_{1},t_{0})x_{0})\end{align}$$
> Then, 
> 1. $\tilde{u}(\cdot)$ steers $(x_{0},t_{0})$ to $(x_{1},t_{1})$.
> 2. $\tilde{u}(\cdot)$ is piecewise-continuous, with discontinuity points at discontinuity points of $B(\cdot)$. Especially, $u(\cdot)$ is continuous if and only if $B(\cdot)$ is continuous.
> 3. $\left\| \tilde{u} \right\|^2_{2}=[x_{1}-\Phi(t_{1},t_{0})x_{0}]^\top W_{r}(t_{0},t_{1})^{-1}[x_{1}-\Phi(t_{1},t_{0})x_{0}]$
> 4. If $u(\cdot)\in L^{2}([t_{0},t_{1}],\mathbb{R}^m)$ steers $(x_{0},t_{0})$ to $(x_{1},t_{1})$, then $\|u\|_{2}\geq\|\tilde{u}\|_{2}$

> [!proof]-
> We have that: 
> 1. For $\tilde{u}(\cdot)$:$$\begin{align}&\quad\ \Phi(t_{1},t_{0})x_{0}+\int_{t_{0}}^{t_{1}} \Phi(t_{1},\tau)B(\tau)\tilde{u}(\tau) \, d\tau \\&=\Phi(t_{1},t_{0})x_{0}+\int_{t_{0}}^{t_{1}} \Phi(t_{1},\tau)B(\tau)B(\tau)^\top\Phi(t_{1},\tau)^\top W_{r}(t_{0},t_{1})^{-1}(x_{1}-\Phi(t_{1},t_{0})x_{0}) \, d\tau\\&=\Phi(t_{1},t_{0})x_{0}+W_{r}(t_{0},t_{1}) W_{r}(t_{0},t_{1})^{-1}(x_{1}-\Phi(t_{1},t_{0})x_{0}) \\&=x_{1}  \end{align}$$
> 2. Obvious from the formula.
> 3. We have that: $$\begin{align}\|\tilde{u}\|^2_{2}&=\int_{t_{0}}^{t_{1}} \tilde{u}(\tau)^\top \tilde{u}(\tau) \, d\tau\\&= (x_{1}-\Phi(t_{1},t_{0})x_{0})^\top W_{r}(t_{0},t_{1})^{-1}(x_{1}-\Phi(t_{1},t_{0})x_{0} )  \end{align}$$
> 4. For all $u(\cdot)$ steering $(x_{0},t_{0})$ to $(x_{1},t_{1})$, $u=\tilde{u}+\hat{u}$ where $\tilde{u}\in \text{Im }\mathcal{L}_{r}^{*}$ and $\hat{u}\in \text{ker }\mathcal{L}_{r}$. Therefore, $$\|u\|^2_{2}=\|\tilde{u}\|^2_{2}+\|\hat{u}\|^2_{2}\geq\|\tilde{u}\|^2_{2} $$by Pythagoras.
---
##### Linear Time-Invariant System
> [!definition]
> For the linear time-varying system $$\begin{align}\dot{x}(t)&=Ax(t)+Bu(t)\\y(t)&=Cx(t)+Du(t)\end{align}$$ the ***controllability matrix*** is defined as: $$P=\begin{bmatrix}B&AB&\dots&A^{n-1}B\end{bmatrix}\in\mathbb{R}^{n,mn}$$
> 
---