#Definition #MeasureTheory 

> [!definition]
> For a [[Topological Space]] $X$, $(C_{c}(X),\|\cdot\|_{b})$ denotes the space of ***continuous functions $f:X\to \mathbb{C}$ with compact support*** where: $$\text{supp }f:=\overline{f^{-1}[\mathbb{C}\backslash\{ 0 \}]}$$
- **Remark**: If $X$ is not compact, $C_{c}(X)$ is not complete.
---
##### Properties
> [!lemma] Theorem 1
> Let $X$ be a [[Locally Compact Hausdorff Space]]. Then, $C_{c}(X)$ is dense in [[Continuous function Vanishing at Infinity|$C_{0}(X)$]]. 

> [!proof]-
> Let $f\in C_{0}(X)$ and $\varepsilon>0$. Then, there exists a compact set $K_{\varepsilon}$ s.t. $\left| f(x) \right|\leq \varepsilon$ for all $x\notin K_{\varepsilon}$. As $X$ is locally compact, we can find $U$ open with compact closure s.t. $K_{\varepsilon}\subseteq U$. Then, by [[Locally Compact Hausdorff Space|Urysohn's Lemma]], there exists $g:X\to[0,1]$ s.t.:
> 1. $g(x)=1$ for all $x\in K_{\varepsilon}$ and 
> 2. $\text{supp }g\subseteq U$.
>    
> Then, for $f\cdot g$, 
> 1. For $x\in K_{\varepsilon}$, $(f\cdot g)(x)=f(x)$ and $\left| f(x)g(x)-f(x) \right|=0$.
> 2. For $x\notin K_{\varepsilon}$, $\left| f(x)g(x)-f(x) \right|=\left| f(x) \right|\left| g(x)-1 \right|\leq \left| f(x) \right|$ and $\left| f(x)g(x)-f(x) \right|\leq \varepsilon$.
> 
> Therefore, $\left\| fg-f \right\|_{b}\leq \varepsilon$.  Further, $fg\in C_{c}(X)$. 
---
> [!lemma] Theorem 2
> Let $X$ be a [[Locally Compact Hausdorff Space]] and $\mu$ a [[Radon measure]] on $X$. Then, $C_{c}(X)$ is dense in $L^p(X,\mathcal{B}_{X},\mu)$ for $1\leq p<+\infty$.
---
> [!lemma] Lemma 3
> Let $\varphi_{1},\varphi_{2}\in C_{c}(\mathbb{R}^n)$. Then, $\text{supp}(\varphi_{1}*\varphi_{2})\subseteq \text{supp}(\varphi_{1})+\text{supp}(\varphi_{2})$

> [!proof]-
> Let $x\notin \text{supp}(\varphi_{1})+\text{supp}(\varphi_{2})$. Then, there exists an open neighborhood $U$ of $x$ s.t. $$U\cap(\text{supp}(\varphi_{1})+\text{supp}(\varphi_{2}))=\varnothing$$
> Then, if $t\in \text{supp}(\varphi_{2})$, then $x-t\notin \text{supp}(\varphi_{1})$. Therefore, 
> $$(\varphi_{1}*\varphi_{2})(x)=\int_{\text{supp}(\varphi_{2})}^{} \varphi_{1}(x-t)\varphi_{2}(t) \, dm(t) =0$$Therefore, $x\notin \text{supp}(\varphi_{1}*\varphi_{2})$.
---
> [!lemma] Theorem 1
> Let $X \subseteq \mathbb{R}^n$ open and $1\leq p<+\infty$. Then, $C^0_{00}(X)$ is [[Dense Subset|dense]] in [[Lp Space|$L^p(X)$]].

> [!proof]-
> We first show that:
> 1. **$C^0_{00}(\mathbb{R}^n)$ is dense in $L^p(\mathbb{R}^n)$**
>    
>    We first define the truncation operator: $T_{k}:\mathbb{R}\to \mathbb{R}$ where: $$T_{k}(x):=\begin{cases}x&\left| x \right| <k\\ k \frac{x}{\left| x \right| }&\left| x \right| >k\end{cases}$$
>     Then, given $f\in L^p(\mathbb{R}^n)$, let: $$f_{k}(x):=\chi_{B_{<k}(0)}(x)\cdot T_{n}(f(k))$$It follows that $\lim_{ k \to \infty }f_{k}(x)=f(x)$ and by [[Summable Function|Lebesgue theorem]], $\lim_{ k \to \infty }\left\| f-f_{k} \right\|_{p}=0$. 
>     
>     Also, notice that $f_{k}\in L^\infty(\mathbb{R}^n)$ for all $k$. Therefore, for $\varepsilon>0$ and $k$ large enough, $$\left\| f-f_{k} \right\|_{p} < \frac{\varepsilon}{2}$$
>     Now, for any $g\in L^\infty(\mathbb{R}^n)$ with compact support and $\delta>0$, there exists $g_{1}\in C^0_{00}(\mathbb{R}^n)$ s.t. $$\left\| g-g_{1} \right\|_{1} <\delta$$Wlog we can assume that $g=\chi_{A}$ where $A$ is $\mu$-measurable and bounded. Then, there exists $F$ closed and $G$ open s.t. $$F\subseteq A\subseteq G,\quad \mu(G \backslash F)<\delta$$By Urysohn lemma, we have $g_{1}:\mathbb{R}^n\to \mathbb{R}$ continuous:
>      1. $0\leq g_{1}(x)\leq 1$
>      2. $g_{1}(x)=0$ on $G^c$ 
>      3. $g_{1}(x)=1$ on $F$
>      
>      and: $$\left\| g-g_{1} \right\| _{1}=\int_{\mathbb{R}^n}^{} \left| \chi_{A}-g_{1} \right|  \, d\mu\leq \mu(G \backslash F)<\delta $$Therefore, by [[Lp Space|Interpolation inequality]],$$\left\| g-g_{1} \right\| _{p}\leq \left\| g-g_{1} \right\| _{1}^{1/p}\left\| g-g_{1} \right\| _{\infty}^{(p-1)/p} \leq\left\| g-g_{1} \right\| _{1}^{1/p}(2\left\| g\right\| _{\infty})^{(p-1)/p}<\delta^{1/p}(2\left\| g\right\| _{\infty})^{(p-1)/p}< \frac{\varepsilon}{2} $$for $\delta>0$ small enough. Therefore, we have: $$\left\| f-g_{1} \right\|_{p}\leq \left\| f-g \right\| _{p}+\left\| g-g_{1} \right\| _{p}<\varepsilon $$
>   2. **$C^0_{00}(X)$ is dense in $L^p(X)$ for $X\subseteq \mathbb{R}^n$ open:**
>      
>      Let $f\in L^p(X)$. Then, we define $\tilde{f}:\mathbb{R}^n\to \mathbb{R}$ where $$\tilde{f}(x)=\begin{cases}f(x)&x\in X\\0&x\notin X\end{cases}$$Then, $\tilde{f}\in L^p(\mathbb{R}^n)$ and for every $\varepsilon>0$, there exists $g_{\varepsilon}\in C^0_{00}(\mathbb{R}^n)$ s.t. $$\left\| \tilde{f}-g_{\varepsilon} \right\| _{p}< \frac{\varepsilon}{2}$$
>      If we consider a sequence of open sets $(O_{k})_{k}\subseteq \mathbb{R}^n$ s.t. 
>      - $\overline{O_{k}}$ is compact,
>      - $\overline{O_{k}}\subseteq O_{k+1}$ and
>      - $\bigcup_{k\geq 1}^{}O_{k}=X$
> 	
> 	 Now, we define: $$\psi_{k}(x):=g_{\varepsilon}(x) \frac{d_{O^c_{k+1}}(x)}{d_{O^c_{k+1}}(x)+d_{O_{k}}(x)}$$Then, 
> 	 1. $\psi_{k}(x)=0$ for $x\in O^c_{k+1}$
> 	 2. $\psi_{k}(x)=1$ for $x\in O_{k}$
> 	 3. $\psi_{k}\in C^0_{00}(X)$
> 	 4. $\left| \psi_{k} \right|\leq \left| g_{\varepsilon} \right|$ and 
> 	 5. $\lim_{ k \to \infty }\left| \psi_{k}(x)-g_{\varepsilon}(x) \right|=0$
> 	
> 	  By Lagrange, we have: $$\lim_{ k \to \infty } \left\| \psi_{k}-g_{\varepsilon} \right\| _{p}=0$$and for all $\varepsilon>0$, there exists $k_{\varepsilon}\geq 1$ s.t. $$\left\| \psi_{k_{\varepsilon}}-g_{\varepsilon} \right\| <\varepsilon /2$$Therefore, $$\begin{align}\left\| f-\psi_{k_{\varepsilon}} \right\| _{L^p(X)}&\leq\left\| \tilde{f}-g_{\varepsilon}\right\| _{L^p(X)}+\left\| \psi_{k_{\varepsilon}} -g_{\varepsilon}\right\| _{L^p(X)}\\&\leq\left\| \tilde{f}-g_{\varepsilon}\right\| _{L^p(\mathbb{R}^n)}+\left\| \psi_{k_{\varepsilon}} -g_{\varepsilon}\right\| _{L^p(X)}\\&\leq \frac{\varepsilon}{2}+\frac{\varepsilon}{2}\\&=\varepsilon\end{align}$$which concludes the proof.
---
> [!lemma] Proposition 2
> For an open set $X\subseteq \mathbb{R}^n$, $C^0_{00}(X)$ is not dense in $L^\infty(X)$.

> [!proof]-
> First, let $X$ be bounded. Then, $\overline{X}$ is compact. We first have: 
> > [!claim] 
> > In the $\left\| \cdot \right\|_{\infty}$ sense, $\overline{C(\overline{X})}=C(\overline{X})$.
>
> > [!proof]-
> > Let $\{ f_{k} \}_{k}\subseteq C(\overline{X})$ s.t. $\lim_{ k \to \infty }\left\| f_{k}-f \right\|_{\infty}=0$. We will show that $f\in C(\overline{X})$. Firstly, we have that $\{ f_{k} \}_{k}$ is a Cauchy sequence and therefore, there exists $\mu$-measurable $E\subseteq \overline{\Omega}$ s.t. $\mu(\overline{\Omega} \backslash E)=0$ and: $$\lim_{ k \to \infty } \sup_{x\in E}\left| f_{k}(x)-f(x) \right| =0$$Therefore, for every $\varepsilon>0$, there exists $k_{\varepsilon}$ s.t for all $\ell,m\geq k_{\varepsilon}$, $$\left| f_{\ell}(x)-f_{m}(x) \right| <\varepsilon,\quad \forall x\in E$$Then, for any $\overline{x}\in \overline{E}$, we have $x_{j}\to \overline{x}$ with $x_{j}\in E$ and therefore: $$\lim_{ j \to \infty } \left| f_{\ell}(x_{j})-f_{m}(x_{j}) \right| =\left| f_{\ell}(x)-f_{m}(x) \right| <\varepsilon$$This means $\{ f_{k}(x) \}_{k}$ is a Cauchy sequence in $\overline{E}$. Then, there exists $g\in C^0(\overline{E})$ and: $$\sup_{x\in \overline{E}}\left| f_{k}(x)-g(x) \right| \xrightarrow{k\to \infty}0$$By Tietze extension theorem, there exists $\overline{g}\in C^0(\overline{\Omega})$ and $\overline{g}|_{\overline{E}}=g$. Therefore, $$\left\| f_{k}-\overline{g} \right\| _{\infty}\to 0$$This proves the statement.
> 
> Then, $$\overline{C^0_{00}(X)}\subseteq \overline{C(X)}\subseteq\overline{C(\overline{X})}=C(\overline{X})\subsetneq L^\infty(X)$$