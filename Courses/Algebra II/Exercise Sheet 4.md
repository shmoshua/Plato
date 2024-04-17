#Series #Algebra 

> [!def] Problem 1
> Let $F\subseteq K\subseteq L$ be fields. Show that $L:F$ is an algebraic extension if and only if $L:K$ and $K:F$ are algebraic.

Let $L:F$ be algebraic. Then, $K:F$ is algebraic by definition and for $\alpha\in L$, $\alpha$ is algebraic over $F$ and thereby $K$. This shows that both $L:K$ and $K:F$ are algebraic.

Conversely, if $L:K$ and $K:F$ are algebraic. Let $\alpha\in L$. Then, $\alpha$ is algebraic over $K$ and therefore, there exists a polynomial $$p(x)=a_{0}+a_{1}\alpha+\dots+a_{n}\alpha^n\in K[X]$$As $a_{i}$ is algebraic over $F$ for all $i$, we have: $[F(a_{0},a_{1},\dots,a_{n}):F]<+\infty$. Therefore, $$[F(a_{0},a_{1},\dots,a_{n},\alpha):F]=[F(a_{0},a_{1},\dots,a_{n},\alpha):F(a_{0},\dots,a_{n})][F(a_{0},\dots ,a_{n}):F]<+\infty$$Therefore, $\alpha$ is algebraic over $F$.

---
> [!def] Problem 2
> Let $L:K$ be an algebraic field extension. Prove that every subring $R$ of $L$ which contains $K$ is a field. Give a counter-example in the case that the extension is not algebraic.

Let $0\neq r\in R$. Then, $r\in L$ and there exists a minimal polynomial $m_{\alpha,K}(x):=x^n+a_{n-1}x^{n-1}+\dots+a_{0}$. By minimality $a_{0}$ is non-zero and there exists an inverse $a_{0}^{-1}$. Therefore, $$r \cdot \frac{r^{n-1}+a_{n-1}r^{n-2}+\dots+a_{1}}{-a_{0}^{-1}}=1$$ This proves the statement.

---
> [!def] Problem 3
> We have: 
> 1. Let $F$ be a field and $a\in \overline{\mathbb{Q}}$ that generates a field extension of $F$ of degree $7$. Prove that $a^{2}$ generated the same extension.
> 2. Prove that part 3.a holds for $7$ replaced by any odd integer.

We have that $[F(a):F]=7$. Firstly, we have that $F(a^{2})\subseteq F(a)$. However, we have that $[F(a):F(a^{2})]$ divides $[F(a):F]=7$. As $a\notin F$, $F(a^{2})=F(a)$.

Further, if $[F(a):F(a^{2})]$ divides any odd integer, $[F(a):F(a^{2})]$ is odd itself. Notice that $m_{a,F(a^{2})}|x^{2}-a^{2}$. Therefore, the degree is an odd integer of degree less than $2$. Therefore, $[F(a):F(a^{2})]=1$ and $F(a)=F(a^{2})$.

---
> [!def] Problem 4
> Let $p$ and $q$ be two distinct primes. Prove that $\mathbb{Q}(\sqrt{ p })$ and $\mathbb{Q}(\sqrt{ q })$ are isomorphic as vector spaces over $\mathbb{Q}$ but not as fields.

The minimal polynomials of $\sqrt{ p }$ and $\sqrt{ q }$ are $x^{2}-p$ and $x^{2}-q$. As both have degree 2, $\mathbb{Q}(\sqrt{ p })$ and $\mathbb{Q}(\sqrt{ q })$ are isomorphic as $\mathbb{Q}$-vector spaces.

Conversely, assume that there exists a field isomorphism: $$\begin{array}{cccc} {\varphi:}&{\mathbb{Q}(\sqrt{ p })}&\to&{\mathbb{Q}(\sqrt{ q })}\end{array}{}$$Then, $\varphi(1)=1$ and $$\varphi(\sqrt{ p })^{2}=\varphi(p)=p\cdot \varphi(1)=p$$Therefore, there exists $x=a+b \sqrt{ q }\in \mathbb{Q}(\sqrt{ q })$ with $$x^{2}=a^{2}+b ^{2} q+2ab \sqrt{ q }=p$$If $a=0$, then $b ^{2}q=p$ which is impossible. If $b=0$, then $a^{2}=p$ which is again not possible. This is a contradiction.

---
> [!def] Problem 5
> Let $x:=\sqrt{ 2 }+\sqrt[3]{3  }$. 
> 1. Prove that $\mathbb{Q}(x)=\mathbb{Q}(\sqrt{ 2 },\sqrt[3]{3  })$.
> 2. Compute the minimal polynomial of $x$ over $\mathbb{Q}(\sqrt{ 2 })$.
> 3. Compute the minimal polynomial of $x$ over $\mathbb{Q}$.

We have: 
1. $\mathbb{Q}(x)\subseteq \mathbb{Q}(\sqrt{ 2 },\sqrt[3]{3  })$ by definition. Then, let $y:=\sqrt[3]{3  }=x-\sqrt{ 2 }$. Then, $(x-\sqrt{ 2 })^3=3$ and $$(x^{3}+6x-3)=(3x^{2}+2)\sqrt{ 2 }$$Therefore, $\sqrt{ 2 }\in \mathbb{Q}(x)$.
2. Let $f(x):=x^{3}-3\sqrt{ 2 }x^{2}+6x-2\sqrt{ 2 }-3\in \mathbb{Q}(\sqrt{ 2 })[X]$. We will show that this is the minimal polynomial of $x$ over $\mathbb{Q}(\sqrt{  2})$, i.e. $[\mathbb{Q}(x):\mathbb{Q}(\sqrt{ 2 })]=3$. This can be shown by showing that the minimal polynomial of $\sqrt[3]{ 3 }$ over $\mathbb{Q}(\sqrt{ 2 })$ has degree 3. Consider $g(x):=x^{3}-3\in \mathbb{Q}(\sqrt{ 2 })[X]$. Then, it suffices to show that $g$ has no root in $\mathbb{Q}(\sqrt{ 2 })$. Let $a+b \sqrt{ 2 }\in \mathbb{Q}(\sqrt{ 2 })$. Then, if:$$a^{3}+3ab \sqrt{ 2 }+6ab ^{2}+2b^{3}\sqrt{ 2 }-3=(a^{3}+6ab ^{2}-3)+(3a+2b^{2})b\sqrt{ 2 }=0$$Then, if $b=0$, then $a^3-3=0$ and $a=\sqrt[3]{3  }\notin \mathbb{Q}$ so contradiction. If $3a+2b ^{2}=0$, Then, $$a^{3}-9a^{2}-3=-8a^{2}-3=0$$and $a^{2}=-\frac{3}{8}$, which is impossible. Therefore, $g$ is irreducible and $f$ is the minimal polynomial.
3. Now we know that $[\mathbb{Q}(x):\mathbb{Q}]=[\mathbb{Q}(x):\mathbb{Q}(\sqrt{ 2 })][\mathbb{Q}(\sqrt{ 2 }):\mathbb{Q}]=6$. Therefore, $$x^6+12x^4-6x^3+36x^{2}-36x+9=2(9x^4+12x^{2}+4)$$and $m_{x,\mathbb{Q}}(x)=x^6-6x^4-6x^3+12x^2-36x+1$.
---