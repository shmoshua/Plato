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
> Let $M$ be a [[smooth manifold]] and $\{ U_{\alpha} \}_{\alpha}$ an open cover of $M$. Then, there exists a smooth countable partition of unity $\{ \varphi_{i} \}_{i\geq 1}$ subordinate to $\{ U_{\alpha} \}_{\alpha}$ s.t. $\varphi_{i}\in C^\infty_{00}(M)$.

> [!proof]-
> Let $C_{\leq \varepsilon}:=[-\varepsilon,\varepsilon]^m\subseteq \mathbb{R}^m$ and $C_{<\varepsilon}:=(-\varepsilon,\varepsilon)^m\subseteq \mathbb{R}^m$ denote the closed and open cube.  We have:
> 1. **Claim 1: There exists a non-negative $\varphi\in C^\infty(\mathbb{R}^m)$ s.t. $\varphi|_{C_{\leq 1}}=1$ and $\varphi|_{\mathbb{R}^m \backslash C_{<2}}=0$.**
>    Consider the function: $$f(t):=\begin{cases}\exp(-1 /t)&t>0\\0&t\leq 0\end{cases}$$Then, $f\geq 0$, $f\in C^\infty$ and positive for $f>0$ for $t>0$. Then, $$g(t):= \frac{f(t)}{f(t)+f(1-t)}$$is non-negative, smooth and $g(t)=1$ for all $t\geq 1$ and $g(t)=0$ for all $t\leq0$. Therefore, $$h(t)=g(2+t)g(2-t)$$is a smooth, non-negative function with $g(t)=1$ for $t\in [-1,1]$ and $g(t)=0$ for $t\notin (-2,2)$. Then, consider $\pi_{i}:\mathbb{R}^m\to \mathbb{R}, x\mapsto x_{i}$ as the coordinate projection, by setting: $$\varphi:=(h\circ \pi_{1})\dots(h\circ \pi_{m})$$we prove the statement.
> 2. **Defining the partition of unity $\{ \varphi_{i} \}_{i}$:** 
>    As $M$ is locally compact Hausdorff and second countable, by [[Paracompact Space|Example 2]], there exists an open cover $\{ G_{i} \}_{i\geq 1}$ of relatively compact sets with $\overline{G_{i}}\subseteq G_{i+1}$. Further, let $G_{0}:=\varnothing$. 
>    
>    For $p\in M$, define $i_{p}$ to be the largest integer s.t. $p\in M\backslash \overline{G_{i_{p}}}$. Choose $\alpha_{p}$ s.t. $p\in U_{\alpha_{p}}$ and let $(V,\psi)$ be a chart centered at $p$ s.t. $V\subseteq U_{\alpha_{p}}\cap(G_{i_{p}+2} \backslash \overline{G_{i_{p}}})$ and $C_{\leq 2}\subseteq \psi(V)$. Let $\varphi$ be the function from Claim 1 and define: $$f_{p}:=\begin{cases}\varphi \circ \psi&\text{on }V\\0&\text{otherwise}\end{cases}$$Then, $f_{p}\in C^\infty(M)$ with $f_{p}(x)=1$ for $x\in W_{p}$ where $W_{p}$ is an open neighborhood of $p$. Further, $$\text{supp }f_{p}\subseteq V\subseteq U_{\alpha_{p}}\cap(G_{i_{p+2}} \backslash \overline{G_{i_{p}}})$$Now, for each $i\geq 1$ choose finite set of point $p\in M$ s.t. $W_{p}$ cover $\overline{G_{i}} \backslash G_{i-1}$. Then, we can order the corresponding $f_{p}$ into $\{ f_{i} \}_{i\geq 1}$, whose support is locally finite. Therefore, $$\varphi:=\sum_{j=1}^{\infty}f_{j}$$is a well-defined $C^\infty$-function on $M$ and $\varphi(p)>0$ for all $p\in M$. Therefore, by defining $\varphi_{i}:= f_{i} / \varphi$, $\{ \varphi_{i} \}$ is a partition of unity subordinate to $\{ U_{\alpha} \}_{\alpha}$.  
---
> [!h] Example 3 (Paracompact Hausdorff Space)
> Let $X$ be a [[Paracompact Space|paracompact]] [[Hausdorff space]] and $\{ U_{\alpha} \}_{\alpha}$ an open cover. Then, 
> 1. there exists a smooth partition of unity $\{ \varphi_{i} \}_{i}$ subordinate to $\{ U_{\alpha } \}_{\alpha}$.

> [!proof]+
> We have:
> 1. By paracompactness, there exists a there exists a locally finite refinement $\{ V_{\beta} \}_{\beta}$ of $\{ U_{\alpha} \}_{\alpha}$.
> 1. **Claim 1: There exists a locally finite refinement of relatively compact sets.**  
>    Let $\{ V_{\beta} \}_{\beta}$ be the base of the topology of $X$. Then, 