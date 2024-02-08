#Series #MeasureTheory 

##### Exercise 8.1
Assume that $f$ is bounded, i.e. for all $x\in \Omega$, $f(x)<+\infty$. Therefore, 
$$\sup_{x\in \mathbb{R}}\left| f(x)-f_{k}(x) \right| =\sum_{j=k+1}^{\infty} \frac{1}{j}\chi_{A_{j}}(x)$$

---
##### Exercise 8.2
Let $f:\Omega\to \overline{\mathbb{R}}$. We define $f^+:=\max(0,f)$ and $f^-:=\max(0,-f)$. Then, $f^+,f^-:\Omega\to[0,+\infty]$ and by [[Measurable Function|Theorem 2.2.6]], there exists measurable sets $\{ A_{k} \}_{k}\subseteq\Omega$ and $\{ B_{k} \}_{k}\subseteq\Omega$ s.t. $$f^+= \sum_{k=1}^{\infty} \frac{1}{k}\chi_{A_{k}},\quad f^-=\sum_{k=1}^{\infty} \frac{1}{k}\chi_{B_{k}}$$
Then, let $C_{2j-1}:=A_{k} \backslash B_{k}$ and $C_{2j}:= B_{k} \backslash A_{k}$. We can then write: $$f=f^+ - f^-=\sum_{\ell=1}^{\infty}d_{\ell}\chi_{C_{\ell}}$$where $d_{2j-1}= 1/j$ and $d_{2j}= -1/j$. It follows that:
$$
f_{k}=\sum_{\ell=1}^{}
$$

Then, we define:
$$f_{k}=\sum_{j=1}^{k} \frac{1}{j}\chi_{A_{j}}-\sum_{j=1}^{k} \frac{1}{j} \chi_{B_{j}}=\sum_{j=1}^{k} \frac{1}{j}(\chi_{A_{j}}-\chi_{B_{j}})$$It follows that:
$$\left| f_{k}(x) \right| =\left| \sum_{j=1}^{k} \frac{1}{j}(\chi_{A_{j}}(x)-\chi_{B_{j}}(x)) \right| $$

---

##### Exercise 8.3
1. **True**. Follows from Theorem 2.4.4
2. **True**. We define $g_{n}(x)=n\left( f\left( x+\frac{1}{n} \right)-f(x) \right)$ for $n\geq 1$. As $f$ is continuous, it is $\mathcal{L}^1$-measurable and $g_{n}$ is $\mu$-measurable for all $n$. This implies that $f'(x)=\lim_{ n \to \infty }g_{n}(x)$ is measurable.
3. **False**. Assume that we have $f:\Omega\to(0,\infty)$ s.t. $f$ is not measurable but $g:=\sqrt{ f }$ is measurable. But, $g^{2}=f$ is a measurable function, which is a contradiction.
4. **True**. We first have $\mu([a,b])=b-a<+\infty$. Furthermore, at any $x\in [a,b]$, $\lim_{ n \to \infty }f_{n}(x)=\lim_{ n \to \infty }e^{-n(1-\sin(x))}=0$. Therefore, $f_{n}\to f\equiv0$ $\mu$-a.e and by the Theorem, $f_{n}\overset{ \mu }{ \to }f$.
---
##### Exercise 8.4
Define $A_{k}:=\left\{ x\in \mathbb{R}^n:|f_{k}(x)-f_{k+1}(x)|\leq  \frac{1}{2^k}  \right\}$. Then, $\mathcal{L}^n(A^c_{k})< \frac{1}{2^k}$ for all $k\in \mathbb{N}$. Now let, $B_{\ell}:=\bigcap_{k\geq \ell}^{}A_{k}$. Then, 
$$ \mathcal{L}^n(B^c_{\ell})\leq \sum_{k\geq \ell}^{}\mathcal{L}^n(A_{k}^c)<\sum_{k\geq \ell}^{} \frac{1}{2^k}=\frac{1}{2^{\ell-1}}$$Then, $$\mathcal{L}^n\left( \left( \bigcup_{\ell=1}^{\infty}B_{\ell} \right)^c \right)=\mathcal{L}^n\left( \bigcap_{\ell=1}^{\infty}B^c_{\ell} \right)=\lim_{ \ell \to \infty } \mathcal{L}^n(B^c_{\ell})\leq 0 $$
For $x\in B_{\ell}$, $\ell<m<n\in \mathbb{N}$, we have: $$\left| f_{m}(x)-f_{n}(x) \right| \leq \sum_{k=m}^{n-1}\left| f_{k}(x)-f_{k+1}(x) \right|\leq \sum_{k=m}^{n-1} \frac{1}{2^k}\leq \frac{1}{2^{m-1}}$$Therefore, $f_{k}(x)$ is a Cauchy sequence in $B_{\ell}$ and $\lim_{ k \to \infty }f_{k}(x)$ exists. This holds for all $x$ $\mathcal{L}^n$-a.e.

---
##### Exercise 8.5
1. Suppose $f_{k}$ doesn't converge to $f$ in measure. Then, there exists $\varepsilon>0$ s.t. $$\lim_{ k \to \infty } \mu(\{ x\in \Omega:\left| f(x)-f_{k}(x) \right| >\varepsilon \})>0$$ Then, 
---
##### Exercise 8.6
---
##### Exercise 8.7
