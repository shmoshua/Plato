 #Definition #Analysis 

> [!definition]
> Let $\mu$ be a translation invariant measure in $\mathbb{R}^n$ and let $f,g: \mathbb{R}^n\to \mathbb{C}$ be measurable functions. For a.e. $x\in \mathbb{R}^n$ s.t. $t\mapsto f(x-t)g(t)$ is in $L^1(\mathbb{R}^n)$, the ***convolution*** of $f,g$ is defined as:$$(f*g)(x)=\int_{\mathbb{R}^n}^{} f(x-t)g(t) \, d\mu(t) $$
- **Remark**: Convolution is commutative: $(f*g)=(g*f)$
---
##### Properties
> [!lemma] Lemma 1
> Let $f:\mathbb{R}^n\to \overline{\mathbb{R}}$ be $\mathcal{L}^n$-measurable. Then, the function: $$F(x,y):=f(x-y)$$is $\mathcal{L}^{2n}$-measurable.

> [!proof]-
> We get: $$F^{-1}[-\infty,a)=\{ (x,y):f(x-y)<a \}=\{ (x,x-z):f(z)<a \}=T[\mathbb{R}^n\times \{ z:f(z)<a \}]$$with $T(x,z)=(x,x-z)$. As $T$ is Lipschitz, by [[Lebesgue Measure|Lemma 12]], it is measurable.
---
> [!lemma] Theorem 2
> Let $1\leq p\leq\infty$. 
> 1. for $f\in L^1(\mathbb{R}^n)$ and $g\in L^p(\mathbb{R}^n)$, $t\mapsto f(x-t)g(t)\in L^1(\mathbb{R}^n)$ for a.e. $x\in \mathbb{R}^n$ and: $$\left\| f*g \right\|_{p}\leq \left\| f \right\| _{1}\left\| g \right\| _{p}$$
> 2. for $r,q$ s.t. $p\leq q\leq r\leq+\infty$ and $1+\frac{1}{r}=\frac{1}{p}+\frac{1}{q}$, $f\in L^p(\mathbb{R}^n)$ and $g\in L^q(\mathbb{R}^n)$,$t\mapsto f(x-t)g(t)\in L^1(\mathbb{R}^n)$ for a.e. $x\in \mathbb{R}^n$ and $f*g\in L^r(\mathbb{R}^n)$ with: $$\left\| f*g \right\|_{r}\leq \left\| f \right\| _{p}\left\| g \right\| _{q}$$

