#Definition #MeasureTheory 

> [!definition]
> Let $(\Omega,\mathcal{F},\mu)$ be a [[measure space]]. Then,
> 1. For a unsigned measurable [[simple function]] $f:\Omega\to[0,+\infty]$ given by $f=\sum_{i=1}^{n}a_{i}\chi_{E_{i}}$ with $a_{n}\in [0,+\infty]$, $$\int_{\Omega}f \, d\mu:=\sum_{i=1}^{n}a_{i}\mu(E_{i}) $$
> 2. 
> Let $\mu$ be a [[Radon Measure|Radon measure]] on $\mathbb{R}^n$ and $\Omega \subseteq \mathbb{R}^n$ a $\mu$-measurable set. Then, for a [[Measurable Function|$\mu$-measurable]] function $f:\Omega\to \overline{\mathbb{R}}$, we define:
> 1. the ***upper integral***: $$\overline{\int_{\Omega}}f \, d\mu :=\inf \left\{ \int_{\Omega}^{} g \, d\mu:g\text{ is simple, }\mu \text{-integrable},  g\geq f \text{ }\mu \text{-a.e.}  \right\}\in \overline{\mathbb{R}} $$
> 2. the ***lower integral***: $$\underline{\int_{\Omega}}f \, d\mu :=\sup \left\{ \int_{\Omega}^{} g \, d\mu:g\text{ is simple, }\mu \text{-integrable},  g\leq f \text{ }\mu \text{-a.e.}  \right\} \in \overline{\mathbb{R}}$$
>    
> Then, $f$ is ***$\mu$-integrable*** if $\overline{\int_{\Omega}}f \, d\mu=\underline{\int_{\Omega}}f \, d\mu$. Then, we write: $$\int_{\Omega}^{} f \, d\mu =\overline{\int_{\Omega}}f \, d\mu=\underline{\int_{\Omega}}f \, d\mu  $$
---
##### Properties
> [!lemma] Lemma 1 (Properties of the Lebesgue Integral for Simple Functions)
> Let $f,g:\Omega\to[0,+\infty]$ be unsigned measurable simple functions and $c\in [0,+\infty]$. Then, 
> 1. $\int_{\Omega}^{} f \, d\mu$ is well-defined.
> 2. **linearity**: $\int_{\Omega}^{} f+g \, d\mu=\int_{\Omega}^{} f \, d\mu+\int_{\Omega}^{} g \, d\mu$ and $\int_{\Omega}^{} cf \, d\mu=c\int_{\Omega}^{} f \, d\mu$
> 3. 

> [!lemma] Proposition 1
> It holds that: $$\underline{\int_{\Omega}}f \, d\mu \leq \overline{\int_{\Omega}}f \, d\mu $$

> [!proof]-
> Firstly, this holds for a simple function $f$ as $f$ is $\mu$-integrable. Then, assume $f$ is not simple. Let $g$ be a simple, $\mu$-measurable function s.t. $g\leq f$ $\mu$-a.e. Similarly, $h$ is a simple $\mu$-measurable function s.t. $f\leq h$ $\mu$-a.e. 
---
> [!lemma] Proposition 2
> Let $f:\Omega\to[0,+\infty]$ be $\mu$-measurable. Then, $f$ is $\mu$-integrable.

