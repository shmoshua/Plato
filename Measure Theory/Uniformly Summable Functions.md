#Definition #MeasureTheory 

> [!definition]
> Let $\mu$ be a [[Radon measure]] on $\mathbb{R}^n$ and $\Omega$ a $\mu$-measurable set. Let $f_{k}:\Omega\to \overline{\mathbb{R}}$ be [[Summable Function|$\mu$-summable]] functions. Then, $\{ f_{k} \}_{k}$ is called ***uniformly $\mu$-summable***, if for all $\varepsilon>0$ there exists $\delta>0$ s.t. any $\mu$-measurable set $A\subseteq \Omega$ with $\mu(A)<\delta$, it holds that: $$\int_{A}^{} \left| f_{k} \right|  \, d\mu<\varepsilon,\quad \forall k\in \mathbb{N} $$

- **Equivalent defintion**: $\{ f_{k} \}_{k}$ is uniformly $\mu$-summable if and only if $$\lim_{ \mu(A) \to 0 } \int_{A}^{} \left| f_{k} \right|  \, d\mu =0$$uniformly in $k$.
---
##### Properties
> [!lemma] Theorem 1 (Vitali)
> Let $f_{k},f:\Omega\to \overline{\mathbb{R}}$ be $\mu$-summable functions. If $\mu(\Omega)<+\infty$, then the following are equivalent: 
> 1. $f_{k}\xrightarrow{\mu}f$ and $\{ f_{k} \}$ is uniformly $\mu$-summable.
> 3. $\lim_{ k \to \infty }\int_{\Omega}^{} \left| f-f_{k} \right| \, d\mu=0$, i.e. $f_{k}\xrightarrow{L^1}f$.

> [!proof]-
> We will show: 
> - (2=>1): By [[Summable Function|Corollary 4]], $f_{k}\xrightarrow{\mu}f$. We will now show that $\{ f_{k} \}_{k}$ is uniformly $\mu$-summable. For $\varepsilon>0$, choose $k_{0}=k_{0}(\varepsilon)$ s.t. for all $k\geq k_{0}$, $$\int_{\Omega}^{} \left| f-f_{k} \right|  \, d\mu\leq \frac{\varepsilon}{2} $$Then, by [[Summable Function|modulus of integrability]], we can choose $\delta$ s.t. for any $\mu$-measurable $A\subseteq\Omega$ with $\mu(A)<\delta$:
> 	1. $\int_{A}^{} \left| f \right| \, d\mu<\varepsilon/2$ and
> 	2. $\max_{1\leq k\leq k_{0}}\int_{A}^{} \left| f_{k} \right| \, d\mu<\varepsilon$
>  
> 	 Then, for $k>k_{0}$:$$\int_{A}^{} \left| f_{k} \right|  \, d\mu\leq \int_{A}^{} \left| f \right|  \, d\mu+\int_{A}^{} \left| f-f_{k} \right|  \, d\mu < \frac{\varepsilon}{2}+  \frac{\varepsilon}{2}=\varepsilon $$Therefore, we have the desired property.
> - (1=>2): Fix some $\varepsilon>0$. Then, let $\delta$ be from the uniform $\mu$-summability, i.e. for any $k\geq 1$ and $\mu$-measurable set $A\subseteq \Omega$ with $\mu(A)<\delta$, $$\int_{A}^{} \left| f_{k} \right|  \, d\mu<\varepsilon $$Then, let $A_{k}:=\{x\in \Omega:\left| f(x)-f_{k}(x) \right|>\varepsilon  \}$ and $B_{k}:=\{ x\in \Omega:\left| f(x)-f_{k}(x) \right|\leq \varepsilon \}$. By convergence in measure, for $k$ large, $$\mu(A_{k})<\delta$$Similarly, from convergence in measure, there exists a subsequence $f_{k_{n}}\to f$ $\mu$-a.e. Therefore, $$\int_{A_{k}}\left|f  \right|   \, d\mu=\int_{A_{k}}^{} \liminf_{ j \to \infty } \left| f_{k_{j}} \right|  \, d\mu \leq \liminf_{ j \to \infty } \int_{A_{k}}^{} \left| f_{k_{j}} \right|  \, d\mu \leq \varepsilon $$
>   It follows that for $k$ large:$$\begin{align}\int_{\Omega}\left| f-f_{k} \right|  \, d\mu&=\int_{A_{k}}^{} \left| f-f_{k} \right|  \, d\mu+\int_{B_{k}}\left| f-f_{k} \right| \, d\mu  \\&\leq \int_{A_{k}}^{} \left| f \right|  \, d\mu+ \int_{A_{k}}^{} \left| f_{k} \right|  \, d\mu +\varepsilon \mu(\Omega)\\&\leq \varepsilon+\varepsilon+\varepsilon \mu(\Omega)\end{align}$$which proves the statement.
---
> [!lemma] Theorem 2
> Let $\mu(\Omega)<+\infty$ and $f,f_{k}:\Omega\to \overline{\mathbb{R}}$ are [[Measurable Function|$\mu$-measurable]] functions s.t. 
> 1. $\int_{\Omega}^{} \left| f \right|^p \, d\mu<+\infty$
> 2. $\int_{\Omega}^{} \left| f_{k} \right|^p \, d\mu<+\infty$
> 3. $\lim_{ k \to \infty }\int_{\Omega}^{} \left| f-f_{k} \right|^p \, d\mu=0$
>    
> for some $1\leq p<+\infty$. Then, $$\lim_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu=\int_{\Omega}^{} f \, d\mu  $$

