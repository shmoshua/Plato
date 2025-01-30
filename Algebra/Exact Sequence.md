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
> For the following commutative diagram with exact rows, $$\begin{CD}&&M @>\varphi>> N @>\psi>> P @>>> 0\\&@VV\alpha V@VV\beta V@VV\gamma V\\0@>>> M'@>>\varphi'> N' @>>\psi'> P' \end{CD}$$
> 1. The following sequence is exact:$$\text{ker }\alpha\to \text{ker }\beta\to \text{ker }\gamma \to M' / \text{im }\alpha \to N' / \text{im }\beta\to P' / \text{im }\gamma$$
> 2. if $\varphi$ is injective, so is $\text{ker }\alpha\to \text{ker }\beta$ in the sequence above.
> 3. if $\psi'$ is surjective, so is $N' / \text{im }\beta\to P'/\text{im }\gamma$ in the sequence above.

> [!proof]- 
> Let's construct the homomorphisms: 
> 1. $\text{ker }\alpha\to \text{ker }\beta$ is given by $\varphi|_{\text{ker }\alpha}$. For $m\in \text{ker }\alpha$, $\beta(\varphi(m))=\varphi'(\alpha(m))= 0$ and $\varphi(m)\in \text{ker } \beta$.
> 2. $\text{ker }\beta\to \text{ker }\gamma$ is given by $\psi|_{\text{ker }\beta}$ with similar reasoning as above.
> 3. $\text{ker }\gamma\to M' / \text{im }\alpha$ is given by the connecting homomorphism $\delta$. Let $p\in \text{ker } \gamma$. As $\psi$ is surjective, there exists $n\in N$ with $\psi(n)=p$. However, $$\psi'(\beta(n))=\gamma(\psi(n))=\gamma(p)=0$$and $\beta(n)\in \text{ker }\psi'=\text{im } \varphi'$. Hence, there exists $m'\in M'$ with $\varphi'(m')=\beta(n)$. We define $\delta(p):=[m']$. 
>    
>    We need to verify that this is well-defined. As $\varphi'$ is injective, the choice of $m'$ was unique. Assume we have a different $\tilde{n}\in N$ with $\psi(n)=p$ with $\tilde{m}'$ s.t. $\varphi'(\tilde{m}')=\beta(\tilde{n})$. Then, $\psi(\tilde{n}-n)=0$ and $\tilde{n}-n\in \text{ker }\psi=\text{im }\varphi$. Hence, $\tilde{n}-n=\varphi(m)$ for some $m\in M$. Therefore, $$\varphi'(\tilde{m}'-m')=\beta(\tilde{n}-n)=\beta(\varphi(m))=\varphi'(\alpha(m))$$Hence, by the injectivity, $\tilde{m}'-m'=\alpha(m)$ and $[m']=[\tilde{m}']$.
> 4. As $\varphi'(\text{im } \alpha)\subseteq \text{im }\beta$, $\varphi'$ gives rise to a well-defined map $M / \text{im }\alpha \to N / \text{im } \beta$. 
> 5. Similarly for the last map.
>    
> It is left to show that this sequence are exact. 
> 1. Exactness at $\text{ker }\beta$: $\psi(\varphi(m))= 0$ for all $m\in \text{ker }\alpha$. Hence, the image is contained in the kernel. Conversely, if $\psi(n)=0$ for some $n\in \text{ker }\beta$, then $n\in \text{ker }\psi=\text{im } \varphi$ and there exists $m\in M$ with $\varphi(m)=n$. However, notice that: $$\varphi'(\alpha(m))=\beta(n)=0$$As $\varphi'$ is injective, $\alpha(m)=0$ and $m\in \text{ker } \alpha$. This shows that $n$ is in the image.
> 2. Exactness at $\text{ker }\gamma$: For $n\in \text{ker } \beta$, we get by construction that $\delta(\psi(n))= 0$. Hence, $\text{im }\tilde{\psi}\subseteq \text{ker } \delta$. Conversely, if $p\in \text{ker }\delta$, then let $n\in N$ with $\psi(n)=p$ and $m'\in M'$ with $\varphi'(m')=\beta(n)$. However, we get that $m'\in \text{im }\alpha$ and there exists $m\in M$ with $\alpha(m) = m'$. Therefore, $$\beta(n)=\varphi'(m')=\varphi'(\alpha(m))=\beta(\varphi(m))$$Hence, $n-\varphi(m)\in \text{ker }\beta$ and: $\tilde{\psi}(n-\varphi(m))= p -\psi(\varphi(m))=p$.
> 3. Exactness at $M' / \text{im }\alpha$: if $\overline{m'}\in \text{im }\delta$, then $\tilde{\varphi}'(m')=\overline{\varphi'(m')}=\overline{\beta(n)}=0$. Conversely, if $\overline{m'}\in \text{ker }\tilde{\varphi}'$, then $n':=\varphi'(m')\in \text{im }\beta$ and $n'=\beta(n)$ for some $n\in N$. Then, $\psi(n)=:p$ satisfies: $$\gamma(p)=\gamma(\psi(n))=\psi'(\beta(n))=\psi'(n')=\psi'(\varphi'(m'))=0$$Hence, $\delta(p)=\overline{m'}$.
> 4. Exactness at $N' / \text{im } \beta$: if $\overline{n'}\in \text{im }\tilde{\varphi}'$, then we have $\tilde{\varphi}'(\overline{m'})=\overline{n'}$ for some $m'\in M'$, hence, $$\tilde{\psi}'(\overline{n'})=\tilde{\psi}'(\tilde{\varphi}'(\overline{m'}))=0$$ Conversely, if $\overline{n'}\in \text{ker }\tilde{\psi'}$, then $\psi'(n')\in \text{im } \gamma$ and $\psi'(n')=\gamma(p)$ for some $p\in P$. As $\psi$ is surjective, let $n\in N$ with $\psi(n)=p$. Then, $$\psi'(n'-\beta(n))=\gamma(p-\psi(n))=0$$and $n'-\beta(n)\in \text{ker }\psi'=\text{im }\varphi'$. Hence, there is $m'\in M'$ with $\varphi'(m')=n'-\beta(n)$ and: $$\tilde{\varphi}'(\overline{m'})=[n'-\beta(n)]=[n']$$
> 5. If $\varphi$ is injective, so is its restriction.
> 6. If $\psi'$ is surjective, then for any $p'\in P'$, there exists $n'\in N'$ with $\psi'(n')=p'$. Hence, $\tilde{\psi'}(\overline{n'})=\overline{p'}$. 
---

> [!lemma] Theorem 3 (5-Lemma)
> Let the following diagram of $R$-modules be commutative: 
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
> [!lemma] Proposition 4 (Hom(,N) is left exact)
> Let $M_{1},M_{2},M_{3}$ be $R$-modules. TFAE:
> 1. $M_{1}\xrightarrow{\varphi_{1}}M_{2}\xrightarrow{\varphi_{2}}M_{3}\to 0$ is exact.
> 2. $0 \to \text{Hom}(M_{3},N)\xrightarrow{\varphi_{2}^{*}}\text{Hom}(M_{2},N)\xrightarrow{\varphi_{1}^{*}}\text{Hom}(M_{1},N)$ is exact for every $R$-module $N$ where $\varphi_{i}^{*}(\psi)=\psi \circ \varphi_{i}$. 

> [!proof]-
> We have that:
> 1. (1=>2): Assume the sequence is exact. Then, 
> 	1. Let $\varphi ^{*}_{2}(\psi)=\psi \circ \varphi_{2}=0$ for some $\psi\in \text{Hom}(M_{3},N)$. Then, as $\varphi_{2}$ is surjective, $\psi=0$. 
> 	2. We have that $\varphi_{1}^{*}(\varphi ^{*}_{2}(\psi))=\psi \circ \varphi_{2} \circ \varphi_{1}=\psi \circ 0=0$. Hence, $\text{im }\varphi ^{*}_{2}\subseteq \text{ker }\varphi ^{*}_{1}$. Conversely, let $\psi\in \text{ker }\varphi ^{*}_{1}$. Then, $\psi \circ \varphi_{1}=0$ and $\text{ker }\varphi_{2}=\text{im }\varphi_{1}\subseteq \text{ker }\psi$. 
> 	   
> 	   Let's define $\psi':M_{3}\to N$ as follows. For any $m_{3}\in M_{3}$, by surjectivity, there exists $m_{2}\in M_{2}$ with $\varphi_{2}(m_{2})=m_{3}$. Then, $\psi'(m_{3})=\psi(m_{2})$. To show that this is well-defined, if $m_{2}'\in M_{2}$ s.t. $\varphi_{2}(m_{2}')=m_{3}$, then, $\varphi_{2}(m_{2}-m'_{2})=0$ and $$m_{2}-m'_{2}\in \text{ker }\varphi_{2}\subseteq \text{ker }\psi$$Hence, $\psi(m_{2})=\psi(m'_{2})$. 
> 	   
> 	   Further, we show that it is a homomorphism. For $a,b\in M_{3}$ with $a',b'\in M_{2}$ with $\varphi_{2}(a')=a$ and $\varphi_{2}(b')=b$, $\varphi_{2}(a'+b')=a+b$ and, $$\psi'(a+b)=\varphi_{2}(a'+b')=\varphi_{2}(a')+\varphi_{2}(b')=\psi'(a)+\psi'(b)$$Similar for scalar multiplication. 
> 	   
> 	   Lastly, $\varphi ^{*}_{2} (\psi')(m_{2})=\psi' (\varphi_{2}(m_{2}))=\psi'(m_{3})=\psi(m_{2})$. Hence, $\psi\in \text{im }\varphi ^{*}_{2}$.
> 2. (2=>1): We first show that the sequence is exact at $M_{2}$. Consider $N=M_{3}$. Then, $$0 = \varphi ^{*}_{1}(\varphi ^{*}_{2}(\text{id}_{M_{3}}))=\text{id}_{M_{3}}\circ  \varphi_{2}\circ \varphi_{1}=  \varphi_{2}\circ \varphi_{1}$$Hence, $\text{im }\varphi_{1}\subseteq \text{ker }\varphi_{2}$. Conversely, let $N:=M_{2} / \text{im } \varphi_{1}$ and $\psi:M_{2}\to N$ be the canonical projection. Then, $$\varphi ^{*}_{1}(\psi)=\psi \circ  \varphi_{1} = 0$$and $\psi\in \text{ker }\varphi ^{*}_{1}=\text{im } \varphi ^{*}_{2}$ and there exists $\psi'\in \text{Hom}(M_{3},N)$ with $\psi' \circ \varphi_{2}=\psi$. Then, $$\text{ker }\varphi_{2}\subseteq \text{ker } \psi=\text{im }\varphi_{1}$$
>    
>    For exactness at $M_{3}$, consider $N:= M_{3} / \text{im }\varphi_{2}$ and $\psi:M_{3}\to N$. Then, $$\varphi_{2}^{*}(\psi)=\psi \circ  \varphi_{2}= 0$$and by injectivity, $\psi= 0$. However, as $\psi$ is surjective by definition, we have that $M_{3} / \text{im }\varphi_{2}= 0$ and $\text{im }\varphi_{2}=M_{3}$. 

---
> [!lemma] Proposition 5
> Let: $$0 \to M_{1} \xrightarrow{\varphi} M_{2} \to \dots \to M_{n}\to 0$$be an exact sequence of $R$-modules of finite length. Then, 
> 1. $\sum_{i=1}^{n}(-1)^i \ell(M_{i})= 0$.

> [!proof]-
> By [[Composition Series|Proposition 2.3]], $$\begin{align}\sum_{i=1}^{n}(-1)^i \ell(M_{i})&=\sum_{i=1}^{n}(-1)^i (\ell(\text{ker }\varphi_{i})+\ell(\text{im }\varphi_{i}))\\&=-\ell(\text{ker }\varphi_{1})+\sum_{i=2}^{n}(-1)^i\ell (\text{ker }\varphi_{i})+\sum_{i=1}^{n-1}(-1)^i \ell(\text{im }\varphi_{i})+(-1)^n \ell(\text{im } \varphi_{n})\\&=-\ell(\text{ker }\varphi_{1})-\sum_{i=1}^{n-1}(-1)^i\ell (\text{im }\varphi_{i})+\sum_{i=1}^{n-1}(-1)^i \ell(\text{im }\varphi_{i})+(-1)^n \ell(\text{im } \varphi_{n})\\&=-\ell(\text{ker }\varphi_{1})+(-1)^n\ell(\text{im }\varphi_{n})\\&=0\end{align}$$
---
##### Examples
> [!h] Example 1 (Examples of SES)
> Let $M,N$ be $R$-modules and $\varphi:M\to N$ a homomorphism. Let $A\leq M$. Then, 
> 1.  $0\to \text{ker }\varphi\hookrightarrow M \xrightarrow{\varphi} \text{im }\varphi \to 0$ is exact.
> 2. $0\to A\hookrightarrow M \xrightarrow{q} M / A \to 0$ where $q$ is the quotient map.
> 3. $0\to \text{ker } \varphi \to M\xrightarrow{\varphi} N \to N / \text{im }\varphi \to 0$ by glueing 1 and 2.
---
> [!h] Example 2 (Ideals)
> Let $I,J\unlhd R$. 
> 1. there is an exact sequence $0\to I\cap J \to I\oplus J \to I+J \to 0$.
> 2. there is an exact sequence $0 \to R / (I\cap J) \to R / I \oplus R / J \to R / (I+J) \to 0$

> [!proof]+
> We have that:
> 1. Consider the map $$f:I\cap J \to I\oplus J, \quad x\mapsto (x,x),\quad g:I\oplus  J \to I+J,\quad (x,y)\mapsto x-y$$Then, $f$ is injective, $g$ is surjective and $g(f(x))=0$ hence $\text{im }f\subseteq \text{ker } g$. Similarly, if $(x,y)\in \text{ker } g$, then $x-y=0$ and $x=y$. Hence, $\text{im } f = \text{ker } g$. 
> 2. Using the Snake lemma, we get $$\begin{CD}&&I\cap J @>f>> I\oplus J @>g>> I+J @>>> 0\\&@VV V@VVV@VVV\\0@>>> R@>>> R\oplus R @>>> R \end{CD}$$where the downward maps are injections. Then, $$ 0 \to 0 \to 0 \to R / (I\cap J) \to R / I \oplus  R / J\to R / (I+J)$$Further, as $R\oplus R \to R$ is surjective, we get and
