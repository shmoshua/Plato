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

> [!proof]+
> We have that: 
> 6. By definition: $$\partial f(x)=\bigcap_{z\in \text{dom f}}^{}\{ g\in \mathbb{R}^n:f(z)\geq f(x)+g^\top (z-x) \}$$
> 7. Choose $\varepsilon>0$ s.t. for all $\left\| y-x \right\|_{2}<\varepsilon$, we have that $f(y)$ is bounded. If $\partial f(x)$ is unbounded, let $g_{n}\in \partial f(x)$ be the sequence s.t. $\left\| g_{n} \right\|_{2}\to \infty$. Let $y_{n}:=x+\frac{\varepsilon g_{n}}{\left\| g_{n} \right\|_{2}}$. Then, $$f(y_{n})\geq f(x)+\varepsilon \left\| g_{n} \right\|_{2} \to \infty$$which is a contradiction to $f(y_{n})$ being bounded.
> 8. As $\text{epi }f$ is a convex set and $(x,f(x))$ a boundary point, we have by separating hyperplane theorem that there exist $a\in \mathbb{R}^n,b\in \mathbb{R}^n$ not both zero s.t.: $$\begin{bmatrix} a \\ b\end{bmatrix}^\top\left( \begin{bmatrix} z \\ t\end{bmatrix} -\begin{bmatrix} x \\ f(x)\end{bmatrix}\right) =a^\top(z-x)+b(t-f(x))\leq 0,\quad \forall(z,t)\in \text{epi }f$$By considering $(x,t')\in \text{epi }f$ for $t'>t$ we have $b\leq 0$ and by considering $(z,f(z))$, we have: $$a^\top(z-x)+b(f(z)-f(x))\leq 0,\quad \forall z$$If $b=0$, then $a^\top(z-x)\leq 0$ for all $z\in \text{dom }f$. However, this is impossible as $x\in (\text{dom }f)^\circ$. Hence, $b<0$, and we have: $$f(z)\geq f(x)-\frac{1}{b}a^\top(z-x)$$and $-\frac{1}{b}a^\top\in \partial f(x)$.
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