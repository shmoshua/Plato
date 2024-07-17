#Definition #Algebra 

> [!definition]
> Let $K$ be a [[field]] and $F\subseteq K$ a subfield. Then, $K$ is an ***extension*** of $F$ and is denoted as $K:F$.
- **Related definition**: For $K:F$ and $A\subseteq K$, we have:
	1. $F[A]:=$ intersection of all subrings of $K$ that contain $F,A$.
	2. $F(A):=$ intersection of all subfields of $K$ that contain $F,A$.
- **Related definition**: An extension $K:F$ is ***simple*** if there exists $a\in K$ s.t. $K=F(a)$. Then, $a$ is called the ***primitive element***.
- **Related definition**: If $L:K$ and $K:F$, then $K$ is the ***intermediate field*** of $L:F$.
- **Related definition**: The ***degree*** of extension $K:F$ is denoted as $[K:F]:=\text{dim}_{F} K$ as a $F$-vector space. (cf. Lemma 1)
- **Related definition**: An extension $K:F$ is ***finitely generated*** if there exists $\alpha_{1},\dots,\alpha_{n}\in K$ s.t. $K=F(\alpha_{1},\dots,\alpha_{n})$.
---
##### Properties
> [!lemma] Lemma 1
> For a field extension $K:F$, $K$ is a [[Vector Space|$F$-vector space]].

> [!proof]-
> We have $(K,+,0)$ as an abelian group. Further, $$\begin{array}{cccc} &{F\times K}&\to&{K}\\&{(\lambda,x)} &\mapsto & {\lambda x} \end{array}{}$$defines the scalar multiplication s.t. $(\lambda+\mu)x=\lambda x+\mu x$, $\lambda(x+y)=\lambda x+\lambda y$ and $(\lambda \mu)x=\lambda(\mu x)$ and $1x=x$.
---
> [!lemma] Theorem 2 (Dimension behaves multiplicatively)
> If $K$ is an intermediate field of a field extension $L:F$, then: $$[L:F]=[L:K][K:F]$$

> [!proof]-
> We have:
> 1. If $[K:F]=\infty$, then there are infinitely many linearly independent vectors in $K$ and thereby in $L$. Hence, $[L:F]=\infty$ as well.
> 2. If $[L:K]=\infty$, then there are infinitely many vectors linearly independent over $K$ and therefore linearly independent over $F$. 
> 3. If $[L:K], [K:F]<+\infty$, then let $\{ x_{1},\dots,x_{n} \}$ be the basis of $K:F$ and $y_{1},\dots,y_{m}$ the basis of $L:K$. We will show that: $$\{ x_{i}y_{j}: i\in[n],j\in [m] \}$$is a basis of $L:F$.
> 	- **Showing that they are generating**:
> 	  Let $y\in L$. Then, $y=\sum_{j=1}^{m}b_{j}y_{j}$ with $b_{j}\in K$. Therefore, for all $j\in [m]$, $b_{j}=\sum_{i=1}^{n}a_{ij}x_{i}$ with $a_{ij}\in F$. It follows that: $$y=\sum_{i=1}^{n}\sum_{j=1}^{m}a_{ij}x_{i}y_{j}$$
>    - **Showing that they are linearly independent**:
> 	   Assume that $\sum_{i=1}^{n}\sum_{j=1}^{m}a_{ij}x_{i}y_{j}=0$. As $y_{j}$'s are linearly independent, $\sum_{i=1}^{n}a_{ij}x_{i}=0$ for all $j\in [m]$. Then, by linear independence of $x_{i}$, $a_{ij}=0$ for all $i,j$.
---
> [!lemma] Theorem 3 (Kronecker)
> Let $F$ be a field and $p\in F[X]$. Then, 
> 1. if $p$ is irreducible, there exists a field $K$ containing an isomorphic copy of $F$ in which $p(x)$ has a root.
> 2. if $p$ is non-constant, there exists a field $K$ containing an isomorphic copy of $F$ in which $p(x)$ has a root.

