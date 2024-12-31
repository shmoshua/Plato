#Definition #Algebra 

> [!definition]
> We have that:
> 1. [[Abelian Group|Abelian groups]] $A,B,C$ and [[Group Homomorphism|homomorphisms]] $A\xrightarrow{i}B\xrightarrow{j} C$ forms an ***exact sequence*** if $\text{ker}(j)=\text{im}(i)$. 
> 2. A sequence $\cdots \to A_{k+1}\xrightarrow{f}A_{k}\xrightarrow{f}A_{k-1}\to \cdots$ of abelian groups is ***exact*** if every subsequence of 3 groups is exact.

^ce710c

- **Remark**: The [[Chain Complex|homology]] of an exact sequence is always zero. ^fcbe50
- **Related definition**: An exact sequence of the type $0\to A\xrightarrow{i} B\xrightarrow{j} C\to 0$ is called a ***short exact sequence (SES)***.  ^c2ad1a
---
##### Properties
> [!lemma] Proposition 1
> For abelian groups $A,B$ and a homomorphism $f$,
> 1. $0\to A\xrightarrow{f} B$ is exact if and only if $f$ is injective.
> 2. $A\xrightarrow{f} B\to 0$ is exact if and only if $f$ is surjective.
> 3. $0\to A\xrightarrow{f} B\to 0$ is exact if and only if $f$ is an isomorphism.

^75c17f

> [!proof]-
> Obvious.

^94e7ab

- **Corollary**: For a SES $0\to A\xrightarrow{i} B\xrightarrow{j} C\to 0$, $i$ is injective, $j$ is surjective and $j$ induces an isomorphism $B /i(A)\to C$.  ^729f68
---
> [!lemma] Theorem 2 (5-Lemma)
> Let the following diagram of abelian groups be commutative: 
> $$\begin{CD}A@>i>>B@>j>>C@>\ell>>D@>k>>E\\@VaVV@VbVV@VcVV@VdVV@VeVV\\A'@>>i'>B'@>>j'>C'@>>\ell'>D'@>>k'>E\end{CD}$$If the two rows are exact sequences, we have that:
> 1. if $b,d$ are injective and $a$ is surjective, then $c$ is injective.
> 2. if $b,d$ are surjective and $e$ is injective, then $c$ is surjective.
> 3. if $a,b,d,e$ are isomorphisms, then $c$ is an isomorphism.

> [!proof]+
> We have that:
> 1. Let $x\in \text{ker}(c)$. Then, $d(\ell(x))=\ell'(c(x))=\ell'(0)=0$. Hence, $\ell(x)\in \text{ker}(d)= 0$ and it follows that $\ell(x)=0$. Therefore, $x\in \text{ker}(\ell)=\text{im}(j)$ and there exists $y\in B$ with $j(y)=x$. Now, we have that: $$j'(b(y))=c(j(y))=c(x)=0$$Hence, $b(y)\in \text{ker}(j')=\text{im}(i')$ and there exists $z'\in A'$ with $i'(z')=b(y)$. Further, as $a$ is surjective, there exists $z\in A$ with $a(z)=z'$. Therefore, we have that: $$b(y)=i'(a(z))=b(i(z))$$By injectivity of $b$, then $y=i(z)\in \text{im}(i)=\text{ker}(j)$. It follows that $x=j(y)=0$ which shows that $c$ is injective.
> 2. Let $x'\in C'$ and consider $\ell'(x')\in D'$. As $d$ is surjective, there exists $y\in D$ with $d(y)=\ell'(x')\in \text{im}(\ell')=\text{ker}(k')$ and $e(k(y))=k'(d(y))=0$. Hence, by injectivity of $e$, $k(y)=0$ and by exactness, there exists $x\in C$ with $\ell(x)=y$. Then, $$\ell'(c(x))=d(\ell(x))=d(y)=\ell'(x')$$and $c(x)-x'\in \text{ker}(\ell')=\text{im}(j')$ with $z'\in B'$ with $j'(z')=c(x)-x'$. Further, as $b$ is surjective, there exists $z\in B$ with $b(z)=z'$. Therefore, $$c(j(z))=j'(b(z))=j'(z')=c(x)-x'$$