#Definition #MeasureTheory 

> [!definition]
> Let $\mu$ be a [[Positive Measure]] on $X$ and $\nu$ on $Y$. Then, we define the ***product measure*** $\mu \times \nu:\mathcal{P}(X\times Y)\to[0,+\infty]$ as
> $$(\mu \times \nu)(S)=\inf\left\{  \left. \sum_{i=1}^{\infty}\mu(A_{i})\nu(B_{i}) \right| S\subseteq \bigcup_{i=1}^{\infty}A_{i}\times B_{i},A_{i}\subseteq X \ \mu \text{-measurable} ,B_{i}\subseteq Y \ \nu \text{-measurable} \right\}$$for any $S\subseteq X\times Y$.
---
##### Properties
> [!lemma] Proposition 1
> $\mu \times \nu$ is the [[Pre-measure|Carathéodory-Hahn extension]] of the [[pre-measure]]: $\lambda:\mathcal{A}\to[0,+\infty]$ with: $$\lambda(A\times B)=\mu(A)\nu(B)$$for every $\mu$-measurable $A\subseteq X$ and $\nu$-measurable $B\subseteq Y$, where: $$\mathcal{A}=\sigma \left( \left\{ \bigcup_{i=1}^{n}A_{i}\times B_{i}:A_{i},B_{i}\text{ measurable} \right\} \right) $$Especially, $\mu \times \nu$ is a measure.

> [!proof]-
> $\lambda$ is $\sigma$-additive by definition and therefore a pre-measure. 
---
> [!lemma] Theorem 2 (Fubini)
> Let $\mu,\nu$ be [[Radon Measure|Radon measures]] on $X:=\mathbb{R}^k,Y:=\mathbb{R}^\ell$ respectively with $k+\ell=n$. Then, 
> 1. For every $\mu$-measurable $A\subseteq X$ and $\nu$-measurable $B\subseteq Y$, $A\times B$ is $\mu \times \nu$-measurable and: $$(\mu \times \nu)(A\times B)=\mu(A)\nu(B)$$
> 2. For a $(\mu \times \nu)$-measurable set $S\subseteq X\times Y$ with $(\mu \times \nu)(S)<+\infty$, 
> 	 - $S_{y}:=\{ x\in X:(x,y)\in S \}$ is $\mu$-measurable for $\nu$-a.e. $y$. Further, $$y\mapsto \mu(S_{y})=\int_{X}^{} \chi_{S_{y}} \, d\mu $$is $\nu$-summable with: $$\int_{Y}^{} \mu(S_{y}) \, d\nu(y)=\int_{Y}^{} \int_{X}^{} \chi_{S_{y}}(x) \, d\mu(x)  \, d\nu(y)=  (\mu \times \nu)(S)$$
> 	 - $S_{x}:=\{ y\in Y:(x,y)\in S \}$ is $\nu$-measurable for $\mu$-a.e. $x$. Further, $$x\mapsto \nu(S_{x})=\int_{Y}^{} \chi_{S_{x}} \, d\nu $$is $\mu$-summable with: $$\int_{X}^{} \nu(S_{x}) \, d\mu(x)=\int_{X}^{} \int_{Y}^{} \chi_{S_{x}}(y) \, d\nu(y)  \, d\mu(x)=  (\mu \times \nu)(S)$$
> 3. $\mu \times \nu$ is Radon.
> 4. If $f:X\times Y\to \overline{\mathbb{R}}$ is $\mu \times \nu$-summable, 
> 	1. $f_{y}(x):=f(x,y)$ is $\mu$-measurable for $\nu$-a.e. $y$.
> 	2. $f_{x}(y):=f(x,y)$ is $\nu$-measurable for $\mu$-a.e. $x$.
> 	3. $y\mapsto \int_{X}^{} f_{y} \, d\mu=\int_{X}^{} f(x,y) \, d\mu(x)$ is $\nu$-summable.
> 	4. $x\mapsto \int_{Y}^{} f_{x} \, d\nu=\int_{Y}^{} f(x,y) \, d\nu(y)$ is $\mu$-summable.
> 	5. It holds that: $$\begin{align}\int_{X\times Y}^{} f \, d(\mu \times \nu)&=\int_{Y}^{} \left( \int_{X}^{} f(x,y) \, d\mu(x)  \right)  \, d\nu(y) =\int_{X}^{} \left( \int_{Y}^{} f(x,y) \, d\nu(y)  \right)  \, d\mu(x)  \end{align}$$

