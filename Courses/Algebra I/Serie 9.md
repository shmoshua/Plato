#Series #Algebra-I 

##### Exercise 49
We first show that $(\text{End}(G),+)$ is an abelian group:
1. $(f_{1}+(f_{2}+f_{3}))(g)=f_{1}(g)+(f_{2}(g)+f_{3}(g))=(f_{1}(g)+f_{2}(g))+f_{3}(g)=((f_{1}+f_{2})+f_{3})(g)$
2. For $f_{0}:G \to \{ e_{G} \}$, we have: $$(f_{0}+f_{1})(g)=e_{G}+f_{1}(g)=f_{1}(g)$$
3. For $f\in \text{End}(G)$, $f^{-1}(g)=-f(g)$. Then, $$(f^{-1}+f)(g)=f^{-1}(g)+f(g)=-f(g)+f(g)=e_{G}=f_{0}(g)$$
4. $(f_{1}+f_{2})(g)=f_{1}(g)+f_{2}(g)=f_{2}(g)+f_{1}(g)=(f_{2}+f_{1})(g)$
5. $$(f_{1}\circ (f_{2}\circ f_{3}))(g)=f_{1}((f_{2}\circ f_{3})(g))=f_{1}(f_{2}(f_{3}(g)))=(f_{1}\circ f_{2})(f_{3}(g))=((f_{1}\circ f_{2})\circ f_{3})(g)$$
6. For identity map $\iota$, $$(f\circ \iota)(g)=f(\iota(g))=f(g)=\iota(f(g))=(\iota \circ  f)(g)$$
7. We have:$$\begin{align}(f_{1}\circ (f_{2}+f_{3}))(g)&=f_{1}(f_{2}(g)+f_{3}(g))=f_{1}(f_{2}(g))+f_{1}(f_{3}(g))\\&=(f_{1}\circ f_{2})(g)+(f_{1}\circ f_{3})(g)=(f_{1}\circ f_{2}+f_{1}\circ f_{3})(g)\end{align}$$
	and $$\begin{align}((f_{1}+f_{2})\circ f_{3})(g)&=(f_{1}+f_{2})(f_{3}(g))=f_{1}(f_{3}(g))+f_{2}(f_{3}(g))\\&=(f_{1}\circ f_{3})(g)+(f_{2}\circ f_{3})(g)=(f_{1}\circ f_{3}+f_{2}\circ f_{3})(g)\end{align}$$
---
##### Exercise 50
1. We will show one by one: 
	- **Additive associativity**: We have that: $$\chi_{A+B}=\chi_{A}+\chi_{B}-2\chi_{A}\chi_{B}$$Then, $$\begin{align}\chi_{(A+B)+C}&=(\chi_{A}+\chi_{B}-2\chi_{A}\chi_{B})+\chi_{C}-2(\chi_{A}+\chi_{B}-2\chi_{A}\chi_{B})\chi_{C}\\&=\chi_{A}+\chi_{B}+\chi_{C}-2\chi_{A}\chi_{B}-2\chi_{A}\chi_{C}-2\chi_{B}\chi_{C}+4\chi_{A}\chi_{B}\chi_{C}\\&=\chi_{A}+(\chi_{B}+\chi_{C}-2\chi_{B}\chi_{C})-2\chi_{A}(\chi_{B}+\chi_{C}-2\chi_{B}\chi_{C})\\&=\chi_{A+(B+C)}\end{align}$$
	- **Additive identity**: $\chi_{A+\varnothing}=\chi_{A}+0-0=\chi_{A}$.
	- **Additive inverse**: $(A\backslash A)\cup(A \backslash A)=\varnothing$. Therefore, $A^{-1}=A$.
	- **Additive commutativity**: $A+B=(A \backslash B)\cup(B \backslash A)=(B \backslash A)\cup (A \backslash B)=B+A$
	- **Multiplicative associativity**: $X*(Y*Z)=X\cap (Y\cap Z)=(X\cap Y)\cap Z=(X*Y)*Z$
	- **Multiplicative identity**: $X\cap S=X=S\cap X$
	- **Distributivity**: $$A*(B+C)=A\cap(B \cup C)\cap(B^c\cup C^c)$$
	- **Multiplicative commutativity**: $A * B=A\cap B=B\cap A=B*A$
2. For $X,Y\in\mathfrak{a}$, we have that: $X\backslash Y\in \mathcal{P}(X)\subseteq \mathfrak{a}$ and $Y \backslash X\in \mathcal{P}(Y)\in\mathfrak{a}$. therefore, 
   $$X+Y=(X \backslash Y)\cup (Y \backslash X)\in \mathfrak{a}$$
	Further, for $Z\in\mathcal{P}(S)$, $$Z*X=X\cap Z\in\mathcal{P}(X)\subseteq \mathfrak{a}$$
---
##### Exercise 51
1.  Assume $\gcd(a,n)=1$. Then, $\overline{a}\in (\mathbb{Z} / n\mathbb{Z})^*$. It follows from Lagrange theorem that: $$\overline{a}^{\varphi(n)}=\bar{1}$$Therefore, $a^{\varphi(n)}-1\in n\mathbb{Z}$ and $n|(a^{\varphi(n)}-1)$.
2. If we prove it for $r=2$, the rest is implied. For $n=q_{1}q_{2}$ with $\gcd(q_{1},q_{2})=1$, $$\begin{align}\varphi(n)&=\left| (\mathbb{Z} / n\mathbb{Z})^{*} \right| \\&=\left| (\mathbb{Z} / q_{1}\mathbb{Z} \oplus  \mathbb{Z} / q_{2}\mathbb{Z})^{*} \right| \\&=\left| (\mathbb{Z} / q_{1}\mathbb{Z} )^{*}\times (\mathbb{Z} / q_{2}\mathbb{Z})^{*}  \right| \\&=\left| (\mathbb{Z} / q_{1}\mathbb{Z})^{*} \right| \times \left| (\mathbb{Z} / q_{2}\mathbb{Z})^{*} \right| \\&=\varphi(q_{1})\varphi(q_{2})\end{align}$$
3. For $p^\ell$ where $p$ is prime and $\ell>0$, from $\{0,\dots,p^\ell-1\}$, only $p^\ell / p$ numbers are not coprime with $n$. Therefore, $$\varphi(p^\ell)=p^\ell-p^{\ell-1}=p^\ell(1-1 / p)$$and as all these factors are coprime,$$\varphi(n)=\prod_{i=1}^{r}\varphi(p_{i}^{\ell_{i}})=\prod_{i=1}^{r}p_{i}^{\ell_{i}}\left( 1-\frac{1}{p_{i}} \right) =n\prod_{i=1}^{r}\left( 1-\frac{1}{p_{i}} \right)$$
---
##### Exercise 52
1. We have that: 
	1. $201=3\cdot 67$
	2. $102= 2\cdot 3\cdot 17$
	3. $96 = 2^5 \cdot 3$
	   
	Therefore, $R\cong \mathbb{Z} /n\mathbb{Z}$ where $n=2^5\cdot 3\cdot 17\cdot 67$. It follows that: $$\left| R^{*} \right| =16\cdot 2\cdot 16\cdot 66=33792$$
2. The inverse of $(\overline{13},\overline{13},\overline{13})$ is: $(\overline{31},\overline{55},\overline{37})$
---
