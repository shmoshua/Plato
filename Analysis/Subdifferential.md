#Definition #Analysis 

> [!definition]
> Let $f:\mathbb{R}^n\to \mathbb{R}$. 
> 1. A vector $g\in \mathbb{R}^n$ is a ***subgradient*** of $f$ at $x\in \text{dom }f$ if: $$f(z)\geq f(x)+g^\top (z-x),\quad \forall z\in \text{dom }f$$
> 2. The ***subdifferential*** $\partial f(x)$ of $f$ at $x\in \text{dom }f$ is the set of all subgradients of $f$ at $x$.
> 3. $f$ is ***subdifferentiable*** at $x$ if $\partial f(x)\neq \varnothing$.
> 4. $f$ is ***subdifferentiable*** if it is subdifferentiable at all $x\in \text{dom }f$.
- **Remark**: If $f$ is convex and differentiable, $\nabla f(x)$ is a subgradient of $f$ at $x$. (cf. [[Convex Function]])

---
##### Examples
> [!h] Example 1 (Absolute Value)
> Let $f:\mathbb{R}\to \mathbb{R},z\mapsto \left| z \right|$. 
> 1. for $x< 0$, $\partial f(x)=\{ -1 \}$.
> 2. for $x> 0$, $\partial f(x)=\{ 1 \}$.
> 3. $\partial f(0)=[-1,1]$.

> [!proof]+
> We have that:
> 1. We know $-1\in \partial f(x)$ as it is differentiable at $x<0$ with gradient $-1$. Then, for $\lambda\in \mathbb{R}$, 
> 	- $-2x \geq -x + \lambda x$ and $-1\geq \lambda$.
> 	- $-\frac{1}{2}x\geq -x-\frac{\lambda}{2}x$
> 2. $$-\frac{1}{2}x \geq - x + \lambda\left( -\frac{1}{2}x \right) $$