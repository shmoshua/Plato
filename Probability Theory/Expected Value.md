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
> 3. if $X(\Omega)\subseteq \mathbb{Z}_{\geq 0}$, then $\mathbb{P}(X=0)\leq \frac{\text{Var}(X)}{\mathbb{E}[X^{2}]}$

^d75029

> [!proof]-
> We have that:
> 1. Using Fubini, $$\mathbb{E}[X]=\mathbb{E}\left[ \int_{0}^{\infty} \mathbb{1}_{\{ X\geq x \}} \, dx  \right] =\int_{0}^{\infty}\mathbb{E}[\mathbb{1}_{\{ X\geq x \}}]  \, dx=\int_{0}^{\infty} \mathbb{P}(X\geq x) \, dx  $$
> 2. We have: $$\mathbb{E}[X]=\mathbb{E}\left[ \sum_{k=1}^{\infty}\mathbb{1}_{{\{ X\geq k \}}} \right] =\sum_{k=1}^{\infty}\mathbb{P}(X\geq k)$$
> 3. For any $i,j\geq 1$, we have that: $$\mathbb{P}(X\geq \max\{ i,j \})\mathbb{P}(X\geq 1)\geq \mathbb{P}(X\geq i)\mathbb{P}(X\geq j)$$Therefore, $$\mathbb{E}[X^{2}]\mathbb{P}(X\geq 1)=\sum_{i,j=1}^{\infty}\mathbb{P}(X\geq  \max\{ i,j \})\mathbb{P}(X\geq 1) \geq \sum_{i,j=1}^{\infty}\mathbb{P}(X\geq i)\mathbb{P}(X\geq j)=\mathbb{E}[X]^2$$Hence, $$\mathbb{P}(X=0)= 1-\mathbb{P}(X\geq 1)\leq 1-\frac{\mathbb{E}[X]^{2}}{\mathbb{E}[X^{2}]}=\frac{\text{Var}(X)}{\mathbb{E}[X^{2}]}$$

^36878b

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

^0e786a

> [!proof]-
> We have:
> 1.
> 9. For 9, we have: $$\mathbb{P}(\left| X-\mathbb{E}[X] \right| \geq a )=\mathbb{P}((X-\mathbb{E}[X])^{2}\geq a^{2} )\leq \frac{\text{Var}(X)}{a^{2}}$$
> 10. First assume that $\mathbb{E}[X] = 0$. Since $e^{\lambda x}$ is a convex function in $x$, we have that for all $x\in[a,b]$: $$e^{\lambda x}= e^{\lambda(\frac{b-x}{b-a}a+\frac{x-a}{b-a}b)}\leq\frac{b-x}{b-a}e^{\lambda a}+\frac{x-a}{b-a}e^{\lambda b}$$Therefore, $$\begin{align}\mathbb{E}[e^{\lambda X} ]&\leq \frac{b-\mathbb{E}[X]}{b-a}e^{\lambda a}+\frac{\mathbb{E}[X]-a}{b-a}e^{\lambda b}\\&= \frac{b}{b-a}e^{\lambda a}-\frac{a}{b-a}e^{\lambda b}\\&=e^{\lambda a}\left( 1+\frac{a-e^{\lambda(b-a)}a}{b-a} \right) \\&=e^{L(\lambda(b-a))}\end{align}$$where $L(h)=\frac{ha}{b-a}+\ln\left( 1+ \frac{a-e^ha}{b-a} \right)$. Then, 
> 	1. $L(0)=0$
> 	2. $L'(h)=\frac{a}{b-a}-\frac{1}{1+\frac{a-e^h a}{b-a}}\left( \frac{e^ha}{b-a} \right)=\frac{a}{b-a}-\frac{e^h a}{b-e^h a}=\frac{a}{b-a}+1-\frac{b}{b-e^ha}$ and $L'(0)=0$.
> 	3. $L''(h)=-\frac{abe^h}{(b-e^ha)^{2}}$
> 	
> 	From AM-GM, we have that for all $h$, $$L''(h)=\left( \frac{b}{b-e^ha} \right) \left( -\frac{e^ha}{b-e^ha} \right) \leq \frac{1}{4}$$Then, there exists some $\theta\in[0,1]$ s.t. $$L(h)=L(0)+hL'(0)+\frac{1}{2}h^{2}L''(h\theta)\leq \frac{h^{2}}{8}$$Therefore, $\mathbb{E}[e^{\lambda X}]\leq \exp \left( \frac{\lambda^{2}(b-a)^{2}}{8} \right)$. 
> 	
> 	Now if $\mathbb{E}[X]$ is arbitrary, then by applying the lemma on $Z:=X-\mathbb{E}[X]$, we have that: $$\mathbb{E}[e^{\lambda (X-\mathbb{E}[X])}]\leq \exp \left(  \frac{\lambda^{2}(b-a)^{2}}{8}\right) $$ and we have that: $$\mathbb{E}[e^{\lambda X}]=\mathbb{E}[e^{\lambda (X-\mathbb{E}[X])}]e^{\lambda \mathbb{E}[X]}\leq e^{\lambda \mathbb{E}[X]}\cdot \exp \left(  \frac{\lambda^{2}(b-a)^{2}}{8}\right) $$
> 	