> [!proof]-
> Assume that $\underline{\int_{\Omega}}f \, d\mu<+\infty$ (otherwise, we're done).
> 
> Then, we have $f(x)<+\infty$ $\mu$-a.e.
> 1. Assume $\mu(\Omega)<+\infty$. Then for $\varepsilon>0$, we define: $$A_{k}:=\{ x\in \Omega:k\varepsilon\leq f(x)<(k+1)\varepsilon \}=f^{-1}[k\varepsilon,(k+1)\varepsilon)$$If we now set $\Omega':=\bigcup_{k\geq 0}^{}A_{k}=f^{-1}[0,+\infty)$ Then, $\mu(\Omega \backslash \Omega')=\mu(f^{-1}[\{ +\infty \}])=0$.
>  
>    Now, consider the simple functions: 
>    $$\begin{align}e(x)&:=\varepsilon \sum_{k=0}^{\infty}k\chi_{A_{k}}(x)\\g(x)&:=\varepsilon \sum_{k=0}^{\infty}(k+1)\chi_{A_{k}}(x)\end{align}$$Then, $e(x)\leq f(x)\leq g(x)$ $\mu$-a.e. Therefore, $$\int_{\Omega}^{} e \, d\mu\leq\underline{\int_{\Omega}}f  \, d\mu\leq  \overline{\int_{\Omega}} f\, d\mu\leq \int_{\Omega}^{} g \, d\mu\leq \int_{\Omega}^{} e \, d\mu+\varepsilon \mu(\Omega)    $$By letting $\varepsilon\to{0}$, we get that $f$ is $\mu$-integrable.
>  2. If $\mu(\Omega)=+\infty$, we choose [[Dyadic Cubes]] $\mathbb{R}^n=\bigcup_{\ell =0}^{\infty}Q_{\ell}$ where $\mu(Q_{\ell})<+\infty$ as $\mu$ is Radon and the compact sets have finite measure. 
>     
>     Then, we compute with $\Omega_{\ell}:=\Omega \cap Q_{\ell}$. Then for all $\ell\geq 0$, there exists $e_{\ell},g_{\ell}:\Omega_{\ell}\to \mathbb{R}^n$ s.t. $$e_{\ell}\leq f\leq g_{\ell}$$in $\Omega_{\ell}$. Then, we take:
>     - $e=\sum_{\ell=0}^{\infty}e_{\ell}\chi_{\Omega_{\ell}}$
>     - $g=\sum_{\ell=0}^{\infty}g_{\ell}\chi_{\Omega_{\ell}}$
>     
>     Then, $$\sum_{\ell=0}^{\infty}\int_{\Omega_{\ell}}^{} e_{\ell} \, d\mu \leq \underline{\int_{\Omega}}f \, d\mu \leq \overline{\int_{\Omega}}f \, d\mu \leq \sum_{\ell=0}^{\infty}\int_{\Omega_{\ell}}^{} g \, d\mu\leq \sum_{\ell=0}^{\infty}\left( \int_{\Omega_{\ell}} e_{\ell}  \, d\mu+\frac{\varepsilon}{2^\ell} \right) $$By letting $\varepsilon\to{0}$, we conclude the proof.



- **Remark**: There exist $\mu$-measurable functions $f:\Omega\to[-\infty,\infty]$ that is not $\mu$-integrable.
---
> [!lemma] Proposition 3 (Monotonicity)
> Let $f_{1},f_{2}:\Omega\to \overline{\mathbb{R}}$ be $\mu$-integrable with $f_{1}\leq f_{2}$ $\mu$-a.e. Then, $$\int_{\Omega}^{} f_{1} \, d\mu \leq \int_{\Omega}^{} f_{2} \, d\mu $$

