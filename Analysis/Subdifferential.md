#Definition #Analysis 

> [!definition]
> Let $f:\mathbb{R}^n\to \mathbb{R}$. 
> 1. A vector $g\in \mathbb{R}^n$ is a ***subgradient*** of $f$ at $x\in \text{dom }f$ if: $$f(z)\geq f(x)+g^\top (z-x),\quad \forall z\in \text{dom }f$$
> 2. The ***subdifferential*** $\partial f(x)$ of $f$ at $x\in \text{dom }f$ is the set of all subgradients of $f$ at $x$.
> 3. $f$ is ***subdifferentiable*** at $x$ if $\partial f(x)\neq \varnothing$.
> 4. $f$ is ***subdifferentiable*** if it is subdifferentiable at all $x\in \text{dom }f$.
- **Remark**: If $f$ is convex and differentiable, $\nabla f(x)$ is a subgradient of $f$ at $x$. (cf. [[Convex Function]])
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\partial f(x)$ is a closed convex set, even when $f$ is not convex.
> 2. if $f$ is continuous at $x$, $\partial f(x)$ is bounded.
> 3. if $f$ is convex and $x\in (\text{dom }f)^\circ$, then $\partial f(x)$ is nonempty and bounded.
> 4. if $f$ is convex and differentiable at $x$, then $\partial f(x)=\{ \nabla f(x) \}$.
> 5. if $f$ is convex and $\partial f(x)=\{ g \}$, then $f$ is differentiable at $x$ and $g=\nabla f(x)$.

> [!proof]-
> We have that: 
> 1. By definition: $$\partial f(x)=\bigcap_{z\in \text{dom f}}^{}\{ g\in \mathbb{R}^n:f(z)\geq f(x)+g^\top (z-x) \}$$
> 2. Choose $\varepsilon>0$ s.t. for all $\left\| y-x \right\|_{2}<\varepsilon$, we have that $f(y)$ is bounded. If $\partial f(x)$ is unbounded, let $g_{n}\in \partial f(x)$ be the sequence s.t. $\left\| g_{n} \right\|_{2}\to \infty$. Let $y_{n}:=x+\frac{\varepsilon g_{n}}{\left\| g_{n} \right\|_{2}}$. Then, $$f(y_{n})\geq f(x)+\varepsilon \left\| g_{n} \right\|_{2} \to \infty$$which is a contradiction to $f(y_{n})$ being bounded.
> 3. As $\text{epi }f$ is a convex set and $(x,f(x))$ a boundary point, we have by separating hyperplane theorem that there exist $a\in \mathbb{R}^n,b\in \mathbb{R}^n$ not both zero s.t.: $$\begin{bmatrix} a \\ b\end{bmatrix}^\top\left( \begin{bmatrix} z \\ t\end{bmatrix} -\begin{bmatrix} x \\ f(x)\end{bmatrix}\right) =a^\top(z-x)+b(t-f(x))\leq 0,\quad \forall(z,t)\in \text{epi }f$$By considering $(x,t')\in \text{epi }f$ for $t'>t$ we have $b\leq 0$ and by considering $(z,f(z))$, we have: $$a^\top(z-x)+b(f(z)-f(x))\leq 0,\quad \forall z$$If $b=0$, then $a^\top(z-x)\leq 0$ for all $z\in \text{dom }f$. However, this is impossible as $x\in (\text{dom }f)^\circ$. Hence, $b<0$, and we have: $$f(z)\geq f(x)-\frac{1}{b}a^\top(z-x)$$and $-\frac{1}{b}a^\top\in \partial f(x)$.
> 4. Let $g\in \partial f(x)$. Then, we have that for any $u\in \mathbb{R}^n$: $$f(x+tu)\geq f(x)+tg^\top u$$Therefore, we have that: $$\braket{ \nabla f(x) , u } =\lim_{ t \to 0 } \frac{f(x+tu)-f(x)}{t} \geq \braket{ g , u } $$and $\braket{ \nabla f(x)-g , u }\geq 0$. As $u$ is arbitrary, we have that $\left\| \nabla f(x)-g \right\|=0$ and $g=\nabla f(x)$.

---
 > [!lemma] Proposition 2
 > Let $f:\mathbb{R}^n\to \mathbb{R}$.
 > 1. $x^{*}$ is a global minimizer of $f$ iff $0\in \partial f(x^{*})$.

> [!proof]-
> We have that:
> 1. if $x^{*}$ is a minimizer of $f$, then: $f(z)\geq f(x^{*})$. Conversely if $0\in \partial f(x^{*})$, for any $z$, $f(z)\geq f(x^{*})$.
---
> [!lemma] Proposition 3 (Subdifferential and Directional Derivative)
> Let $f:\mathbb{R}^n\to \mathbb{R}$ be a convex function.
> 1. $f'(x;v)=\sup_{g\in \partial f(x)}g^\top v$

> [!proof]-
> We have that:
> 1. By the definition, for $g\in \partial f(x)$: $$f(x+tv)\geq f(x)+t g^\top v$$and $f'(x;v)\geq \sup_{g\in \partial f(x)}g^\top v$. To show that $f'(x;v)\leq \sup_{g\in \partial f(x)}g^\top v$. 
---
> [!lemma] Lemma 4 (Subgradient Calculus)
> We have that:
> 1. $\partial(\alpha f)(x)=\alpha \partial f(x)$ for $\alpha\geq0$.
> 2. $\partial(f_{1}+\dots+f_{m})(x)=\partial f_{1}(x)+\dots+\partial f_{m}(x)$ if they're convex.
> 3. for convex $f$, let $h(x):=f(Ax+b)$. Then, $\partial h(x)=A^\top \partial f(Ax+b)$.
> 4. $\partial(\max_{i}f_{i})(x)=\text{conv}\left( \bigcup_{f_{i}(x)=f(x)}\partial f_{i}(x) \} \right)$ for finite number of convex functions.

