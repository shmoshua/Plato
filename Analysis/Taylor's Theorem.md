#Definition #Analysis 

> [!lemma] Theorem 1
> Let $f\in C^{k+1}(B(x_{0},r))$ for some $r>0$. Then, $$f(x)=P_{k}(x;x_{0})+(k+1)\sum_{\left| \alpha \right| =k+1}^{}\left( \int_{0}^{1} (1-t)^k \text{D}^\alpha f(x_{0}+t(x-x_{0}))\, dt  \right) \frac{(x-x_{0})^\alpha}{\alpha!}$$where $P_{k}(x;x_{0})$ is the Taylor polynomial of degree $k$. 

---
> [!lemma] Corollary 2
> Let $f\in C^2(B(x_{0},r))$. Then, $$f(x_{0}+u)=f(x_{0})+\braket{ \nabla f(x_{0}) ,u  } +\sum_{i,j=1}^{n}\left( \int_{0}^{1} (1-t) \left. \frac{ \partial^{2} }{ \partial_{i}\partial_{j} }f \right| _{x_{0}+tu}  \, dt \right)u_{i}u_{j} $$

---
> [!lemma] Theorem 1 (First-order Remainder Form)
> Let $S$ be a [[convex set]] and $f\in C^1([x,y])$ for $x,y\in S$. Then, $$\exists z\in [x,y]: f(y)=f(x)+\nabla f(z)^\top(y-x)$$

^baca64

