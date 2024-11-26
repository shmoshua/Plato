#Definition #ProbabilityTheory 

> [!definition]
> For a [[probability space]] $(\Omega,\mathcal{A},\mathbb{P})$ and an event $B\in \mathcal{A}$ with $\mathbb{P}(B)>0$, 
> 1. the ***conditional probability*** given $B$ is a new probability measure: $$\mathbb{P}(A|B):=\frac{\mathbb{P}(A\cap B)}{\mathbb{P}(B)}$$
> 2. for a [[random variable]] $X\in L^1(\Omega,\mathcal{A},\mathbb{P})$, the ***conditional expectation*** of $X$ given $B$ is: $$\mathbb{E}[X|B]:=\frac{\mathbb{E}[X\cdot \mathbb{1}_{B}]}{\mathbb{P}(B)}$$which is also the [[Expected Value|expectation]] over $\mathbb{P}(\cdot|B)$.
> 3. for a random variable $X\in L^1$ and a random variable $Y:\Omega\to E$, the ***conditional expectation*** of $X$ given $Y$ is a *real random variable* $\mathbb{E}[X|Y]:\Omega\to \mathbb{R}$ with $\mathbb{E}[X|Y]=\varphi(Y)$ where: $$\varphi: E\to \mathbb{R},\quad y\mapsto \begin{cases}\mathbb{E}[X|Y=y]& \text{if }\mathbb{P}(Y=y)>0\\0&\text{otherwise}\end{cases}$$
> 4. for $X\in L^1$ and a sub-$\sigma$-algebra $\mathcal{B\subseteq A}$, the ***conditional expectation*** of $X$ given $\mathcal{B}$ is the unique element $\mathbb{E}[X|\mathcal{B}]$ in $L^1(\Omega,\mathcal{B},\mathbb{P})$ s.t.
> 	$$\mathbb{E}[X\cdot \mathbb{1}_{B}]=\mathbb{E}[\mathbb{E}[X|\mathcal{B}]\cdot \mathbb{1}_{B}],\quad \forall B\in \mathcal{B}$$

^22a6cd

- **Remark**: If $\mathcal{B}=\{ \varnothing, B, B^c, \Omega \}$, then $\mathbb{E}[X |B]:=\mathbb{E}[X|\mathcal{B}]=\mathbb{E}[X\cdot \mathbb{1}_{\mathbf{B}}]$
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
> 1. $\mathbb{E}[X|\mathcal{B}]\in L^1(\Omega,\mathcal{B},\mathbb{P})$ exists and is unique.
> 2. for every bounded $\mathcal{B}$-measurable real random variable $Z$, $$\mathbb{E}[XZ]=\mathbb{E}[\mathbb{E}[X|\mathcal{B}]Z]$$
> 3. if $X\geq 0$ then $\mathbb{E}[X|\mathcal{B}]\geq 0$ almost surely.

> [!proof]-
> We have:
> 1. Uniqueness is given as follows: Assume $X',X''$ are two such random variables in $L^1$. Then, take $B:=\{ X'>X'' \}$ which is measurable. Then, we get: $$\mathbb{E}[(X'-X'')\cdot \mathbb{1}_{\{ X'>X'' \}}]=0$$and $(X'-X'')\mathbb{1}_{\{ X'>X'' \}}=0$ almost surely. Hence, $X'\leq X''$ almost surely. By symmetry we have the opposite inequality.
>    
>    For existence, first assume that $X\geq 0$. We define a finite measure $\mu$ on $(\Omega,\mathcal{B})$ by: $$\mu(B):=\mathbb{E}[X\cdot \mathbb{1}_{B}]$$Further, we can consider $\mathbb{P}:=\mathbb{P}|_{\mathcal{B}}$ and notice that $\mu\ll \mathbb{P}$. Indeed, if for $B\in \mathcal{B}$, $\mathbb{P}(B)=0$, then $\mathbb{1}_{B}$ almost surely and $\mu(B)=0$. Then, by [[Lebesgue Integral|Radon-Nikodym]] we get a non-negative $\mathcal{B}$-measurable random variable $\tilde{X}$ s.t. $$\mathbb{E}[X\cdot \mathbb{1}_{B}]=\int_{E}^{} \tilde{X} \, d\mathbb{P}=\mathbb{E}[\tilde{X}\cdot \mathbb{1}_{B}],\quad \forall B\in \mathcal{B} $$Taking $B=\Omega$, we have that $\mathbb{E}[\tilde{X}]=\mathbb{E}[X]<\infty$ and thus $\tilde{X}\in L^1(\Omega,\mathcal{B},\mathbb{P})$. If $X$ is an arbitrary sign, we can take: $$\mathbb{E}[X|\mathcal{B}]:=\mathbb{E}[X^+|\mathcal{B}]-\mathbb{E}[X^-|\mathcal{B}]$$
> 2. First, assume that $Z$ is simple with $Z=\sum_{i=1}^{n}\lambda_{i}\mathbb{1}_{B_{i}}$. Then, $$\mathbb{E}[XZ]=\sum_{i=1}^{n}\lambda_{i}\mathbb{E}[X\cdot \mathbb{1}_{B_{i}}]=\sum_{i=1}^{n}\lambda_{i}\mathbb{E}[\mathbb{E}[X|\mathcal{B}]\cdot \mathbb{1}_{B_{i}}]=\mathbb{E}[\mathbb{E}[X|\mathcal{B}]\cdot Z]$$In the general case, as $Z$ is a pointwise limit of simple $\mathcal{B}$-measurable random variables $(Z_{n})_{n}$ that are uniformly bounded (as $Z$ is bounded) we can use [[Expected Value|DCT]] and get: $$\mathbb{E}[XZ]=\lim_{ n \to \infty } \mathbb{E}[XZ_{n}]=\lim_{ n \to \infty } \mathbb{E}[\mathbb{E}[X|\mathcal{B}]\cdot Z_{n}]=\mathbb{E}[\mathbb{E}[X|\mathcal{B}]\cdot Z]$$
> 3. If $X\geq 0$, then 

