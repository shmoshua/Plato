#Definition #AGAO 

> [!definition]
> Let $f:X\to \mathbb{R}$ be a differentiable function where $X\subseteq \mathbb{R}^n$ is convex, open. 
> 1. $f$ is ***$\beta$-gradient Lipschitz/$\beta$-smooth*** if for all $x,y\in X$, $$\left\| \nabla f(x)-\nabla f(y) \right\| _{2}\leq \beta \left\| x-y \right\| _{2}$$

---
##### Properties
> [!lemma] Proposition 1
> Let $f\in C^2(X)$. Then,
> 1. $f$ is $\beta$-gradient Lipschitz if and only if $\left\| \nabla^{2}f(x) \right\|\leq \beta$ for all $x\in X$.
---
> [!lemma] Proposition 2
> Let $f:X\to \mathbb{R}$ be $\beta$-gradient Lipschitz. 
> 1. for all $x,y\in X$, $$f(y)\leq f(x)+\nabla f(x)^\top(y-x)+\frac{\beta}{2}\left\| y-x \right\| ^{2}_{2}$$

> [!proof]-
> From [[Taylor's Theorem|Theorem 1]], we have that: $$f(y)=f(x)+\int_{0}^{1} \nabla f(x+t(y-x))^\top(y-x) \, dt $$Therefore, $$\begin{aligned}f(y)&=f(x)+\int_{0}^{1} \nabla f(x+t(y-x))^\top(y-x) \, dt\\&=f(x)+\int_{0}^{1} \nabla f(x)^\top(y-x) \, dt+\int_{0}^{1} (\nabla f(x+t(y-x))-\nabla f(x))^\top(y-x) \, dt \\&\leq f(x)+\int_{0}^{1} \nabla f(x)^\top(y-x) \, dt+\int_{0}^{1} \|\nabla f(x+t(y-x))-\nabla f(x)\|\cdot \|y-x\|  \, dt\\&\leq f(x)+\int_{0}^{1} \nabla f(x)^\top(y-x) \, dt+\beta\int_{0}^{1}  t\|y-x\|^{2}  \, dt \\&\leq f(x)+ \nabla f(x)^\top(y-x) +\frac{\beta}{2}\|y-x\|^{2} \end{aligned}$$

---
> [!lemma] Theorem 3 (Gradient Descent)
> Let $f:X\to \mathbb{R}$ be a convex, $\beta$-gradient Lipschitz function and $x_{0}\in X$. Further, let $$x_{i+1}:=x_{i}-\frac{1}{\beta}\nabla f(x_{i})$$Then, the $k$-th iterate satisfies: $$f(x_{k})-f(x^{*})\leq \frac{2\beta \left\| x_{0}-x^{*} \right\| ^{2}_{2}}{k+1}$$where $x^{*}\in \text{argmin}f(x)$. 

> [!proof]-
> Let $\text{gap}_{i}:=f(x_{i})-f(x^{*})$.
> 1. **Claim 1**: $f(x_{i+1})\leq f(x_i)-\frac{\|\nabla f(x_{i})\|^2_{2}}{2\beta}$ for all $i$.
>    We have that from Proposition 2: $$f(x_{i+1})\leq f(x_{i})-\frac{1}{\beta}\|\nabla f(x_{i})\|^{2}_{2}+\frac{1}{2\beta}\|\nabla f(x_{i})\|^{2}_{2}= f(x_{i})-\frac{1}{2\beta}\|\nabla f(x_{i})\|^{2}_{2}$$Further, $\text{gap}_{i+1}-\text{gap}_{i}=f(x_{i+1})-f(x_{i})\leq -\frac{1}{2\beta}\|\nabla f(x_{i})\|^{2}_{2}$. 
> 2. **Claim 2**: $\text{gap}_{i}\leq \left\| \nabla f(x_{i}) \right\|_{2}\left\| x_{i}-x^{*} \right\|_{2}$. 
>    As $f$ is convex, we have by [[Convex Function|first order convexity]], $$\text{gap}_{i}=f(x_{i})-f(x^{*})\leq \nabla f(x_{i})^\top(x_{i}-x^{*})\leq \left\| \nabla f(x_{i}) \right\| \left\| x_{i}-x^{*} \right\| $$
> 3. **Claim 3**: $\left\| x_{i}-x^{*} \right\|_{2}\leq \left\| x_{0}-x^{*} \right\|_{2}$. 
> 
> Therefore, we have that: $$\text{gap}_{i+1}-\text{gap}_{i}\leq -\frac{1}{2\beta}\left( \frac{\text{gap}_{i}}{\|x_0-x^{*}\|_{2}} \right) ^{2}$$
> 
> Now we prove the claim using induction over $i$. 
> 
>  4. Let $i=0$. Then, $$\text{gap}_{0}=f(x_{0})-f(x^{*})\leq \nabla f(x_{0})^\top(x_{0}-x^{*})\leq \left\| \nabla f(x_{0}) \right\|_{2}\left\| x_{0}-x^{*} \right\| _{2}\leq \beta \left\| x_{0}-x^{*} \right\| _{2}^2$$where for the first inequality, we use the convexity, for the second we use Cauchy-Schwarz and for the last, $\beta$-gradient-Lipschitzness and $\nabla f(x^{*})=0$. Therefore, the statement holds.
>  5. Let $i\geq 1$. Then, from the lectures, we have that: $$\frac{1}{\text{gap}_{i+1}}-\frac{1}{\text{gap}_{i}}=\frac{\text{gap}_{i}-\text{gap}_{i+1}}{\text{gap}_{i+1}\text{gap}_{i}}\geq \frac{1}{2\beta\|x_0-x^{*}\|^{2}_{2}}\cdot \frac{\text{gap}_{i}}{\text{gap}_{i+1}}\geq \frac{1}{2\beta\|x_0-x^{*}\|^{2}_{2}}$$Therefore,$$\frac{1}{\text{gap}_{i+1}}\geq \frac{1}{\text{gap}_{i}}+\frac{1}{2\beta \left\| x_{0}-x^{*} \right\| ^{2}_{2}}\geq \frac{i+1}{2\beta \left\| x_{0}-x^{*} \right\| ^2_{2}}$$This proves the statement.
> >    