> [!proof]-
> We have that:
> 5. For $g\in \mathbb{R}^n$, $$\alpha f(z)\geq \alpha f(x)+\alpha g^\top (z-x) \iff  f(z)\geq  f(x)+g^\top (z-x)$$
> 6. It suffices to show for two functions. Let $g\in \partial(f_{1}+f_{2})(x)$. Then: $$f_{1}(z)+f_{2}(z)\geq f_{1}(x)+f_{2}(x)+g^\top (z-x)$$
> 7. $\subseteq$: Let $g\in \partial h(x)$. Then, $$f(Az+b)\geq f(Ax+b)+g^\top (z-x)$$
>    
>    if $g\in \partial f(Ax+b)$, then $$f(z)\geq f(Ax+b)+g^\top(z-Ax-b)$$
---
##### Examples
> [!h] Example 1 (Absolute Value)
> Let $f:\mathbb{R}\to \mathbb{R},z\mapsto \left| z \right|$. 
> 1. for $x< 0$, $\partial f(x)=\{ -1 \}$.
> 2. for $x> 0$, $\partial f(x)=\{ 1 \}$.
> 3. $\partial f(0)=[-1,1]$.

> [!proof]-
> We have that:
> 1. We know $-1\in \partial f(x)$ as it is differentiable at $x<0$ with gradient $-1$. Then, for $\lambda\in \mathbb{R}$, 
> 	- $-2x \geq -x + \lambda x$ and $-1\leq  \lambda$.
> 	- $-\frac{1}{2}x\geq -x-\frac{\lambda}{2}x$ and $-1\geq \lambda$.
> 2. Similarly for $x>0$.
> 3. We have that: 
> 	- for $z>0$, $z\geq \lambda z$ and $z\geq -\lambda z$ and $\lambda\in[-1,1]$.
> 	- Conversely, $\lambda\in[-1,1]$ is a subgradient.