^f56d8e

---
> [!lemma] Proposition 4
> Let $X:\Omega\to \mathcal{X}$ be a random variable and $g:\mathbb{R}\times \mathcal{X}\to \mathbb{R}$ s.t. $g(\cdot,X)$ is integrable and $g$ is continuously differentiable w.r.t. $t$. 
> 1. if there exists a random variable $Z$ with $\left| \frac{\partial}{\partial t}g(t,X) \right|\leq Z$ almost surely for all $t$ and $\mathbb{E}[Z]<+\infty$. Then, $$\frac{ \partial  }{ \partial t } \mathbb{E}[g(t,X)]=\mathbb{E}\left[ \frac{ \partial  }{ \partial t } g(t,X) \right]$$
> 2. if $f:\mathbb{R}^n\times \mathcal{X}\to \mathbb{R}$ s.t. $f$ is integrable and $f$ is continuously differentiable w.r.t. $t$. If there exists a random variable $Z$ with $\left\| \nabla _{x}f(x,X) \right\|\leq Z$ a.s. for all $x$ and $\mathbb{E}[Z_{i}]<+\infty$. Then, $$\nabla_{x}\mathbb{E}[f(x,X)]=\mathbb{E}[\nabla_{x}f(x,X)]$$

> [!proof]+
> We have that: 
> 1. Notice that: $$\begin{align}\frac{ \partial  }{ \partial t } \mathbb{E}[g(t,X)]&=\lim_{ h \to 0 } \frac{\mathbb{E}[g(t+h,X)]-\mathbb{E}[g(t,X)]}{h}\\&=\lim_{ h \to 0 } \mathbb{E}\left[ \frac{g(t+h,X)-g(t,X)}{h} \right]\\&=\lim_{ h \to 0 } \mathbb{E}\left[ \frac{ \partial  }{ \partial t } g(\tau(h),X) \right] \end{align}$$where $\tau(h)\in (t,t+h)$ exists because of mean value theorem. Then, by DCT, $$\frac{ \partial  }{ \partial t } \mathbb{E}[g(t,X)]=\mathbb{E}\left[ \frac{ \partial  }{ \partial t } g(t,X) \right]$$
> 2. We have that from 1: $$\begin{align}\nabla_{x}\mathbb{E}[f(x,X)]&=(\partial_{1}\mathbb{E}[f(x,X)],\dots,\partial_{n}\mathbb{E}[f(x,X)])\\&=(\mathbb{E}[\partial_{1}f(x,X)],\dots,\mathbb{E}[\partial_{n}f(x,X)])\\&=\mathbb{E}[\nabla_{x}f(x,X)]\end{align} $$