#Definition #ProbabilityTheory 

> [!definition]
> For a [[probability space]] $(\Omega,\mathcal{A},\mathbb{P})$ 
> 1. for $X\in L^1(\Omega,\mathcal{A},\mathbb{P})$ and a sub-$\sigma$-algebra $\mathcal{B\subseteq A}$, the ***conditional expectation*** of $X$ given $\mathcal{B}$ is the unique element $\mathbb{E}[X|\mathcal{B}]$ in $L^1(\Omega,\mathcal{B},\mathbb{P})$ s.t.
> 	$$\mathbb{E}[X\cdot \mathbb{1}_{B}]=\mathbb{E}[\mathbb{E}[X|\mathcal{B}]\cdot \mathbb{1}_{B}],\quad \forall B\in \mathcal{B}$$

- **Remark**: For $A,B\in \mathcal{A}$ with $0<\mathbb{P}[B]<1$. If $\mathcal{B}:=\{ \varnothing,B,B^c,\Omega \}$, then: $$\mathbb{E}[\mathbb{1}_{A}|\mathcal{B}]=\begin{cases}\frac{\mathbb{P}(A\cap B)}{\mathbb{P}(B)}&\omega=B\\\frac{\mathbb{P}(A\cap B^c)}{\mathbb{P}(B^c)}&\omega=B^c\end{cases}$$as $\mathbb{E}[\mathbb{1}_{A}\cdot \mathbb{1}_{B}]=\mathbb{P}(A\cap B)=\int_B \frac{\mathbb{P}(A\cap B)}{\mathbb{P}(B)}\, d\mathbb{P}$ and the other case follows analogously.
- **Remark**: If $X=\mathbb{1}_{A}$ for some $A\in \mathcal{A}$, we have that: $$\mathbb{E}[\mathbb{1}_{A}\cdot \mathbb{1}_{B}]=\int_{A\cap B}^{} 1 \, d\mathbb{P}= \mathbb{P}(A\cap B)=\int_{B}\mathbb{E}[\mathbb{1}_{A}|\mathcal{B}]  \, d\mathbb{P} $$

---
##### Properties
> [!lemma] Theorem 1 (Conditional Expectation on Sigma Algebra)
> We have for $X\in L^1$ and $\mathcal{B}\subseteq \mathcal{A}$ a $\sigma$-algebra, 
> 1. $\mathbb{E}[X|\mathcal{B}]\in L^1(\Omega,\mathcal{B},\mathbb{P})$ exists and is unique.
> 2. for every bounded $\mathcal{B}$-measurable real random variable $Z$, $$\mathbb{E}[XZ]=\mathbb{E}[\mathbb{E}[X|\mathcal{B}]Z]$$
> 3. if $X\geq 0$ then $\mathbb{E}[X|\mathcal{B}]\geq 0$ almost surely.