> [!proof]-
> We have:
> 1. Since $p$ is irreducible, $I:=(p)$ is maximal in the ED $F[X]$. Let $K:=F[X] / I$ which is a field. Then, for the canonical projection: $$\pi:F[X]\to F[X] / I,\quad q\mapsto q+I$$ The restriction $\pi|_{F}$ gives a field homomorphism. As all field homomorphisms are injective, $F\cong \pi(F)\subseteq K:=F[X] / I$ and $K$ contains an isomorphic copy of $F$.
>    
>    Now, we show that $K$ has a root of $p$. Let $\alpha:=x+I\in K$. Then, for $p(x):=a_{0}+a_{1}x+\dots+a_{n}x^n$, $$\begin{align}p(\alpha)&=a_{0}+a_{1}x+\dots+a_{n}x^n+I\\&=p(x)+(p)\\&=(p)\end{align}$$
> 2. If $p$ is not irreducible, then let $p=q_{1}\dots q_{r}$. If any of $q_{i}$ is linear, i.e. $q_{i}(x)=(ax-b)$, then $b/a\in F$ and $K=F$ already satisfies the statement.
>    
>    If they are all at least quadratic, choose $q_{i}$ and use 1 and take $K:=F[X] / (q_{i})$ where we have $\alpha:=x+(q_{i})$ as a root of $q_{i}$ and thereby of $p$.
---
> [!lemma] Theorem 4 (Kronecker, extended)
> Let $p(x)\in F[X]$ be an irreducible polynomial of degree $n$ over a field $F$. Let $K:=F[X] / (p(x))$ and $\alpha:=x+(p(x))$. Then, 
> 1. $1,\alpha,\alpha^{2},\dots,\alpha^{n-1}$ forms a basis of $K$ as a $F$-vector space.
> 2. $[K:F]=n$
> 3. We have: $$K=\{ a_{0}+a_{1} \alpha+\dots+a_{n-1}\alpha^{n-1}:a_{i}\in F\}=F_{n-1}[\alpha]=F(\alpha)$$where $F_{n-1}$ is the set of polynomials of degree $\leq n-1$.

> [!proof]-
> For any $f(x)\in F[X]$ as $F[X]$ is a ED, we get that: $$f(x)=p(x)q(x)+r(x)$$where $\deg r<\deg p$. Therefore, $f(x)+(p(x))=r(x)+(p(x))$ where $\deg r<n$. 
> 
> Now, if $1,\alpha,\dots,\alpha^{n-1}$ were linearly dependent in $K$, then there would be $b_{0},\dots,b_{n-1}$ in $F$, not all zero, s.t. $$g(x)+(p):=b_{0}+b_{1}\alpha+\dots+b_{n-1}\alpha^{n-1}=0_{K}$$Therefore, $g\in (p)$ and $p|g$. But this is impossible as $\deg p=n>n-1=\deg q$. It follows that they form a basis in $K$.
> 
> Note that $K=F_{n-1}[\alpha]\subseteq F(\alpha)$. However, as $F(\alpha)$ is the smallest field that contains $F$ and $\alpha$, $F_{n-1}[\alpha]\supseteq F(\alpha)$ and $K=F(\alpha)$.
---
> [!lemma] Theorem 5
> Let $F$ be a field and $p(x)\in F[X]$ an irreducible polynomial. 
> 1. for any field extension $L:F$ with a root $\alpha$ of $p(x)$, $$F[X] / (p(x))\cong F(\alpha)\subseteq L$$