> [!proof]-
> We show for $p=1$ first. 
> 1. Suppose $f,g\geq 0$. Then, $F:(x,y)\mapsto f(x-y)g(y)$ is $\mu$-integrable. By [[Product Measure|Tonelli's theorem]],  $F$ is $\mu$-summable if and only if one of the following integrals exists and is finite: $$\begin{align}\left\| f*g \right\| _{1}&=\int_{\mathbb{R}^n}\left( \int_{\mathbb{R}^n}f(x-t)g(t)\, d\mu(t)  \right)  \, d\mu(x)\\&=\int_{\mathbb{R}^n}\left( \int_{\mathbb{R}^n}f(x-t)g(t)\, d\mu(x)  \right)  \, d\mu(t)\\&=\int_{\mathbb{R}^n}g(t)\left( \int_{\mathbb{R}^n}f(x-t)\, d\mu(x)  \right)\, d\mu(t)\\&=\left\| f \right\| _{1}\left\| g \right\| _{1}<+\infty\end{align} $$
> 2. For general $f,g$: we have: $\left| F(x,y) \right|=\left| f(x-t) \right|\left| g(t) \right|\in L^1(\mathbb{R}^{2n})$. Therefore, by Fubini, $\left| f \right|*\left| g \right|\in L^1(\mathbb{R}^n)$ and: $$\begin{align}\left\| f*g \right\| _{1}&=\int_{\mathbb{R}^n}^{} \left| \int_{\mathbb{R}^n}^{} f(x-t)g(t) \, d\mu(t)  \right|  \, d\mu(x) \\&\leq \int_{\mathbb{R}^n}^{} \int_{\mathbb{R}^n}^{} \left| f(x-t) \right| \left| g(t) \right|  \, d\mu(t)  \, d\mu(x)\\&=\left\| \left| f \right| *\left| g \right|  \right\| _{1}\\&=\left\| f \right\| _{1}\left\| g \right\| _{1} \end{align}$$
> 3. Let now $1<p<+\infty$ with conjugate $q$. Then, $$\begin{align}\int_{\mathbb{R}^n}^{} \left| f*g \right| ^p \, d\mu&=\int_{\mathbb{R}^n}^{} \left| \int_{\mathbb{R}^n}^{} f(x-t)g(t) \, d\mu(t)  \right|^p  \, d\mu(x)  \\&\leq\int_{\mathbb{R}^n}^{} \left(\int_{\mathbb{R}^n}^{} \left| f(x-t) \right| ^{1/q}\left| f(x-t) \right| ^{1/p}\left| g(t) \right|  \, d\mu(t)  \right)^p  \, d\mu(x)  \end{align}$$We have that $g^p\in L^1(\mathbb{R}^n)$ and from $p=1$, it follows that for a.e. $x\in \mathbb{R}^n$: $t\mapsto \left| f(x-t) \right|\left| g(t) \right|^p$ is in $L^1(\mathbb{R}^n)$. Therefore, $$t\mapsto \left| f(x-t) \right| ^{1/p}\left| g(t) \right| \in L^p(\mathbb{R}^n)$$Moreover, $t\mapsto \left| f(x-t) \right|^{1/q}\in L^q(\mathbb{R}^n)$. Therefore, by [[Lp Space|Hölder's inequality]], $$\left| f(x-t) \right| \left| g(t) \right| =\left| f(x-t) \right| ^{1/q}\left| f(x-t) \right| ^{1/p}\left| g(t) \right|\in L^1(\mathbb{R}^n) $$Now, we have: $$\begin{align}\int_{\mathbb{R}^n}^{} \left| f*g \right| ^p \, d\mu&=\int_{\mathbb{R}^n}^{} \left| \int_{\mathbb{R}^n}^{} f(x-t)g(t) \, d\mu(t)  \right|^p  \, d\mu(x)  \\&\leq\int_{\mathbb{R}^n}^{} \left(\int_{\mathbb{R}^n}^{} \underbrace{ \left| f(x-t) \right| ^{1/q} }_{ \in L^q }\underbrace{ \left| f(x-t) \right| ^{1/p}\left| g(t) \right| }_{ \in L^p }  \, d\mu(t)  \right)^p  \, d\mu(x) \\&\leq \int_{\mathbb{R}^n}^{} \left( \int_{\mathbb{R}^n}^{} \left| f(x-t) \right| \, dx  \right) ^{p/q}\left( \int_{\mathbb{R}^n}^{} \left| f(x-t) \right| \left| g(t) \right| ^p \, d\mu(t)  \right)  \, d\mu(x)\\&=\left\| f \right\| ^{p/q}_{1}\left\|  \left| f \right| *\left| g \right| ^p\right\|_{1}   \\&\leq \left\| f \right\| _{1}^{p/q+1}\left\| g \right\| _{p}^p\end{align}$$Therefore, $\left\| f*g \right\|_{p}\leq \left\| f \right\|_{1}\left\| g \right\|_{p}$.
> 4. For $p=\infty$, we have: $$\begin{align}\left| (f*g)(x) \right|&=\left| \int_{\mathbb{R}^n}^{} f(x-t)g(t) \, d\mu(t)  \right| \\&\leq \int_{\mathbb{R}^n}^{} \left| f(x-t)g(t) \right|  \, d\mu(t) \\&\leq \left\| f \right\| _{1}\left\| g \right\| _{\infty}\end{align} $$Therefore, $\left\| f*g \right\|_{\infty}\leq \left\| f \right\|_{1}\left\| g \right\|_{\infty}$.
> 
> For 2, 
> 1. If $r=\infty$, we have: $$\begin{align}\left| (f*g)(x) \right|& \leq \int_{\mathbb{R}^n}^{} \left| f(x-t) \right| \left| g(t) \right|  \, d\mu(t)\\& \leq \left\| f \right\| _{p}\left\| g \right\| _{q}\end{align}$$
> 2. If $p=1$, we have proven in part 1.
> 3. Assume $1<p\leq q<r<+\infty$. Then, $$\begin{align}\int_{\mathbb{R}^n}^{} \left| f(x-t) \right| \left| g(t) \right|  \, d\mu(t)&=\int_{\mathbb{R}^n}^{}\underbrace{  \left| f(x-t) \right| ^{1-p/r} }_{ L^s }\underbrace{ \left| g(t) \right| ^{1-q/r} }_{ L^t }\underbrace{ \left| f(x-t) \right| ^{p/r}\left| g(t) \right| ^{q/r} }_{ L^r } \, d\mu(t) \\&\leq \left\| f \right\| _{p}^{1/s}\left\| g \right\|_{q}^{1/t}\left\| \left| f \right| ^p*\left| g \right| ^q \right\|_{1}^{1/r} \\&\leq   \left\| f \right\| _{p}^{1/s+p/r}\left\| g \right\|_{q}^{1/t+q/r} \end{align}$$with $s= \frac{p}{1-\frac{p}{r}},t= \frac{q}{1-\frac{q}{r}}$. Notice that: $$\frac{1}{r}+\frac{1}{s}+\frac{1}{t}=\frac{1}{r}+\left( \frac{1}{p}-\frac{1}{r} \right)+\left( \frac{1}{q}-\frac{1}{r} \right)=1 $$Therefore, $$\begin{align}\left\| f*g \right\| _{r}&\leq \left( \int_{\mathbb{R}}  \, dx  \right) \end{align}$$
---
> [!lemma] Proposition 3
> Let $f\in C^0_{00}(\mathbb{R}^n)$ and $g\in L^1_{\text{loc}}(\mathbb{R}^n)$. Then, $(f*g)(x)$ is well-defined for every $x\in \mathbb{R}^n$ and $$f*g\in C^0(\mathbb{R}^n)$$

> [!proof]-
> We have that: $$\begin{align}(f*g)(x)&=\int_{\mathbb{R}^n}^{} f(x-t)g(t) \, d\mu(t)\\&=\int_{\mathbb{R}^n}^{} f(z)g(x-z) \, d\mu(z)\\&=\int_{\mathbb{R}^n}^{} f(z)\chi_{\text{supp }f}(z) g(x-z) \, d\mu(z)\\&\leq M\int_{\text{supp }f}^{} \left| g(x-z) \right|  \, d\mu(z) \end{align}$$where $M:=\max_{x\in \text{supp }f}\left| f(x) \right|$.
> 
> Now, let $x_{j}\to x$ and we define: $$K:=\bigcup_{j\geq 1}^{}(x_{j}-\text{supp }f)$$ We notice that $\overline{K}$ is compact. Then, for any $y\in \mathbb{R}^n$ and $j\geq 1$, let $z\notin K$. Then, $$\begin{align}&z\notin \bigcup_{j\geq 1}^{}(x_{j}-\text{supp }f)\\\implies&z\notin x_{j}-\text{supp }f,\quad \forall j\geq 1\\\implies&x_{j}-z\notin \text{supp }f,\quad \forall j\geq 1\end{align}$$Therefore, for $\tilde{f}(y):=f(x_{j}-y)$, $\text{supp }f(x_{j}-y)\subseteq K$$$\left| f(x_{h}-t)g(t) \right| \leq$$
> 
> 
> $$\begin{align}(f*g)(x_{j})&=\int_{\mathbb{R}^n}^{} f(x_{j}-t)g(t) \, d\mu(t) \end{align}$$
---
> [!lemma] Proposition 4
> If $f\in C_{00}^\infty(\mathbb{R}^n)$ and $g\in L^p(\mathbb{R}^n)$, then: 
> 1. $f*g\in C^{\infty}(\mathbb{R}^n)$ and 
> 2. $D^\alpha(f*g)=(D^\alpha f)*g$

> [!proof]+
> > [!lemma]
> > Let $(X,\Sigma,\mu)$ be a $\sigma$-finite measure space, $D\subseteq \mathbb{R}^n$ an open set and $f:D\times X \to \mathbb{C}$ a measurable function s.t. 
> > 1. $f(\cdot,y)\in C^1(D)$ for all $y\in Y$
> > 2. $f(x,\cdot)\in L^1(X,\mu )$ for all $x\in X$
> > 3. $\frac{ \partial f }{ \partial x_{i} }(x,\cdot)\in L^1(X,\mu)$ for all $x\in X$ and $i\in[n]$
> > 4. $G_{i}: x\mapsto \int_{X}^{} \frac{ \partial f }{ \partial x_{i} }(x,y) \, d\mu(y)\in C^0(D)$ for all $i\in[n]$
> > 
> > Then,
> > 1.  $F:x\mapsto \int_{X}^{} f(x,y) \, d\mu(y)\in C^1(D)$
> > 2.  $\frac{ \partial F }{ \partial x_{i} }=G_{i}$ for all $i\in[n]$.
>
> > [!proof]+
> > We have: $$\begin{align}\frac{F(x+te_{i})-F(x)}{t}&=\frac{1}{t}\int_X f(x+te_{i},y)-f(x,y)d\mu(y)\\&=\int_X \frac{f(x+te_{i},y)-f(x,y)}{t}d\mu(y)\end{align}$$As $\left| f(x+te_{i},y)-f(x,y) \right|\leq \left| f(x+te_{i},y) \right|+\left| f(x,y) \right|$, using [[Summable Function|DCT]], $$\begin{align}\lim_{ t \to 0 }\frac{F(x+te_{i})-F(x)}{t}&=\lim_{ t \to 0 }\int_X \frac{f(x+te_{i},y)-f(x,y)}{t}d\mu(y)\\&=\int_X \lim_{ t \to 0 }\frac{f(x+te_{i},y)-f(x,y)}{t}d\mu(y)\\&=\int_{X}^{} \frac{ \partial f }{ \partial x_{i} } (x,y) \, d\mu(y) \end{align} $$
> 
> We want to apply this lemma to 
> 1. $X=\mathbb{R}^n$, $D=B_{<r}(0)$ and
> 1. $h(x,t):=f(x-t)g(t)$ which is measurable.
> 
> Let $r_{1}>0$ s.t. $\text{supp }f\subseteq B_{<r_{1}}(0)$. Then, for all $x\in D$: $$(f*g)(x)=\int_{\mathbb{R}^n}^{} f(x-t)\chi_{B_{<r+r'}(0)}(t)g(t) \, dm(t) $$Now consider $h(x,t):=f(x-t)\chi_{B_{<r+r'}(0)}(t)g(t)$ and observe that $\chi_{B_{<r+r'}(0)}\cdot g\in L^1(\mathbb{R}^n)$ as $B_{<r+r'}(0)$ is finite. Therefore, 1, 2 and 3 from the Lemma are satisfied. 
> 
> In addition:$$G_{j}(x) =\int_{\mathbb{R}^n}^{} \frac{ \partial f }{ \partial x_{j} }(x-t) \chi_{B_{<r+r'}(0)}(t) g(t)\, d\mu(t)= \frac{ \partial f }{ \partial x_{j} } *(\chi_{B_{<r+r'}(0)}\cdot g)$$is continuous by Proposition 3. As $D$ is arbitrary, $$f*g\in C^1(\mathbb{R}^n)$$and $\frac{ \partial }{ \partial x_{j} }(f*g)=\frac{ \partial f }{ \partial x_{j} }*g$. As $\frac{ \partial f }{ \partial x_{j} }\in C^{\infty}_{00}(\mathbb{R}^n)$, with recurrence we can show that $f*g\in C^\infty(\mathbb{R}^n)$.
---
> [!lemma] Proposition 5
> The convolution on $L^1(\mathbb{R}^n)$, i.e. $$\begin{array}{cccc} &{L^1(\mathbb{R}^n)\times L^1(\mathbb{R}^n)}&\to&{L^1(\mathbb{R}^n)}\\&{(f,g)} &\mapsto & {f*g} \end{array}{}$$defines a [[C*-algebra]] with no identity, i.e. there exists no $\delta\in L^1(\mathbb{R}^n)$ s.t. $$\delta*f=f$$for all $f\in L^1(\mathbb{R}^n)$.

> [!proof]-
> Assume such $\delta\in L^1(\mathbb{R}^n)$ exists. Using [[Fourier transform]], we get that: $$\widehat{\delta}\cdot \widehat{f}=\widehat{f}$$where $\widehat{\delta}\in C_{0}(\mathbb{R}^n)$. As $C^\infty_{00}(\mathbb{R}^n)\subseteq \mathcal{F}[L^1(\mathbb{R}^n)]$, there exists $\widehat{\delta}\in C_{0}(\mathbb{R}^n)$ s.t. $\widehat{\delta}\cdot\varphi=\varphi$ for all $\varphi\in C^\infty_{00}(\mathbb{R}^n)$. This means that $\widehat{\delta}=1$ as we can have a bump function around every point. This is a contradiction to $\widehat{\delta}\in C_{0}(\mathbb{R}^n)$.
---