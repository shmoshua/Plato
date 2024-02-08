#Definition #LST 

> [!definition]
> Given a system: $$\begin{align}\dot{x}(t)&=f(x(t),u(t),t)\in \mathbb{R}^n\\y(t)&=r(x(t),u(t),t)\in \mathbb{R}^p\end{align}$$where $t\in \mathbb{R}$, $f:\mathbb{R}^n\times \mathbb{R}^m\times \mathbb{R}\to \mathbb{R}^n$ and $r:\mathbb{R}^n\times \mathbb{R}^m\times \mathbb{R}\to \mathbb{R}^p$, such that: 
> 1. $f$ is Lipschitz in $x$, continuous in $u$, piecewise-continuous in $t$.
> 2. $u(\cdot)$ is piecewise-continuous in $t$.
> 3. $r$ is continuous in $x,u$ and piecewise-continuous in $t$.
> 
> Then, for $t_{0}<t_{1}$, the system is ***observable*** on $[t_{0},t_{1}]$ if for all $x_{0}\in\mathbb{R}^n$ and $u(\cdot)\in PC([t_{0},t_{1}],\mathbb{R}^m)$, given $u(\cdot)$ and the corresponding output $y(\cdot)=\rho(\cdot,t_{0},x_{0},u):[t_{0},t_{1}]\to \mathbb{R}^p$, $x_{0}$ can be uniquely determined.
- **Remark**: A system is observable if and only if for all $u(\cdot):PC([t_{0},t_{1}],\mathbb{R}^m)$,  the function: $$\begin{array}{cccc} {\rho(\cdot ,t_{0},\odot ,u):}&{\mathbb{R}^n}&\to&{PC([t_{0},t_{1}],\mathbb{R}^p)}\\&{x_{0}} &\mapsto & {\rho(\cdot ,t_{0},x_{0},u)} \end{array}{}$$ is injective.
---
##### Properties
> [!lemma] Theorem 1 
> Consider $t_{0},t_{1}\in \mathbb{R}$ with $t_{0}\leq t_{1}$. Then, the following statements are equivalent: 
> 1. The following system is observable in $[t_{0},t_{1}]$:
>    $$\begin{align}\dot{x}(t)&=f(x(t),u(t),t)\\y(t)&=r(x(t),u(t),t)\end{align}$$
> 2. The following system is observable in $[t_{0},t_{1}]$:
>    $$\begin{align}\dot{x}(t)&=f(x(t),w(t)+F_{O}(r(x(t),t),t),t)=f_{O}(x(t),w(t),t)\\y(t)&=r(x(t),u(t),t)\end{align}$$
> 3. The following system is observable in $[t_{0},t_{1}]$:
>    $$\begin{align}\dot{x}(t)&=f(x(t),u(t),t)\\z(t)&=r(x(t),u(t),t)+F_{F}(u(t),t)=r_{F}(x(t),u(t),t)\end{align}$$

