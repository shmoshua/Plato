#Definition #ProbabilityTheory 

> [!definition]
> Let $(\Omega,\mathcal{A},\mathbb{P})$ be a [[probability space]]. 
> 1. Events $A_{1},\dots,A_{n}\in \mathcal{A}$ are ***independent*** if $$\mathbb{P}\left( \bigcap_{i\in J}^{}A_{i} \right)=\prod_{i\in J}^{}\mathbb{P}(A_{i}),\quad \forall J\subseteq[n]$$
> 2. Sub-[[Sigma Algebra|$\sigma$-algebras]] $\mathcal{B_{1},\dots,B}_{n}\subseteq \mathcal{A}$ are ***independent*** if: $$\mathbb{P}(A_{1}\cap A_{2}\cap\dots \cap A_{n})=\prod_{i\in[n]}^{}\mathbb{P}(A_{i}),\quad \forall A_{i}\in \mathcal{B}_{i}$$
> 3. [[Random Variable|Random variables]] $X_{1},..,X_{n}$ taking values in $(E_{i},\mathcal{E}_{i})$ are ***independent*** if $\sigma(X_1),\dots,\sigma(X_{n})$ are independent, i.e. $$\mathbb{P}(X_{1}\in F_{1},\dots,X_{n}\in F_{n})=\mathbb{P}(X_{1}\in F_{1})\dots \mathbb{P}(X_{n}\in F_{n}),\quad \forall F_{i}\in \mathcal{E}_{i}$$

^48b93f

- **Remark**: Pairwise independence is not enough to guarantee independence.
- **Remark**: if $\mathcal{B}_{1},\dots,\mathcal{B}_{n}\subseteq \mathcal{A}$ are independent, $X_{1},\dots,X_{n}$ are independent if $X_{i}$ is $\mathcal{B}_{i}$-measurable.
---
##### Properties
> [!lemma] Proposition 1
> For $A_{1},\dots,A_{n}\in\mathcal{A}$ events, the following are equivalent.
> 1. $A_{1},\dots,A_{n}$ are independent.
> 2. $\mathbb{P}(B_{1}\cap\dots \cap B_{n})=\prod_{i=1}^{n}\mathbb{P}(B_{i})$ for $B_{i}\in \sigma(A_{i})=\{ \varnothing,A_{i},A_{i}^c,\Omega \}$, i.e. $\sigma(A_{i})$ are independent.

> [!proof]-
> We have:
> 1. (1=>2): This holds from the fact that if $A_{1},\dots,A_{n}$ are independent, then $A_{1}^c,A_{2},\dots,A_{n}$ are independent. Indeed, $$\begin{align}\mathbb{P}(A_{1}^c\cap A_{2}\cap\dots \cap A_{n})&=\mathbb{P}(A_{2}\cap\dots \cap A_{n})-\mathbb{P}(A_{1}\cap A_{2}\cap\dots \cap A_{n})\\&=(1-\mathbb{P}(A_{1}))\prod_{i=2}^{n}\mathbb{P}(A_{2})\\&=\mathbb{P}(A_{1}^c)\prod_{i=2}^{n}\mathbb{P}(A_{2})\end{align}$$
> 2. (2=>1): obvious.
---
> [!lemma] Theorem 2
> Let $X_{1},\dots,X_{n}$ be random variables taking values in $(E_{1},\mathcal{E}_{1}),\dots,(E_{n},\mathcal{E}_{n})$. 
> 1. $X_{1},\dots,X_{n}$ are independent if and only if $\mathbb{P}_{(X_{1},\dots,X_{n})}=\mathbb{P}_{X_{1}}\otimes\dots \otimes \mathbb{P}_{X_{n}}$.
> 2. If $X_{1},\dots,X_{n}$ are independent, $\mathbb{E}\left[ \prod_{i=1}^{n}f_{i}(X_{i}) \right]=\prod_{i=1}^{n}\mathbb{E}[f_{i}(X_{i})]$ where $f_{i}$ is a non-negative measurable function on $(E_{i},\mathcal{E}_{i})$
> 3. if $X_{1},\dots,X_{n}$ are independent and real with [[density]] $p_{i}$, then $(X_{1},\dots,X_{n})$ has density: $$p(x_{1},\dots,x_{n}):=\prod_{i=1}^{n}p_{i}(x_{i})$$
> 4. if $(X_{1},\dots,X_{n})$ has density $p$ which can be written as: $$p(x_{1},\dots,x_{n})=\prod_{i=1}^{n}q_{i}(x_{i})$$for non-negative measurable functions $q_{1},\dots,q_{n}$,  then $X_{1},\dots,X_{n}$ are independent with density $p_{i}=C_{i}q_{i}$ for some constant $C_{i}>0$.


