#Definition #FunctionalAnalysis

> [!definition] 
> Fix a prime $p$. For $n\geq 1$ and , $A_{n}:= \mathbb{Z} / p^n\mathbb{Z}$ is a finite [[ring]] with $1$. These rings are connected by the surjective homomorphism: $$\begin{array}{cccc} {\phi_{n}:}&{A_{n}}&\to&{A_{n-1}}\\&{x} &\mapsto & {x\mod p^{n-1}} \end{array}{}$$Then, the ring $\mathbb{Z}_{p}$ of ***$p$-adic integers*** is defied as: $$\mathbb{Z}_{p}:=\left\{  (x_{1},x_{2},\dots)\in\prod_{n\geq 1}^{}A_{n}:\phi_{n}(x_{n})=x_{n-1}, \forall n\geq 2  \right\}$$
- **Related definition**: Let $\varepsilon_{n}:\mathbb{Z}_{p}\to A_{n},x\mapsto x_{n}$ denote the ***evaluation map***.
- **Related definition**: For $0\neq x\in \mathbb{Z}_{p}$, the ***valuation*** is defined as $v_{p}(x)=n$ where $x=p^n\cdot u$ is the unique decomposition (cf. Proposition 2). For, $x=0$, $v_{p}(0)=+\infty$.
- **Related definition**: The ***$p$-adic norm*** is defined as: $\|x\|_{p}=e^{-v_{p}(x)}$
---
##### Properties
> [!lemma] Proposition 1
> The following sequence is [[exact]]: $$(0)\hookrightarrow \mathbb{Z}_{p}\xrightarrow{p^n}\mathbb{Z}_{p}\xrightarrow{\varepsilon_{n}}A_{n}\xrightarrow{0} (0)$$In other words, 
> 1. $\text{ker }p^n=(0)$
> 2. $\varepsilon_{n}$ is surjective, $\varepsilon_{n}(\mathbb{Z}_{p})=A_{n}$
> 3. $\text{ker }\varepsilon_{n}=p^n\mathbb{Z}_{p}$
> 

> [!proof]-
> We have: 
> 1. It suffices to show that $\text{ker }p=(0)$. Let $x=(x_{n})_{n\geq 1}\in \mathbb{Z}_{p}$ and $px_{n}=0$ in $A_{n}$ for all $n\geq 1$. Since $px_{1}=0$ always, this is equivalent to: $$px_{n+1}=0\in \mathbb{Z} /p^{n+1}\mathbb{Z},\quad \forall n\geq 1$$So $x_{n+1}=p^n y_{n+1}$ for $y_{n+1}\in A_{n+1}$ and hence: $$x_{n}=\phi_{n+1}(x_{n+1})=\phi_{n+1}(p^ny_{n+1})=\phi_{n+1}(p^n)\phi_{n+1}(y_{n+1})=0$$Therefore, $x=0$. 
> 2. for $m\in \mathbb{Z}$, $\varepsilon_{n}(m\cdot 1)=m\mod p^n$. Therefore, $\varepsilon_{n}$ is surjective.
> 3. $\varepsilon_{n}$ is a group homomorphism and: $$\varepsilon_{n}(p^nx)=p^n\varepsilon_{n}(x)=0$$and $p^n\mathbb{Z}_{p}\subseteq \text{ker }\varepsilon_{n}$. 
>    
>    Conversely, assume that $x=(x_{m})_{m\geq 1}\in \text{ker }\varepsilon_{n}$. Then, for all $m\geq n$, $$x_{m}\in p^n A_{m}$$Therefore, the multiplication by $p^n$ induces an isomorphism $A_{m-n}\cong p^n A_{m}$ s.t. $$\begin{CD}A_{m-n+1} @>p^n>>p^n A_{m+1}\\@V{\mod p^{m-n}}VV&@VV{\mod p^{m}}V\\A_{m-n}@>p^n>>p^n A_{m}\end{CD}$$commutes. Let $y_{m-n}\in A_{m-n}$ s.t. $p^ny_{m-n}=x_{m-n}$. Then, $y=(y_{i})_{i\geq 1}\in \mathbb{Z}^p$ and $p^ny=x$.
---

> [!lemma] Proposition 2
> We have:
> 1. $x\in \mathbb{Z}_{p}$ is invertible if and only if $x\notin p\mathbb{Z}_{p}$
> 2. let $U:=\{ x\in \mathbb{Z}_{p}:x \text{ is invertible} \}$. Then, every $x\in \mathbb{Z}_{p} \backslash\{ 0 \}$ can be written uniquely as: $$x=p^n\cdot u$$for $n\geq 0,u\in U$, where $n$ is called the ***valuation of $x$*** denoted as $v_{p}(x)\in \mathbb{N}$.