> [!proof]-
> Consider the following homomorphism. $$\begin{array}{cccc} {\varphi:}&{F[X]}&\to&{F(\alpha)\subseteq L}\\&{f(x)} &\mapsto & {f(\alpha)} \end{array}{}$$ As $(p(x))\subseteq \text{ker }\varphi$, this induces a unique homomorphism: $\overline{\varphi}:F[X] / (p(x))\to F(\alpha)$.  As this is a field homomorphism, it is injective and $F[X] / (p(x))\cong \text{Im}(\overline{\varphi})\subseteq F(\alpha)$. However, as the image contains $F$ and $\alpha$, $F[X] / (p(x))\cong F(\alpha)$.
---
> [!lemma] Theorem 6 (Isomorphism of Extensions)
> Let $\varphi:F\to \tilde{F}$ be a field isomorphism and $p(x)=a_{0}+a_{1}x+\dots+a_{n}x^n\in F[X]$ be irreducible. 
> 1. For $\tilde{p}(x):=\varphi(a_{0})+\varphi(a_{1})x+\dots+\varphi(a_{n})x^n\in \tilde{F}[X]$, $\alpha$ root of $p$ in some extension of $F[X]$, $\beta$ the root of $\tilde{p}(x)$ in some extension of $\tilde{F}[X]$, there exists a field isomorphism $\sigma:F(\alpha)\to \tilde{F}(\beta)$ that extends $\varphi$ and $\sigma(\alpha)=\beta$.

> [!proof]-
> We have that $\varphi:F\to \tilde{F}$ induces an isomorphism of polynomial rings: $$\varphi:F[X]\to \tilde{F}[X],\quad b_{0}+b_{1}x+\dots+b_{n}x^n\mapsto\varphi(b_{0})+\varphi(b_{1})x+\dots+\varphi(b_{n})x^n$$Therefore, $\tilde{p}$ is irreducible and $\varphi$ induces the isomorphism of fields: $$F[X] / (p(x))\cong \tilde{F}[X] / (\tilde{p}(x))$$Then, by Theorem 5, $F(\alpha)\cong F[X] / (p(x))\cong \tilde{F}[X] / (\tilde{p}(x))\cong \tilde{F}(\beta)$ given by: $$\sigma:F(\alpha)\to \tilde{F}(\beta),\quad \sum_{i=1}b_{i}\alpha^i\mapsto \sum_{i=1}\varphi(b_{i})\beta^i$$
> 
---
> [!lemma] Lemma 7
> Let $f,g\in F[X]$. then, 
> 1. $f,g$ are relatively prime if and only if $f,g$ have no common root in any extension of $F$.
> 2. if $f,g$ are distinct monic irreducible polynomials, then they have no common root in any extension of $F$.

> [!proof]-
> We have:
> 1. Let $(f,g)=1$ in $F[X]$. Then, there exists $a,b\in F[X]$ s.t. $a(x)f(x)+b(x)g(x)=1$. Let $K:F$ be an extension where $\alpha$ is a common root of $f,g$ in $K[X]$. Then, $$0=a(\alpha)f(\alpha)+b(\alpha)g(\alpha)=1$$which is a contradiction. Conversely, $(f,g)=(h)$ for some $h\in F[X]$. Then, $h|f$ and $h|g$ and if $h\neq 1$, then $h$ is non-constant and by Kronecker, there exists a field extension $K:F$ where $h$ has a root $\alpha$. Then, $(x-\alpha)$ divides $h$ in $K$ and thereby $f$ and $g$. Therefore, $\alpha$ is a root of both $f,g$.
> 2. We will show that $f,g$ are relatively prime. Assume that $(f,g)=(h)$ where $h|f$ and $h|g$. As $f,g$ are irreducible, $\deg(h)=0$ or $\deg(h)=\deg(f)$. If $\deg(h)=0$, then $(h)=(1)$ and $f,g$ are relatively prime. Otherwise, as $\deg(f),\deg(g)\geq 1$, $\deg(f)=\deg(h)=\deg(g)$. Therefore, $f(x)=ah(x)$ and $g(x)=bh(x)$ for some $a,b\in F$. However, as $f,g$ are both monic, $a=b$, which is a contradiction.
---
> [!lemma] Theorem 8
> An extension $K:F$ is finite, i.e. $[K:F]<+\infty$ if and only if there exists $\alpha_{1},\dots,\alpha_{n}\in K$ algebraic over $F$ s.t. $$K=F(\alpha_{1},\dots,\alpha_{n})$$