> [!proof]-
> We have:
> 1. Let $F_{i}\in \mathcal{E}_{i}$. Then, $$\mathbb{P}_{(X_{1},\dots,X_{n})}(F_{1}\times\dots \times F_{n})=\mathbb{P}(X_{1}\in F_{1},\dots,X_{n}\in F_{n})$$On ther other hand, $$\mathbb{P}_{X_{1}}\otimes \dots \otimes \mathbb{P}_{X_{n}}(F_{1}\times\dots \times F_{n})=\prod_{i=1}^{n}\mathbb{P}_{X_{i}}(F_{i})=\prod_{i=1}^{n}\mathbb{P}(X_{i}\in F_{i})$$This proves the statement as the product measure is characterized by its values on the "box-sets".
> 2. Using Fubini, we have: $$\begin{align}\mathbb{E}\left[ \prod_{i=1}^{n}f_{i}(X_{i}) \right] &=\int_{E_{1}\times\dots \times E_{n}}f_{1}(x_{1})\dots f_{n}(x_{n}) \, d\mathbb{P}_{X_{1}}(x_{1})\dots d\mathbb{P}_{X_{n}}(x_{n}) \\&=\prod_{i=1}^{n}\int_{E_{i}}f_{i}(x_{i}) \, d\mathbb{P}_{X_{i}}(x_{i})\\&=\prod_{i=1}^{n}\mathbb{E}[f_{i}(X_{i})] \end{align}$$
> 3. From 3.
> 4. By Fubini: $$\prod_{i=1}^{n}\int_{}^{} q_{i} \, dx=\int_{\mathbb{R}^n}^{} p \, dx_{1}\dots dx_{n}=1  $$Therefore, $K_{i}:=\int q_{i}  \, dx$ is positive and finite. Then, we have by [[Density|Proposition 1]]: $$\begin{align}p_{i}(x_{i})&=\int_{\mathbb{R}^{n-1}}^{} p(x_{1},\dots,x_{n}) \, dx_{1}\dots dx_{i-1}dx_{i+1}\dots dx_{n}\\&=\left( \prod_{j\neq i}^{}K_{j} \right)q_{i}(x_{i})\\&=\frac{1}{K_{i}}q_{i}(x_{i}) \end{align}$$Hence, $p(x_{1},\dots,x_{n})=\prod_{i=1}^{n}p_{i}(x_{i})$ and $\mathbb{P}_{(X_{1},\dots,X_{n})}=\mathbb{P}_{X_{1}}\otimes\dots \otimes \mathbb{P}_{X_{n}}$. 
- **Remark**: We can extend $f_{i}$ to real- and complex measurable functions, if $\mathbb{E}[\left| f_{i}(X_{i}) \right|]<+\infty$ for all $i$.
- **Corollary**: if $X_{1},\dots,X_{n}\in L^1$ are independent, then $X_{1}\dots X_{n}\in L^1$. 
---
> [!lemma] Lemma 3
> Let $X_{1},X_{2}\in L^2$ be two independent random variables. Then,
> 1. $\text{Cov}(X_{1},X_{2})=0$.