> [!proof]-
> We have:
> 1. Uniqueness is given as follows: Assume $X',X''$ are two such random variables in $L^1$. Then, take $B:=\{ X'>X'' \}$ which is $\mathcal{B}$-measurable. Then, we get: $$\mathbb{E}[(X'-X'')\cdot \mathbb{1}_{\{ X'>X'' \}}]=0$$and $(X'-X'')\mathbb{1}_{\{ X'>X'' \}}=0$ almost surely by [[Expected Value|Theorem 3.1]]. Hence, $X'\leq X''$ almost surely. By symmetry we have the opposite inequality.
>    
>    For existence, first assume that $X\geq 0$. We define a finite measure $\mu$ on $(\Omega,\mathcal{B})$ by: $$\mu(B):=\mathbb{E}[X\cdot \mathbb{1}_{B}]$$Further, we can consider $\mathbb{P}:=\mathbb{P}|_{\mathcal{B}}$ and notice that $\mu\ll \mathbb{P}$. Indeed, if for $B\in \mathcal{B}$, $\mathbb{P}(B)=0$, then $\mathbb{1}_{B}=0$ almost surely and $\mu(B)=0$. Then, by [[Lebesgue Integral|Radon-Nikodym]] we get a non-negative $\mathcal{B}$-measurable random variable $\tilde{X}$ s.t. $$\mathbb{E}[X\cdot \mathbb{1}_{B}]=\int_{E}^{} \tilde{X} \, d\mathbb{P}=\mathbb{E}[\tilde{X}\cdot \mathbb{1}_{B}],\quad \forall B\in \mathcal{B} $$Taking $B=\Omega$, we have that $\mathbb{E}[\tilde{X}]=\mathbb{E}[X]<\infty$ and thus $\tilde{X}\in L^1(\Omega,\mathcal{B},\mathbb{P})$. If $X$ is an arbitrary sign, we can take: $$\mathbb{E}[X|\mathcal{B}]:=\mathbb{E}[X^+|\mathcal{B}]-\mathbb{E}[X^-|\mathcal{B}]$$
> 2. First, assume that $Z$ is simple with $Z=\sum_{i=1}^{n}\lambda_{i}\mathbb{1}_{B_{i}}$. Then, $$\mathbb{E}[XZ]=\sum_{i=1}^{n}\lambda_{i}\mathbb{E}[X\cdot \mathbb{1}_{B_{i}}]=\sum_{i=1}^{n}\lambda_{i}\mathbb{E}[\mathbb{E}[X|\mathcal{B}]\cdot \mathbb{1}_{B_{i}}]=\mathbb{E}[\mathbb{E}[X|\mathcal{B}]\cdot Z]$$In the general case, as $Z$ is a pointwise limit of simple $\mathcal{B}$-measurable random variables $(Z_{n})_{n}$ that are uniformly bounded (as $Z$ is bounded) we can use [[Expected Value|DCT]] and get: $$\mathbb{E}[XZ]=\lim_{ n \to \infty } \mathbb{E}[XZ_{n}]=\lim_{ n \to \infty } \mathbb{E}[\mathbb{E}[X|\mathcal{B}]\cdot Z_{n}]=\mathbb{E}[\mathbb{E}[X|\mathcal{B}]\cdot Z]$$ 

- **Remark**: We have that in the discrete case $\mathbb{E}[X|Y]=\mathbb{E}[X|\sigma(Y)]$.
---
> [!lemma] Proposition 2 (Properties of Conditional Expectation)
> Let $X,Y$ be integrable random variables and $\mathcal{B}\subseteq \mathcal{A}$ sub $\sigma$-algebra. Further, let $a,b,c\in \mathbb{R}$. Then, 
> 1. $\mathbb{E}[\mathbb{E}[X|\mathcal{B}]]=\mathbb{E}[X]$
> 2. $\mathbb{E}[aX+bY|\mathcal{B}]=a\mathbb{E}[X|\mathcal{B}]+b\mathbb{E}[Y|\mathcal{B}]$ almost surely.
> 3. if $X$ is $\mathcal{B}$-measurable then $\mathbb{E}[X|\mathcal{B}]=X$ almost surely.
> 4. $\mathbb{E}[c|\mathcal{B}]=c$ almost surely.
> 5. $\mathbb{E}[X|\{ \varnothing,\Omega \}]=\mathbb{E}[X]$
> 6. if $X\geq 0$ almost surely, then $\mathbb{E}[X | \mathcal{B}]\geq 0$ almost surely.
> 7. if $X\leq Y$ almost surely, then $\mathbb{E}[X|\mathcal{B}]\leq \mathbb{E}[Y|\mathcal{B}]$ almost surely.
> 8. $\left| \mathbb{E}[X| \mathcal{B}] \right|\leq \mathbb{E}[\left| X \right| | \mathcal{B}]$
> 9. if $Y$ is a $\mathcal{B}$-measurable real random variable, $\mathbb{E}[YX|\mathcal{B}]=Y\mathbb{E}[X|\mathcal{B}]$
> 	1. if $X,Y$ are both non-negative or
> 	2. if $X,YX$ are both integrable.