> [!proof]-
> Assume that $[K:F]=n$. Then, there exists a basis $\alpha_{1},\dots,\alpha_{n}\in K$ that generates $K$. Furthermore, $\alpha_{i}$ is algebraic as $K:F(\alpha_{i}):F$ and $[F(\alpha_{i}):F]$ is finite by [[Algebraic and Transcendental Element|Prop 2]].
> 
> Conversely, if there exists $\alpha_{1},\dots,\alpha_{n}\in K$ algebraic over $F$ s.t. $K=F(\alpha_{1},\dots,\alpha_{n})$, we have that: $$[K:F]=[F(\alpha_{1}):F]\prod_{i=2}^{n}[F(\alpha_{1},\dots,\alpha_{i}):F(\alpha_{1},\dots,\alpha_{i-1})]$$which is finite as a finite product.
---
> [!lemma] Theorem 9 (Finite Extensions are Simple in char 0)
> Let $F$ be a field s.t. $\text{char }F=0$. Then, every finite extension $K:F$ is simple, i.e. there exists $\alpha\in K$ s.t. $K=F(\alpha)$.

> [!proof]-
> Since $[K:F]$ is finite, we have that $K=F(\alpha_{1},..,\alpha_{n})$ for some $\alpha_{i}\in K$. We will use induction on $n$. 
> 
> If $n=1$, the statement holds automatically. it suffices to prove the claim for $n=2$. So assume $K=F(a,b)$ and let $f,g$ be the minimal polynomial of $a,b$ respectively over $F$. Let $M:F$ be the field extension of $F$ where $f,g$ both split. 
> 
> Let $a=:x_{1},\dots,x_{r}$ be the roots of $f$ and $b=:y_{1},\dots,y_{s}$ be the roots of $g$. As $\text{char } F=0$, $g$ has distinct roots per [[Separable Extension|Theorem 3]] and $b\neq y_{j}$ for all $j\neq 1$. If we define: $$z_{ij}:=\frac{x_{i}-a}{b-y_{j}}\in M$$then $z_{ij}$ is the only element of $M$ which solves: $a+tb=x_{i}+ty_{j}$. Since $F$ is infinite, we can choose $z\in F$ different from all $z_{ij}$ s.t. $$a+zb\neq x_{i}+zy_{j}$$unless $i,j=1$. Then, for $c:=a+zb$, $F(c)\subseteq F(a,b)$. 
> 
> Now, define $h(x):=f(c-zx)\in F(c)[X]$. Then, $h(b)=f(c-zb)=f(a)=0$. Since $b$ is also a root of $g$, $(x-b)|g$ and $(x-b)|h$.
> 
> Since $g$ splits over $M$, $\text{gcd}(g,h)$ must be a product of linear factors. However, for $j\neq 1$, $$h(y_{j})=f(c-zy_{j})\neq 0$$as $c-zy_{j}\neq x_{i}$ for any $i$. Therefore, $(x-y_{j})\nmid h(x)$ and $\text{gcd}(g,h)=(x-b).$ In other words, $b\in F(c)$ and consequently, $a\in F(c)$. This shows that $F(c)=F(a,b)$.
> 
---
##### Examples
> [!h] Example 1
> We have that:
> 1. $\mathbb{R}:\mathbb{Q}$
> 2. $\mathbb{C}:\mathbb{R}$
> 3. $\mathbb{C}:\mathbb{Q}$ with $\mathbb{R}$ as intermediate field.
---
> [!h] Example 2 (Complex Numbers)
> Let $F:=\mathbb{R}$ and $p(x):=x^{2}+1$. 
> 1. $x^2+1$ is irreducible in $\mathbb{R}[X]$ as it has no zeros.
> 2. By Kronecker, it as a root in $K:=\mathbb{R} [X] / (x^2+1)$ given by $\alpha:=x+(x^{2}+1)$ and: $$K=\{ a+b\alpha:a,b\in \mathbb{R} \}$$for which it holds that:
> 	1. $(a+b\alpha)+(c+d\alpha)=(a+c)+(b+d)\alpha$
> 	2. $(a+b\alpha)(c+d\alpha)=ac+(ad+bc)\alpha+bd\alpha^{2}=(ac-bd)+(ad+bc)\alpha$
> 3. Therefore, there exists an isomorphism: $$\begin{array}{cccc} {\varphi:}&{\mathbb{R} [X] / (X^{2}+1)}&\to&{\mathbb{C}}\\&{a+b\alpha} &\mapsto & {a+bi} \end{array}{}$$
---
> [!h] Example 4 (Finding Inverses)
> Let $p(x)=x^{3}-2\in \mathbb{Q}[X]$.
> 1. $p$ is irreducible by [[Unique Factorization Domain|Eisenstein]]. 
> 2. By Kronecker, $p$ has a root in $K:=\mathbb{Q}[X] / (x^3-2)$ given by $\alpha:=x+(x^3-2)$. with: $$K=\{ a+b\alpha +c\alpha^{2}:a,b,c\in \mathbb{Q}\}$$
> 3. $p$ is irreducible hence relatively prime to any polynomial of lower degree.
> 4. $(1-\alpha)^{-1}=-\alpha^{2}-\alpha-1$
> 5. $(\alpha^2+1)^{-1}=\left( \frac{1}{5}+\frac{2}{5}\alpha-\frac{\alpha^{2}}{5} \right)$
> 6. For the three roots $\sqrt[3]{2  },\sqrt[3]{2  }\left( \frac{-1+i\sqrt{ 3 }}{2} \right),\sqrt[3]{2  }\left( \frac{-1-i\sqrt{ 3 }}{2} \right)$, $$\mathbb{Q}(\sqrt[3]{2  })\cong \mathbb{Q}\left( \sqrt[3]{2  }\left( \frac{-1+i\sqrt{ 3 }}{2} \right) \right)\cong\mathbb{Q}\left( \sqrt[3]{2  }\left( \frac{-1-i\sqrt{ 3 }}{2} \right) \right)\cong \mathbb{Q}[X] / (x^3-2)$$

