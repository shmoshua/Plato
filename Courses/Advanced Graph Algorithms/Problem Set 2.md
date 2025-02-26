#Series #AGAO 

#### Problem 1
Let $A\in \text{Mat}_{n,n}(\mathbb{R})$ be symmetric. Then, it admits a decomposition $A=Q\Lambda Q^\top$ where $Q$ is orthogonal and $\Lambda$ is diagonal. Therefore, $$\|A\|=\|Q\Lambda Q^\top\|=\|\Lambda Q^\top\|=\|Q\Lambda^\top\|=\|\Lambda^\top\|=\|\Lambda\|=\sup_{\|x\|=1}\|\Lambda x\|$$and where we use the orthogonality of $Q$ and the fact that induced norm is invariant under transposition, given by Hahn-Banach. 

We claim that $\sup_{\|x\|=1}\|\Lambda x\|= \max_{i}|\lambda_{i}|=\max(\left| \lambda_{\max}(A) \right|,\left| \lambda_{\min}(A) \right|)$. 

Let $j\in[n]$ s.t. $\left| \lambda_{j} \right|=\max_{i}\left| \lambda_{i} \right|$. Then, $\|\Lambda e_{j}\|=\left| \lambda_{j} \right|$ and $\sup_{\|x\|=1}\left\| \Lambda x \right\|\geq \max_{i}\left| \lambda_{i} \right|$. Conversely, for any $\|x\|=1$, we have that: $$\left\| \Lambda x \right\| ^{2}=\sum_{i=1}^{n}\left| \lambda_{i} \right|^{2} x_{i}^{2}\leq \left| \lambda_{j} \right| ^{2}\sum_{i=1}^{n}x_{i}^{2}=\left| \lambda_{j} \right| ^{2}$$Hence, $\left\| \Lambda x \right\|\leq \max_{i}\left| \lambda_{i} \right|$ for all $x$ with $\|x\|=1$ and we have the statement.


Now, consider $$A:=\begin{bmatrix}0&2\\0 &0\end{bmatrix}$$Then, the eigenvalues of $A$ are only zero. However, for $x=(0,1)$, we have $\|Ax\|_{2}=2>0$.

---
#### Problem 2
Assume $f$ is $\beta$-gradient Lipschitz. Let $x\in S$ and as $S$ is open, there exists $r>0$ s.t. $B_{\leq r}(x)\subseteq S$. Let $\delta\in B_{\leq r}(x)$. Then, we have: $$\nabla f(x+\delta)-\nabla f(x)=H_{f}(x)\delta+R(\delta)$$where $R(\delta)_{i}=o(\|\delta\|_{2})$ for all $i\in[n]$. Hence, 

$$\beta\|\delta\|_{2}\geq\|\nabla f(x+\delta)-\nabla f(x)\|_{2}=\|H_{f}(x)\delta+R_{1}(\delta) \|_{2}$$and:$$\frac{\left\| H_{f}(x)\delta \right\| _{2}}{\left\| \delta \right\| _{2}}\leq\beta +o(1) $$
Hence, for any unit vector $u$, we have as $t\to 0$: $$\|H_{f}(x)u\|_{2}=\lim_{ t \to 0 } \frac{\left\| H_{f}(x)tu \right\| _{2}}{\left\| tu \right\|_{2} }\leq \beta,\quad \left\| H_{f}(x) \right\| \leq \beta$$

Conversely, let $\left\| H_{f}(x) \right\|\leq \beta$. Then, for any $x,y\in S$, there exists $z\in [x,y]$ s.t.:  $$\left\| \nabla f(y)-\nabla f(x) \right\|_{2}= \left\| H_{f}(z)(y-x) \right\|_{2}\leq \left\| H_{f}(z) \right\| \left\| y-x \right\| _{2}\leq \beta \left\| y-x \right\| _{2} $$
This proves the statement.

---
#### Problem 3
We will show that $\|x_{i+1}-x^{*}\|_{2}\leq \|x_{i}-x^{*}\|_{2}$ for all $i$. Then, it holds that: $$\left\| x_{i+1}-x^{*} \right\| _{2}\leq \left\| x_{i}-x^{*} \right\| _{2}\leq\dots\leq \left\| x_{0}-x^{*} \right\| _{2}$$Notice that: $$\left\| x_{i+1}-x^{*} \right\| _{2}^2=\left\| x_{i}-\frac{1}{\beta}\nabla f(x_{i})-x^{*} \right\|^2_{2}=\left\| x_{i}-x^{*} \right\| ^2_{2}-\frac{2}{\beta}\nabla f(x_{i})^\top(x_{i}-x^{*})+\frac{1}{\beta^{2}}\left\| \nabla f(x_{i}) \right\|^{2}_{2}  $$Therefore, it suffices to show that $\frac{1}{\beta^{2}}\left\| \nabla f(x_{i}) \right\|^{2}_{2} -\frac{2}{\beta}\nabla f(x_{i})^\top(x_{i}-x^{*})\leq 0$. By convexity, we have: $$f(x_{i})-f(x^{*})\leq \nabla f(x_{i})^\top(x_{i}-x^{*})$$and from the lectures we get that: $$\frac{1}{2\beta}\left\| \nabla f(x_{i}) \right\| ^{2}_{2}\leq f(x_{i})-f(x_{i+1})$$Hence, $$\frac{1}{\beta^{2}}\left\| \nabla f(x_{i}) \right\|^{2}_{2} -\frac{2}{\beta}\nabla f(x_{i})^\top(x_{i}-x^{*})\leq \frac{2}{\beta}\left( f(x_{i})-f(x_{i+1})-f(x_{i})+f(x^{*}) \right) =\frac{2}{\beta}(f(x^{*})-f(x_{i+1}))\leq 0$$as $f(x^{*})\leq f(x_{i+1})$. This proves the statement.

