#Definition #MeasureTheory 

> [!definition]
> Let $\mu$ be a [[Positive Measure|measure]] on $\mathbb{R}^n$, $\Omega \subseteq \mathbb{R}^n$ [[Measurable Set|$\mu$-measurable]]. Further, let $f,f_{k}:\Omega \to \overline{\mathbb{R}}$ be [[Measurable Function|$\mu$-measurable]] and $\left| f \right|<+\infty$ $\mu$-a.e.
> 
> Then, ***$(f_{k})_{k}$ converges in measure $\mu$ to $f$***, i.e. $f_{k} \overset{ \mu }{ \to }f$ as $k\to \infty$, if for all $\varepsilon>0$, $$\lim_{ k \to \infty } \mu(\{ x\in \Omega:\left| f(x)-f_{k}(x) \right| >\varepsilon \})=0$$

---
##### Properties
> [!lemma] Theorem 1
> Let $\mu(\Omega)<+\infty$. If $f_{k}\to f$ $\mu$-a.e. then $f_{k}\overset{ \mu }{ \to }f$.

> [!proof]-
> From [[Measurable Function|Egoroff's Theorem]], for any $\delta>0$, we have a $\mu$-measurable set $A_{\delta}\subseteq\Omega$ s.t. 
> 1. $\mu(\Omega \backslash A_{\delta})<\delta$ and
> 2. for all $\varepsilon>0$, there exists $n_{\varepsilon}>0$ s.t. $$\sup_{x\in A_{\delta}}\left| f_{k}(x)-f(x) \right| <\varepsilon$$ for all $k\geq k_{\varepsilon}$.
>    
> Therefore, for $k\geq k_{\varepsilon}$, $$\{ x\in \Omega:\left| f_{k}(x)-f(x) \right| >\varepsilon \}\subseteq \Omega \backslash A_{\delta}$$and it follows that:$$\lim_{ k \to \infty } \mu (\{ x\in \Omega:\left| f_{k}(x)-f(x) \right| >\varepsilon \})\leq \mu(\Omega \backslash A_{\delta})<\delta$$

- **Remark**: This does not hold if $\mu(\Omega)=+\infty$.  **Example**: $\Omega=\mathbb{R}$, $f_{k}(x)=\chi_{[-k,k]}(x)$  and $\mu=\mathcal{L}^1$.  Then, $f_{k}\to f \equiv 1$ in $\mathbb{R}$, but for all $\varepsilon>0$, $$\mathcal{L}^1(\{ x\in \mathbb{R}:\left| f_{k}-1 \right| >\varepsilon \})=\mathcal{L}^1([-k,k]^c)=\infty$$
- **Remark**: The converse of this theorem does not hold. 
  **Example**: $\Omega=[0,1)$ and $\mu=\mathcal{L}^1$, $f_{k}=\chi_{\left[  \frac{k-2^n}{2^n}, \frac{k+1-2^n}{2^n} \right)}$ where $n$ is chosen s.t. $2^n\leq k <2^{n+1}$. Then, $$\mu(\{ x\in [0,1]:f_{k}(x)>0 \})=\frac{1}{2^n}< \frac{2}{k}\to{0}$$Therefore, $f_{k}\overset{ \mu }{ \to }f\equiv 0$. But for every $x\in \Omega$, $n\in \mathbb{N}$, $k\in \mathbb{N}$, we have: $$f_{k}(x)=\begin{cases}1&k=\lfloor 2^n x\rfloor+2^n\\0&\text{for }k\in\{ 2^n+1,\dots,2^{n+1}-1 \}\end{cases}$$  It follows that $f_{k}$ cannot converge to $f$ $\mu$-a.e..
---
> [!lemma] Theorem 2
> Let $f_{k}\overset{ \mu }{ \to }f$. Then, there exists a subsequence $\{ f_{k_{n}} \}_{n}$ which converges to $f$ $\mu$-a.e. as $n\to+\infty$

> [!proof]-
> Since $f_{k}\overset{ \mu }{ \to }f$, for every $n$, there exists $k_{n}$ s.t. for all $k\geq k_{n}:$$$\mu\left( \left\{  x\in \Omega:\left| f_{k}(x)-f(x) \right| > \frac{1}{2^n}  \right\} \right)< \frac{1}{2^n}$$We then define: $$A_{n}=\left\{  x\in \Omega:\left| f_{k_{n}}(x)-f(x) \right| > \frac{1}{2^n}  \right\}$$
> For $h\geq 1$, we also define $E_{h}=\bigcup_{n=h}^{\infty}A_{n}$. Then, by subadditivity: $$\mu(E_{h})\leq \sum_{n=h}^{\infty}\mu(A_{n})<\sum_{n=h}^{\infty} \frac{1}{2^n}=\frac{1}{2^{h-1}}$$
> Let $x\in \Omega \backslash E_{h}$. Then $x \notin A_{n}$ for all $n\geq h$.  Thus, $f_{k_{n}}(x)\to f(x)$ on $\Omega \backslash E_{h}$. If $E=\bigcap_{h=1}^{\infty}E_{h}$, then: $$\mu(E)=\lim_{ h \to \infty } \mu(E_{h})=0$$Therefore, $f_{k_{n}}(x)\to f(x)$ on $\Omega \backslash E$, i.e. $\mu$-a.e.
---