> [!proof]-
> For any simple, $\mu$-measurable $g$ s.t. $f_{2}\leq g$ $\mu$-a.e., we have $f_{1}\leq g$ $\mu$-a.e. Therefore, $$\int_{\Omega}^{} f_{1} \, d\mu \leq \int_{\Omega}^{} g \, d\mu $$and consequently, $$\int_{\Omega}^{} f_{1} \, d\mu \leq \overline{\int_{\Omega}}f_{2} \, d\mu =\int_{\Omega}^{} f_{2} \, d\mu  $$
---
> [!lemma] Theorem 4 (Fatou's Lemma)
> Let $f_{k}:\Omega\to[0,+\infty]$ be $\mu$-measurable. Then, $$\int_{\Omega}^{} \liminf_{ k \to \infty } f_{k} \, d\mu\leq \liminf_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu  $$

> [!proof]-
> By Proposition 2, $f_{k}$ and $f:=\liminf_{ k \to \infty }f_{k}$ are $\mu$-integrable. Therefore, it is sufficient to show that it holds: $$\int_{\Omega}^{} g \, d\mu\leq \liminf_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu  $$for every simple function $g=\sum_{j=0}^{\infty}a_{j}\chi _{A_{j}}$ with $g\leq f$ $\mu$-a.e.
> 
> Wlog we can assume that $a_{0}=0$ and $a_{j}>0$ for $j\geq 1$. We choose $0<t<1$. Now, for all $j\geq 0$ and $k\geq 1$, we define: $$B_{j,k}:=\{ x\in A_{j}:f_{\ell}(x)>ta_{j}\quad \ell\geq k \}$$Then, $B_{j,k}\subseteq B_{j,k+1}$. 
> > [!claim]
> > We have that: $A_{j}=\bigcup_{k=1}^{\infty}B_{j,k}$
> 
> > [!proof]-
> > $\supseteq$ is clear. Assume that we have $x\in A_{j}$. Then, $$ta_{j}<a_{j}=g(x)\leq \liminf_{ k \to \infty }f_{k}(x)=\sup_{n\geq 1}\inf_{k\geq n}f_{k}(x)$$
> > Therefore, there exists $\overline{n}\geq 1$ s.t. $$\inf_{k\geq \overline{n}}f_{k}(x)>ta_{j}$$In other words, $x\in B_{j,\overline{n}}$. This proves the statement.
> 
> Since $A_{j}=\bigcup_{k=1}^{\infty}B_{j,k}$, $$\lim_{ k \to \infty } \mu(B_{j,k})=\mu(A_{j})$$For $J,k\in \mathbb{N}$, we have: $$\begin{align}\int_{\Omega}f_{k}  \, d\mu\geq \sum_{j=1}^{J}\int _{A_{j}}f_{k} \, d\mu\geq \sum_{j=1}^{J}\int_{B_{j,k} }^{}  f_{k}\, d\mu\geq t\cdot \sum_{j=1}^{J}a_{j}\mu(B_{j,k})   \end{align}$$Then, by letting $k\to+\infty$, $$\liminf_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu\geq t\cdot \sum_{j=1}^{J}a_{j}\mu(A_{j}) $$Then, by letting $J\to \infty$, then:$$\liminf_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu\geq t\cdot \sum_{j=1}^{\infty}a_{j}\mu(A_{j})=t\int_{\Omega}^{} g \, d\mu  $$We conclude the proof by $t\to 1$.

- **Remark**: $f_{k}\geq 0$ is necessary. **Example**: $\mu=\mathcal{L}^n$, $\Omega=\mathbb{R}^n$, $f_{k}=-\frac{1}{k^n}\chi_{B_{<k}(0)}$. Then, 
	- $\liminf_{ k \to \infty }\int_{\Omega}^{} f_{k} \, d\mathcal{L}^n=-\liminf_{ k \to \infty } \frac{1}{k^n}\mathcal{L}^n(B_{<k}(0))=-w_{n}$
	- $\liminf_{ k \to \infty }f_{k}=0$.
---
> [!lemma] Theorem 5 (Monotone Convergence Theorem, Beppo-Levi)
> Let $f_{k}:\Omega\to[0,+\infty]$ be $\mu$-measurable and increasing, i.e. $f_{1}\leq f_{2}\leq\dots$ $\mu$-a.e. Then, $$\int_{\Omega}^{} \lim_{ k \to \infty } f_{k} \, d\mu=\lim_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu  $$

> [!proof]-
> As we have $f_{j}\leq \lim_{ k \to \infty }f_{k}$ $\mu$-a.e. By monoticity, $$\int_{\Omega}^{} f_{j} \, d\mu\leq \int_{\Omega}^{} \lim_{ k \to \infty}f_{k}  \, d\mu  $$By taking the limit, we have $\int_{\Omega}^{} \lim_{ k \to \infty } f_{k} \, d\mu\geq\lim_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu$.
> 
> For the opposite inequality we have: $$\begin{align}\int_{\Omega}^{} \lim_{ k \to \infty } f_{k} \, d\mu&=\int_{\Omega}^{} \liminf_{ k \to \infty } f_{k} \, d\mu \leq \liminf_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu=\lim_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu   \end{align}$$
---
> [!lemma] Corollary 6
> Let $f_{k}:\Omega\to[0,+\infty]$ be a sequence of $\mu$-measurable functions. Then, $$\int_{\Omega}^{} \sum_{k=1}^{\infty}f_{k} \, d\mu=\sum_{k=1}^{\infty}\int_{\Omega}^{} f_{k} \, d\mu  $$

> [!proof]-
> We define $s_{n}:=\sum_{k=1}^{n}f_{k}$. Then, $(s_{n})_{n}$ is an increasing sequence of $\mu$-measurable functions. Therefore, using monotone convergence theorem: $$\int_{\Omega}^{}\sum_{k=1}^{\infty}f_{k} \, d\mu=\int_{\Omega}^{} \lim_{ n \to \infty } \sum_{k=1}^{n}f_{k} \, d\mu=\lim_{ n \to \infty } \int_{\Omega}^{} \sum_{k=1}^{n}f_{k} \, d\mu=\lim_{ n \to \infty } \sum_{k=1}^{n}\int_{\Omega}^{} f_{k} \, d\mu =\sum_{k=1}^{\infty}\int_{\Omega}^{} f_{k} \, d\mu  $$
---
> [!lemma] Lemma 7 (Borel-Cantelli)
> Let $\{ E_{k} \}$ be $\mu$-measurable sets in $\mathbb{R}^n$ s.t. $\sum_{k=1}^{\infty}\mu(E_{k})<+\infty$. Then, $$\mu \left( \limsup_{ k \to \infty } E_{k} \right)=0 $$

> [!proof]-
> We have that $\chi_{E_{k}}$ are $\mu$-measurable functions. Then, $$\int_{\Omega}^{} \sum_{k=1}^{\infty}\chi_{E_{k}} \, d\mu=\sum_{k=1}^{\infty}\int_{\Omega}^{} \chi_{E_{k}} \, d\mu =\sum_{k=1}^{\infty}\mu(E_{k})<+\infty $$Therefore, since $f$ is $\mu$-summable, by [[Summable Function|Proposition 2]],$$\mu\left(\limsup_{ k \to \infty } E_{k}\right)=\mu(\{ x\in \Omega: f(x)=+\infty \})=0$$
---
> [!lemma] Theorem 8 (Radon-Nikodym)
> Let $(X,\Sigma)$ be a measurable space and $\mu,\nu$ are finite measures on $(X,\Sigma)$ s.t. $\nu\ll \mu$, i.e. for every $E\in \Sigma$, $$\mu(E)=0 \implies \nu(E)=0$$Then, there exists a unique function $\rho\in L^1(X,\mu)$ s.t. for any $E\in \Sigma$:$$\nu(E)=\int_{E}^{} \rho \, d\mu $$

> [!proof]-
> We have: 
> 1. **Proving the existence**: We define the auxiliary measure $\lambda:=\mu+\nu$. Then, $\nu \ll \mu\ll \lambda$ and $\lambda(X)<+\infty$. We now define a functional: $$\begin{array}{cccc} {T:}&{L^2(X,\lambda)}&\to&{\mathbb{C}}\\&{u} &\mapsto & {\int_{X}^{} u \, d\nu } \end{array}{}$$which is well-defined, because by Hölder, $$\left( \int_{X}^{} \left| u \right|  \, d\nu  \right) ^{2}\leq \left( \int_{X}^{} \left| u \right|  \, d\lambda  \right) ^{2}\leq\lambda(X)\int_{X}^{} \left| u \right| ^{2} \, d\lambda $$Furthermore, $T$ is linear and bounded as: $$\left| T(u) \right| \leq \lambda(X)^{1/2}\|u\|$$Therefore, by Riesz-representation, there exists a unique function $f\in L^2(X,\lambda)$ s.t. $$T(u)=\int_{X}^{} u \, d\nu=\int_{X}^{} fu \, d\lambda  $$for all $u\in L^2(X,\lambda)$. As $\lambda=\nu+\mu$, $$\int_{X}^{}(1-f) u \, d\nu=\int_{X}^{} fu \, d\mu$$Then, by using $u:=\chi_{\{ f<0 \}}$, $$0\leq \int_{\{ f<0 \}}^{}\underbrace{ (1-f) }_{ \geq0 }  \, d\nu=\int_{\{ f<0 \}}^{} f \, d\mu \leq 0 $$which means $\mu(\{ f<0 \})=0$. Further, by $u:=\chi_{\{ f\geq 1 \}}$, we get: $$0\geq\int_{\{ f\geq 1 \}}^{}\underbrace{ (1-f) }_{ \leq 0 }  \, d\nu=\int_{\{ f\geq 1 \}}^{}f  \, d\mu  \geq \mu(\{ f\geq 1 \})$$Therefore, $\mu(\{ f\geq 1 \})=0$ and for $\mu$-a.e. $x$, $0\leq f(x)<1$. As $\nu\ll \mu$, we have that $f\in L^\infty(X,\lambda)$. 
>    
>    Let's define $\rho_{n}=1+f+f^{2}+\dots+f^n$. Then, $\rho_{n}\in L^\infty(X,\lambda)$ and for any $E\in \Sigma$, we can use $u:=\rho_{n}\chi_{E}$ to see that: $$\int_{E}^{} (1-f^{n+1}) \, d\nu=\int_{E}^{} (f+f^{2}+\dots+f^{n+1}) \, d\mu  $$ Now, we have that $1-f^{n+1}\leq 1-f^{n+2}$ for all $n$ $\nu$-a.e and $\sum_{k=1}^{n}f^k\leq\sum_{k=1}^{n+1}f^k$ for all $n$ $\mu$-a.e. Therefore, $$\begin{align}\nu(E)&=\int_{E}^{} \lim_{ n \to \infty } (1-f^{n+1}) \, d\nu\\&=\lim_{ n \to \infty } \int_{E}^{} (f+f^{2}+\dots+f^{n+1}) \, d\mu \\&=\int_{E}^{}\sum_{k=1}^{\infty}f^k  \, d\mu \\&=\int_{E}^{} \frac{f}{1-f} \, d\mu \end{align} $$By defining $\rho:= \frac{f}{1-f}$, we have the statement.
> 2. **Proving the uniqueness**: Suppose there are two functions $\rho_{1},\rho_{2}$ and define $E_{1}:=\{ \rho_{1}(x)>\rho_{2}(x) \}$. Then, $$0=\nu(E_{1})-\nu(E_{1})=\int_{E_{1}}^{} (\rho_{1}-\rho_{2}) \, d\mu $$Therefore, $\mu(E_{1})=0$ By symmetry, we have that $\rho_{1}=\rho_{2}$ $\mu$-a.e.
---
