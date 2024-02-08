#Definition #LST #Analysis 

> [!definition]
> For the linear space of all continuous functions $f:(U,F,\|\cdot\|_{U})\to(V,F,\|\cdot\|_{V})$, the ***induced norm*** is defined as: $$\|f\|:=\sup_{{u \neq 0}} \frac{\left\| f(u) \right\|_{V}}{\|u\|_{U}} $$

---
##### Properties
> [!lemma] Fact IndNorm.1
> For two normed spaces $(U,F,\|\cdot\|_{U}),(V,F,\|\cdot\|_{V})$ and a continuous linear function $\mathcal{A}:U \to V$, the induced norm can also be written as: $$\|\mathcal{A}\|=\sup_{\|u\|_{U}=1}\|\mathcal{A}(u)\|_{V}$$

> [!proof]-
> For every $u\in U$ s.t. $u \neq 0$, we define $v:= \frac{u}{\|u\|_{U}}$. Then, $$\frac{\left\| \mathcal{A}(v) \right\|_{V} }{\|v\|_{U}} =\frac{ \frac{1}{\|u\|_{U}}\|\mathcal{A}(u)\|_{V} }{\frac{1}{\|u\|_{U}}\|u\|_{U}}=\frac{\|\mathcal{A}(u)\|_{V}}{\|u\|_{U}}$$Therefore, for any $u\in U \backslash\{ 0 \}$, we have a vector with norm 1 that evaluate to the same value. So we can limit the domain of the supremum to vectors with norm 1.