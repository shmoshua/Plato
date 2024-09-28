#Definition #ProbabilityTheory 

> [!definition]
> For a [[probability space]] $(\Omega,\mathcal{A},\mathbb{P})$ and an event $B\in \mathcal{A}$ with $\mathbb{P}(B)>0$, 
> 1. the ***conditional probability*** given $B$ is a new probability measure: $$\mathbb{P}(A|B):=\frac{\mathbb{P}(A\cap B)}{\mathbb{P}(B)}$$
> 2. for a [[random variable]] $X\in L^1(\Omega,\mathcal{A},\mathbb{P})$, the ***conditional expectation*** of $X$ given $B$ is: $$\mathbb{E}[X|B]:=\frac{\mathbb{E}[X\cdot \mathbb{1}_{B}]}{\mathbb{P}(B)}$$which is also the [[Expected Value|expectation]] over $\mathbb{P}(\cdot|B)$.
> 3. for a random variable $X\in L^1$ and a random variable $Y:\Omega\to E$, the ***conditional expectation*** of $X$ given $Y$ is a *real random variable* $\mathbb{E}[X|Y]:\Omega\to \mathbb{R}$ with $\mathbb{E}[X|Y]=\varphi(Y)$ where: $$\varphi: E\to \mathbb{R},\quad y\mapsto \begin{cases}\mathbb{E}[X|Y=y]& \text{if }\mathbb{P}(Y=y)>0\\0&\text{otherwise}\end{cases}$$
> 4. for $X\in L^1$ and a sub-$\sigma$-algebra $\mathcal{B\subseteq A}$, the ***conditional expectation*** of $X$ given $\mathcal{B}$ is the unique element $\mathbb{E}[X|\mathcal{B}]$ in $L^1(\Omega,\mathcal{B},\mathbb{P})$ s.t. $$\mathbb{E}[X\cdot \mathbb{1}_{B}]=\mathbb{E}[\mathbb{E}[X|\mathcal{B}]\cdot \mathbb{1}_{B}],\quad \forall B\in \mathcal{B}$$
- **Remark**: the $\varphi(y)$ value when $\mathbb{P}(Y=y)=0$ is irrelevant as $$\mathbb{P}(Y\in \{ y\in E:\mathbb{P}(Y=y)=0 \})=\sum_{y\in \{ y\in E:\mathbb{P}(Y=y)=0 \}}^{}\mathbb{P}(Y=y)=0$$
---
##### Properties
> [!lemma] Proposition 1
> Let $X\in L^1(\Omega,\mathcal{A},\mathbb{P})$. Then, 
> 1. $\mathbb{E}[\left| \mathbb{E}[X|Y] \right|]\leq \mathbb{E}[\left| X \right|]$
> 2. $\mathbb{E}[X|Y]\in L^1(\Omega,\mathcal{A},\mathbb{P})$.
> 3. for every bounded $\sigma(Y)$-measurable real random variable $Z$, $$\mathbb{E}[ZX]=\mathbb{E}[Z\cdot \mathbb{E}[X|Y]]$$
> 4. if $Y$ is another random variable s.t. $\sigma(Y)=\sigma(Y')$, then: $$\mathbb{E}[X|Y]=\mathbb{E}[X|Y']\text{ almost surely}$$