> [!proof]-
> We have:
> 1. $\text{Cov}(X_{1},X_{2})=\mathbb{E}[X_{1}X_{2}]-\mathbb{E}[X_{1}]\mathbb{E}[X_{2}]=\mathbb{E}[X_{1}]\mathbb{E}[X_{2}]-\mathbb{E}[X_{1}]\mathbb{E}[X_{2}]=0$.
- **Remark**: The converse is not true: $\text{Cov}(X,Y)=0$ doesn't imply $X,Y$ are independent.
---
> [!lemma] Proposition 4
> Let $X,Y:\Omega\to \mathbb{R}^d$ be two independent random variables. Then, 
> 1. $\mathbb{P}_{X+Y}=\mathbb{P}_{X}*\mathbb{P}_{Y}$ where $*$ denotes the [[Convolution (Measure)|convolution]].
> 2. if $X$ has [[density]] $p_{X}$ and $Y$ has density $p_{Y}$, $X+Y$ has density $p_{X}*p_{Y}$.
> 3. for the [[characteristic function]], $\Phi_{X+Y}(\xi)=\Phi_{X}(\xi)*\Phi_{Y}(\xi)$
> 4. if $\mathbb{E}[\left| X \right|^{2}],\mathbb{E}[\left| Y \right|^{2}]<+\infty,$, the [[Covariance|covariance matrix]] $\Sigma_{X+Y}=\Sigma_{X}+\Sigma_{Y}$.
> 5. if $d=1$ and $X,Y\in L^2$, then $\text{Var}(X+Y)=\text{Var}(X)+\text{Var}(Y)$

> [!proof]-
> We have:
> 1. As $\mathbb{P}_{(X,Y)}=\mathbb{P}_{X}\otimes \mathbb{P}_{Y}$, for any non-negative measurable function $\varphi$ on $\mathbb{R}^d$, $$\int_{\mathbb{R}^d}^{} \varphi \, d\mathbb{P}_{X+Y} =\mathbb{E}[\varphi(X+Y)]=\int_{\mathbb{R}^d}^{} \int_{\mathbb{R}^d}^{} \varphi(x+y) \, d\mathbb{P}_{X}(x)  \, d\mathbb{P}_{Y}(y)=\int_{\mathbb{R}^d}^{} \varphi \, d\mathbb{P}_{X}*\mathbb{P}_{Y} $$
> 2. We have that: $$\int_{\mathbb{R}^d}^{} \int_{\mathbb{R}^d}^{} \varphi(x+y)p_{X}(x)p_{Y}(y) \, dx  \, dy=\int_{\mathbb{R}^d}^{} \varphi(z)\left( \underbrace{ \int_{\mathbb{R}^d}^{} p_{X}(x)p_{Y}(z-x) \, dx  }_{ =p_{X}*p_{Y}(z) } \right) \, dz $$
> 3. .
> 4. $\text{Cov}(X_{i}+Y_{i},X_{j}+Y_{j})=\text{Cov}(X_{i},X_{j})+\text{Cov}(Y_{i},Y_{j})$
> 5. From 4.
---
> [!lemma] Theorem 5 (Weak Law of Large Numbers)
> Let $(X_{n})_{n}$ be a sequence of i.i.d real random variables in $L^2$. Then, $$\frac{1}{n}(X_{1}+\dots+X_{n})\overset{ L^2 }{ \underset{ n\to \infty }{ \longrightarrow } }\mathbb{E}[X_{1}]$$

