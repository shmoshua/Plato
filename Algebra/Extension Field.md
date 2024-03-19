#Definition #Algebra 

> [!definition]
> Let $K$ be a [[field]] and $F\subseteq K$ a subfield. Then, $K$ is called an ***extension*** of $F$ denotes as $K:F$ or $K / F$.
- **Related definition**: For $K:F$ and $A\subseteq K$, we have:
	1. $F[A]:=$ intersection of all subrings of $K$ that contain $F,A$.
	2. $F(A):=$ intersection of all subfields of $K$ that contain $F,A$.
- **Related definition**: An extension $K:F$ is ***simple*** if there exists $a\in K$ s.t. $K=F(a)$. Then, $a$ is called the ***primitive element***.
- **Related definition**: If $L:K$ and $K:F$, then $K$ is the ***intermediate field*** of $L:F$.
- **Related definition**: The ***degree*** of extension $K:F$ is denoted as $[K:F]:=\text{dim}_{F} K$ as a $F$-vector space. (cf. Lemma 1)
---
##### Properties
> [!lemma] Lemma 1
> For a field extension $K:F$, $K$ is a [[Vector Space|$F$-vector space]].

> [!proof]-
> We have $(K,+,0)$ as an abelian group. Further, $$\begin{array}{cccc} &{F\times K}&\to&{K}\\&{(\lambda,x)} &\mapsto & {\lambda x} \end{array}{}$$defines the scalar multiplication.
---
> [!lemma] Theorem 2 (Dimension behaves multiplicatively)
> If $K$ is an intermediate field of a field extension $L:F$, then: $$[L:F]=[L:K][K:F]$$

> [!proof]-
> We have: 
> 1. **Case 1: $[K:F]=\infty$**:
>    Then, there are infinitely many linearly independent vectors in $K$ and thereby in $L$. Therefore, the dimension of $[L:F]$ is also infinite.
> 2. **Case 2: $[L:K]=\infty$**:
>    Then, there are infinitely many vectors linearly independent over $K$ and thereby over $F$. 
> 3. **Case 3: $[L:K],[K:F]<+\infty$**:
>    Let $\{ x_{1},\dots,x_{n} \}$ be the basis of $K / F$ and $\{ y_{1},\dots,y_{m} \}$ be a basis of $L / K$. Then, we show that: $$\{ x_{i}y_{j}: i\in [n],j\in [m] \}$$is a basis of $L / F$.
>    - **Showing that they are generating**:
> 	  Let $y\in L$. Then, $y=\sum_{j=1}^{m}b_{j}y_{j}$ with $b_{j}\in K$. Therefore, for all $j\in [m]$, $b_{j}=\sum_{i=1}^{n}a_{ij}x_{i}$ with $a_{ij}\in F$. It follows that: $$y=\sum_{i=1}^{n}\sum_{j=1}^{m}a_{ij}x_{i}y_{j}$$
>    - **Showing that they are linearly independent**:
> 	   Assume that $\sum_{i=1}^{n}\sum_{j=1}^{m}a_{ij}x_{i}y_{j}=0$. As $y_{j}$'s are linearly independent, $\sum_{i=1}^{n}a_{ij}x_{i}=0$ for all $j\in [m]$. Then, by linear independence of $x_{i}$, $a_{ij}=0$ for all $i,j$.
---
> [!lemma] Theorem 3 (Kronecker)
> Let $F$ be a field and $p(x)\in F[X]$ an [[Integral Domain|irreducible]] polynomial. Then, there exists a field $K$ containing an isomorphic copy of $F$ in which $p(x)$ has a root.

> [!proof]-
> Since $p(x)$ is irreducible, $I:=(p(x))$ is maximal in the PID $F[X]$. Let $K:=F[X] / I$. Then, $K$ is a field and for the following canonical map: $$\begin{array}{cccc} {\pi:}&{F[X]}&\to&{F[X] / I}\\&{q} &\mapsto & {q+I} \end{array}{}$$the restriction $\pi|_{F}$ gives a field homomorphism, which is injective by [[Field|Lemma 5]]. Therefore, $F\cong \pi(F)\subseteq K$ and $K$ contains an isomorphic copy of $F$. 
> 
> Now, we show that $K$ has a root of $p(x)$. Let $\alpha:=x+I\in K$. Then, for $p(x):=a_{0}+a_{1}x+\dots+a_{n}x^n$, $$\begin{align}p(\alpha)&=a_{0}+a_{1}x+\dots+a_{n}x^n +I\\&=p(x)+(p(x))\\&=0_{K}\end{align}$$
---
##### Examples
> [!h] Example 1
> We have that:
> 1. $\mathbb{R}:\mathbb{Q}$
> 2. $\mathbb{C}:\mathbb{R}$
> 3. $\mathbb{C}:\mathbb{Q}$ with $\mathbb{R}$ as intermediate field.
---
> [!h] Example 2 (Kronecker)
> For $p(x)=x^2+1\in \mathbb{R}[X]$, 