> [!proof]-
> We have:
> 1. from the definition of $\mathbb{E}[X|Y]$: $$\begin{align}\mathbb{E}[\left| \mathbb{E}[X|Y] \right| ]&=\sum_{\mathbb{P}(Y=y)>0}^{}\mathbb{P}(Y=y)\frac{\left| \mathbb{E}[X\cdot \mathbb{1}_{Y=y}] \right|}{\mathbb{P}(Y=y)}\\&\leq \sum_{y\in E}^{}\left| \mathbb{E}[X\cdot \mathbb{1}_{\{ Y=y \}}] \right| \\&\leq \sum_{y\in E}^{} \mathbb{E}[\left| X \right| \cdot \mathbb{1}_{\{ Y=y \}}]\\&=\mathbb{E}[\left| X \right| ] \end{align} $$
> 2. from 1.
> 3. from [[Random Variable|Proposition 1]], there exists a bounded measurable function $\psi:E\to \mathbb{R}$ s.t. $Z=\psi(Y)$. Then, $$\begin{align}\mathbb{E}[\psi(Y)\mathbb{E}[X|Y]]&=\sum_{y\in E}^{}\psi(y)\mathbb{E}[X\cdot \mathbb{1}_{\{ Y=y \}}]\\&=\sum_{y\in E}^{}\mathbb{E}[\psi(Y)X\cdot \mathbb{1}_{\{ Y=y \}}]\\&=\mathbb{E}[\psi(Y)X]\end{align}$$
> 4. Let $Z=\mathbb{1}_{\{ E[X|Y]>E[X|Y'] \}}$ which is measurable w.r.t. $\sigma(Y)$. Therefore, $$\mathbb{E}[Z\cdot \mathbb{E}[X|Y]]=\mathbb{E}[ZX]=\mathbb{E}[Z\cdot \mathbb{E}[X|Y']]$$and $\mathbb{E}[\mathbb{1}_{\{ E[X|Y]>E[X|Y'] \}}\cdot(\mathbb{E}[X|Y]-\mathbb{E}[X|Y'])]=0$ which is only possible if $\mathbb{1}_{\{ E[X|Y]>E[X|Y'] \}}\cdot(\mathbb{E}[X|Y]-\mathbb{E}[X|Y'])=0$ a.s. as it is non-negative. Therefore, $\mathbb{E}[X|Y]\leq \mathbb{E}[X|Y']$ a.s.
>    
>    By symmetry, we have the statement.
---
> [!lemma] Proposition 2 (Conditional Expectation on Sigma Algebra)
> We have for $X\in L^1$ and $\mathcal{B}\subseteq \mathcal{A}$ a $\sigma$-algebra, 
> 1. $\mathbb{E}[X|\mathcal{B}]\in L^1(\Omega,\mathcal{A},\mathbb{P})$ exists and is unique.
> 2. for every bounded $\mathcal{B}$-measurable real random variable $Z$, $$\mathbb{E}[XZ]=\mathbb{E}[\mathbb{E}[X|\mathcal{B}]Z]$$
> 3. if $X\geq 0$ then $\mathbb{E}[X|\mathcal{B}]\geq 0$ almost surely.

> [!proof]+
> We have:
> 1. Uniqueness is given as follows: Assume $X',X''$ are two such random variables in $L^1$. Then, take $B:=\{ X'>X'' \}$ which is measurable. Then, we get: $$\mathbb{E}[(X'-X'')\cdot \mathbb{1}_{\{ X'>X'' \}}]=0$$and $(X'-X'')\mathbb{1}_{\{ X'>X'' \}}=0$ almost surely. Hence, $X'\leq X''$ almost surely. By symmetry we have the opposite inequality.
>    
>    For existence, first assume that $X\geq 0$. We define a finite measure $\mu$ on $(\Omega,\mathcal{B})$ by: $$\mu(B):=\mathbb{E}[X\cdot \mathbb{1}_{B}]$$Further, we can consider $\mathbb{P}:=\mathbb{P}|_{\mathcal{B}}$ and notice that $\mu\ll \mathbb{P}$. Indeed, if for $B\in \mathcal{B}$, $\mathbb{P}(B)=0$, then $\mathbb{1}_{B}$ almost surely and $\mu(B)=0$. Then, by [[Lebesgue Integral|Radon-Nikodym]] we get a non-negative $\mathcal{B}$-measurable random variable $\tilde{X}$ s.t. $$\mathbb{E}[X\cdot \mathbb{1}_{B}]=\int_{E}^{} \tilde{X} \, d\mathbb{P}=\mathbb{E}[\tilde{X}\cdot \mathbb{1}_{B}],\quad \forall B\in \mathcal{B} $$Taking $B=\Omega$, we have that $\mathbb{E}[\tilde{X}]=\mathbb{E}[X]<\infty$ and thus $\tilde{X}\in L^1(\Omega,\mathcal{B},\mathbb{P})$. If $X$ is an arbitrary sign, we can take: $$\mathbb{E}[X|\mathcal{B}]:=\mathbb{E}[X^+|\mathcal{B}]-\mathbb{E}[X^-|\mathcal{B}]$$
> 2. 1 implies 2 when $Z$ is a simple 
