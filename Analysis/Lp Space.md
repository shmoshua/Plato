#Definition #Analysis 

> [!definition]
> Let $(X,\Sigma,\mu)$ be a [[Measure Space|measure space]]. Then for a [[measurable function]] $f:X\to \mathbb{K}$, we define: 
> 1. if $1\leq p < +\infty$,
> $$\left\| f \right\| _{p}:=\left( \int_{X}^{} \left| f \right| ^p \, d\mu  \right) ^{1/p}$$
> 2. if $p=+\infty$, $$\left\| f \right\| _{\infty}:=\inf \{ M>0:\left| f \right|  \leq M\ \mu \text{-a.e.}\}$$
> 
> Then, for $1\leq p\leq+\infty$:
> $$L^p(X,\mu,\mathbb{K}):=\left\{  f:X \to \mathbb{K} \text{ measurable s.t.} \left\| f \right\| _{p}<+\infty \right\}_{/\sim}$$
> where $f_{1}\sim f_{2}$ if $f_{1}=f_{2}$ [[Almost Everywhere|$\mu$-a.e]].
> 
- **Related Definition**: If $\mu$ is the [[Measure|counting measure]], we denote $\ell^p(X,\mathbb{K}):=L^p(X,\mu,\mathbb{K})$.
- **Remark**: For $f\in L^\infty(X,\mu)$, $\left| f \right|\leq \left\| f \right\|_{\infty}$ $\mu$-a.e.
- **Remark**: If $p=2$, the $L^p$ norm comes from the inner product: $$\braket{ f , g } =\int_{X}^{} f\overline{g} \, d\mu  $$ 
---
##### Properties
> [!lemma] Lemma 1 (Young's Inequality)
> Let $1<p,q<\infty$ s.t. $1 / p+1 / q=1$. Then, for all $a,b\geq 0$ $$ab\leq \frac{a^p}{p}+\frac{b^q}{q}$$

> [!proof]-
> If $b=0$, it trivially holds. Therefore, assume $b>0$. We consider the function: $$\begin{array}{cccc} {h:}&{[0,+\infty)}&\to&{\mathbb{R}}\\&{a} &\mapsto & {ab-\frac{a^p}{p}} \end{array}{}$$Then, $h(0)=0$ and $\lim_{ a \to \infty }h(a)=-\infty$. Therefore, $h$ has an absolute maximum at $a^*$, where $$a^*=b^{1/(p-1)}$$Then, $$h(a^*)=\frac{b^{q}}{q}$$Therefore, $$ab-\frac{a^p}{p}\leq \frac{b^q}{q}$$
---
> [!lemma] Lemma 2 (Hölder's Inequality)
> Let $1\leq p,q\leq+\infty$ be conjugate. Then, for $f\in L^p(X),g\in L^q(X)$, we have: 
> 1. $f\cdot g\in L^1(X)$ and 
> 2. $\left\| fg \right\|_{1}\leq \left\| f \right\|_{p}\left\| g \right\|_{q}$

> [!proof]-
> We have: 
> 1. If $p=1$ and $q=+\infty$, then: $$\left\| fg \right\|_{1}=\int_{X}^{} \left| f \right| \left| g \right|  \, d\mu\leq \int_{X}^{} \left| f \right| \left\| g \right\| _{\infty} \, d\mu=\left\| g \right\| _{\infty}\left\| f \right\| _{1}  $$
> 2. If $1<p<+\infty$, we can wlog assume that $\left\| f \right\|_{p}$ and $\left\| g \right\|_{q}$ are both non-zero. This is because, assume if $\left\| f \right\|_{p}=0$, then $f=0$ $\mu$-a.e. and $fg=0$ $\mu$-a.e. and the inequality trivially holds. 
>    
>    If we define: 
>    1. $\tilde{f}(x)= f(x)/\left\| f \right\|_{p}$
>    2. $\tilde{g}(x)= g(x)/\left\| g \right\|_{q}$
>       
>    Then, $$\begin{align}\frac{1}{\left\| f \right\| _{p}\left\| g \right\| _{q}}\int_{X}^{} \left| f\cdot g \right|  \, d\mu =\int_{X}^{} \left| \tilde{f}\cdot \tilde{g} \right|  \, d\mu&\leq \frac{1}{p}\int_{X}^{} \frac{\left| f \right|^p}{\left\| f \right\| _{p}^p} \, d\mu+\frac{1}{q}\int_{X}^{} \frac{\left| g \right|^q}{\left\| g \right\| _{q}^q} \, d\mu =\frac{1}{p}+\frac{1}{q}=1 \end{align}$$
---
> [!lemma] Corollary 3 (Minkowski's Inequality)
> Let $1\leq p\leq+\infty$ and $f,g\in L^p(X)$. Then, $f+g\in L^p(X)$ and $$\left\| f+g \right\| _{p}\leq \left\| f \right\|_{p} +\left\| g \right\|_{p} $$

> [!proof]-
> If $p=1$, then: $$\left\| f+g \right\| _{1}=\int_{X}^{} \left| f+g \right|  \, d\mu\leq \int_{X}^{} \left| f \right|  \, d\mu +\int_{X}^{} \left| g \right|  \, d\mu=\left\| f \right\| _{1}+\left\| g \right\|_{1}  $$
> If $p=+\infty$, then: $$\left| f(x)+g(x) \right| \leq \left| f(x) \right| +\left| g(x) \right| \leq \left\| f \right\| _{\infty}+\left\| g \right\| _{\infty}$$ $\mu$-a.e. Therefore, $\left\| f+g \right\|_{\infty}\leq \left\| f \right\|_{\infty}+\left\| g \right\|_{\infty}$.
> 
> If $1<p<+\infty$, Then, as $\left| x^p \right|$ is convex, $$\frac{\left| f(x)+g(x) \right|^p}{2^p}\leq \frac{1}{2}(\left| f(x) \right| ^p+\left| g(x) \right| ^p) $$for any $x\in X$. Therefore, $f+g\in L^p(X)$ and: $$\left| f+g \right| ^{p-1}\in L^{p/(p-1)}$$
> Therefore, by Hölder's inequality,$$\begin{align}\left\| f+g \right\| _{p}^p&=\int_{X}\left| f+g \right| \cdot \left| f+g \right| ^{p-1}  \, d\mu\\&\leq \int_{X}^{} \left| f \right| \left| f+g \right| ^{p-1} \, d\mu+\int_{X}^{} \left| g \right| \left| f+g \right| ^{p-1} \, d\mu\\  &\leq \left\| f \right\| _{p}\left( \int_{X}^{} \left| f+g \right| ^{p} \, d\mu \right) ^{(p-1)/p}+\left\| g \right\| _{p}\left( \int_{X}^{} \left| f+g \right| ^{p} \, d\mu \right) ^{(p-1)/p} \\&=(\left\| f \right\| _{p}+\left\| g \right\| _{p})\left\| f+g \right\| ^{p-1}_{p}\end{align}$$It follows that: $$\left\| f+g \right\| _{p}\leq \left\| f \right\| _{p}+\left\| g \right\| _{p}$$
---
> [!lemma] Lemma 4 (Interpolation Inequality)
> Let $1\leq p<r<q<\infty$ and $f\in L^p(X)\cap L^q(X)$. Then, $f\in L^r(X)$ and: $$\left\| f \right\| _{r}\leq \left\| f \right\| _{p}^t\left\| f \right\| _{q}^{1-t}$$where $\frac{1}{r}=\frac{t}{p}+\frac{1-t}{q}$ for $t\in[0,1]$.

> [!proof]-
> We have that $1= \frac{1}{p'}+\frac{1}{q'}$ where $p'=\frac{p}{rt}$ and $q'=\frac{q}{r(1-t)}$. Then, we further set:
> 1. $\tilde{f}:=\left| f \right|^{rt}$ and
> 2. $\tilde{g}:=\left| f \right|^{r(1-t)}$
> 
> Then, $\tilde{f}\in L^{p/rt}$ and $\tilde{g}\in L^{q/r(1-t)}$ where $\frac{p}{rt}$ and $\frac{q}{r(1-t)}$ are conjugates. Therefore, by Hölder's inequality, $$\begin{align}\int_{X}^{} \left| f\right| ^r \, d\mu =\left\| \tilde{f}\tilde{g} \right\| _{1}\leq \left( \int_X\left| f \right| ^{p}  \, d\mu \right)^{rt/p} \left( \int_X\left| f \right| ^{q}  \, d\mu \right)^{r(1-t)/q} =\left\| f \right\| _{p}^{rt}\left\| f \right\| _{q}^{r(1-t)}\end{align} $$Therefore, $$\left\| f \right\| _{r}\leq \left\| f \right\| _{p}^t\left\| f \right\| _{q}^{1-t}$$
---
> [!lemma] Lemma 5
> We have: 
> 1. Let $f\in L^p$ and $g\in L^q$ with $\frac{1}{r}=\frac{1}{p}+\frac{1}{q}\leq 1$. Then, $fg\in L^r$ and $$\left\| fg \right\| _{r}\leq \left\| f \right\| _{p}\left\| g \right\| _{q}$$
> 2. If $\mu(X)<+\infty$, for all $1\leq r<s\leq+\infty$ $$L^s(X)\subseteq L^r(X)$$

> [!proof]-
> For 1, if $r=+\infty$, it is clear. If $r<+\infty$, then by Hölder, $\left| f \right|^r\in L^{p/r}$ and $\left| g \right|^r\in L^{q/r}$, we have $\left| f\cdot g \right|^r\in L^1(X)$ and $f\cdot g\in L^r(X)$. Further, $$\left\| fg \right\| _{r}=\left\| \left| f\cdot g \right| ^r \right\|_{1}^{1/r}\leq \left\| f^r \right\|_{p/r}^{1/r}\left\| g^r \right\|_{q/r}^{1/r}=\left\| f \right\| _{p}\left\| g \right\| _{q}  $$
> For 2, set $g=1\in L^{rs/(s-r)}$. Then, $\frac{1}{r}=\frac{1}{s}+\frac{s-r}{rs}$ and therefore, by 1 for $f\in L^s$: $$f\cdot 1=f\in L^r$$
---
> [!lemma] Proposition 6
> Let $\mu(X)<+\infty$ and $1\leq p<+\infty$. If $f:X\to \overline{\mathbb{R}}$ s.t. $fg\in L^1(X,\mu)$ for all $g\in L^p(X)$, then $f\in L^q(X)$ for all $q\in [1,p')$ where $p'$ is the conjugate of $p$.

> [!proof]-
> Notice that: $$\left( \int_{X}^{} 1^p \, d\mu \right)^{1/p}=\mu(X)^{1/p}<+\infty $$Therefore, $1\in L^p(X)$ and $f\in L^1(X)$. Now, let's consider $g=\left| f \right|^{1/p}$. We have: $$\int_{X}^{} \left| g \right|^pd\mu=\int_{X}^{} \left| f \right|  \, d\mu<+\infty $$Therefore, $g\in L^p$ and $\left| f \right|^{1+1/p}\in L^1$. By iterating we get that $f\in L^{p'}$. Further from Interpolation inequality, it holds that $f\in L^q$ for $q\in [1,p')$. 
---
> [!lemma] Theorem 7
> For all $1\leq p \leq \infty$, 
> 1. $\|\cdot\|_{p}$ is a [[Norm|norm]] and
> 2. $L^p(X,\mu,\mathbb{K})$ is [[Banach Space|Banach]]

> [!proof]-
> We have that: 
> 1. Let $f\in L^p(X)$ s.t. $\left\| f \right\|_{p}=0$. Then, $$\int_{X}^{} \left| f \right| ^p \, d\mu=0 $$Therefore, $\left| f(x) \right|^p=0$ $\mu$-a.e. which means $f=0$ $\mu$-a.e. Similarly, if $\left\| f \right\|_{\infty}=0$, then $\left| f \right|\leq 0$ $\mu$-a.e.
>    
>    Secondly, we have: $$\left\| \lambda f \right\|_{p}=\left( \int_{X}^{} \left| \lambda \right| ^p\left| f \right| ^p \, d\mu \right) ^{1/p}=\left| \lambda \right| \left\| f \right\| _{p} $$and $\left\| \lambda f \right\|_{\infty}=\inf\{ M>0:\left| \lambda f(x) \right| \leq M\ \mu \text{-a.e.}\}=\left| \lambda \right|\left\| f \right\|_{\infty}$.
>    
>    Lastly, the triangle inequality holds from Minkowski's inequality.
>2. Let $\{ f_{k} \}_{k}\subseteq L^p(X)$ be a Cauchy sequence. Then, for all $\varepsilon>0$ there exists $N\in \mathbb{N}$ s.t. for all $m,n\geq N$: $$\left\| f_{n}-f_{m} \right\| _{p}=\left( \int_{X}\left| f_{n}-f_{m} \right| ^p \, d\mu \right)^{1/p}<\varepsilon $$
>   
>    **Case 1: $1\leq p<+\infty$:** 
>    For every $n$, we choose $k_{n}$ s.t. $$\left\| f_{n}-f_{m} \right\|_{p} < \frac{1}{2^n},\quad \forall n,m\geq k_{n}$$and $(k_{n})_{n}$ is increasing. Then, we show that $(f_{k_{n}})_{n}$ converges in $L^p$. Let's define $$g_{n}:=\sum_{j=1}^{n}\left| f_{k_{j+1}}-f_{k_{j}} \right| $$Then, $\left\| g_{n} \right\|_{p}\leq \sum_{j=1}^{n}\left\| f_{k_{j+1}}-f_{k_{j}} \right\|_{p}<\sum_{j=1}^{n}\frac{1}{2^j}\leq1$. 
>   
>     By [[Integrable Function|monotone convergence theorem]], $$\lim_{ n \to \infty } \int_{X}^{} \left| g_{n} \right| ^p \, d\mu=\int_{X}^{} \left| g \right| ^p \, d\mu  $$where $g:=\sum_{j=1}^{\infty}\left| f_{k_{j+1}}-f_{k_{j}} \right|$. On the other hand, for $m\geq \ell\geq 2$, we have: $$\begin{align}\left| f_{k_{m}}(x)-f_{k_{\ell}}(x) \right|& \leq \sum_{j=\ell}^{m-1}\left| f_{k_{j+1}}(x)-f_{k_{j}}(x) \right|\\&= g_{m-1}(x)-g_{\ell-1}(x)\\&\leq g(x)-g_{\ell-1}(x)\end{align}$$As $g_{n}\to g$ $\mu$-a.e., $(g_{n})_{n}$ is Cauchy and therefore, $(f_{k_{n}})_{n}$ is also Cauchy $\mu$-a.e. and there exists $f$ s.t. $f_{k_{n}}\to f$ $\mu$-a.e.
>     
>     We can see that $$\left| f(x)-f_{k_{\ell}}(x) \right| \leq g(x)-g_{\ell-1}(x)\leq g(x)$$By applying the [[Summable Function|dominated convergence theorem]] on $\left| f-f_{k_{\ell}} \right|^p$, $$\lim_{ \ell \to \infty } \int_{X}^{} \left| f-f_{k_{\ell}} \right| ^p \, d\mu =0$$Therefore, $\left\| f-f_{k_{\ell}} \right\|_{p}\to{0}$. Then, $$\left\| f \right\| _{p}\leq \left\| f-f_{k_{\ell}} \right\|_{p} +\left\| f_{k_{\ell}} \right\|_{p}<+\infty $$This shows that $f\in L^p(X)$. 
>     
>      Now we will show that $\left\| f-f_{k} \right\|\xrightarrow{k\to \infty}0$. We have for all $n$ and $k\geq k_{n}$: $$\begin{align}\left\| f-f_{k} \right\|_{p} &\leq \left\| f_{k}-f_{k_{n}} \right\|_{p} +\left\| f_{k_{n}}-f \right\| _{p}\\&< \frac{1}{2^n}+\left\| f-f_{k_{n}} \right\|_{p} \end{align}$$This proves that $\lim_{ k \to \infty }\left\| f-f_{k} \right\|_{p}=0$.
>      
>     **Case 2: $p=+\infty$:**
>     For a Cauchy sequence $(f_{k})_{k}\subseteq L^\infty(X)$, we define for all $\ell,m\geq 1$: $$E_{\ell,m}:=\{ x\in \Omega:\left| f_{\ell}(x)-f_{m}(x) \right| >\left\| f_{\ell}-f_{m} \right\| _{\infty} \}$$Then, $\mu(E_{\ell,m})=0$. Then, $E_{0}:=\bigcup_{{\ell,m}\geq 1}^{}E_{\ell,m}$ and $\mu(E_{0})=0$. For $x\in X\backslash E_{0}$, we have: $$\left| f_{\ell}(x)-f_{m}(x) \right| \leq \left\| f_{\ell}-f_{m} \right\| _{\infty}<\varepsilon$$Therefore, $\{ f_{k}(x) \}$ is a Cauchy sequence in $\mathbb{R}$. We define $f(x):=\lim_{ k \to \infty }f_{k}(x)$. Then, as $\left| f_{\ell}(x)-f(x) \right|<\varepsilon$ $\mu$-a.e., $\left\| f_{\ell}-f \right\|_{\infty}\leq\varepsilon$ which shows that the sequence converges in $L^\infty$ and 
>     $$\left\| f \right\| _{\infty}\leq \left\| f_{\ell}-f \right\| _{\infty}+\left\| f_{\ell} \right\| _{\infty}\leq \varepsilon+\left\| f_{\ell} \right\|_{\infty}<+\infty $$
---
> [!lemma] Theorem 8
> Let $X\subseteq \mathbb{R}^n$ and $1\leq p<\infty$. Then, $L^p(X)$ is [[Separable Space|separable]].

> [!proof]-
> We will show that $L^p(\mathbb{R}^n)$ is separable. Then, the rest follows. We define: 
> $$E:=\left\{  \sum_{k=1}^{N}a_{k}\chi_{Q_{k}}:a_{k}\in \mathbb{Q},Q_{k}\subseteq \mathbb{R}^n\text{ is a dyadic cube of length }2^{-\ell},\ell\geq 0 \right\}$$
> We will show that $E$ is dense in $L^p(\mathbb{R}^n)$. Firstly, we claim the following: 
> > [!claim]
> > For every $\mu$-measurable $A\subseteq \mathbb{R}^n$ with $\mu(A)<+\infty$, $\chi_{A}\in \overline{E}$.
>
> > [!proof]-
> > Since $\mu$ is Radon, we have: $\mu(A)=\inf_{A\subseteq G}\mu(G)$, $G$ open. Let us choose $(G_{k})_{k}$ open sets s.t. 
> > 1. $A\subseteq G_{k}$ and
> > 2. $G_{k+1}\subseteq G_{k}$
> > 3. $\mu(G_{k})<\mu(A)+\frac{1}{k}$
> >    
> > Then, $$\int_{\mathbb{R}^n}^{} \left| \chi_{G_{k}}-\chi_{A} \right| ^p \, d\mu=\int_{\mathbb{R}^n}^{} \left| \chi_{G_{k} \backslash A} \right|^p  \, d\mu=\mu(G_{k}\backslash A)\leq \frac{1}{k} $$Therefore, we can suppose that $A$ is open. Then, by [[Dyadic Cubes|Lemma 2]], we can express $A$ as a countable union of disjoint dyadic cubes $A=\bigcup_{\ell=1}^{\infty}I_{\ell}$ with $\mu(A)=\sum_{\ell=1}^{\infty}\mu(I_{\ell})$. Further, $$\chi_{\bigcup_{\ell=1}^{n}I_{\ell}}=\sum_{\ell=1}^{n}\chi_{I_{\ell}}\xrightarrow{n\to \infty}\chi_{A}$$Therefore, by the [[Summable Function|Lebesgue theorem]], $$\lim_{ n \to \infty }\left\| \chi_{A}- \sum_{\ell=1}^{n}\chi_{I_{\ell}}\right\|_{p}=0  $$This proves the claim.
> 
> Let $f\in L^p(\mathbb{R}^n)$ s.t. $f\geq 0$. Then, by [[Measurable Function|Theorem 3]], $f$ is a pointwise limit of the sequence $$f_{k}=\sum_{j=1}^{k} \frac{1}{j}\chi_{A_{j}}$$Which by Lebesgue theorem, we can show that: $$\lim_{ k \to \infty } \left\| f-f_{k} \right\| _{p}=0$$Therefore, $f\in \overline{E}$. Similarly, for general $f$, we can use $f=f^+ -f^-$.
> 
> 
- **Remark**: $L^\infty(X)$ is not separable. Let $X:=(0,1)$ and $\mu=\mathcal{L}^1$. For $0<t<1$, consider $f_{t}:=\chi_{(0,t)}$ with $\left\| f_{t}-f_{s} \right\|_{\infty}=1$ if $t\neq s$. We notice that $(f_{t})_{0<t<1}$ is uncountable, however if $L^\infty(X)$ is separable, there exists $(e_{k})_{k}$ s.t. $$\inf_{k\geq 1}\left\| f_{t}-e_{k} \right\| < \frac{1}{2}, \forall t>0$$However, no two from $(f_{t})_{t}$ can be in the same ball $B_{<1/2}(e_{k})$ which is a contradiction. 
---
> [!lemma] Theorem 8
> Let $1\leq p<+\infty$ and $f,f_{k}\in L^p(X)$. Then the following are equivalent: 
> 1. $\lim_{ k \to \infty }\left\| f_{k}-f \right\|_{p}=0$
> 2. $f_{k}\xrightarrow{\mu}f$ and $\lim_{ k \to \infty }\left\| f_{k} \right\|_{p}=\left\| f \right\|_{p}$

> [!proof]-
> We have that:
> - (1=>2): We have that by Chebyshev: $$\lim_{ k \to \infty } \mu(\{ x\in X :\left| f(x)-f_{k}(x) \right| >\varepsilon\})\leq \frac{1}{\varepsilon}\lim_{ k \to \infty }\int_{X}^{} \left| f-f_{k} \right|  \, d\mu =0 $$Further, from Minkowski: $$\left| \left\| f_{k} \right\| _{p}-\left\| f \right\| _{p} \right| \leq \left\| f-f_{k} \right\| _{p}$$
> - (2=>1): We observe that: $$\left| f_{k}(x)-f(x) \right| ^p\leq 2^{p-1}(\left| f(x) \right|^p +\left| f_{k}(x) \right|^p )$$Let $(f_{k_{n}})_{n}$ be a subsequence of $(f_{k})_{k}$ converging to $f$ $\mu$-a.e. Then, by Fatou's lemma: $$$$
---
> [!lemma] Theorem 9 (Dual of Lp-Spaces)
> Let $1\leq p<+\infty$ and $q$ the conjugate exponent, i.e. $\frac{1}{p}+\frac{1}{q}=1$.  Then, the map $$\begin{array}{cccc} {J:}&{L^q(X)}&\to&{(L^p(X))^{*}}\\&{g} &\mapsto & {\ell_g:f\mapsto \int_{X}^{} fg \, d\mu } \end{array}{}$$is an [[Bounded Linear Map|isometric]] isomorphism with $\left\| \ell_{g} \right\|\leq \left\| g \right\|_{q}$.
---
> [!lemma] Corollary 10
> For $1<p<+\infty$, $L^p(X)$ is [[Bidual Space|reflexive]].
---
> [!lemma] Theorem 11 (Grothendieck's Theorem)
> Let $(X,\Sigma,\mu)$ be a finite [[measure space]], i.e. $\mu(X)<+\infty$. If:
> 1. $E$ is a closed subspace of $L^p(X,\mu)$, for some $1\leq p<+\infty$ and
> 2. $E \subseteq L^\infty(X,\mu)$
> 
> Then, $E$ is finite-dimensional.

> [!proof]-
> We have:
> 1. **Showing that $\left\| f \right\| _{\infty}\leq M\left\| f \right\| _{p}$ for some $M>0$ for all $f\in E$**:
> 	Let $I:E\hookrightarrow L^\infty(X,\mu)$ be the embedding and show that $\overline{\text{graph}(I)}\subseteq \text{graph}(I)$.
> 	
> 	Let $(f,g)\in \overline{\text{graph}(I)}\subseteq E\times L^\infty(X,\mu)$ and $(f_{n})_{n}\subseteq E$ s.t. $f_{n}\to f$ in $L^p$ and $I(f_{n})=f_{n}\to g$ in $L^\infty$. 
> 	
> 	From $f_{n}\to f$ in $L^p$, by Theorem 8, $f_{n}\xrightarrow{\mu}f$ and by [[Convergence in Measure|Theorem 2]], there exists a subsequence $(f_{n_{k}})_{k}$ s.t. $f_{n_{k}}\to f$ $\mu$-a.e.
> 	
> 	From $f_{n}\to g$ in $L^\infty$, then, $$\left\| f_{n}-g \right\| _{1}=\int_{X}^{} \left| f_{n}-g \right|  \, d\mu\leq \left\| f_{n}-g \right\| _{\infty}\mu(X)\xrightarrow{n\to \infty}0 $$Therefore, $f_{n}\to g$ $\mu$-a.e. This shows that $f=g$ and $(f,g)=(f,I(f))$.
> 	
> 	Using the [[Bounded Linear Map|closed graph theorem]], $I$ is bounded and there exists $M>0$ s.t. for all $f\in E$: $$\left\| f \right\| _{\infty}\leq M\left\| f \right\| _{p}$$
> 2. **Showing that $\left\| f \right\|_{p}\leq A\left\| f \right\|_{2}$ for some $A>0$ for all $f\in E$**:
> 	As $\mu(X)<+\infty$, by Lemma 5, $E\subseteq L^\infty(X)\subseteq L^2(X)$.
> 	
> 	- If $1\leq p\leq 2$, then by Hölder's inequality, $$\left\| f \right\| ^p_{p}=\left\| |f|^p\cdot 1 \right\| _{1}\leq \left\| |f|^p \right\|_{2/p}\left\| 1 \right\| _{2 /(2-p)}=\left\| f \right\|_{2}^p\cdot \mu(X)^{(2-p)/2}   $$Therefore, $\left\| f \right\|_{p}\leq \left\| f \right\|_{2}\mu(X)^{(2-p)/2p}$.
> 	- If $2<p<+\infty$, $$\left\| f \right\| ^p_{p}\leq \left\| f \right\| _{\infty}^{p-2}\int_{X}^{} \left| f \right| ^{2} \, d\mu=\left\| f \right\| _{\infty}^{p-2}\left\| f \right\| ^{2}_{2}\leq M^{p-2}\left\| f \right\| _{p}^{p-2}\left\| f \right\| ^2_{2} $$Therefore, $\left\| f \right\|_{p}\leq \left\| f \right\|_{2}M^{(p-2)/2}$
> 3. **Showing that $E$ is finite-dimensional**:
>    Let $f_{1},\dots,f_{n}$ be an orthonormal set in $E$, achieved using Gram-Schmidt. Further, let: $$B:=\left\{  \rho\in \mathbb{C}^n:\left\| \rho \right\|_{2}\leq 1 \right\}$$be the unit closed ball in $\mathbb{C}^n$. For every $\rho\in B$, define: $f_{\rho}=\sum_{j=1}^{n}\rho_{j}f_{j}$. Then, $\left\| f_{\rho} \right\|_{2}^2=\sum_{j=1}^{n}\left| \rho_{j} \right|^2\leq 1$ and from part 1 and 2, $\left\| f_{\rho} \right\| _{\infty}\leq A$ for some $A>0$ for all $\rho\in B$. 
> 
>    So for every $\rho\in B$, there exists a measurable subset $X_{\rho}\subseteq X$ with $\mu(X_{\rho})=\mu(X)$ s.t. $\left| f_{\rho}(x) \right|\leq A$ for all $x\in X_{\rho}$. Let now $\{ \rho_{n}:n\geq 1 \}\subseteq B$ be a countable dense subset of $B$ and $S:=\bigcap_{i=1}^{\infty}X_{\rho_{i}}$. Then, $\left| f_{\rho_{i}}(x) \right|\leq A$ for all $i\in \mathbb{N}$ and $x\in S$. Further, $\mu(S)=\mu(X)$. 
> 
>    However, observe that for all $x\in S$, $\rho\mapsto f_{\rho}(x)$ is continuous and therefore, $\left| f_{\rho}(x) \right| \leq A$ for all $x\in S$ and $\rho\in B$. For a fixed $x\in S$, $$\left( \sum_{j=1}^{n}\left| f_{j}(x) \right| ^{2} \right)^{1/2}=\sup_{\left\| \rho \right\| _{2}\leq 1}\left| f_{\rho}(x) \right| \leq A$$Then, $$n=\sum_{j=1}^{n}\int_{S}^{} \left| f_{k} \right|^{2}  \, d\mu=\int_{S}^{} \sum_{j=1}^{n}\left| f_{k} \right|^{2}  \, d\mu \leq A^{2} \mu(X)$$Therefore, $\text{dim }E<+\infty$.
---
##### Dual of $L^p(X)$
Let $1\leq p <+\infty$ and $q$ the conjugate exponent, i.e. $$\frac{1}{p}+\frac{1}{q }=1$$Then, Hölder's inequality ensures that every $g\in L^q(X)$ gives rise to a continuous linear form $\ell_{g}:L^p(X)\to \mathbb{C}$ by: $$\ell_{g}(f):=\int _{X}f(x)g(x) \, d\mu(x) $$with $\left\| \ell \right\|\leq \left\| g \right\|_{q}$.

> [!lemma] Theorem 3
> 

> [!proof]- Proof (Incomplete)
> $J$ is trivially linear. Then, from Hölder's inequality, we have: $$\left\| \ell_{g} \right\| =\sup_{\left\| f \right\| _{p} \leq 1}\left| \int _{X}f(x)g(x) \, d\mu(x)  \right| \leq \left\| g \right\| _{q}$$Therefore, $$\left\| J \right\| =\sup_{\left\| g \right\| _{q}\leq 1}\left\| \ell_{g} \right\| \leq 1$$Now, if $1<p<+\infty$, we have $q<\infty$ and $p=\frac{q}{q-1}$. For some $g\in L^q(X)$, we choose $f=g\left| g \right|^{q-2}\in L^p(X)$ where:$$\left\| f \right\| _{p}=\left( \int _{X}\left| g(x) \right| ^q \, d\mu(x)  \right)^{(q-1)/q} =\left\| g \right\| _{q}^{q-1}$$Therefore, $$\left\| g \right\| ^q_{q}=\int _{X}\left| g(x) \right| ^q \, d\mu(x)= \left| \int _{X}f(x)g(x) \, d\mu(x)  \right| =\left| \ell_{g}(f) \right| \leq \left\| \ell_{g} \right\| \|f\|_{p}=\left\| \ell_{g} \right\| \left\| g \right\|_{q}^{q-1} $$It follows that $\left\| g \right\|_{q}\leq \left\| \ell_{g} \right\|$ and $\left\| g \right\|_{q}= \left\| \ell_{g} \right\|$.
> 
> Now let $p=1$ and $q=\infty$. Let $g\in L^\infty(X)$. 
##### Examples

---

