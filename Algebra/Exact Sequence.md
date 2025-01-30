#Definition #Algebra 

> [!definition]
> Let $R$ be a [[ring]] and $(M_{n})_{n}$ be a sequence of $R$-[[Module|modules]] given by: $$\dots\to M_{i+1}\xrightarrow{\varphi_{i+1}} M_{i} \xrightarrow{\varphi_{i}} M_{i-1} \to \cdots  $$where $\varphi_{i}:M_{i}\to M_{i-1}$ are $R$-module homomorphisms. 
> 1. The sequence is called ***exact at $M_{i}$*** if $\text{im } \varphi_{i+1}=\text{ker }\varphi_{i}$. 
> 2. The sequence is called ***exact***, if it is exact at every module $M_{i}$ except the ends. 

^ce710c

- **Remark**: The [[Chain Complex|homology]] of an exact sequence is always zero. ^fcbe50
- **Related definition**: An exact sequence of the type $0\to A\xrightarrow{i} B\xrightarrow{j} C\to 0$ is called a ***short exact sequence (SES)***.  ^c2ad1a
---
##### Properties
> [!lemma] Proposition 1
> For $R$-modules $A,B$ and a homomorphism $f$,
> 1. $0\to A\xrightarrow{f} B$ is exact if and only if $f$ is injective.
> 2. $A\xrightarrow{f} B\to 0$ is exact if and only if $f$ is surjective.
> 3. $0\to A\xrightarrow{f} B\to 0$ is exact if and only if $f$ is an isomorphism.
> 4. $0\to A\to 0$ is exact if and only if $A=0$.

^75c17f

> [!proof]-
> Obvious.

^94e7ab

- **Corollary**: For a SES $0\to A\xrightarrow{i} B\xrightarrow{j} C\to 0$, $i$ is injective, $j$ is surjective and $j$ induces an isomorphism $B /i(A)\to C$.  ^729f68
---
> [!lemma] Lemma 2 (Splitting and Gluing)
> We have that:
> 1. **Splitting**: If $M_{1}\xrightarrow{\varphi_{1}}M_{2}\xrightarrow{\varphi_{2}}M_{3}\xrightarrow{\varphi_{3}}M_{4}$ is an exact sequence of $R$-modules, $$M_{1}\xrightarrow{\varphi_{1}}M_{2}\xrightarrow{\varphi_{2}}\text{ker }\varphi_{3}\to 0,\quad 0\to \text{ker }\varphi_{3}\hookrightarrow M_{3}\xrightarrow{\varphi_{3}}M_{4}$$are exact as well.
> 2. **Gluing**: If the following sequences are exact: $$M_{1}\xrightarrow{\varphi_{1}}M_{2}\xrightarrow{\varphi_{2}}N\to 0, \quad 0\to N\hookrightarrow M_{3}\xrightarrow{\varphi_{3}}M_{4}$$with $N\leq M_{3}$, then $M_{1}\xrightarrow{\varphi_{1}}M_{2}\xrightarrow{\varphi_{2}}M_{3}\xrightarrow{\varphi_{3}}M_{4}$ is exact as well.

> [!proof]-
> We have:
> 1. First sequence is exact as $\text{ker }\varphi_{3}=\text{im }\varphi_{2}$. The second sequence is exact trivially.
> 2. The exactness at $M_{3}$ follows from, $\text{im }\varphi_{2}=N=\text{ker }\varphi_{3}$.
- **Corollary:** $0\to M_{n}\xrightarrow{\varphi}M_{n-1}\to\dots\to M_{1}\to 0$ can be split into SES's: $$0\to \text{ker }\varphi \to M_{i} \xrightarrow{\varphi} \text{im }\varphi_{i}\to 0$$
---
> [!lemma] Theorem 3 (Snake Lemma)
> Let: $$\begin{CD}

\end{CD}$$
---

> [!lemma] Theorem 3 (5-Lemma)
> Let the following diagram of abelian groups be commutative: 
>$$\begin{CD}A@>i>>B@>j>>C@>\ell>>D@>k>>E\\@VaVV@VbVV@VcVV@VdVV@VeVV\\A'@>>i'>B'@>>j'>C'@>>\ell'>D'@>>k'>E\end{CD}$$If the two rows are exact sequences, we have that:
> 1. if $b,d$ are injective and $a$ is surjective, then $c$ is injective.
> 2. if $b,d$ are surjective and $e$ is injective, then $c$ is surjective.
> 3. if $a,b,d,e$ are isomorphisms, then $c$ is an isomorphism.

^b971c0

> [!proof]-
> We have that:
> 1. Let $x\in \text{ker}(c)$. Then, $d(\ell(x))=\ell'(c(x))=\ell'(0)=0$. Hence, $\ell(x)\in \text{ker}(d)= 0$ and it follows that $\ell(x)=0$. Therefore, $x\in \text{ker}(\ell)=\text{im}(j)$ and there exists $y\in B$ with $j(y)=x$. Now, we have that: $$j'(b(y))=c(j(y))=c(x)=0$$Hence, $b(y)\in \text{ker}(j')=\text{im}(i')$ and there exists $z'\in A'$ with $i'(z')=b(y)$. Further, as $a$ is surjective, there exists $z\in A$ with $a(z)=z'$. Therefore, we have that: $$b(y)=i'(a(z))=b(i(z))$$By injectivity of $b$, then $y=i(z)\in \text{im}(i)=\text{ker}(j)$. It follows that $x=j(y)=0$ which shows that $c$ is injective.
> 2. Let $x'\in C'$ and consider $\ell'(x')\in D'$. As $d$ is surjective, there exists $y\in D$ with $d(y)=\ell'(x')\in \text{im}(\ell')=\text{ker}(k')$ and $e(k(y))=k'(d(y))=0$. Hence, by injectivity of $e$, $k(y)=0$ and by exactness, there exists $x\in C$ with $\ell(x)=y$. Then, $$\ell'(c(x))=d(\ell(x))=d(y)=\ell'(x')$$and $c(x)-x'\in \text{ker}(\ell')=\text{im}(j')$ with $z'\in B'$ with $j'(z')=c(x)-x'$. Further, as $b$ is surjective, there exists $z\in B$ with $b(z)=z'$. Therefore, $$c(j(z))=j'(b(z))=j'(z')=c(x)-x'$$and $c(x-j(z))=x'$. This proves that $c$ is surjective.
> 3. Follows from 1,2.

^dc9a84

---
##### Examples
> [!h] Example 1 (Examples of SES)
> Let $M,N$ be $R$-modules and $\varphi:M\to N$ a homomorphism. Let $A\leq M$. Then, 
> 1.  $0\to \text{ker }\varphi\hookrightarrow M \xrightarrow{\varphi} \text{im }\varphi \to 0$ is exact.
> 2. $0\to A\hookrightarrow M \xrightarrow{q} M / A \to 0$ where $q$ is the quotient map.
> 3. $0\to \text{ker } \varphi \to M\xrightarrow{\varphi} N \to N / \text{im }\varphi \to 0$ by glueing 1 and 2.