> [!proof]-
> For $p=1$ is trivial. Suppose $p>1$. Then, from Chebyshev's inequality, we get: $$\begin{align}\lim_{ k \to \infty } \mu(\{ x\in \Omega:\left| f(x)-f_{k}(x) \right| >\varepsilon \})&=\lim_{ k \to \infty } \mu(\{ x\in \Omega:\left| f(x)-f_{k}(x) \right|^p >\varepsilon^p \})\\&\leq \lim_{ k \to \infty }  \frac{1}{\varepsilon^p}\int_{\Omega}^{} \left| f-f_{k} \right| ^p \, d\mu\\&=0\end{align}$$Therefore, $f_{k}\xrightarrow{\mu}f$. Now, we will show that $\{ f_{k} \}_{k}$ is uniformly $\mu$-summable. For $\varepsilon>0$ there exists $\delta>0$ and $\overline{k}>0$ s.t. if $\mu(A)<\delta$, then $$\int_{A}^{} \left| f \right| ^p \, d\mu<\varepsilon,\quad \int_{A}^{} \left|f-f_{k}  \right|^p  \, d\mu<\varepsilon,\quad \forall k\geq \overline{k}  $$But, $$\begin{align}\int_{A}^{} \left| f_{k} \right|  \, d\mu&\leq \int_{A}^{} 1+\left| f_{k} \right|^p \, d\mu\\ &=\mu(A)+\int_{A}^{} \left| f_{k} \right| ^p \, d\mu  \\&\leq\mu(A)+2^{p-1}\int_{A}^{}\left| f \right| ^p+\left|f- f_{k} \right| ^p \, d\mu \\&\leq \delta+2^p\varepsilon\\&\leq \varepsilon(1+2^p)  \end{align}$$If $\mu(A)<\delta\leq \varepsilon$ and $k\geq \overline{k}$. Therefore, $\{ f_{k} \}_{k}$ is uniformly $\mu$-summable and by the Vitali theorem, $$\lim_{ k \to \infty } \int_{\Omega}^{} \left| f-f_{k} \right|  \, d\mu $$which proves the statement.
---
##### Examples
1. **Example of non-uniformly summable functions**: $f_{k}:=k\chi_{\left[ 0, \frac{1}{k} \right]}$ with $\mu=\mathcal{L}^1$. Then, for $\varepsilon=\frac{1}{2}$ assume $\delta>0$ works. However, for $A:=[0,\delta / 2]$, $\mathcal{L}^1(A)<\delta$ but for $k>2/\delta$, we have: $$\int_{A}^{} \left| f_{k} \right|  \, d\mu=k\cdot \frac{1}{k}=1> \frac{1}{2}  $$
---
 