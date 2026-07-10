#Definition #Analysis 

> [!definition]
> A ***Schwartz distribution*** on $\mathbb{R}^d$ is a continuous linear functional $T:C^\infty_{00}(\mathbb{R}^d;\mathbb{C})\to \mathbb{C}$.
---
##### Examples
> [!h] Example 1
> Let $f:\mathbb{R}^d\to \mathbb{C}$ be a locally integrable function, i.e. for any compact $K$, $$\int _{K}f \, dw $$is well-defined and finite. Then,
> 1. the functional given by: $$T(\varphi):=\int f\varphi \, dw $$ is a Schwartz distribution.

> [!proof]-
> We have that: 
> 1. By definition $T$ is a linear functional. Let $\varphi_{k}\to 0$. Then, there is a compact set $K$ s.t. $\text{supp}(\varphi_{k})\subseteq K$ and for any multi-index $\alpha$, $\sup_{w\in K}\left| \partial_{\alpha}\varphi_{k}(w) \right|\to0$. More specifically $\left\| \varphi_{k} \right\|_{\infty,K}\to 0$.
>    
>    Now we have that: $$\left| T(\varphi_{k}) \right| \leq \int_{K}^{} \left| f \right| \left| \varphi_{k} \right|  \, dw \leq \left\| \varphi_{k} \right\| _{K,\infty}\int_K \left| f \right|   \, dw\to 0 $$This shows that $T$ is continuous.

---
> [!h] Example 2
> We have that: $$T(\varphi):=\varphi(0)$$is a Schwartz distribution.

> [!proof]+
> We have that:
> 1. $T$ is a linear functional. Further, $$\left| T(\varphi) \right| \leq \left| \varphi(0) \right| \leq \left\| \varphi \right\| _{\infty,K}$$Hence, it is continuous.