---
#### Problem 4
We show this by induction over $i$. 
1. Let $i=0$. Then, $$\text{gap}_{0}=f(x_{0})-f(x^{*})\leq \nabla f(x_{0})^\top(x_{0}-x^{*})\leq \left\| \nabla f(x_{0}) \right\|_{2}\left\| x_{0}-x^{*} \right\| _{2}\leq \beta \left\| x_{0}-x^{*} \right\| _{2}^2$$where for the first inequality, we use the convexity, for the second we use Cauchy-Schwarz and for the last, $\beta$-gradient-Lipschitzness and $\nabla f(x^{*})=0$. Therefore, the statement holds.
2. Let $i\geq 1$. Then, from the lectures, we have that: $$\text{gap}_{i+1}\leq \text{gap}_{i}-\frac{1}{2\beta}\frac{\text{gap}_{i}^{2}}{\left\| x_{0}-x^{*} \right\| ^2_{2}}=\frac{\text{gap}_{i}(2\beta \left\| x_{0}-x^{*} \right\| ^{2}_{2}-\text{gap}_{i})}{2\beta \left\| x_{0}-x^{*} \right\| ^{2}_{2}}$$Hence, $$\frac{1}{\text{gap}_{i+1}}\geq \frac{2\beta \left\| x_{0}-x^{*} \right\| ^{2}_{2}}{\text{gap}_{i}(2\beta \left\| x_{0}-x^{*} \right\| ^{2}_{2}-\text{gap}_{i})}=\frac{1}{\text{gap}_{i}}+\frac{1}{2\beta \left\| x_{0}-x^{*} \right\| ^{2}_{2}-\text{gap}_{i}}$$Now, as $\text{gap}_{i}\leq \text{gap}_{i-1}-\frac{\left\| \nabla f(x_{i-1}) \right\|^2_{2}}{2\beta}\leq \text{gap}_{i-1}$ for all $i$, from Case 1, $\text{gap}_{i}\leq 2\beta \left\| x_{0}-x^{*} \right\|^2_{2}$ and we get the relation: $$\frac{1}{\text{gap}_{i+1}}\geq \frac{1}{\text{gap}_{i}}+\frac{1}{2\beta \left\| x_{0}-x^{*} \right\| ^{2}_{2}-\text{gap}_{i}}\geq \frac{1}{\text{gap}_{i}}+\frac{1}{2\beta \left\| x_{0}-x^{*} \right\| ^{2}_{2}}\geq \frac{i+1}{2\beta \left\| x_{0}-x^{*} \right\| ^2_{2}}$$This proves the statement.

---
#### Problem 5
1. Firstly, $g:x\mapsto \left| x \right|$ is convex on $\mathbb{R}$ by triangle inequality. Further, $h:x\mapsto x^p$ is convex on $[0,\infty)$ for any $p\geq 1$. Indeed, $h''(x)=p(p-1)x^{p-2}\geq 0$. 
   
   Also, notice that $h$ is an increasing function for all $p$. Hence, $$\left| tx+(1-t)y \right| ^{p}=h(g(tx+(1-t)y))\leq h(tg(x)+(1-t)g(y))\leq t \left| x \right| ^p+(1-t)\left| y \right| ^p$$This shows the convexity of $f$.
   
   $f$ cannot be $\beta$-gradient-Lipschitz as it is not differentiable at $x=0$. 
