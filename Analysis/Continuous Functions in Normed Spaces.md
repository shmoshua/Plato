#Definition #LST #Analysis 

> [!definition]
> For a function $f:(U,\|\cdot\|_{U})\to(V,\|\cdot\|_{V})$, $f$ is called ***continuous at*** $u\in U$ if and only if for all $\varepsilon>0$ there exists $\delta>0$ s.t. $$\|u-u'\|_{U}<\delta\quad\Longrightarrow\quad \|f(u)-f(u')\|_{V}<\varepsilon$$The function is ***continuous on $U$***, if and only if it is continuous at every $u\in U$.
- **Equivalent Definition**: $f$ is continuous at $u\in U$, if for every neighborhood $B$ of $f(u)$, there exists a neighborhood $A$ of $u$ s.t. $f(A)\subseteq B$.
- **Remark**: With the [[Open and Closed Balls| open balls]], one can write $f$ is continuous at $u\in U$ if for all $\varepsilon>0$ there exists $\delta>0$ s.t. $$u'\in B(u,\delta)\quad\Longrightarrow\quad f(u')\in B(f(u),\varepsilon)$$or that $\lim_{ u' \to u }f(u')=f(u)$.
---
##### Properties
> [!lemma] Theorem ContFuncNS.1
> The set of continuous functions $f:(U,F,\|\cdot\|_{U})\to(V,F,\|\cdot\|_{V})$ is a [[Vector Subspace| linear subspace]] of $\mathcal{F}(U,V)$.

> [!proof]-
> Let $f,f':(U,F,\|\cdot\|_{U})\to(V,F,\|\cdot\|_{V})$ be continuous and $a,b\in F$. Then, $af+bf'$ is a continuous function as well on $U$ as for any $u\in U$: $$\lim_{ u' \to u } (af+bf')(u')=a\lim_{ u' \to u } f(u')+b\lim_{ u' \to u } f'(u')=af(u)+bf'(u)=(af+b f')(u)$$
> Therefore, the set is a linear subspace.

---
##### Related Definitions
- [[Piecewise Continuous Function]]