> [!proof]+
> If $x$ is invertible, then $\varepsilon_{1}(x)$ is invertible. Therefore, $x\notin \text{ker }\varepsilon_{1}=p\mathbb{Z}_{p}$. Conversely, if $x\notin p\mathbb{Z}_{p}$, then $x_{n}\notin p A_{n}$, so there exists $y_{n}\in A_{n}$ s.t. $x_{n}y_{n}=1_{A_{n}}$. 
> 
> 2. Let $0\neq x\in \mathbb{Z}_{p}$. Then, $x=(x_{\ell})_{\ell\geq 1}$ with $x_{\ell}\in \mathbb{Z} / p^\ell \mathbb{Z}$. Let: $$n:=\max\{\ell\geq 1:x_{\ell}=0  \}$$Then, $n<+\infty$. So $\varepsilon_{n}(x)=0$ and as $\text{ker }\varepsilon_{n}=p^n\mathbb{Z}_{p}$, there exists $y\in \mathbb{Z}_{p}$ s.t. $x=p^n\cdot y$. If $y$ is not invertible, then $y\in p \mathbb{Z}_{p}$, i.e. $y=pz$ for $z\in \mathbb{Z}_{p}$. But then, $$x=p^{n+1}z=\text{ker }\varepsilon_{n+1}$$and $x_{n+1}=\varepsilon_{n+1}(x)=0$. This contradicts the definition of $n$.
---

> [!lemma] Proposition 3
> For $\mathbb{Z}_{p}$, it holds that:
> 1. $\mathbb{Z}_{p}$ is a subring of $\prod_{n\geq 1}^{}A_{n}$ with identity $1:=(1,1,\dots)$.
> 2. $\mathbb{Z}_{p}$ is compact Hausdorff.
> 3. $(\mathbb{Z}_{p},+)$ is a compact [[topological group]].
> 4. $\mathbb{Z}\hookrightarrow \mathbb{Z}_{p}$ injects as a subring.

> [!proof]-
> We have:
> 1. Follows from the fact that $\phi_{n}$ is a ring homomorphism for all $n\geq 2$:
> 	$$\phi_{n}(x_{n}+y_{n})=\phi_{n}(x_{n})+\phi_{n}(y_{n})=x_{n-1}+y_{n-1}$$
> 2. Endow $A_{n}$ with the discrete topology. As $A_{n}$ is finite, it is compact and by [[Compact Space|Tychonoff]], $\prod_{n\geq 1}^{}A_{n}$ is compact Hausdorff w.r.t. the product topology. Then, $$F_{n}:=\left\{  x\in \prod_{n\geq 1}^{}A_{n}:\phi_{n}(x_{n})=x_{n-1}  \right\}$$is closed and $\mathbb{Z}_{p}=\bigcap_{{n\geq 2}}^{}F_{n}$ is closed and a compact Hausdorff space.
> 1. Let $x\neq 0$ and $y\neq 0$. Then, $x=p^nu$ and $y=p^m v$. Then, $$xy=p^{n+m}uv\neq 0$$ Since $\varepsilon_{{n+m+1}}(xy)\neq 0$.
> 
> 
> 
---

> [!lemma] Proposition 4 (Valuation Lemmas)
> We have that: 
> 1. $v_{p}(xy)=v_{p}(x)+v_{p}(y)$
> 2. $v_{p}(x+y)\geq \min(v_{p}(x),v_{p}(y))$
> 3. $\|x\|_{p}=0 \iff x=0$
> 4. $\|xy\|_{p}=\|x\|_{p}\|y\|_{p}$
> 5. $\|x+y\|_{p}\leq \max(\|x\|_{p},\|y\|_{p})$
> 6. The topology on $\mathbb{Z}_{p}$ can be defined by the distance: $$d_{p}(x,y):=\|x-y\|_{p}=e^{-v_{p}(x-y)}$$The metric space is complete and $\mathbb{Z}$ is dense in $\mathbb{Z}_{p}$.
> 7. $\{ p^n\mathbb{Z}_{p}:n\geq 0 \}$ is a basis of neighborhoods of $0$ in $\mathbb{Z}_{p}$.
> 8. $d(0,x)\leq e^{-n}\iff v_{p}(x)\geq n\iff x\in p^n \mathbb{Z}_{p}$ and $p^n\mathbb{Z}_{p}=B(0,e^{-n})$.

> [!proof]-
> Let $x=p^n u$ and $y=p^m w$, wlog $n\geq m$. Then, $$x+y=p^n u+p^mw=p^m[v+up^{n-m}]$$and $$v_{p}(x+y)=m+v_p(v+up^{n-m})\geq m$$
> 1. **Showing that $\mathbb{Z}$ is dense in $\mathbb{Z}_{p}$**: 
>    For every $n\geq 1$, let $y^{(n)}\in \mathbb{Z}$ s.t. $y^{(n)}\equiv_{p^n} x_{n}$. Then, for every $\ell\leq n$, $y^{(n)}\equiv_{p^\ell}x_{\ell}$. Let $$\mathbb{Z}\ni y^{(n)}\mapsto Y^{(n)}\in \mathbb{Z}_{p}$$Then, $d(Y^{(n)},x)=e^{-v_{p}(Y^{(n)-x})}\leq e^{-n}$ because $\varepsilon_{n}(Y^{({n})}-x)=0$ and $v_{p}(Y^{(p)}-x)\geq n$.
---