#Definition #MeasureTheory 

> [!definition]
> Let $\mu$ be a [[Radon measure]] on $\mathbb{R}^n$ and $\Omega \subseteq \mathbb{R}^n$ a $\mu$-measurable set. Then, a $\mu$-measurable function $f:\Omega\to \overline{\mathbb{R}}$ is ***$\mu$-summable*** if: $$\int_{\Omega}^{} \left| f \right|  \, d\mu <+\infty$$i.e. $f\in L^1(\Omega,\mu)$. Similarly, a $\mu$-measurable function $f:\Omega\to \overline{\mathbb{R}}$ is ***locally $\mu$-summable*** in $\Omega$, if $f|_{K}$ is $\mu$-summable for any compact set $K\subseteq \Omega$, i.e. $f|_{K}\in L^1(K,\mu)$.
---
##### Properties
> [!lemma] Proposition 1
> We have for $f,g:\Omega\to \overline{\mathbb{R}}$:
> 1. if $f$ is $\mu$-summable, then $f$ is $\mu$-integrable.
> 2. if $f=0$ $\mu$-a.e., then $f$ is $\mu$-integrable and $\int_{\Omega}^{} f \, d\mu=0$.
> 3. if $f,g$ are $\mu$-integrable and $f=g$ $\mu$-a.e., then $\int_{\Omega}^{} f \, d\mu=\int_{\Omega}^{} g \, d\mu$

> [!proof]-
> We have: 
> 1. Let $f=f^+- f^-$. Then, as $f^+,f^-\leq \left| f \right|$, by monotonicity, $\int_{\Omega}^{} f^+ \, d\mu,\int_{\Omega}^{} f^- \, d\mu<+\infty$. Therefore, we can find simple functions $e_{+},e_{-},g_{+},g_{-}$ s.t.:
> 	- $e_{+}\leq f^+\leq g_{+}$ and
> 	- $e_{-}\leq f^-\leq g_{-}$ and
> 	$$\int_{\Omega}^{} e_{\pm} \, d\mu \leq \int_{\Omega}^{} f^\pm \, d\mu\leq \int_{\Omega}^{} g_{\pm} \, d\mu\leq \int_{\Omega} e_{\pm} \, d\mu+\varepsilon   $$
> 	
> 	Then, by setting $e:=e_{+}-g_{-}$ and $g:=g_{+}-e_{-}$, we have: $$\int_{\Omega}^{} e \, d\mu \leq \underline{\int_{\Omega}}f \, d\mu \leq \overline{\int_{\Omega}} f\, d\mu\leq \int_{\Omega}^{} g \, d\mu \leq \int_{\Omega}^{} e \, d\mu+2\varepsilon  $$where we assume wlog that $e_{\pm}=g_{\pm}=0$ on $\{ x\in \Omega:f^{\pm}(x)=0 \}$. By setting $\varepsilon\to{0}$, we prove the statement. 
> 2. We can easily set $e=g=0$. Then: $$0=\int_{\Omega}^{} e \, d\mu\leq \underline{\int_{\Omega}}f \, d\mu \leq \overline{\int_{\Omega}}f \, d\mu \leq \int_{\Omega}^{} g \, d\mu  =0$$
> 3. We have that $f\leq g$ $\mu$-a.e. and by monotonicity, $$\int_{\Omega}^{} f \, d\mu\leq\int_{\Omega}^{} g \, d\mu$$Similarly, as $f\geq g$ $\mu$-a.e. we have: $$\int_{\Omega}^{} f \, d\mu=\int_{\Omega}^{} g \, d\mu$$
---
> [!lemma] Proposition 2
> Let $f:\Omega\to[0,+\infty]$ be $\mu$-measurable. Then,
> 1. if $\int_{\Omega}^{} f \, d\mu=0$, then $f=0$ $\mu$-a.e.
> 2. if $\int_{\Omega}^{} f \, d\mu<+\infty$, then $f<+\infty$ $\mu$-a.e.

