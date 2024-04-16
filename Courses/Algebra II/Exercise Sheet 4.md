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

We have that $[F(a):F]=7$. Firstly, we have that $F(a^{2})\subseteq F(a)$. 