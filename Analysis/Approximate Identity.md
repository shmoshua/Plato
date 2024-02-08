#Definition #FunctionalAnalysis 

> [!definition]
> For any $\delta\in C^\infty_{00}(\mathbb{R}^n)$ with $\delta\geq 0$ s.t. $\int_{\mathbb{R}^n}^{} \delta(y) \, dm(y)=1$ and for $\varepsilon>0$, we define the ***approximate identity*** as $$\delta_{\varepsilon}(y):=\frac{1}{\varepsilon^n}\delta(y / \varepsilon)$$
---
##### Properties
> [!lemma] Proposition 1
> For the approximate identity $\delta_{\varepsilon}$, it holds that:
> 1. $\delta_{\varepsilon}\in C_{00}^\infty(\mathbb{R}^n)$
> 2. $\int_{\mathbb{R}^n}^{} \delta_{\varepsilon}(y) \, dm(y)=1$ and 
> 3. if $\text{supp }\delta \subseteq B_{\leq r}(0)$, then $\text{supp }\delta_{\varepsilon}\subseteq B_{\leq \varepsilon r}(0)$

> [!proof]-
> We have:
> 1. Obvious
> 2. $$\int_{\mathbb{R}^n}^{} \delta_{\varepsilon} \, dm=\frac{1}{\varepsilon^n}\int_{\mathbb{R}^n}^{} \delta(y / \varepsilon) \, dm(y)=  \int_{\mathbb{R}^n}^{} \delta(x) \, dm(x)=1 $$
> 3. If $\delta_{\varepsilon}(x)\neq 0$, then $\delta(x /\varepsilon)\neq 0$ and $x / \varepsilon\in B_{\leq r}(0)$. 

---
> [!lemma] Proposition 2
> We have: 
> 1. If $f\in C(\mathbb{R}^n)$, then $\delta_{\varepsilon}*f\xrightarrow{\varepsilon\to{0}}f$ uniformly on compact sets. 
> 2. For $1\leq p<+\infty$ and $f\in L^p(\mathbb{R}^n)$, $\delta_{\varepsilon}*f\xrightarrow{\varepsilon\to{0}}f$ in $L^p(\mathbb{R}^n)$.

> [!proof]-
> We have: 
> 1. by change of variable: $$(\delta_{\varepsilon}*f)(x)=\int_{\mathbb{R}^n}^{} \delta_{\varepsilon}(y)f(x-y) \, dm(y) $$and $$(\delta_{\varepsilon}*f)(x)-f(x)=\int_{\mathbb{R}^n}^{} \delta_{\varepsilon}(y)(f(x-y)-f(x)) \, dm(y)$$Therefore, $$\left|(\delta_{\varepsilon}*f)(x)-f(x) \right| \leq\sup_{y\in B_{\leq \varepsilon r}(0)}\left| f(x-y)-f(x) \right| $$which shows 1. 
> 2. Let $f\in L^p(\mathbb{R}^n)$, $0< \varepsilon\leq 1$ and $\varphi\in C_{00}(\mathbb{R}^n)$ with $\left\| f-\varphi \right\|_{p}<\varepsilon$. Then, $$\begin{align}\left\| \delta_{\varepsilon}*f-f \right\| _{p}&\leq\left\| \delta_{\varepsilon}*f-\delta_{\varepsilon}*\varphi \right\| _{p}+\left\| \delta_{\varepsilon}*\varphi-\varphi \right\|_{p}+\left\| f-\varphi \right\| _{p} \\&=\left\| \delta_{\varepsilon}*(f-\varphi) \right\| _{p}+\left\| \delta_{\varepsilon}*\varphi-\varphi \right\|_{p}+\left\| f-\varphi \right\| _{p}\\&\leq\left\| \delta_{\varepsilon}\|_{1}\|f-\varphi \right\| _{p}+\left\| \delta_{\varepsilon}*\varphi-\varphi \right\|_{p}+\left\| f-\varphi \right\| _{p}\\&=\left\|f-\varphi \right\| _{p}+\left\| \delta_{\varepsilon}*\varphi-\varphi \right\|_{p}+\left\| f-\varphi \right\| _{p}\\&<2\varepsilon+\left\| \delta_{\varepsilon}*\varphi-\varphi \right\|_{p}\end{align}$$
>    Now, $\text{supp }(\delta_{\varepsilon}*\varphi)\subseteq B_{\leq r}(0)+\text{supp }(\varphi)=:K$. Then, $$\begin{align}\left\| \delta_{\varepsilon}*\varphi-\varphi \right\|_{p}^p&=\int_K\left| (\delta_{\varepsilon}*\varphi)(y)-\varphi(y) \right| ^p  \, dm(y)\\&\leq \sup_{y\in K}\left| (\delta_{\varepsilon}*\varphi)(y)-\varphi(y) \right| ^p \cdot m(K) \end{align} $$which converges to $0$ as $\varepsilon\to {0}$.
---