> [!proof]-
> By linearity, we have that: $$\mathbb{E}\left[ \frac{1}{n}(X_{1}+\dots+X_{n}) \right]=\mathbb{E}[X_{1}]$$Furthermore, by proposition 4, $\text{Var}(X_{1}+\dots+X_{n})=n\text{Var}(X_{1})$. Therefore, $$\mathbb{E}\left[ \left( \frac{X_{1}+\dots X_{n}}{n}-\mathbb{E}[X_{1}] \right) ^{2} \right]=\frac{1}{n^{2}}\text{Var}(X_{1}+\dots +X_{n})=\frac{\text{Var}(X_{1})}{n}\to 0 $$
---
> [!lemma] Theorem 6 (Conditional Expectation and Independence)
> Let $\mathcal{B}_{1},\mathcal{B}_{2}\subseteq \mathcal{A}$ be two $\sigma$-subalgebras. Then,
> 1. $\mathcal{B}_{1}$ and $\mathcal{B}_{2}$ are independent if and only if $$\mathbb{E}[\mathbb{1}_{B}|\mathcal{B}_{1}]=\mathbb{P}(B),\quad \forall B\in \mathcal{B}_{2}$$
> 2. if $\mathcal{B}_{1}$ and $\mathcal{B}_{2}$ are independent, for every non-negative $\mathcal{B}_{2}$-measurable random variable $X$ and for every $X\in L^1(\Omega,\mathcal{B}_{2},\mathbb{P})$, $$\mathbb{E}[X|\mathcal{B}_{1}]=\mathbb{E}[X]$$
> 3. for $X\in L^1(\Omega,\mathcal{A},\mathbb{P})$, if $\mathcal{B}_{1}$ is independent of $\sigma(\sigma(X),\mathcal{B}_{2})$, then: $$\mathbb{E}[X|\sigma(\mathcal{B}_{1},\mathcal{B}_{2})]=\mathbb{E}[X|]$$

> [!proof]-
> We have:
> 1. The forward direction is shown in 2. Conversely, if $\mathbb{E}[\mathbb{1}_{B}|\mathcal{B}_{1}]=\mathbb{P}(\mathcal{B})$ for all $B\in \mathcal{B}_{2}$, then for all $A\in \mathcal{B}_{1}$ and $B\in \mathcal{B}_{2}$, $$\mathbb{P}(A\cap B)=\mathbb{E}[\mathbb{1}_{A}\mathbb{1}_{B}]=\mathbb{E}[\mathbb{1}_{A}\mathbb{E}[\mathbb{1}_{B}|\mathcal{B}_{1}]]=\mathbb{E}[\mathbb{1}_{A}\cdot \mathbb{P}(B)]=\mathbb{P}(A)\cdot \mathbb{P}(B)$$which shows the independence.
> 2. Let $\mathcal{B}_{1}$ and $\mathcal{B}_{2}$ be independent. Let $X$ be a non-negative $\mathcal{B}_{2}$-measurable random variable. Then, for every non-negative $\mathcal{B}_{1}$-measurable random variable $Z$, $Z$ and $X$ are independent and thus: $$\mathbb{E}[ZX]=\mathbb{E}[Z]\mathbb{E}[X]=\mathbb{E}[Z\mathbb{E}[X]]$$Therefore, $\mathbb{E}[X]=\mathbb{E}[X|\mathcal{B}_{1}]$. If $X$ is integrable, by setting $X=X^+-X^-$, we get the same result.
- **Corollary**:  Two real random variables $X,Y$ are independent if and only if for every Borel $h:\mathbb{R}\to \mathbb{R}$ s.t. $\mathbb{E}[\left| h(X) \right|]<\infty$, $$\mathbb{E}[h(X)|Y]=\mathbb{E}[h(X)]$$
- **Corollary**: if $X,Y$ are independent $\mathbb{E}[X|Y]=\mathbb{E}[X]$. But the converse is not always true. 
---
##### Examples
##### Non-Examples
> [!h] Non-Example
> Consider two coin throws of a fair coin and the three events:
> 1. $A_{1}:=$ getting heads in the first trial.
> 2. $A_{2}:=$ getting heads in the second trial.
> 3. $A_{3}:=$ getting the same outcome in both trials.
> 
> Then, 
> 1. $A_{1},A_{2},A_{3}$ are pairwisely independent.
> 2. $A_{1},A_{2},A_{3}$ are not independent as $\mathbb{P}(A_{1}\cap A_{2}\cap A_{3})=\frac{1}{4}\neq \frac{1}{8}=\mathbb{P}(A_{1})\mathbb{P}(A_{2})\mathbb{P}(A_{3})$.
---