> [!proof]+
---
##### Linear Time-Varying Systems
> [!definition]
> The linear time-varying system $$\begin{align}\dot{x}(t)&=A(t)x(t)+B(t)u(t)\\y(t)&=C(t)x(t)+D(t)u(t)\end{align}$$ or equivalently, the pair $(C(\cdot),A(\cdot))$ is ***observable*** on $[t_{0},t_{1}]$ for $t_{0}<t_{1}$ if for all $x_{0}\in \mathbb{R}^n$ and $u(\cdot):[t_{0},t_{1}]\to \mathbb{R}^m$, one can uniquely determine $x_{0}$ from $\{ (u(t),y(t)):t\in[t_{0},t_{1}] \}$.
> 
> A state $x_{0}\in \mathbb{R}^n$ is ***unobservable on $[t_{0},t_{1}]$***, if for all $t\in[t_{0},t_{1}]$: $$C(t)\Phi(t,t_{0})x_{0}=0$$
> 
> The ***observability map*** of $(C(\cdot),A(\cdot))$ is the function: $$\begin{array}{cccc} {\mathcal{L}_{o}:}&{\mathbb{R}^n}&\to&{L^2([t_{0},t_{1}],\mathbb{R}^p)}\\&{x_{0}} &\mapsto & {C(t)\Phi(t,t_{0})x_{0}} \end{array}{}$$
> 
> The ***observability gramian*** of $(C(\cdot ),A(\cdot))$ is the matrix: $$W_{o}(t_{0},t_{1})=\int_{t_{0}}^{t_{1}} \Phi(\tau,t_{0})^\top C(\tau)^\top C(\tau)\Phi(\tau,t_{0}) \, d\tau \in \mathbb{R}^{n,n}$$
> 
- **Remark**: If we know $u(\cdot)$, we can easily compute the last two terms in: $$y(t)=C(t)\Phi(t,t_{0})x_{0}+C(t)\int_{t_{0}}^{t}\Phi(t,\tau)B(\tau)u(\tau)  \, d\tau+D(t)u(t) $$
  Therefore, observability comes down to whether we can uniquely determine $x_{0}$ from $C(t)\Phi(t,t_{0})x_{0}$. Hence, we can w.l.o.g. assume that $u(\cdot)\equiv{0}$.
---
> [!lemma] Lemma 2
> For the observability map $\mathcal{L}_{o}$, it holds that: 
> 1. $\mathcal{L}_{o}$ is a bounded linear map.
> 2. for all $x_{0}\in \mathbb{R}^n$, $\mathcal{L}_{o}(x_{0})\in PC([t_{0},t_{1}],\mathbb{R}^p)$.
> 4. $x_{0}\in \mathbb{R}^n$ is unobservable if and only if $x_{0}\in \text{ker }\mathcal{L}_{o}$.
> 5. $(C(\cdot),A(\cdot))$ is observable on $[t_{0},t_{1}]$ if and only if $\text{ker }\mathcal{L}_{o}=\{ 0 \}$.