- **Remark**: We have that in the discrete case $\mathbb{E}[X|Y]=\mathbb{E}[X|\sigma(Y)]$.
---
> [!lemma] Proposition 3 (Properties of Conditional Expectation)
> Let $X\in L^1(\Omega,\mathcal{A},\mathbb{P})$ and $\mathcal{B}\subseteq \mathcal{A}$ a sub-$\sigma$-algebra. Then, 
> 1. if $X$ is $\mathcal{B}$-measurable, then $\mathbb{E}[X |\mathcal{B}]=X$.
> 2. $L^1(\Omega,\mathcal{A},\mathbb{P})\to L^1(\Omega,\mathcal{B},\mathbb{P}),X\mapsto \mathbb{E}[X | \mathcal{B}]$ is linear.
> 3. $\mathbb{E}[\mathbb{E}[X | \mathcal{B}]]=\mathbb{E}[X]$
> 4. $\left| \mathbb{E}[X|\mathcal{B}] \right|\leq \mathbb{E}[\left| X \right| |\mathcal{B}]$ and $\mathbb{E}[\left| \mathbb{E}[X|\mathcal{B}] \right|]\leq \mathbb{E}[\left| X \right|]$
> 5. for $X'\in L^1(\Omega,\mathcal{A},\mathbb{P})$ if $X'\geq X$, then $\mathbb{E}[X'|\mathcal{B}]\geq \mathbb{E}[X|\mathcal{B}]$ almost surely.
> 6. if $Y$ is a $\mathcal{B}$-measurable real random variable, $\mathbb{E}[YX|\mathcal{B}]=Y\mathbb{E}[X|\mathcal{B}]$
> 	1. if $X,Y$ are both non-negative or
> 	2. if $X,YX$ are both integrable.

> [!proof]-
> We have:
> 1. As $X$ is $\mathcal{B}$-measurable, $X\in L^1(\Omega,\mathcal{B},\mathbb{P})$ and it holds by uniqueness of $\mathbb{E}[X|\mathcal{B}]$.
> 2. Let $X,X'\in L^1(\Omega,\mathcal{A},\mathbb{P})$ and $\alpha\in \mathbb{R}$. Then, $$\begin{align}\mathbb{E}[(\alpha X+X')\cdot \mathbb{1}_{B}]&=\alpha \mathbb{E}[X\cdot \mathbb{1}_{B}]+\mathbb{E}[X'\cdot \mathbb{1}_{B}]\\&=\alpha \mathbb{E}[\mathbb{E}[X|\mathcal{B}]\cdot \mathbb{1}_{B}]+[\mathbb{E}[X'|\mathcal{B}]\cdot \mathbb{1}_{B}]\\&=\mathbb{E}[(\alpha \mathbb{E}[X|\mathcal{B}]+\mathbb{E}[X'|\mathcal{B}])\cdot \mathbb{1}_{B}]\end{align}$$
> 3. Use $B=\Omega$ on the property.
> 4. From Proposition 2.3, $$\left| \mathbb{E}[X|\mathcal{B}] \right| \leq \mathbb{E}[X^+|\mathcal{B}]+\mathbb{E}[X^-|\mathcal{B}]=\mathbb{E}[\left| X \right| | \mathcal{B} ]$$
> 5. By linearity.
> 6.
---
> [!lemma] Proposition 4 (Nested $\sigma$-algebras)
> Let $\mathcal{B}_{1},\mathcal{B}_{2}$ be two sub-$\sigma$-algebras of $\mathcal{A}$ s.t. $\mathcal{B}_{1}\subseteq \mathcal{B}_{2}$. Then, for every non-negative or integrable random variable $X$,  $$\mathbb{E}[\mathbb{E}[X|\mathcal{B}_{2}]|\mathcal{B}_1]=\mathbb{E}[X|\mathcal{B}_{1}]=\mathbb{E}[\mathbb{E}[X|\mathcal{B}_{1}]|\mathcal{B}_2]$$

> [!proof]-
> Consider the case when $X\geq 0$. Let $Z$ be a non-negative $\mathcal{B}_{1}$ measurable random variable. Then, since $Z$ is also $\mathcal{B}_{2}$-measurable, $$\mathbb{E}[Z\cdot \mathbb{E}[\mathbb{E}[X|\mathcal{B}_{2}]|\mathcal{B}_{1}]]=\mathbb{E}[Z \cdot \mathbb{E}[X|\mathcal{B}_{2}]]=\mathbb{E}[ZX]$$Hence, by uniqueness we have that $\mathbb{E}[\mathbb{E}[X|\mathcal{B}_{2}]|\mathcal{B}_{1}]=\mathbb{E}[X|\mathcal{B}_{1}]$.
---
