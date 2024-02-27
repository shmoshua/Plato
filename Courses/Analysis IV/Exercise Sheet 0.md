#Series #Analysis 

> [!definition] Problem 1: Inclusion between Lp spaces.
> For $L^p$ spaces:
> 1. is it true that if $f\in L^1(\mathbb{R}^n)$ then $f\in L^2(\mathbb{R}^n)$?
> 2. is it true that if $f\in \ell^1(\mathbb{N})$ then $f\in \ell^2(\mathbb{N})$?
> 3. Give an example of a function that is $L^{99}(0,1)$ but not $L^{100}(0,1)$. Could you find one also in $L^{100}(0,1)\backslash L^{99}(0,1)$?

We have:
1. Consider $f(x)= \frac{1}{\sqrt{ x }}\chi_{(0,1]}(x)$. Then, $$\left\| f \right\| _{1}=\int_{0}^{1}  \frac{1}{\sqrt{ x }} \, dx =2,\quad \left\| f \right\| _{2}=\int_{0}^{1} \frac{1}{x} \, dx=\infty$$
2. Yes. Assume that $\sum_{n=0}^{\infty}\left| f(n) \right|<+\infty$. Then, $\lim_{ n \to \infty }f(n)=0$ and there exists $N\geq 0$ s.t. $\left| f(n) \right|<1$ for all $N\geq n$. Therefore, $\left| f(n) \right|^{2}\leq \left| f(n) \right|$ and $$\sum_{n=0}^{\infty}\left| f(n) \right| ^{2}\leq\sum_{n=0}^{N}\left| f(n) \right| ^{2}+\sum_{n=0}^{\infty}\left| f(n) \right| <+\infty$$
3. Let $f(x)=x^{- 1/100}$. Then, $$\left\| f \right\|_{99}=\int_{0}^{1}  \frac{1}{x^{99/100}}  \, dx =100, \quad \left\| f \right\| _{100}=\int_{0}^{1} \frac{1}{x} \, dx =\infty$$$L^{100}(0,1) \backslash L^{99}(0,1)=\varnothing$ as $\mathcal{L}^1(0,1)=1<+\infty$ and $L^{100}(0,1)\subseteq L^{99}(0,1)$.
---
> [!definition] Problem 2: Exchanging limits and integrals.
> Consider
> 1. Recall that the DCT implies that a collection of measurable functions $f_{n}:\mathbb{R}\to \mathbb{C}$, satisfying $\left| f_{n} \right|\leq g$ for some $g\in L^1(\mathbb{R})$, also satisfies $$\lim_{ n \to \infty } \int_{\mathbb{R}}^{} f_{n}(x) \, dx =\int_{\mathbb{R}}^{} \left( \lim_{ n \to \infty } f_{n}(x) \right)  \, dx $$ whenever the pointwise limit $\lim_{ n \to \infty }f_{n}(x)$ exists a.e. Show, via a counterexample, that the hypothesis $\left| f_{n} \right|\leq g\in L^1(\mathbb{R})$ is necessary. 
> 2. Let $(f_{n})_{n\in\mathbb{N}}$ be a collection of non-negative measurable functions. Is it true that

Consider
1. Let $f_{n}=\chi_{[n,n+1]}$. Then, $\left| f_{n} \right|\leq 1$ where $1\notin L^1(\mathbb{R})$. It follows that:
	$$\lim_{ n \to \infty } \int_{n}^{n+1} 1 \, dx=1\neq 0= \int_{\mathbb{R}}^{} \left( \lim_{ n \to \infty } f_{n}(x) \right) \, dx  $$

---