> [!proof]-
> We have: 
> 1. Let $A=\{ x\in \Omega:f(x)>0 \}$ and assume that $\mu(A)>0$. Then, for all $k\geq 1$, we define: $$A_{k}:=\left\{  x\in \Omega :f(x)> \frac{1}{k} \right\}=f^{-1}\left(\frac{1}{k},+\infty\right]$$Then, $A_{k}$ is $\mu$-measurable and $A_{k}\subseteq A_{k+1}$. Further, $\bigcup_{k\geq 1}^{}A_{k}=A$. Therefore, $$\lim_{ n \to \infty } \mu(A_{k})=\mu(A)>0 $$This means, there exists $\overline{k}$ s.t. $\mu(A_{\overline{k}})>0$. Then,$$\frac{1}{\overline{k}}\chi_{A_{\overline{k}}}\leq f,\quad\mu\text{-a-e.}$$Therefore,$$0<\int_{\Omega}^{} \frac{1}{\overline{k}}\chi_{A_{\overline{k}}} \, d\mu\leq \int_{\Omega}^{} f \, d\mu=0  $$which is a contradiction.
> 2.  Let $A:=\{ x\in \Omega:f(x)=\infty \}$ and assume that $\mu(A)>0$. Then, $$\infty \cdot \chi_{A}\leq f,\quad \mu\text{-a-e.}$$But, $$\infty=\int_{\Omega}^{} \infty \cdot \chi_{A} \, d\mu\leq \int_{\Omega}^{} f \, d\mu<+\infty  $$which is a contradiction.
---
> [!lemma] Theorem 3 (Chebyshev's Inequality)
> For a $\mu$-summable function $f:\Omega\to \overline{\mathbb{R}}$, for all $a>0$: $$\mu(\{ x\in\Omega:\left| f(x) \right| >a \})\leq \frac{1}{a}\int_{\Omega}^{} \left| f \right|  \, d\mu $$

> [!proof]-
> Let $A:=\{ x\in \Omega:\left| f(x) \right|>a \}$. Then, $$a \chi_{A}\leq \left| f \right|,\quad\mu \text{-a.e.} $$Therefore, $$a\mu(A)\leq \int_{\Omega}^{} \left| f \right|  \, d\mu  $$
---
> [!lemma] Corollary 4
> Let $f,f_{k}:\Omega\to \overline{\mathbb{R}}$ be $\mu$-integrable with $f_{k}\xrightarrow{L_{1}}f$, i.e. $$\lim_{ k \to \infty } \left\| f_{k}-f \right\|_{1} =\lim_{ k \to \infty } \int_{\Omega}^{} \left| f_{k}-f \right|  \, d\mu=0 $$Then, $f_{k}\xrightarrow{\mu}f$ as $k\to +\infty$. Further, from [[Convergence in Measure|Theorem 2]], there exists a subsequence $\{ k_{n} \}_{n}$ s.t. $f_{k_{n}}\to f$ $\mu$-a.e. 

> [!proof]-
> By the Chebyshev's inequality, $$\lim_{ k \to \infty } \mu(\{ x\in \Omega:\left| f_{k}(x)-f(x) \right| >\varepsilon \})\leq \lim_{ k \to \infty } \frac{1}{\varepsilon}\int_{\Omega}^{} \left| f_{k}-f \right|  \, d\mu = {0}$$Therefore, $f_{k}\xrightarrow{\mu}f$ as $k\to +\infty$.
---
> [!lemma] Theorem 5
> Let $f,g:\Omega\to \overline{\mathbb{R}}$ be $\mu$-summable. Then, for $\lambda\in \mathbb{R}$, $f+g,\lambda f$ are $\mu$-summable and: 
> $$\begin{align}\int_{\Omega}^{} f+g \, d\mu&=\int_{\Omega}^{} f \, d\mu+\int_{\Omega}^{} g \, d\mu  \\\int_{\Omega}^{} \lambda f \, d\mu&=\lambda \int_{\Omega}^{} f \, d\mu   \end{align}$$

> [!proof]-
> We have:
> 1. Firstly, assume $f$ and $g$ are $\mu$-integrable simple functions, i.e. $$f=\sum_{k=1}^{\infty}a_{k}\chi_{A_{k}},\quad g=\sum_{k=1}^{\infty}b_{k}\chi_{B_{k}}$$We can always wlog assume that $A_{k}=B_{k}$. 

- **Corollary**: For $\mu$-summable $f: \Omega\to \overline{\mathbb{R}}$, $$\left| \int_{\Omega}^{} f \, d\mu  \right| \leq \int_{\Omega}^{} \left| f \right|  \, d\mu $$
---
> [!lemma] Lemma 6
> Let $f:\Omega\to \overline{\mathbb{R}}$ be $\mu$-summable and $\Omega_{1}\subseteq\Omega$ be $\mu$-measurable. Then, $f_{1}:=f|_{\Omega_{1}}$ and $f\chi_{\Omega_{1}}$ are $\mu$-summable on $\Omega_{1}$ and $\Omega$ respectively and: $$\int_{\Omega_{1}}^{} f_{1} \, d\mu=\int_{\Omega}^{} f\chi_{\Omega_{1}} \, d\mu  $$

> [!proof]-
> We first show the result for a simple $\mu$-summable function $g:\Omega\to \overline{\mathbb{R}}$. Let $$g(x)=\sum_{k=1}^{\infty}a_{k}\chi_{A_{k}}(x)$$where $A_{k}$ are disjoint and $\bigcup_{k=1}^{\infty}A_{k}=\Omega$. Then, 
> - $g_{1}(x):=g|_{\Omega_{1}}(x)=\sum_{k=1}^{\infty}a_{k}\chi_{A_{k}\cap\Omega_{1}}(x)$
> - $g\chi_{\Omega_{1}}(x):=\sum_{k=1}^{\infty}a_{k}\chi_{A_{k}}(x)\chi_{\Omega_{1}}(x)=\sum_{k=1}^{\infty}a_{k}\chi_{A_{k}\cap\Omega_{1}}(x)$
>   
> Further, both $g_{1}$ and $g\chi_{\Omega_{1}}$ are $\mu$-summable as $\left| g_{1} \right|,\left| g\chi_{\Omega_{1}} \right|\leq \left| g \right|$.
> 
> Now, let $\varepsilon>0$ and choose simple $\mu$-integrable functions $g,h$ s.t. $$g\leq f\leq h,\quad \mu\text{-a.e in }\Omega$$and $$\int_{\Omega}^{} f \, d\mu-\varepsilon\leq \int_{\Omega}g  \, d\mu,\quad \int_{\Omega}h \, d\mu\leq \int_{\Omega}^{} f \, d\mu + \varepsilon   $$
> 
>1. **$f_{1}$ is $\mu$-integrable.**
> $$\begin{align}0&\leq \overline{\int_{\Omega_{1}}}f_{1}\, d\mu -\underline{\int_{\Omega_{1}}}f_{1} \, d\mu\\&\leq \int_{\Omega_{1}}^{} h \, d\mu-\int_{\Omega_{1}}^{} g \, d\mu \\&= \int_{\Omega}^{} h\chi_{\Omega_{1}} \, d\mu-\int_{\Omega}^{} g\chi_{\Omega_{1}} \, d\mu   \\&=\int_{\Omega}^{} (h-g)\chi_{\Omega_{1}}\, d\mu \\&\leq \int_{\Omega}^{} (h-g) \, d\mu\\&\leq 2\varepsilon \end{align}$$By letting $\varepsilon\to{0}$, $f_{1}$ is $\mu$-integrable.
> 2. **$f\chi_{\Omega_{1}}$ is $\mu$-integrable.**
> $$\begin{align}0&\leq \overline{\int_{\Omega}}f\chi_{\Omega_{1}} \, d\mu -\underline{\int_{\Omega}}f\chi_{\Omega_{1}} \, d\mu\\&\leq \int_{\Omega}^{} h\chi_{\Omega_{1}} \, d\mu-\int_{\Omega}^{} g\chi_{\Omega_{1}} \, d\mu   \\&=\int_{\Omega}^{} (h-g)\chi_{\Omega_{1}}\, d\mu \\&\leq \int_{\Omega}^{} (h-g) \, d\mu\\&\leq 2\varepsilon \end{align}$$By letting $\varepsilon\to{0}$, $f\chi_{\Omega_{1}}$ is $\mu$-integrable.
> 3. $\int_{\Omega_{1}}^{} f_{1} \, d\mu=\int_{\Omega}^{} f\chi_{\Omega_{1}} \, d\mu$
> 	We have: $$\begin{align}\int_{\Omega_{1}}^{} f_{1} \, d\mu-\int_{\Omega}^{} f\chi_{\Omega_{1}} \, d\mu&\leq \int_{\Omega}^{} (h-g)\chi_{\Omega_{1}} \, d\mu \leq 2\varepsilon  \end{align}$$$$\begin{align}\int_{\Omega_{1}}^{} f_{1} \, d\mu-\int_{\Omega}^{} f\chi_{\Omega_{1}} \, d\mu&\ge \int_{\Omega}^{} (g-h)\chi_{\Omega_{1}} \, d\mu \geq -2\varepsilon  \end{align}$$We prove the statement by $\varepsilon\to{0}$.

- **Corollary**: For a $\mu$-summable function $f:\Omega\to \overline{\mathbb{R}}$ and $\Omega_{1}\subseteq\Omega$ s.t. $\mu(\Omega_{1})=0$. Then, $$\int_{\Omega_{1}}^{} f \, d\mu=\int_{\Omega}^{} f\chi_{\Omega_{1}} \, d\mu=0  $$from Proposition 1, as $f\chi_{\Omega_{1}}=0$ $\mu$-a.e.
---
> [!lemma] Proposition 7
> Let $f:\Omega\to \overline{\mathbb{R}}$ be $\mu$-summable and $\Omega=\Omega_{1}\cup\Omega_{2}$ where $\Omega_{1},\Omega_{2}$ are $\mu$-measurable and $\Omega_{1}\cap\Omega_{2}=\varnothing$. Then, $$\int_{\Omega}^{} f \, d\mu=\int_{\Omega_{1}}^{} f \, d\mu+\int_{\Omega_{2}}^{} f \, d\mu   $$

> [!proof]-
> We have $f=f\chi_{\Omega_{1}}+f\chi_{\Omega_{2}}$. Therefore, $$\int_{\Omega}^{} f \, d\mu=\int_{\Omega}^{} f\chi_{\Omega_{1}}+f\chi_{\Omega_{2}} \, d\mu=\int_{\Omega_{1}}^{} f \, d\mu+\int_{\Omega_{2}}^{} f \, d\mu    $$
---
> [!lemma] Theorem 8 (Dominated Convergence Theorem, Lebesgue)
> Let $f,f_{k}:\Omega\to \overline{\mathbb{R}}$ be $\mu$-measurable and $g:\Omega\to[0,+\infty]$ be $\mu$-summable. Further, let:
> 1. $\left| f_{k} \right|\leq g$ for all $k\geq 1$ and 
> 2. $f_{k}\to f$ $\mu$-a.e.
> 
> Then, $f_{k}\xrightarrow{L^1}f$, i.e.:$$\lim_{ k \to \infty } \int_{\Omega}^{} \left| f-f_{k} \right|  \, d\mu=0 $$Moreover, $$\lim_{ k \to \infty } \int_{\Omega} f_{k}\, d\mu=\int_{\Omega}^{} f \, d\mu  $$

> [!proof]-
> As $\left| f \right|=\lim_{ k \to \infty }\left| f_{k} \right|\leq g$ $\mu$-a.e., we have: $$0\leq\left| f-f_{k} \right| \leq \left| f \right| +\left| f_{k} \right| \leq 2g$$Therefore, $\left| f-f_{k} \right|$ is $\mu$-summable. Then, $$\begin{align}\int_{\Omega}2g  \, d\mu&=\int_{\Omega}^{} \liminf_{ k \to \infty } (2g -\left| f_{k}-f \right| ) \, d\mu\\&\leq \liminf_{ k \to \infty } \int_{\Omega}^{} 2g-\left| f_{k}-f \right|  \, d\mu\\&=\int_{\Omega}^{} 2g \, d\mu-\limsup_{ k \to \infty } \int_{\Omega}^{} \left| f-f_{k} \right|  \, d\mu    \end{align}$$As $g$ is $\mu$-summable, $$\lim_{ k \to \infty } \int_{\Omega}^{} \left| f-f_{k} \right|  \, d\mu=0 $$Moreover, $$\begin{align}\left| \lim_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu-\int_{\Omega}^{} f \, d\mu   \right| =\lim_{ k \to \infty } \left| \int_{\Omega}^{} f_{k} \, d\mu-\int_{\Omega}^{} f \, d\mu  \right| &\leq \lim_{ k \to \infty } \int_{\Omega}^{} \left| f-f_{k} \right|  \, d\mu =0\end{align} $$Therefore, $$\lim_{ k \to \infty } \int_{\Omega} f_{k}\, d\mu=\int_{\Omega}^{} f \, d\mu  $$
---
> [!lemma] Theorem 9 (Modulus of Integrability)
> For a $\mu$-summable $f:\Omega\to \overline{\mathbb{R}}$ and $\varepsilon>0$, there exists $\delta>0$ s.t. for all $\mu$-measurable $A\subseteq\Omega$ with $\mu(A)<\delta$, it holds that: $$\int_{A}^{} \left| f \right|  \, d\mu<\varepsilon $$

> [!proof]-
> Assume that there exists $\varepsilon>0$ s.t. there exists $(A_{k})_{k}$ $\mu$-measurable with:
> 1. $\mu(A_{k})<1 / 2^{k}$ and
> 2. $\int_{A_{k}}^{} \left| f \right| \, d\mu\geq \varepsilon$
>    
> Now, define $B_{k}:=\bigcup_{\ell\geq k}^{}A_{\ell}$. Then, $$\mu(B_{k})\leq \sum_{\ell=k}^{\infty}\mu(A_{\ell})< \frac{1}{2^{k-1}}\xrightarrow{k\to \infty}0$$As $\left| f \right|\cdot \chi_{B_{k}}\leq\left| f \right|$ for all $k\geq 1$ and $\left| f \right|\cdot \chi_{B_{\ell}}\to \left| f \right|\cdot \chi_{A}$ where $A=\bigcap_{\ell=1}^{\infty}B_{\ell}$. Then, $$\mu(A)=\lim_{ k \to \infty } \mu(B_{k})=0$$
>  Therefore, dy the dominated convergence theorem:$$\begin{align}\varepsilon\leq\lim_{ k \to \infty } \int_{A_{k}}^{} \left| f \right|  \, d\mu\leq\lim_{ k \to \infty } \int_{B_{k}}^{} \left| f \right|  \, d\mu=\lim_{ k \to \infty } \int_{\Omega}^{} \left| f \right| \cdot \chi_{B_{k}} \, d\mu =\int_{A}^{}\left| f \right|   \, d\mu=0 \end{align}$$
---
> [!lemma] Theorem 10 (Improved Lebesgue)
> Let $\mu(\Omega)<+\infty$. Further, let $f,f_{k}:\Omega\to \overline{\mathbb{R}}$ be $\mu$-measurable and $g,g_{k}:\Omega\to[0,+\infty]$ be $\mu$-summable. Further, let:
> 1. $\left| f_{k} \right|\leq \left| g_{k} \right|$ $\mu$-a.e. for all $k\geq 1$ and 
> 2. $f_{k}\xrightarrow{\mu} f$ 
> 3. $g_{k}\xrightarrow{L^1}g$
> 
> Then, $f_{k}\xrightarrow{L^1}f$.

> [!proof]-
> Since $\lim_{ k \to \infty } \int_{\Omega}^{} \left| g-g_{k} \right|  \, d\mu=0$, by [[Uniformly Summable Functions|Vitali's Theorem]], $\{ g_{k} \}_{k}$ are uniformly $\mu$-summable, i.e. for every $\varepsilon>0$ there exists $\delta>0$ s.t. for any $\mu$-measurable set $A\subseteq\Omega$ with $\mu(A)<\delta$, we have: $$\sup_{k\in \mathbb{N}}\int_{A}^{} \left| g_{k} \right|  \, d\mu<\varepsilon $$Therefore, we have: $$\int_{A}^{}  \left| f_{k} \right| \, d\mu\leq \int_{A}^{} \left| g_{k} \right|  \, d\mu<\varepsilon  $$for every $k\geq 1$. Therefore, $(f_{k})_{k}$ is also uniformly $\mu$-summable and by Vitali's theorem, we get the result.
---
##### Exercises
> [!Exercise] Exercise 1
> Apply the Dominated Convergence Theorem to the counting measure on $\mathbb{N}$ to verify that: $$\lim_{ n \to \infty } n\sum_{i=1}^{\infty}\sin \left( \frac{2^{-i}}{n} \right)=2 $$

> [!proof]- Answer
> For a counting measure $\mu$ and a function $f:\mathbb{N}\to \mathbb{R}$, $$\int_{\mathbb{N}}^{} \left| f \right|  \, d\mu=\sum_{k=0}^{\infty}\left| f(k) \right|  $$Then, we set: $f_{n}(i):=n \sin \left( \frac{2^{-i}}{n} \right)$. Then, $\left| f_{n}(i) \right|\leq 1 / 2^i$ for all $n$ and $g(i):=\frac{1}{2^i}$ is summable as: $$\int_{\mathbb{N}}^{} \left| g \right|  \, d\mu=\sum_{k=0}^{\infty} \frac{1}{2^k}=2 $$Further, $$\lim_{ n \to \infty } n \sin \left( \frac{2^{-i}}{n} \right)= \frac{1}{2^{i}} $$Therefore, by the Dominated Convergence Theorem, $$\lim_{ n \to \infty }n\sum_{i=1}^{\infty}\sin \left( \frac{2^{-i}}{n} \right) =\lim_{ n \to \infty } \int_{\mathbb{N}}^{} f_{n} \, d\mu=\int_{\mathbb{N}}^{} g \, d\mu  =2 $$