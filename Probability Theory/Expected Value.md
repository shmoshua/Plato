#Definition #ProbabilityTheory 

> [!definition]
> Let $(\Omega,\mathcal{A},\mathbb{P})$ be a [[probability space]] and $X$ a [[random variable]]. The ***expected value*** of $X$ is given as: $$\mathbb{E}[X]:=\int_{\Omega}^{} X \, d\mathbb{P} $$where $X$ is positive or $X$ is real or complex and $\int_{\Omega}^{} \left| X \right| \, d\mathbb{P}<+\infty$.

- **Remark**: This can be extended to when $X\in \mathbb{R}^d$ or $X\in \mathbb{C}^d$ by taking the expectation component-wise.
---
##### Properties
> [!lemma] Proposition 1 (Tailsum Formula)
> Let $X:\Omega\to[0,+\infty]$ be a random variable. Then, 
> 1. $\mathbb{E}[X]=\int_{0}^{\infty} \mathbb{P}(X\geq x) \, dx$
> 2. if $X(\Omega)\subseteq \mathbb{Z}_{\geq 0}$, then $\mathbb{E}[X]=\sum_{k=1}^{\infty}\mathbb{P}(X\geq k)$

> [!proof]-
> We have that:
> 1. Using Fubini, $$\mathbb{E}[X]=\mathbb{E}\left[ \int_{0}^{\infty} \mathbb{1}_{\{ X\geq x \}} \, dx  \right] =\int_{0}^{\infty}\mathbb{E}[\mathbb{1}_{\{ X\geq x \}}]  \, dx=\int_{0}^{\infty} \mathbb{P}(X\geq x) \, dx  $$
> 2. We have: $$\mathbb{E}[X]=\mathbb{E}\left[ \sum_{k=1}^{\infty}\mathbb{1}_{{\{ X\geq k \}}} \right] =\sum_{k=1}^{\infty}\mathbb{P}(X\geq k)$$
---
> [!lemma] Proposition 2 
> Let $X:\Omega\to (E,\mathcal{E})$ be a random variable. For every measurable function $f:E\to[0,+\infty]$, $$\mathbb{E}[f(X)]=\int_{E}^{} f\, d\mathbb{P}_{X} $$
- **Remark**: This is equivalent to the expectation of $f$ as a random variable of a pushforward probability space $(E,\mathcal{E},\mathbb{P}_{X})$. 
- **Remark**: This can be extended to real- or complex-valued $f$ if $\mathbb{E}[\left| f(X) \right|]<+\infty$. 
---
> [!lemma] Theorem 3 (Extension of Measure Theory Theorems)
> We have:
> 1. for $X:\Omega\to[0,+\infty]$, 
> 	1. if $\mathbb{E}[X]<+\infty$ then $X<+\infty$ almost surely.
> 	2. if $\mathbb{E}[X]=0$ then $X=0$ almost surely.
> 2. [[Lebesgue Integral|MCT]]: for $(X_{n})_{n}$ where $X_{n}:\Omega\to[0,+\infty]$ and $X_{1}\leq X_{2}\leq\dots$ almost surely,
> 	1. if for $X:\Omega\to[0,+\infty]$, $X=\lim_{ n \to \infty }X_{n}$ almost surely, then $\lim_{ n \to \infty }\mathbb{E}[X_{n}]=\mathbb{E}[X]$.
> 3. [[Lebesgue Integral|Fatou's Lemma]]: for $(X_{n})_{n}$ where $X_{n}:\Omega\to[0,+\infty]$, $$\mathbb{E}[\liminf_{ n \to \infty } X_{n}]\leq \liminf_{ n \to \infty } \mathbb{E}[X_{n}]$$
> 4. [[Summable Function|DCT]]: for $(X_{n})_{n}$ where $X_{n}:\Omega\to \mathbb{R}$ and $X,Z:\Omega\to \mathbb{R}$ s.t. $\mathbb{E}[Z]<+\infty$ and $\left| X_{n} \right|\leq Z$, 
> 	1. if $X_{n}\to X$ almost surely, then$$\lim_{ n \to \infty } \mathbb{E}[\left| X_{n}-X \right| ]=0,\quad \lim_{ n \to \infty } \mathbb{E}[X_{n}]=\mathbb{E}[X]$$
> 5. [[Lp Space|Hölder's inequality]]: for $X,Y:\Omega\to \mathbb{R}$, and $p,q\in (1,+\infty)$ conjugates, $$\mathbb{E}[\left| XY \right| ]\leq \mathbb{E}[\left| X \right| ^p]^{1/p}\mathbb{E}[\left| Y \right| ^q]^{1/q}$$
> 6. [[Lp Space|Cauchy Schwarz]]: for $X,Y:\Omega\to \mathbb{R}$, $\mathbb{E}[\left| XY \right|]\leq \mathbb{E}[X^2]^{1/2}\mathbb{E}[Y^2]^{1/2}$ and 
> 	1. $\mathbb{E}[\left| X \right|]^{2}\leq \mathbb{E}[X^{2}]$
> 7. **Jensen's inequality**: for $X\in L^1(\Omega,\mathcal{A},\mathbb{P})$ and $f:\mathbb{R}\to \mathbb{R}_{\geq 0}$ convex, $$\mathbb{E}[f(X)]\geq f(\mathbb{E}[X])$$
> 8. **Markov's inequality**: for $X:\Omega\to[0,+\infty]$ and $a>0$: $$\mathbb{P}(X\geq a)\leq \frac{\mathbb{E}[X]}{a}$$
> 9. **Bienaymé-Chebyshev Inequality**: if $X\in L^2(\Omega,\mathcal{A},\mathbb{P})$ and $a>0$, $$\mathbb{P}(\left| X-\mathbb{E}[X] \right| \geq a)\leq \frac{1}{a^{2}}\text{Var}(X)$$
> 10. **Hoeffding's Lemma**: if $X:\Omega\to \mathbb{R}$ with $a\leq X\leq b$ almost surely, then for all $\lambda\in \mathbb{R}$: $$\mathbb{E}[e^{\lambda X}]\leq \exp \left( \lambda \mathbb{E}[X]+\frac{\lambda^{2}(b-a)^{2}}{8} \right) $$

> [!proof]+
> We have:
> 1.
> 9. For 9, we have: $$\mathbb{P}(\left| X-\mathbb{E}[X] \right| \geq a )=\mathbb{P}((X-\mathbb{E}[X])^{2}\geq a^{2} )\leq \frac{\text{Var}(X)}{a^{2}}$$
> 10. First assume that $\mathbb{E}[X] = 0$. Since $e^{\lambda x}$ is a convex function in $x$, we have that for all $x\in[a,b]$: $$e^{\lambda x}= e^{\lambda(\frac{b-x}{b-a}a+\frac{x-a}{b-a}b)}\leq\frac{b-x}{b-a}e^{\lambda a}+\frac{x-a}{b-a}e^{\lambda b}$$Therefore, $$\begin{align}\mathbb{E}[e^{\lambda X} ]&\leq \frac{b-\mathbb{E}[X]}{b-a}e^{\lambda a}+\frac{\mathbb{E}[X]-a}{b-a}e^{\lambda b}\\&= \frac{b}{b-a}e^{\lambda a}-\frac{a}{b-a}e^{\lambda b}\\&=e^{\lambda a}\left( 1+\frac{a-e^{\lambda(b-a)}a}{b-a} \right) \\&=e^{L(\lambda(b-a))}\end{align}$$where $L(h)=\frac{ha}{b-a}+\ln\left( 1+ \frac{a-e^ha}{b-a} \right)$. Then, 
> 	1. $L(0)=0$
> 	2. $L'(h)=\frac{a}{b-a}+\frac{1}{1+\frac{a-e^h a}{b-a}}$
> 	
---