> [!proof]-
> We have that:
> 1. Use $B=\Omega$. 
> 2. Let $X,Y\in L^1(\Omega,\mathcal{A},\mathbb{P})$ and $a,b\in \mathbb{R}$. Then, $$\begin{align}\mathbb{E}[(aX+bY)\cdot \mathbb{1}_{B}]&=a \mathbb{E}[X\cdot \mathbb{1}_{B}]+b\mathbb{E}[Y\cdot \mathbb{1}_{B}]\\&=a \mathbb{E}[\mathbb{E}[X|\mathcal{B}]\cdot \mathbb{1}_{B}]+b[\mathbb{E}[Y|\mathcal{B}]\cdot \mathbb{1}_{B}]\\&=\mathbb{E}[(a \mathbb{E}[X|\mathcal{B}]+b\mathbb{E}[X'|\mathcal{B}])\cdot \mathbb{1}_{B}]\end{align}$$The rest follows by uniqueness.
> 3. If $X$ is $\mathcal{B}$-measurable, then $X\in L^1(\Omega,\mathcal{B},\mathbb{P})$ and it holds by uniqueness.
> 4. $c$ is $\mathcal{B}$-measurable and from 3. 
> 5. We have that: $$\mathbb{E}[X]=\mathbb{E}[\mathbb{E}[X]],\quad \mathbb{E}[0]=0$$The rest holds by uniqueness.
> 6. Let $Y:=\mathbb{E}[X | \mathcal{B}]$ and assume $\mathbb{P}(Y<0)>0$. Then, there exists $n$ s.t. $\mathbb{P}\left( Y< -\frac{1}{n} \right)>0$. Then, let $B:=\left\{  Y< -\frac{1}{n}  \right\}$, which is in $\mathcal{B}$. Hence, $$\mathbb{E}[X\mathbb{1}_{B}]=\mathbb{E}[Y\mathbb{1}_{B}]<-\int_{B} \frac{1}{n}\, d\mathbb{P} <0$$which is a contradiction as $X\mathbb{1}_{B}\geq 0$.
> 7. From 6 and 2. 
> 8. From Proposition 2.3, $$\left| \mathbb{E}[X|\mathcal{B}] \right| \leq \mathbb{E}[X^+|\mathcal{B}]+\mathbb{E}[X^-|\mathcal{B}]=\mathbb{E}[\left| X \right| | \mathcal{B} ]$$
> 9. If $X,Y\geq 0$, then for every non-negative $\mathcal{B}$-measurable random variable, $$\mathbb{E}[Z(Y\mathbb{E}[X|\mathcal{B}])]=\mathbb{E}[(ZY)\mathbb{E}[X|\mathcal{B}]]=\mathbb{E}[ZYX]$$If $X,YX$ are both integrable, we can use the decomposition $X=X^+ -X^-$.



---
> [!lemma] Proposition 3 (Conditional Expectation Inequalities)
> Let $X\in L^1(\Omega,\mathcal{A},\mathbb{P})$ and $\mathcal{B}\subseteq \mathcal{A}$ a sub-$\sigma$-algebra. Then, 
> 1. **MCT**: If $(X_{n})_{n}\subseteq L^1(\Omega,\mathcal{A},\mathbb{P})$ where $0\leq X_{1}\leq X_{2},\dots$ a.s. and $X_{n}\to X$ a.s., then $$\lim_{ n \to \infty } \mathbb{E}[X_{n}|\mathcal{B}]=\mathbb{E}[X|\mathcal{B}],\quad \text{ a.s.}$$
> 2. **Fatou**: If $X_{n}\geq 0$ for all $n$, then: $\mathbb{E}[\liminf_{ n \to \infty }X_{n}|\mathcal{B}]\leq \liminf_{ n \to \infty }\mathbb{E}[X_{n}|\mathcal{B}]$ a.s.

> [!proof]+
> We have:
> 1. Let $Z:=\lim_{ n \to \infty }\mathbb{E}[X_{n}|\mathcal{B}]$. Then, of course $Z$ is $\mathcal{B}$-measurable and for $B\in \mathcal{B}$ using Proposition 2.9: $$\mathbb{E}[Z\mathbb{1}_{B}]=\mathbb{E}[\lim_{ n \to \infty } \mathbb{E}[X_{n}|\mathcal{B}]\mathbb{1}_{B}]=\mathbb{E}[\lim_{ n \to \infty } \mathbb{E}[X_{n}\mathbb{1}_{B}|\mathcal{B}]]$$Now, for $Y_{n}:=\mathbb{E}[X_{n}\mathbb{1}_{B}|\mathcal{B}]$, by Proposition 2.6 and 2.7, we have that $0\leq Y_{1}\leq Y_{2}\leq\dots$. Therefore by [[Expected Value|MCT]], $$\mathbb{E}[Z\mathbb{1}_{B}]=\mathbb{E}[\lim_{ n \to \infty } \mathbb{E}[X_{n}\mathbb{1}_{B}|\mathcal{B}]]=\lim_{ n \to \infty } \mathbb{E}[\mathbb{E}[X_{n}\mathbb{1}_{B}|\mathcal{B}]]=\lim_{ n \to \infty } \mathbb{E}[X_{n}\mathbb{1}_{B}]=\mathbb{E}[X\mathbb{1}_{B}]$$By uniqueness, we have the statement.
> 2. For $n\geq m$, we have that $X_{n}\geq Z_{m}:=\text{inf}_{k\geq m}X_{m}$. Therefore, $\mathbb{E}[X_{n}|\mathcal{B}]\geq \mathbb{E}[Z_{m}|\mathcal{B}]$ and $\text{inf}_{n\geq m}\mathbb{E}[X_{n}|\mathcal{B}]\geq \mathbb{E}[Z_{m}|\mathcal{B}]$ almost surely. Therefore, by MCT, $$\mathbb{E}[\liminf_{ n \to \infty } X_{n}|\mathcal{B}]=\mathbb{E}[\lim_{ m \to \infty } Z_{m}|\mathcal{B}]=\lim_{ m \to \infty } \mathbb{E}[Z_{m}|\mathcal{B}]\leq \liminf_{ m \to \infty } \mathbb{E}[X_{n}|\mathcal{B}]$$
---
> [!lemma] Proposition 4 (Nested $\sigma$-algebras)
> Let $\mathcal{B}_{1},\mathcal{B}_{2}$ be two sub-$\sigma$-algebras of $\mathcal{A}$ s.t. $\mathcal{B}_{1}\subseteq \mathcal{B}_{2}$. Then, for every non-negative or integrable random variable $X$,  $$\mathbb{E}[\mathbb{E}[X|\mathcal{B}_{2}]|\mathcal{B}_1]=\mathbb{E}[X|\mathcal{B}_{1}]=\mathbb{E}[\mathbb{E}[X|\mathcal{B}_{1}]|\mathcal{B}_2]$$

> [!proof]-
> Consider the case when $X\geq 0$. Let $Z$ be a non-negative $\mathcal{B}_{1}$ measurable random variable. Then, since $Z$ is also $\mathcal{B}_{2}$-measurable, $$\mathbb{E}[Z\cdot \mathbb{E}[\mathbb{E}[X|\mathcal{B}_{2}]|\mathcal{B}_{1}]]=\mathbb{E}[Z \cdot \mathbb{E}[X|\mathcal{B}_{2}]]=\mathbb{E}[ZX]$$Hence, by uniqueness we have that $\mathbb{E}[\mathbb{E}[X|\mathcal{B}_{2}]|\mathcal{B}_{1}]=\mathbb{E}[X|\mathcal{B}_{1}]$.
---
