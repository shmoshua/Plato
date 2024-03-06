#Series #Analysis 

> [!definition] Problem 3
> Determine whether the following sets $X$ are well-defined, open, close, subspaces and convex.
> 1. In the normed space $(C([0,1]),\|\cdot\|_{\infty})$ the subset $X$ of nowhere vanishing functions.
> 2. In the normed space $(C([0,1]),\|\cdot \|_{2})$, the subset $X$ of nowhere vanishing functions.
> 3. In the normed space $(L^2([0,1]),\|\cdot\|_{2})$, the subset $X=\left\{  f:\int_{0}^{1} f \, dx =1  \right\}$.
> 4. In the normed space $(L^2(\mathbb{R}),\|\cdot\|_{2})$, the subset $\{ f:f(x)=f(-x)\text{ for a.e.}x\in \mathbb{R} \}$.
> 5. In the normed space $(L^2([0,1]),\|\cdot\|_{2})$, the subset $X=\left\{  f:f\geq 0\land \int_{0}^{1} \frac{2f}{1+f} \, dx \geq 1 \right\}$.

We have:
1. 
1. **$X$ is not well-defined**: Consider $f(x)=\frac{1}{2\sqrt{ x }}$. Then, $$\int_{0}^{1} \frac{1}{2\sqrt{ x }} \, dx =\sqrt{ x }|^1_{0}=1$$and $f\in X$. However, $$\|f\|_{2}^2=\int_{0}^{1} \frac{1}{4x} \, dx=\frac{1}{4} \ln x=+\infty$$