2. $f$ is convex as $f''(x)=\exp(x)\geq 0$ for all $x\in \mathbb{R}$. However, it cannot be $\beta$-gradient-Lipschitz for any $\beta$ as $f''$ is unbounded by Proposition 3.3.2.
3. $f$ is convex as $\exp$ is convex on $\mathbb{R}$ and a restriction of a convex function is still convex. However, this time we also have that $f''(x)=\exp(x)\leq e$ for all $x\in (-1,1)$. Hence, $f$ is $e$-gradient-Lipschitz. 
4. We have that: $$H_{f}(x,y)=- \frac{1}{4\sqrt{ x+y }^3}\begin{bmatrix}1&1\\1&1\end{bmatrix}$$which has $\left( 0,-\frac{1}{2\sqrt{ x+y }^3} \right)$ as eigenvalues. Hence, $H_{f}(x,y)$ cannot be positive semidefinite and $f$ is not convex. However, we have that $\left\| H_{f}(x,y) \right\|=\frac{1}{2\sqrt{ x+y }^3}$ from Exercise 1 and $f$ cannot be $\beta$-gradient-Lipschitz as $\sup_{x,y\in(0,1)} \frac{1}{2\sqrt{ x+y }^3} =\infty$.
5. With the same reason as above $f$ is not convex. However, we have that: $$\sup_{x,y\in\left( \frac{1}{2},1 \right)} \frac{1}{2\sqrt{ x+y }^3}=\frac{1}{2}$$and $f$ is $\beta$-gradient-Lipschitz.
6. We have $f(x)=\|x\|$ on $x\in \mathbb{R}^{2}$. Hence, $f$ is a convex function by triangle inequality. Further, it is not $\beta$-gradient Lipschitz as it is not differentiable at $0$.

---
#### Problem 6
1. Let $x,y\in \mathbb{R}^n$. Wlog, we may assume that $x\neq y$. Then, by 2nd Taylor: $$f(y)=f(x)+\nabla f(x)^\top(y-x)+\frac{1}{2}(y-x)^\top H_{f}(z)(y-x)$$for some $z\in \mathbb{R}^n$. Note that as $H_{f}(z)$ is symmetric, by Courant-Fischer, $$\frac{(y-x)^\top H_{f}(z)(y-x)}{\|y-x\|^2_{2}}\geq\min_{u\in \mathbb{R}^n,u\neq 0}\frac{u^\top H_{f}(z)u}{\|u\|^2_{2}}=\lambda_{\min}(H_{f}(z))\geq \mu$$Hence, $$f(y)\geq f(x)+\nabla f(x)^\top(y-x)+\frac{\mu}{2}\|y-x\|^2_{2}$$
2. Fix $x_{0}\in \mathbb{R}^n$. Then, let: $$h:\mathbb{R}^n\to \mathbb{R},\quad x\mapsto \nabla f(x_{0})^\top(x-x_{0})+\frac{\mu}{2}\left\| x-x_{0} \right\| ^2_{2}$$We get that: $$\nabla h(x)=\nabla f(x_{0})+\mu(x-x_{0})$$Hence, $h$ attains a minimum at $x_{0}-\frac{1}{\mu}\nabla f(x_{0})$. Therefore, for any $x\in \mathbb{R}^n$: $$f(x)\geq f(x_{0})-\frac{1}{2\mu}\|\nabla f(x_{0})\|^2_{2}=:L$$
3. As the smallest eigenvalue is positive, $H_{f}(x)$ is positive definite for all $x\in \mathbb{R}^n$. Hence, $f$ is strictly convex. Assume $x^{*},y^{*}$ are two minimizers s.t. $x^{*}\neq y^{*}$. Then, $$f(x^{*})=f(y^{*})\geq f(x^{*})+\underbrace{ \nabla f(x^{*})^\top }_{=0 }(y^{*}-x^{*})+\frac{\mu}{2}\left\| y^{*}-x^{*} \right\| ^2_{2}=f(x^{*})+\frac{\mu}{2}\left\| y^{*}-x^{*} \right\| ^2_{2}$$Hence, $\frac{\mu}{2}\left\| y^{*}-x^{*} \right\|^2_{2}\leq 0$ which is a contradiction as $\mu> 0$ and $\left\| y^{*}-x^{*} \right\|^2_{2}> 0$.
4. Let $t\leq \frac{8\gamma}{\mu}\log(\left\| x_{0}-x^{*} \right\|_{2} / \delta)$.    We will iteratively generate a sequence $x_{1},\dots,x_{t}$. Given $x_{i-1}$, we let $x_{i}:=\text{DecentDescent}(x_{i-1},1)$. Then, $$\frac{\gamma \left\| x_{i-1}-x^{*} \right\|^2_{2}}{2} \geq f(x_{i})-f(x^{*})\geq \underbrace{ \nabla f(x^{*})^\top }_{ =0 }(x_{i}-x^{*})+\frac{\mu}{2}\left\| x_{i}-x^{*} \right\| ^2_{2}\geq \frac{\mu}{2}\left\| x_{i}-x^{*} \right\| ^2_{2}$$ Hence, $\left\| x_{i}-x^{*} \right\|^2_{2}\leq \frac{\gamma}{\mu}\left\| x_{i-1}-x^{*} \right\|^2_{2}$ and $\left\| x_{t}-x^{*} \right\|^2_{2}\leq (\frac{\gamma}{\mu})^t\left\| x_{0}-x^{*} \right\|^2_{2}$. 