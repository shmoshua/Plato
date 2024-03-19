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
> [!lemma] Theorem 4
> Let $p(x)\in F[X]$ be an irreducible polynomial of degree $n$ over a field $F$. Let $K:=F[X] / (p(x))$ and $\alpha:=x+(p(x))$. Then, 
> 1. $1,\alpha,\alpha^{2},\dots,\alpha^{n-1}$ forms a basis of $K$ as a $F$-vector space.
> 2. $[K:F]=n$
> 3. We have: $$K=\{ a_{0}+a_{1} \alpha+\dots+a_{n-1}\alpha^{n-1}:a_{i}\in F\}=F_{n-1}[\alpha]=F(\alpha)$$

> [!proof]-
> For any $f(x)\in F[X]$, using the euclidean algorithm we get that: $$f(x)=p(x)q(x)+r(x)$$where $\deg r<\deg p$. Therefore, $f(x)+(p(x))=r(x)+(p(x))$ where $\deg r<n$. 
> 
> Now, if $1,\alpha,\dots,\alpha^{n-1}$ were linearly dependent in $K$, then there would be $b_{0},\dots,b_{n-1}$ in $F$, not all zero, s.t. $$g(\alpha)+(p(x)):=b_{0}+b_{1}\alpha+\dots+b_{n-1}\alpha^{n-1}=0_{K}$$Therefore, $g(x)\in (p(x))$ and $p(x)|g(x)$. But this is impossible as $\deg p=n>n-1=\deg q$. It follows that they form a basis in $K$.
> 
> Note that $K=F_{n-1}[\alpha]\subseteq F(\alpha)$. However, as $F(\alpha)$ is the smallest field that contains $F$ and $\alpha$, $F_{n-1}[\alpha]\supseteq F(\alpha)$ and $K=F(\alpha)$.
---
> [!lemma] Theorem 5
> Let $F$ be a field and $p(x)\in F[X]$ an irreducible polynomial. For any field extension $L:F$ with a root $\alpha$ of $p(x)$, $$F[X] / (p(x))\cong F(\alpha)\subseteq L$$

> [!proof]-
> Consider the following homomorphism. $$\begin{array}{cccc} {\varphi:}&{F[X]}&\to&{F(\alpha)\subseteq L}\\&{f(x)} &\mapsto & {f(\alpha)} \end{array}{}$$ As $(p(x))\subseteq \text{ker }\varphi$, this induces a unique homomorphism: $\overline{\varphi}:F[X] / (p(x))\to F(\alpha)$.  As this is a field homomorphism, it is injective and $F[X] / (p(x))\cong \text{Im}(\overline{\varphi})\subseteq F(\alpha)$. However, as the image contains $F$ and $\alpha$, $F[X] / (p(x))\cong F(\alpha)$.
---
> [!lemma] Theorem 6
> Let $\varphi:F\to \tilde{F}$ be a field isomorphism and $p(x)\in F[X]$ be irreducible. Let $\tilde{p}(x)\in \tilde{F}[X]$ be the irreducible polynomial obtained by applying $\varphi$ to the coefficients of $p$. If $\alpha$ is the root of $p(x)$ in some extension of $F[X]$ and $\beta$ is the root of $\tilde{p}(x)$ in some extension of $\tilde{F}[X]$. Then, there exists an isomorphism $\sigma:F(\alpha)\to \tilde{F}(\beta)$ s.t. 
> 1. $\sigma|_{F}=\varphi$ and
> 2. $\sigma(\alpha)=\beta$.

> [!proof]-
> We get an isomorphism $F(\alpha)\cong F[X] / (p(x))\cong \tilde{F}[X] / (\tilde{p} (x))\cong \tilde{F} (\beta)$. 
---
> [!lemma] Lemma 7
> Let $f,g\in F[X]$. then, 
> 1. $f,g$ are relatively prime if and only if $f,g$ have no common root in any extension of $F$.
> 2. if $f,g$ are distinct monic irreducible polynomials, then they have no common root in any extension of $F$.
---
##### Examples
> [!h] Example 1
> We have that:
> 1. $\mathbb{R}:\mathbb{Q}$
> 2. $\mathbb{C}:\mathbb{R}$
> 3. $\mathbb{C}:\mathbb{Q}$ with $\mathbb{R}$ as intermediate field.
---
> [!h] Example 2 (Kronecker)
> For $p(x)=x^2+1\in \mathbb{R}[X]$, there is no zeros in $\mathbb{R}$. However, in $K:=\mathbb{R}[X] / (X^{2}+1)$, $\alpha:=X+(X^{2}+1)\in K$ is a root as: $$\alpha^{2}+1=X^{2}+(X^{2}+1)+1+(X^{2}+1)=0_{K}$$
---
> [!h] Example 3 (Complex Numbers)
> Let $F:=\mathbb{R}$ and $p(x):=x^{2}+1$ with $\alpha=x+(x^{2}+1)$. Then, for $$K=\mathbb{R}[X] / (X^{2}+1)=\{ a+b\alpha:a,b\in \mathbb{R} \}$$
> 1. $(a+b\alpha)+(c+d\alpha)=(a+c)+(b+d)\alpha$
> 2. $(a+b\alpha)(c+d\alpha)=ac+(ad+bc)\alpha+bd\alpha^{2}=(ac-bd)+(ad+bc)\alpha$
> 3. Therefore, there exists an isomorphism: $$\begin{array}{cccc} {\varphi:}&{\mathbb{R} [X] / (X^{2}+1)}&\to&{\mathbb{C}}\\&{a+b\alpha} &\mapsto & {a+bi} \end{array}{}$$
---
> [!h] Example 4 (Finding Inverses)
> Let $p(x)=x^{3}-2\in \mathbb{Q}[X]$ which is irreducible by [[Unique Factorization Domain|Eisenstein]]. 
> 1. $(1-\alpha)^{-1}=-\alpha^{2}-\alpha-1$

> [!proof]-
> We have that:
> $$\begin{align}x^{3}-2&=(-x^{2}-x-1)(1-x)-1\end{align}$$Therefore, $(1-\alpha)^{-1}=(-\alpha^{2}-\alpha-1)$.
---
