#Definition #FunctionalAnalysis 

> [!definition]
>  A ***seminorm*** in a $\mathbb{K}$-vector space $V$ is a function $p:V \to [0,+\infty)$ s.t. 
>  1. $p(\alpha v)=\left| \alpha \right|p(v)$ for all $\alpha\in \mathbb{K}$ and $v\in V$
>  2. $p(v_{1}+v_{2})\leq p(v_{1})+p(v_{2})$ for all $v_{1},v_{2}\in V$.

- **Remark**: A seminorm differs from a [[Norm|norm]] in a sense that it is possible that $p(v)=0$ for some $v \neq 0$.  
---
##### Properties
> [!lemma] Theorem 1 (Hahn-Banach)
> Let $V$ be a $\mathbb{K}$-vector space, $p:V \to [0,+\infty)$ a seminorm, $M \subseteq V$ a $\mathbb{K}$-vector subspace and $f:M \to \mathbb{K}$ a linear form with: $$\left| f(v) \right| \leq p(v)$$for all $v\in M$. Then, there is a $\mathbb{K}$-linear extension $F:V \to \mathbb{K}$ s.t.
> 1. $F$ is linear.
> 2. $F|_{M}=f$.
> 3. $\left| F(v) \right|\leq p(v)$ for all $v\in V$.

> [!proof]-
> We can assume that $\mathbb{K}=\mathbb{C}$ as for $\mathbb{R}$, it follows from [[Gauge Function|Hahn-Banach, the Analytic form]]. 
> 
> Now, let $f:M \to \mathbb{C}$ and $f=f_{1}+if_{2}$ where $f_{1},f_{2}:M\to \mathbb{R}$. Then, firstly, we have: $$f_{1}(iv)+if_{2}(iv)=f(iv)=if(v)=-f_{2}(v)+if_{1}(v)$$
> and $f_{1}(iv)=-f_{2}(v)$. As we have, 
>  $$f_{1}(v) \leq p(v)$$and there is a linear extension $F_{1}:V \to \mathbb{R}$ with: $$F_{1} (v)\leq p(v) $$for all $v\in V$. Now define $F(v):=F_{1}(v)-iF_{1}(iv)$. Then, 
>  1. $F$ is $\mathbb{C}$-linear as $F(iv)=iF(v)$.
>  2. $F$ extends $f$ as for all $v\in M$:$$F(v)=F_{1}(v)-iF_{1}(iv)=f_{1}(v)-if_{1}(iv)=f(v)$$
>  3. $|F|$ is bounded by $p$. Let $v\in V$ and $\alpha\in \mathbb{C}$ with $\left| \alpha \right|=1$ s.t.:
> $$\left| F(v) \right| =\alpha F(v)=F(\alpha v)=F_{1}(\alpha v)$$Thus, $$\left| F(v) \right| =F_{1}(\alpha v)\leq p(\alpha v)=p(v)$$
---