> [!proof]-
> We define the set: $$\mathcal{F}:=\{ S \subseteq X\times Y:S\text{ satisfies 1 and 2} \}$$ where:
> 1. $S_{y}$ is $\mu$-measurable $\nu$-a.e. $y$.
> 2. $y\mapsto \mu(S_{y})$ is $\nu$-measurable.
> 
> Then, for $S \in \mathcal{F}$, we set: $$\rho(S)=\int_{Y}^{} \mu(S_{y}) \, d\nu(y) =\int_{Y}^{} \left( \int_{X}^{}\chi_{S}(x,y)  \, d\mu(x)  \right)  \, d\nu(y) $$We also denote the sets:
> 1. $\mathcal{P}_{0}:=\{ A\times B:A\subseteq X\ \mu\text{-measurable},B\subseteq Y\ \nu\text{-measurable} \}$
> 2. $\mathcal{P}_{1}:=\left\{  \bigcup_{j=1}^{\infty}S_{j}:S_{j}\in \mathcal{P}_{0}  \right\}$
> 3. $\mathcal{P}_{2}:=\left\{  \bigcap_{j=1}^{\infty}R_{j}:R_{j}\in \mathcal{P}_{1}  \right\}$
>    
> > [!claim] Claim 1
> > $\mathcal{P}_{0},\mathcal{P}_{1},\mathcal{P}_{2}\subseteq \mathcal{F}$
>
> > [!proof]-
> > We have: 
> > 1. $\mathcal{P}_{0}\subseteq \mathcal{F}$:
> >     Let $S=A\times B\in \mathcal{P}_{0}$. Then,  $$S_{y}=\begin{cases}A&y\in B\\\varnothing&y\notin B\end{cases}$$Therefore, $S_{y}$ is $\mu$-measurable for any $y$. Further, $$\mu(S_{y})=\mu(A)\chi_{B}$$It follows that $\mu(A)\chi_{B}$ is $\nu$-measurable and $\rho(S)=\mu(A)\nu(B)$
> > 2. $\mathcal{P}_{1}\subseteq \mathcal{F}$:
> > 	 First, for $A_{1}\times B_{1},A_{2}\times B_{2}\in \mathcal{P}_{0}$, we have that: $$\begin{align}(A_{1}\times B_{1})\cap (A_{2}\times B_{2})&=(A_{1}\cap A_{2})\times(B_{1}\cap B_{2})\in \mathcal{P}_{0}\\(A_{1}\times B_{1})\backslash (A_{2}\times B_{2})&=[(A_{1}\backslash A_{2})\times B_{1}]\cup[(A_{1}\cap A_{2})\times (B_{1} \backslash B_{2})]\end{align}$$Let now $S:=\bigcup_{j=1}^{\infty}S_{j}$, we define: 
> > 	 1. $\tilde{S}_{1}:=S_{1}$
> > 	 2. $\tilde{S}_{2}:=S_{2} \backslash S_{1}$
> > 	 3. $\tilde{S}_{n}:=S_{n} \backslash \bigcup_{k=1}^{n-1}S_{k}$
> > 	    
> > 	 Therefore, $S$ is a countable disjoint union of members of $\mathcal{P}_{0}$. Wlog we can assume that $(S_{j})_{j}$ are mutually disjoint. Then, $$S_{y}=\bigcup_{j=1}^{\infty}S_{j,y}=\lim_{ n \to \infty } \bigcup_{j=1}^{n}S_{j,y}$$which is $\mu$-measurable $\nu$-a.e. Further, $$y\mapsto \mu(S_{y})=\lim_{ n \to \infty } \mu \left( \bigcup_{j=1}^{n}S_{j,y} \right) =\lim_{ n \to \infty } \sum_{j=1}^{n}\mu(S_{j,y})$$which is $\nu$-measurable. Moreover, $$\begin{align}\rho(S)&=\int_{Y}^{} \mu(S_{y})\, d\nu(y)\\&=\int_{Y}^{} \sum_{j=1}^{\infty}\mu(S_{j,y}) \, d\nu(y) \\&=\sum_{j=1}^{\infty}\int_{Y}^{} \mu(S_{j,y}) \, d\nu(y)\\&=\sum_{j=1}^{\infty}\rho(S_{j})  \end{align}$$
> >   3. $\mathcal{P}_{2}\subseteq \mathcal{F}$:
> >      We first show that for $R=\bigcap_{i=1}^{\infty}R_{j}$ with $R_{j}\in \mathcal{P}_{1}$ and $\rho(R_{j})<+\infty$, $$\rho(R)=\lim_{ n \to \infty } \rho \left( \bigcap_{i=1}^{n}R_{j} \right) $$Wlog we may assume that $R_{j+1}\subseteq R_{j}$. Then, $$\mu(R_{y})=\lim_{ n \to \infty } \mu\left( \bigcap_{j=1}^{n} R_{j,y}\right)=\lim_{ n \to \infty } \mu(R_{n,y})$$
> >      , $$\begin{align}\rho(R)&=\int_{Y}^{} \mu(R_{y}) \, d\nu(y)\\&=\int_{Y}^{} \lim_{ n \to \infty } \mu(R_{n,y}) \, d\nu(y)\\&=\lim_{ n \to \infty } \int_{Y}^{} \mu(R_{n,y}) \, d\nu(y)\\&=\lim_{ n \to \infty } \rho(R_{n}) \end{align}$$
> ---
> > [!claim] Claim 2
> > For $S\subseteq X\times Y$, $$(\mu \times \nu)(S)=\inf\{ \rho(R):S\subseteq R,R\in \mathcal{P}_{1} \}$$
> 
> > [!proof]-
> > We first observe that if $S\subseteq R:=\bigcup_{i=1}^{\infty}A_{i}\times B_{i}$, then: $$\rho(R)\leq \sum_{i=1}^{\infty}\rho(A_{i}\times B_{i})=\sum_{i=1}^{\infty}\mu(A_{i})\nu(B_{i})$$Therefore, $$\inf\{ \rho(R):S\subseteq R,R\in \mathcal{P}_{1} \}\leq (\mu \times \nu)(S)$$Moreover, there exists a disjoint sequence $\{ A_{j}'\times B'_{j} \}_{j}\subseteq \mathcal{P}_{0}$ s.t. $$R=\bigcup_{j=0}^{\infty}(A'_{j}\times B'_{j})$$Therefore, $$\rho(R)=\sum_{j=0}^{\infty}\mu(A'_{j})\nu(B'_{j})\geq (\mu \times \nu)(S)$$
> ---
> Therefore, let $A\times B\in \mathcal{P}_{0}$. Then, $\rho(A\times B)=\mu(A)\nu(B)$ and we have: $$(\mu \times \nu)(A\times B)\leq \rho(A\times B)=\mu(A)\nu(B)\leq \rho(R)\leq (\mu \times \nu)(A\times B)$$Then, for $T\subseteq X\times Y$, there exists $R\in \mathcal{P}_{1}$ s.t. $T\subseteq R$ and: $$\begin{align}(\mu\times \nu)(T \backslash(A\times B))+(\mu\times \nu)(T \cap(A\times B))&\leq \rho(R \backslash (A\times B))+\rho(R \cap (A\times B))\\&=\rho(R)\\&\leq(\mu \times \nu) (T)\end{align}$$by Claim 2. This proves that $A\times B$ is $(\mu \times \nu)$-measurable.
> > [!claim] Claim 3
> > For each $S\subseteq X\times Y$, there exists $R\subseteq \mathcal{P}_{2}$ s.t. $S\subseteq R$ and $\rho(R)=(\mu \times \nu)(S)$
> 
> > [!proof]-
> > If $(\mu \times \nu)(S)=+\infty$, then take $R=X\times Y$. Otherwise, for $j\in \mathbb{N}$, choose $S\subseteq R_{j}\in \mathcal{P}_{1}$ with $$(\mu \times \nu)(S)\leq \rho(R_{j})\leq (\mu \times \nu)(S)+ \frac{1}{j}$$Wlog we assume that $R_{j+1}\subseteq R_{j}$. Then, $R:=\bigcap_{j=1}^{\infty}R_{j}\supseteq S$. Therefore, $$(\mu \times \nu)(S)\leq\rho(R)=\lim_{ j \to \infty } \rho(R_{j})\leq (\mu \times \nu)(S)$$
> ---
> Now we will prove 2. Let $S\subseteq X\times Y$ be $(\mu \times \nu)$-measurable with $(\mu \times \nu)(S)<+\infty$. Then, we choose $R\in \mathcal{P}_{2}$ according to Claim 3, s.t. $$(\mu \times \nu)(S)=\rho(R)$$
> - Case 1: $(\mu \times \nu)(S)=0$. Then, $\rho(R)=\int_{Y}^{} \mu(R_{y}) \, d\nu(y)=0$ and $\mu(R_{y})=0$ for $\nu$-a.e. $y$. Then, $\mu(S_{y})=0$  and $S_{y}$ is $\mu$-measurable. 
> - Case 2: $(\mu \times \nu)(S)>0$. Then, $$\begin{align}(\mu \times \nu)(R\backslash S)&=(\mu \times \nu)(R)-(\mu \times \nu)(S)\\&=\rho(R)-  \rho(R)\\&=0\end{align}$$Therefore, by case 1, $\rho(R \backslash S)=0$. This means, $$\mu((R \backslash S)_{y})=\mu(R_{y}\backslash S_{y})=0$$This proves that $S_{y}$ is $\mu$-measurable and $\mu(R_{y})=\mu(S_{y})$ Therefore, $$(\mu \times \nu)(S)=\rho(R)=\int_{Y}^{} \mu(R_{y}) \, d\nu(y)=\int_{Y}^{} \mu(S_{y}) \, d\nu(y)=\rho(S) $$
> ---
> We prove 4 finally. If $f=\chi_{S}<+\infty$, then 4 follows from 2. If $f\geq 0$, we have: $$f=\sum_{j=0}^{\infty} \frac{1}{j}\chi_{S_{j}}$$where $A_{j}$ are $(\mu \times \nu)$-measurable. Therefore, by 2, the property holds for: $$f_{k}:=\sum_{j=1}^{k} \frac{1}{j}\chi_{A_{j}}$$Using the [[Integrable Function|monotone convergence theorem]], $$\begin{align}\int_{Y}^{} \int_{X}^{} f(x,y) \, d\mu(x)  \, d\nu(y) &=\int_{Y}^{} \int_{X}^{} \sum_{j=1}^{\infty} \frac{1}{j}\chi_{A_{j}}\, d\mu  \, d\nu \\&= \sum_{j=1}^{\infty}\frac{1}{j} \int_{Y}^{} \int_{X}^{}\chi_{A_{j}}\, d\mu  \, d\nu\\&=\sum_{j=1}^{\infty}\frac{1}{j} (\mu \times \nu)(A_{j}) \\&=\int_{{X\times Y}}f  \, d(\mu \times \nu) \end{align}$$Finally, for general $f$, consider $f=f^+ - f^-$.
- **Remark**: There exists a non-$(\mu \times \nu)$-summable $f:X\times Y\to \overline{\mathbb{R}}$ s.t. one of the integrals is finite. For $(0,1]\times[0,2\pi]$ and $\mu=\nu=\mathcal{L}^1$ then, for $f(x,y):=\sin(y) / x$ $$\int_{0}^{1} \frac{1}{x}\int_{0}^{2\pi} \sin(y) \, dy  \, dx =0$$Hence, $x\mapsto \int_{Y}^{}f_{x}  \, d\nu$ is $\mu$-summable. However, $$\int_{0}^{2\pi}\sin(y) \int_{0}^{1} \frac{1}{x} \, dx  \, dy =+\infty$$which means $f$ is not $\mathcal{L}^2$-summable.
---
> [!lemma] Theorem 3 (Tonelli)
> If $f:X\times Y\to[0,+\infty]$ is $\mu \times \nu$-measurable, Then, 
> 1. $f_{y}(x):=f(x,y)$ is $\mu$-measurable for $\nu$-a.e. $y$.
> 2. $f_{x}(y):=f(x,y)$ is $\nu$-measurable for $\mu$-a.e. $x$.
> 3. $y\mapsto \int_{X}^{} f_{y} \, d\mu=\int_{X}^{} f(x,y) \, d\mu(x)$ is $\nu$-measurable.
> 4. $x\mapsto \int_{Y}^{} f_{x} \, d\nu=\int_{Y}^{} f(x,y) \, d\nu(y)$ is $\mu$-measurable.
> 5. It holds that: $$\begin{align}\int_{X\times Y}^{} f \, d(\mu \times \nu)&=\int_{Y}^{} \left( \int_{X}^{} f(x,y) \, d\mu(x)  \right)  \, d\nu(y) =\int_{X}^{} \left( \int_{Y}^{} f(x,y) \, d\nu(y)  \right)  \, d\mu(x)  \end{align}$$
- **Remark**: There exists a non-$(\mu \times \nu)$-measurable set $S\subseteq X\times Y$ s.t. $S_{y}$ is $\mu$-measurable for $\nu$-a.e. $y$. For $X=Y=\mathbb{R}$ and $\mu=\nu=\mathcal{L}^1$ and a non-measurable $A\subseteq[0,1]$ we set: $$S:=\left\{  (x,y)\in \mathbb{R}\times[0,1]:\left| x-\chi_{A}(y) \right| < \frac{1}{2}  \right\}$$Then, $S$ is not $(\mu \times \nu)$-measurable. But for all $y\in[0,1]$, $S_{y}$ is $\mu$-measurable and $\mu(S_{y})=1$.
---
> [!lemma] Corollary 4
> Let $A\subseteq X$ be a non-$\mu$-measurable set. Then,
> 1. for every non-$\nu$-measurable $B\subseteq Y$, $A\times B$ is non-$(\mu \times \nu)$-measurable.
> 2. for every $\nu$-measurable $B\subseteq Y$ s.t. $\nu(B)>0$, $A\times B$ is non-$(\mu \times \nu)$-measurable.
> 3. for every $\nu$-measurable $B\subseteq Y$ s.t. $\nu(B)=0$, $A\times B$ is $(\mu \times \nu)$-measurable.

