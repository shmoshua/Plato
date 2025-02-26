#Series #AGAO 

#### Problem 1
Let $A\in \text{Mat}_{n,n}(\mathbb{R})$ be symmetric. Then, it admits a decomposition $A=Q\Lambda Q^\top$ where $Q$ is orthogonal and $\Lambda$ is diagonal. Therefore, $$\|A\|=\|Q\Lambda Q^\top\|=\|\Lambda Q^\top\|=\|Q\Lambda^\top\|=\|\Lambda^\top\|=\|\Lambda\|=\sup_{\|x\|=1}\|\Lambda x\|$$and where we use the orthogonality of $Q$ and the fact that induced norm is invariant under transposition, given by Hahn-Banach. 

We claim that $\sup_{\|x\|=1}\|\Lambda x\|= \max_{i}|\lambda_{i}|=\max(\left| \lambda_{\max}(A) \right|,\left| \lambda_{\min}(A) \right|)$. 

Let $j\in[n]$ s.t. $\left| \lambda_{j} \right|=\max_{i}\left| \lambda_{i} \right|$. Then, $\|\Lambda e_{j}\|=\left| \lambda_{j} \right|$ and $\sup_{\|x\|=1}\left\| \Lambda x \right\|\geq \max_{i}\left| \lambda_{i} \right|$. Conversely, for any $\|x\|=1$, we have that: $$\left\| \Lambda x \right\| ^{2}=\sum_{i=1}^{n}\left| \lambda_{i} \right|^{2} x_{i}^{2}\leq \left| \lambda_{j} \right| ^{2}\sum_{i=1}^{n}x_{i}^{2}=\left| \lambda_{j} \right| ^{2}$$Hence, $\left\| \Lambda x \right\|\leq \max_{i}\left| \lambda_{i} \right|$ for all $x$ with $\|x\|=1$ and we have the statement.

If the steps above are unclear:
1. Claim 1: for an orthogonal matrix $A\in \text{Mat}_{n,n}(\mathbb{R})$, for any vector $x\in \mathbb{R}^n$, $$\|Ax\|_{2}^2=x^\top A^\top Ax=x^\top x=\|x\|^2_{2}$$
2. In particular, for any matrix $B\in \text{Mat}_{n,n}(\mathbb{R})$, $$\|AB\|=\sup_{\|x\|=1}\|ABx\|_{2}=\sup_{\|x\|=1}\|Bx\|_{2}=\|B\|$$

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
1. Firstly, $g:x\mapsto \left| x \right|$ is convex on $\mathbb{R}$ by triangle inequality. Further, $h_{p}:x\mapsto x^p$ is convex on $[0,\infty)$ for any $p\geq 1$. Indeed, $h''(x)=p(p-1)x^{p-2}\geq 0$. 
   
   Therefore, $$\left| tx+(1-t)y \right| ^{3/2}=h_{3/2}(g(tx+(1-t)y))\leq$$
2. For any $x,y\in \mathbb{R}$ and $t\in[0,1]$, $$\left| tx+(1-t)y \right| ^{3/2}\leq t\left| x \right|^{3/2}+(1-t)\left| y \right| ^{3/2} $$as we have $\left| tx+(1-t)y \right|^3\leq t^{2}\left| x \right|^3+(1-t)^{2}\left| y \right|^3$