> [!proof]-
> We have that: 
> 1. $\mathcal{L}_{o}$ is linear by definition. For boundedness, $$\left\| \mathcal{L}_{o}(x_{0}) \right\| ^{2}_{2}=\int_{t_{0}}^{t_{1}} \left\| C(\tau)\Phi(\tau,t_{0})x_{0} \right\|^{2}  \, d\tau\leq\int_{t_{0}}^{t_{1}} \left\| C(\tau)\Phi(\tau,t_{0})\|^{2}\|x_{0} \right\|^{2}  \, d\tau\leq M^2(t_{1}-t_{0})\left\| x_{0} \right\| ^{2} $$
> 2. Obvious from definition.
> 3. $x_{0}$ is unobservable if and only if $\mathcal{L}_{o}(x_{0})=0$. 
> 4. $(C(\cdot),A(\cdot))$ is observable on $[t_{0},t_{1}]$ if and only if $\mathcal{L}_{o}$ is injective.
---
> [!lemma] Lemma 3
> The observability gramian $W_{o}(t_{0},t_{1})$ has the following properties:
> 1. Symmetric positive semi-definite: $W_{o}(t_{0},t_{1})=W_{o}(t_{0},t_{1})^\top$
> 2. For all $t'_{1}\geq t_{1}$, $W_{o}(t_{0},t'_{1})\geq W_{o}(t_{0},t_{1})$ i.e. for all $x\in \mathbb{R}^n$:$$x^\top[W_{o}(t_{0},t'_{1})-W_{o}(t_{0},t_{1})]x\geq 0$$

> [!proof]-
> We have that: 
> 1. Symmetry is easy to see. For any $x\in \mathbb{R}^n$:$$x^\top W_{o}(t_{0},t_{1})x=\int_{t_{0}}^{t_{1}} x^\top\Phi(\tau,t_{0})^\top C (\tau)^\top C(\tau)\Phi(\tau,t_{0})x \, d\tau=\int_{t_{0}}^{t_{1}} \|C(\tau)\Phi(\tau,t_{0}) x\|^{2} \, d\tau \geq 0$$
> 2. We have that: $$x^\top[W_{o}(t_{0},t'_{1})-W_{o}(t_{0},t_{1})]x=\int_{t_{1}}^{t'_{1}} \left\| C(\tau)\Phi(\tau,t_{0})x \right\|^{2}  \, d\tau\geq 0 $$
---
> [!lemma] Theorem 4
> For $t_{0}<t_{1}$, the following statements are equivalent:
> 1. $(C(\cdot),A(\cdot))$ is observable on $[t_{0},t_{1}]$
> 2. $\text{ker }\mathcal{L}_{o}=\{ 0 \}$.
> 3. $\text{ker}(\mathcal{L}_{o}^{*}\circ\mathcal{L}_{o})=\{ 0 \}$.
> 4. $\det(W_{o}(t_{0},t_{1}))\neq 0$, i.e. $W_{o}(t_{0},t_{1})$ is positive definite.

> [!proof]-
> We have that: 
> - 1 <=> 2: From Lemma 2.
> - 2 <=> 3: By the finite rank lemma.
> - 3 <=> 4: We will show that $(\mathcal{L}_{o}^{*}\circ\mathcal{L}_{o})(x)=W_{o}(t_{0},t_{1})(x)$ for all $x\in \mathbb{R}^n$. We can see that: $$\mathcal{L}_{o}^{*}(v)=\int_{t_{0}}^{t_{1}} \Phi(\tau,t_{0})^\top C(\tau)^\top v(\tau) \, d\tau $$and therefore, $$(\mathcal{L}_{o}^{*}\circ \mathcal{L}_{o})(x)=\int_{t_{0}}^{t_{1}} \Phi(\tau,t_{0})^\top C(\tau)^\top C(\tau)\Phi(\tau,t_{0})x d\tau =W_{o}(t_{0},t_{1})x$$Therefore, the linear map has the trivial kernel, if and only if the matrix is invertible.
---
> [!lemma] Theorem 5 (Duality Theorem)
> Let $\mathcal{S}_{1}$ be the following system: $$\begin{align}\dot{x}(t)&=A(t)x(t)+B(t)u(t)\\y(t)&=C(t)x(t)+D(t)u(t)\end{align}$$and $\mathcal{S}_{2}$ its dual: $$\begin{align}\dot{\overline{x}}(t)&=-A(t)^\top \overline{x}(t)-C(t)^\top \overline{u}(t)\\\overline{y}(t)&=B(t)^\top \overline{x}(t)+D(t)^\top \overline{u}(t)\end{align}$$
> Then, the following statements hold:
> 1. $\Phi_{2}(t,t_{0})=\Phi_{1}(t_{0},t)^\top$
> 2. $\mathcal{S}_{1}$ is controllable on $[t_{0},t_{1}]$ if and only if $\mathcal{S}_{2}$ is observable on $[t_{0},t_{1}]$.
> 3. $\mathcal{S}_{1}$ is observable on $[t_{0},t_{1}]$ if and only if $\mathcal{S}_{2}$ is controllable on $[t_{0},t_{1}]$.

> [!proof]-
> We have that: 
> 1. As $\frac{ \partial  }{ \partial t }\Phi_{2}(t,t_{0})=-A(t)^\top\Phi_{2}(t,t_{0})$:
>    $$\begin{align}\Phi_{1}(t_{0},t)\Phi_{1}(t,t_{0})&=I\\\frac{ \partial  }{ \partial t } \Phi_{1}(t_{0},t)\Phi_{1}(t,t_{0})+\Phi_{1}(t_{0},t)\frac{ \partial  }{ \partial t }\Phi_{1}(t,t_{0})&=0 \\\frac{ \partial  }{ \partial t } \Phi_{1}(t_{0},t)\Phi_{1}(t,t_{0})&=-\Phi_{1}(t_{0},t)A(t)\Phi_{1}(t,t_{0})\\\frac{ \partial  }{ \partial t } \Phi_{1}(t_{0},t)^\top&=-A(t)^\top\Phi_{1}(t_{0},t)^\top\end{align}$$and it holds by the uniqueness of the solution.
>  2. $\mathcal{S}_{2}$ is observable on $[t_{0},t_{1}]$ if and only if $W_{o}(t_{0},t_{1})$ is invertible: $$\begin{align}\int_{t_{0}}^{t_{1}}\Phi_{2}(\tau,t_{0})^\top B(\tau) B(\tau)^\top\Phi_{2}(\tau,t_{0})  \, d\tau&=\int_{t_{0}}^{t_{1}}\Phi_{1}(t_{0},\tau) B(\tau) B(\tau)^\top\Phi_{1}(t_{0},\tau)^\top  \, d\tau\\&=\Phi_{1}(t_{0},t_{1})W_{r}(t_{0},t_{1})\Phi_{1}(t_{0},t_{1})^\top\end{align} $$
>     As $\Phi_{1}(t_{0},t_{1})$ is invertible, $W_{o}(t_{0},t_{1})$ is invertible if and only if $W_{r}(t_{0},t_{1})$ is invertible.
>   3. $\mathcal{S}_{2}$ is controllable on $[t_{0},t_{1}]$ if and only if $W_{r}(t_{0},t_{1})$ is invertible: $$\begin{align}\int_{t_{0}}^{t_{1}}\Phi_{2}(t_{1},\tau)C(\tau)^\top C(\tau)\Phi_{2}(t_{1},\tau)^\top  \, d\tau&=\Phi_{2}(t_{1},t_{0})\int_{t_{0}}^{t_{1}}\Phi_{2}(t_{0},\tau)C(\tau)^\top C(\tau)\Phi_{2}(t_{0},\tau)^\top  \, d\tau \Phi_{2}(t_{1},t_{0})^\top\\&=\Phi_{2}(t_{1},t_{0})\int_{t_{0}}^{t_{1}}\Phi_{1}(\tau,t_{0})^\top C(\tau)^\top C(\tau)\Phi_{1}(\tau,t_{0}) \, d\tau \Phi_{2}(t_{1},t_{0})^\top\\&=\Phi_{2}(t_{1},t_{0})W_{o}(t_{0},t_{1}) \Phi_{2}(t_{1},t_{0})^\top\end{align} $$
---
> [!lemma] Theorem 6
> Assume that $(C(\cdot),A(\cdot))$ is observable on $[t_{0},t_{1}]$. For any $y(\cdot):L^2([t_{0},t_{1}],\mathbb{R}^p)$: $$x_{0}=[(\mathcal{L}^{*}_{o}\circ \mathcal{L}_{o})^{-1}\mathcal{L}^{*}_{o}](y)=W_{o}(t_{0},t_{1})^{-1}\int_{t_{0}}^{t_{1}} \Phi(\tau,t_{0})^\top C(\tau)^\top y(\tau) \, d\tau $$is the unique minimizer of $\underset{ x\in \mathbb{R}^n }{ \text{argmin} }\left\| y-\mathcal{L}_{o}(x) \right\|^2_{2}$ with value $$\left\| y-\mathcal{L}_{o}(x_{0}) \right\|^2_{2}=\left\| y \right\| ^2_{2}-x_{0}^\top W_{o}(t_{0},t_{1})x_{0} $$

> [!proof]+
---
##### Linear Time-Invariant Systems
> [!definition]
> For the linear time-varying system $$\begin{align}\dot{x}(t)&=Ax(t)+Bu(t)\\y(t)&=Cx(t)+Du(t)\end{align}$$ the ***observability matrix*** is defined as: $$O=\begin{bmatrix}C\\CA\\ \vdots\\CA^{n-1}\end{bmatrix}\in \mathbb{R}^{np,n}$$
> 
---
> [!lemma] Lemma 7
> The observability matrix $O$ has the following properties
> 1. for all $t_{0}<t_{1}$, $\text{ker }O=\text{ker }\mathcal{L}_{o}=\{ x_{0}\in \mathbb{R}^n:x_{0}\text{ is unobservable} \}$
> 2. $\text{ker }O$ is an $A$-invariant subspace, i.e. for all $x_{0}\in \text{ker }O$, $Ax_{0}\in \text{ker }O$.

> [!proof]-
> We have that: 
> 1. $x_{0}\in \mathbb{R}^n$ is unobservable if and only if $x_{0}\in \text{ker }\mathcal{L}_{o}$ from Lemma 2. As we have time-invariant, we can wlog assume that $t_{0}=0$ and: $$\begin{align}C\Phi(t,0)x_{0}&=0&&\forall t\in[0,t_{1}]\\Ce^{At}x_{0}&=0&&\forall t\in[0,t_{1}]\\C\left( I+At+ \frac{A^{2}t^{2}}{2}+\dots \right)x_{0}&=0&&\forall t\in[0,t_{1}]\\CA^kx_{0}&=0&&k=0,1,\dots,n-1\\Ox_{0}&=0 \end{align}$$Therefore, $\text{ker }O=\text{ker }\mathcal{L}_{o}$.
> 2. For $x_{0}\in \text{ker }O$, i.e. $CA^kx_{0}=0$ for all $k=0,1,\dots,n-1$. Then, $$CA^{k+1}x_{0}=0$$Therefore, $Ax_{0}\in \text{ker }O$
---
> [!lemma] Theorem 8
> For any $t_{0}<t_{1}$, the following are equivalent: 
> 1. $(C,A)$ is observable on $[t_{0},t_{1}]$.
> 2. $\text{rank}(O)=n$
> 3. for all $\lambda\in \mathbb{C}$: $$\text{rank}\begin{bmatrix}\lambda I-A\\C \end{bmatrix}=n$$

> [!proof]-
> For $[t_{0},t_{1}]$ with $t_{0}=0$, 
> - (1<=>2) We have that: $$\begin{align}(C,A)\text{ is observable on }[t_{0},t_{1}]&\iff \text{ker }\mathcal{L}_{o}=\{ 0 \}\\&\iff \text{ker }O=\{ 0 \}\\&\iff \text{rank }O=n\end{align}$$
> - (1=>3): Assume there exists $\lambda\in \mathbb{C}$ s.t. $$\text{rank}\begin{bmatrix}\lambda I-A\\C \end{bmatrix}<n$$ Then, the columns are linearly dependent and there exists $v\neq 0$ s.t. $$\begin{bmatrix}(\lambda I-A)v\\Cv\end{bmatrix}=\begin{bmatrix}0\\0\end{bmatrix}$$Therefore, $\lambda$ is the eigenvalue of $A$ with $v$ as eigenvector and $Cv=0$. Recall that if $v\in \mathbb{C}^n$ is an eigenvector of $A$, then: $$s(t,0,v,0)=e^{At}v=e^{\lambda t}v$$Hence, $$Ce^{At}v=e^{\lambda t}Cv=0$$for all $t\geq 0$, i.e. $v$ is unobservable. Therefore, $(C,A)$ is not observable.
> - (3=>2): If $\text{rank}(O)<n$, then $\text{ker }O=r>0$ and there exists a basis $\{ v_{1},\dots,v_{r} \}$ for $\text{ker }O$. Let $w_{1},\dots,w_{n-r}$ be a basis for $\text{ker }O^\bot$. Therefore, we will assume that all vectors $x\in \mathbb{R}^n$ is represented in this basis $\{ w_{1},\dots,w_{n-r},v_{1},\dots,v_{r} \}$. 
>   
>   Then, for $x\in \text{ker }O$, we have: $$x=\begin{bmatrix}0\\x_{2}\end{bmatrix}$$and $$Ax=\begin{bmatrix}A_{11}&A_{12}\\A_{21}&A_{22}\end{bmatrix}\begin{bmatrix}0\\x_{2} \end{bmatrix}=\begin{bmatrix}A_{12}x_{2}\\A_{22}x_{2}\end{bmatrix}$$As $\text{ker }O$ is a $A$-invariant subspace, $A_{12}x_{2}=0$ for all $x_{2}\in \mathbb{R}^r$. Therefore, $A_{12}=0$.
>   
>   Similarly, we have that $x\in \text{ker }C$ and: $$Cx=\begin{bmatrix}C_{1}&C_{2}\end{bmatrix}\begin{bmatrix}0\\x_{2}\end{bmatrix}=C_{2}x_{2}=0$$Hence, $C_{2}=0$. 
>   
>   Bringing them together, we have the system: $$\begin{array}{ccccccc}\dot{x}_{1}(t)&=&A_{11}x_{1}(t)&&&+&B_{1}u(t)\\\dot{x}_{2}(t)&=&A_{21}x_{1}(t)&+&A_{22}x_{2}(t)&+&B_{2}u(t)\\y(t)&=&C_{1}x_{1}(t)&&&+&Du(t)\end{array}$$Then, an eigenvalue $\lambda\in \mathbb{C}$ of $A_{22}$ with eigenvector $v\in \mathbb{R}^r$ will have that: $$\begin{bmatrix}\lambda I-A\\C\end{bmatrix}\begin{bmatrix}0\\v\end{bmatrix}=\begin{bmatrix}0\\(\lambda I-A_{22})v\\0\end{bmatrix}=\begin{bmatrix}0\\0\\0\end{bmatrix}$$which means that the columns are linearly dependent and the matrix has rank $<n$.

- **Remark**: The conditions 2 and 3 are independent of $t_{0},t_{1}$. Therefore, being observable on $[t_{0},t_{1}]$ is equivalent to being observable on any $[t_{0},t_{1}]$.
---
> [!lemma] Corollary 9
> For any $C\in \mathbb{R}^{p,n}$ and $A\in \mathbb{R}^{n,n}$, there exists $T\in \mathbb{R}^{n,n}$ with $\det T\neq 0$ s.t. $$\hat{A}:=TAT^{-1}=\begin{bmatrix}A_{11}&0\\A_{21}&A_{22}\end{bmatrix},\quad \hat{C}:=CT^{-1}=\begin{bmatrix}C_{1}&0\end{bmatrix}$$and $(C_{1},A_{11})$ is observable.

> [!proof]-
> If $(C_{1},A_{11})$ is not observable, there exists $x_{1}\in\mathbb{R}^{n-r}$ s.t. $x_{1}\neq 0$ and $$\begin{bmatrix}C_{1}\\C_{1}A_{11}\\\vdots\\C_{1}A_{11}^{n-r-1}\end{bmatrix}x_{1}=0$$Therefore, by Cayley-Hamilton, $C_{1}A^k_{11}x_{1}=0$ for all $k\geq 1$. Therefore, $$O\begin{bmatrix}x_{1}\\0\end{bmatrix}=\begin{bmatrix}C_{1}&0\\C_{1}A_{11}&0\\\vdots&\vdots\\C_{1}A_{11}^{n-1}&0\end{bmatrix}\begin{bmatrix}x_{1}\\0\end{bmatrix}=0$$Therefore, $[x_{1},0]^\top\in \text{ker }O$. However, as $x_{1}\in \text{ker }O^{\bot}$, $x_{1}=0$ which is a contradiction.
---