> [!proof]-
> For 4, we have that $(1-x,x^3+1)=1$ and there exists $a,b\in \mathbb{Q}[X]$ s.t. $$a(x)(1-x)+b(x)(x^3-2)=1$$Therefore, $a(x)(1-x)=1+(x^3+1)$ in $K$ and $a=(1-x)^{-1}$ in $K$. Especially,
> $$\begin{align}x^{3}-2&=(-x^{2}-x-1)(1-x)-1\end{align}$$Therefore, $(1-\alpha)^{-1}=(-\alpha^{2}-\alpha-1)$.
> 
> For 5, we can use the euclidean algorithm to get: $$\begin{align}x^3-2&=x(x^2+1)+(-x-2)\\(x^2+1)&=(-x+2)(-x-2)+5\end{align}$$Then, $$\begin{align}5&=(x^2+1)-(-x+2)(-x-2)\\&=(x^2+1)-(-x+2)((x^3-2)-x(x^2+1))\\&=(1+2x-x^2)(x^2+1)+(x-2)(x^3-2)\end{align}$$and $1=(x^2+1)\left( \frac{1}{5}+\frac{2}{5}x-\frac{x^2}{5} \right)+\left( \frac{x}{5}-\frac{2}{5} \right)(x^3-2)$ and: $$(\alpha^{2}+1)^{-1}=\left( \frac{1}{5}+\frac{2}{5}\alpha-\frac{\alpha^{2}}{5} \right)$$
---