> [!proof]-
> We have:
> 1. Assume $A\times B$ is $\mu \times \nu$-measurable. Then, $\chi_{A\times B}$ is $\mu \times \nu$-measurable. Therefore, by Tonelli, for most $y$, $$f_{y}(x):=\chi_{A\times B}(x,y)=\begin{cases}\chi_{A}(x)&y\in B\\0&y\notin B\end{cases}=\chi_{A}(x)\chi_{B}(y)$$ is $\mu$-measurable, which implies that $A$ is $\mu$-measurable, which is a contradiction. 
> 2. Assume $A\times B$ is $\mu \times \nu$-measurable. Then, $\chi_{A\times B}$ is $\mu \times \nu$-measurable. Therefore, by Tonelli, for most $y$, $$f_{y}(x):=\chi_{A\times B}(x,y)=\begin{cases}\chi_{A}(x)&y\in B\\0&y\notin B\end{cases}=\chi_{A}(x)\chi_{B}(y)$$ is $\mu$-measurable, which implies that $A$ is $\mu$-measurable, which is a contradiction. 
> 3. There exists a $\mu$-measurable set $R$ s.t. $A\times B\subseteq R\times B$. Then, $$(\mu \times \nu)(A\times B)\leq(\mu \times \nu)(R\times B)=\mu(R)\nu(B)=0$$Therefore, $A\times B$ is $\mu \times \nu$-measurable.
---
##### Examples
> [!claim] Claim
> We have: $\mathcal{L}^k\times \mathcal{L}^\ell=\mathcal{L}^{k+\ell}$.

