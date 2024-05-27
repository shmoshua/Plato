#Definition #DifferentialGeometry 

> [!definition]
> Let $X$ be a [[topological space]]. A ***partition of unity*** on $X$ is a collection $\{ f_{j} \}_{j}$ of continuous functions $f_{j}:X\to[0,1]$ s.t.
> 1. $\{ \text{supp }f_{j} \}_{j}$ is locally finite, i.e. for $x\in X$, there exists a neighborhood $U\ni x$ s.t. $U\cap \text{supp }f_{j}=\varnothing$ except finitely many.
> 2. $\sum_{j\in J}^{}f_{j}(x)=1$ for all $x\in X$.
> 
- **Related definition**: A partition of unity $\{ f_{j} \}_{j}$ is ***subordinate*** to an open cover $\{ U_{\alpha} \}_{\alpha}$ if for each $j$, there exists $\alpha$ with $\text{supp }f_{j}\subseteq U_{\alpha}$.
- **Related definition**: A partition of unity $\{ f_{j} \}_{j}$ is ***smooth*** if $f_{j}\in C^\infty(X)$ for all $j\in J$.  
---
##### Examples
> [!h] Example 1 (Normal Spaces)
> 
> Let $X$ be a [[normal space]] and $\{ U_{i} \}_{i\in[k]}$ a finite open covering. Then, there exists a partition of unity subordinate to $\{ U_{i} \}_{i\in [k]}$.

> [!proof]-
> We have:
> 1. **Claim 1: We can find $V_{i}\subseteq U_{i}$ open with $\overline{V_{i}}\subseteq U_{i}$ s.t. $(V_{i})_{i\in [k]}$ is a covering of $X$.**
>    We show by induction on $1\leq j\leq k$. For $j=1$, let $A_{1}:=X \backslash\bigcup_{i=2}^{k}U_{i}$. Then, $A_{1}$ is closed and $A_{1}\subseteq U_{1}$. As $X$ is normal, there exists $V_{1}\subseteq X$ open s.t. $A_{1}\subseteq V_{1}\subseteq \overline{V_{1}}\subseteq U_{1}$ and $V_{1}\cup \bigcup_{i=2}^{k}U_{i}=X$.
>     
>    
>    Let now $j>1$. Then, similarly, let $A_{j}:=X \backslash \bigcup_{i\neq j}^{}U_{i}$ and there exists $V_{j}\subseteq X$ open s.t. $A_{j}\subseteq V_{j}\subseteq \overline{V_{j}}\subseteq U_{j}$. Indeed,
   $$\bigcup_{i\leq j}^{}V_{i}=V_{j}\cup\bigcup_{i\leq j-1}^{}V_{i}\supseteq A_{j}\cup X\backslash \bigcup_{i\geq j}^{}U_{i}=X\backslash \bigcup_{i>j}^{}U_{i}$$This proves the claim.
> 2. **Claim 2: there are coverings $(W_{i})_{i\in[k]}$ and $(V_{i})_{i\in [k]}$ and continuous functions $g_{i}:X\to[0,1]$ s.t. $\overline{W_{i}}\subseteq V_{i}\subseteq \overline{V_{i}}\subseteq U_{i}$, and $g_{i}|_{W_{i}}=1$ and $g_{i}|_{X \backslash V_{i}}=0$.**
>    Repeating the process in 1 on $(V_{i})_{i\in[k]}$, we get $(W_{i})_{i\in[k]}$ s.t. $W_{i}\subseteq\overline{W_{i}}\subseteq V_{i}\subseteq \overline{V_{i}}\subseteq U_{i}$. Then, $\overline{W_{i}}$ and $X \backslash V_{i}$ are two disjoint closed sets and by normality of $X$, there exist such continuous functions $g_{i}$.
> 3. **Claim 3: $\text{supp}(g_{i})\subseteq U_{i}$ and that $\sum_{i=1}^{k}g_{i}(x)>0$ for all $x\in X$.**
>    We have that $\text{supp}(g_{i})\subseteq \overline{V_{i}}\subseteq U_{i}$. Further, assume if there exists $x\in X$ where $\sum_{i=1}^{k}g_{i}(x)=0$, then $g_{i}(x)=0$ for all $i\in[k]$, which contradicts that $(W_{i})_{i\in[k]}$ is a covering.
> 
>  Finally, we define: $f_{i}=g_{i}/\sum_{i=1}^{k}g_{i}$, which is well-defined, continuous and $\text{Im }f_{i}\subseteq[0,1]$. Therefore, $$\sum_{i=1}^{k}f_{i}=1$$

---
> [!h] Example 2 (Smooth Manifolds)
> Let $M$ be a [[smooth manifold]] and $\{ V_{\alpha} \}_{\alpha}$ be an open cover of $M$. Then, there exists a countable partition of unity $\{ f_{i} \}_{i\in F}$ s.t.
> 1. $f_{i}\in C^\infty_{00}(M)$
> 2. $\{ \text{supp }f_{i}: i\in F\}$ is a locally finite cover of $M$ refining $\{ V_{\alpha} \}_{\alpha}$. 

> [!proof]-
> From [[Atlas|Lemma 4]], there is a countable family of charts $(U_{i},\varphi_{i})_{i}$ with the described properties. Then, by the smooth version of Urysohn's lemma, there exists a smooth function $g:\mathbb{R}^m\to [0,1]$ with: 
> 1. $g(x)=1$ for $x\in C_{\varepsilon}^m(0)$ and 
> 2. $g(x)=0$ for $x\notin C_{2\varepsilon}^m(0)$
> 
> Now, define $g_{i}:M\to \mathbb{R}$: $$g_{i}(x):=\begin{cases} g(\varphi(x))&x\in U_{i}\\0&x\notin U_{i}\end{cases}$$ Then, $\sum_{i\in I}^{}g_{i}$ is well-defined, smooth and strictly positive. Therefore, $$f_{i}:=\frac{g_{i}}{\sum_{j\in I}^{}g_{j}}$$has the desired properties.
---