> [!proof]-
> Let $S \subseteq \mathbb{R}^{k+\ell}$. We will show that: $$\mathcal{L}^{k+\ell}(S)=(\mathcal{L}^k\times \mathcal{L}^\ell)(S)=\inf\left\{  \sum_{i=1}^{\infty}\mathcal{L}^k(A_{i})\mathcal{L}^\ell(B_{i}):S\subseteq  \right\}$$
---
> [!claim] Exercise
> Show that: $$f(x,y):= \frac{x^2-y^2}{(x^2+y^2)^{2}}$$is not $\mathcal{L}^2$-summable in $[0,1]^{2}$.

> [!proof]-
> Assume $f$ is $\mathcal{L}^2$-summable. Then, by Fubini the two iterated integrals should equal. $$\begin{align}\int_{0}^{1}\left( \int_{0}^{1} \frac{x^2-y^2}{(x^2+y^2)^{2}} \, dy  \right)   \, dx&=\int_{0}^{1}\left( \int_{0}^{1} \frac{x^2+y^2}{(x^2+y^2)^{2}} \, dy + \int_{0}^{1} \frac{-2y^2}{(x^2+y^2)^{2}} \, dy  \right)   \, dx \\&=\int_{0}^{1}\left( \int_{0}^{1} \frac{1}{x^2+y^2} \, dy + \int_{0}^{1} \frac{-2y^2}{(x^2+y^2)^{2}} \, dy  \right)   \, dx\\&=\int_{0}^{1} \frac{1}{x^2+1}  \, dx \\&=\arctan x|^1_{0}\\&=\frac{\pi}{4}\end{align} $$However, $$\begin{align}\int_{0}^{1}\left( \int_{0}^{1} \frac{x^2-y^2}{(x^2+y^2)^{2}} \, dx  \right)   \, dy&=-\frac{\pi}{4}\end{align}$$
---
