#Algebra #Definition 

> [!definition]
> Let $K$ be a [[field]] and $\mathbb{A}_{K}^n$ is the [[affine space]] over $K$. 
> 1. For $S\subseteq K[x_{1},\dots,x_{n}]$, the ***zero locus*** of $S$ is given as:$$V(S):=\{  x\in \mathbb{A}_{K}^n:f(x)=0, \forall f\in S \}\subseteq \mathbb{A}_{K}^n$$Subsets like these are called ***varieties***.
> 2. For any $X\subseteq \mathbb{A}_{K}^n$, the ***ideal of $X$*** is defined as:$$I(X):=\{  f\in K[x_{1},\dots,x_{n}]:f(x)=0,\forall x\in X \}\subseteq K[x_{1},\dots,x_{n}]$$ 
> 3. For a variety $X\subseteq \mathbb{A}_{K}^n$, the ***ring of polynomial functions/coordinate ring*** of $X$ is defined as: $$A(X):=K[x_{1},\dots,x_{n}] / I(X)$$where $[f]=[g]\in A(X)$ if and only if $f|_{X}=g|_{X}$. 
> 4. For a variety $X\subseteq \mathbb{A}_{K}^n$ and $S\subseteq A(X)$, 
> 	1. a ***subvariety*** of $X$ is given by: $V_{X}(S):=\{  x\in X: f(x)=0, \forall f\in S \}\subseteq X$
> 	2. with ideal $I_{X}(Y)=\{ f\in A(X): f(y)=0, \forall y\in Y \}\unlhd A(X)$.
> 	
   Subvarieties of $X$ are exactly the varieties in $\mathbb{A}_{K}^n$ contained in $X$.

^1a7b97

- **Remark**: If $S:=\{ f_{1},\dots,f_{k} \}$ is finite, let $V(f_{1},\dots,f_{k}):=V(S)$.
- **Remark**: $f,g\in K[x_{1},\dots,x_{n}]$ are equal if and only if they equal on $X$. So $[f]\in A(X)$ is equivalent to a function $X\to K,x\mapsto f(x)$.  ^ca999a
- **Related definition**: A variety $X$ is ***irreducible*** if there is no proper decomposition into subvarieties $X=X_{1}\cup X_{2}$ s.t. $X_{1},X_{2}\subsetneq X$. Otherwise, $X$ is ***reducible***.
- **Related definition**: The ***dimension*** $\text{dim}X$ of a variety $X$ is given by the [[Krull dimension]] of the coordinate ring $A(X)$. 
	1. A ***curve*** is a 1-dimensional variety.
	2. The ***codimension*** of a irreducible subvariety $Y$ in $X$ is given by $\text{codim}_{X}Y:=\text{codim}_{A(X)}I(Y)$.

---
##### Properties
> [!lemma] Proposition 1 (Properties of Ideal)
> For $X\subseteq \mathbb{A}_{K}^n$, 
> 1. $I(X)\unlhd K[x_{1},\dots,x_{n}]$, i.e. $I(X)$ is an [[Ideal (Ring)|ideal]].

^35d70d

> [!proof]-
> We have:
> 1. for any $f\in I(X)$ and $g\in K[x_{1},\dots,x_{n}]$, $fg(x)=0$ for $x\in X$. Further, $I(X)$ is an additive subgroup.
> 2. 

^c6655d

---
> [!lemma] Lemma 2
> For a variety $X\subseteq \mathbb{A}_{K}^n$ with its coordinate ring $A(X)$, $Y,Y'\subseteq X$ and $S,S'\subseteq A(X)$:
> 1. if $Y\subseteq Y'$, $I_{X}(Y')\subseteq I_{X}(Y)$. 
> 2. if $S\subseteq S'$, $V_{X}(S')\subseteq V_{X}(S)$. 
> 3. $Y\subseteq V(I(Y))$ and $S\subseteq I(V(S))$.
> 4. if $Y\subseteq X$ is a subvariety, $Y=V(I(Y))$.
> 5. if $Y\subseteq X$ is a subvariety, $A(X) / I(Y)\cong A(Y)$ 

^dfb872

> [!proof]-
> We have: 
> 1. if $f\in I_{X}(Y')$, then $f(x)=0$ for all $x\in Y'$ and thereby $Y$.
> 2. if $x\in V_{X}(S')$, then $f(x)=0$ for all $f\in S'$ and thereby $S$.  
> 3. for $x\in Y$ and $f\in I(Y)$, $f(x)= 0$. Therefore, $x\in V(I(Y))$. Similarly, for $f\in S$ and $x\in V(S)$, $f(x)=0$. Therefore, $S\subseteq I(V(S))$. 
> 4. One direction is clear from 3. If $Y$ is a subvariety, $Y=V(S)$ for some $S\subseteq A(X)$ and as $S\subseteq I(V(S))$, we have by 2, $Y=V(S)\supseteq V(I(V(S)))$.
> 5. Consider the ring homomorphism: $$\psi:A(X)\to A(Y),\quad [f]_{X}\mapsto [f]_{Y}$$which is well-defined as if $f|_{X}=g|_{X}$, then $f|_{Y}=g|_{Y}$. Then, $$\text{ker }\psi=\{ [f]_{X}\in A(X):f|_{Y}=0 \}=I(Y)$$

^c712ee

- **Corollary**: there are maps between subvarieties of $X$ and ideals in $A(X)$ given by $I$ and $V$. ($I$ is injective but $V$ is not. e.g. $V(x)=V(x^2))\subseteq \mathbb{A}_{K}^1$)   ^df9fc7
---
> [!lemma] Lemma 3
> Let $X\subseteq \mathbb{A}_{K}^n$ be a variety. Then, 
> 1. for $I,J\unlhd A(X)$, $V(I)\cup V(J)=V(I\cap J)=V(IJ)$
> 2. for $\{ I_{\lambda} \}_{\lambda\in \Lambda}$ where $I_{\lambda}\unlhd A(X)$, $\bigcap_{\lambda\in \Lambda}^{}V(I_{\lambda})=V\left( \sum_{\lambda\in \Lambda}^{}I_{\lambda} \right)$ and $\sum_{\lambda\in \Lambda}I_{\lambda}:=\left( \bigcup_{\lambda\in \Lambda}^{}I_{k} \right)$
> 3. $V(0)=X$, $V(1)=\varnothing$.

^bc5221

> [!proof]-
> We have that:
> 1. $IJ\subseteq I\cap J\subseteq I,J$. Therefore, by Lemma 2, $V(I),V(J)\subseteq V(I\cap J)\subseteq V(IJ)$. Therefore, $$V(I)\cup V(J)\subseteq V(IJ)$$Now, assume $x\notin V(I)\cup V(J)$. Then, there exists $f\in I$ and $g\in J$ s.t. $f(x)\neq 0$ and $g(x)\neq 0$ and $fg(x)\neq 0$. Therefore, $x\notin V(IJ)$. This proves the statement.
> 2. We have that $$\begin{align}x\in \bigcap_{\lambda\in \Lambda}^{}V(I_{\lambda})&\iff x\in V(I_{\lambda}),\quad \forall\lambda\in \Lambda\\&\iff f(x)=0,\quad \forall f\in \bigcup_{\lambda\in \Lambda}^{}I_{\lambda}\\&\iff f(x)=0,\quad \forall f\in \sum_{\lambda\in \Lambda}^{}I_{\lambda}\\&\iff x\in V\left( \sum_{\lambda\in \Lambda}^{}I_{\lambda} \right)\end{align}$$
> 3. Obvious.

^37ac6e

- **Remark**: This endows the closed sets of a topology, called [[Zariski Topology]].
---

> [!lemma] Proposition 4
> For a variety $X\subseteq \mathbb{A}_{K}^n$ and $Y\subseteq X$ a subvariety. Then, 
> 1. $I_{X}(Y)\unlhd A(X)$ is [[Radical (Ring)|radical]].

^4f0f2a

> [!proof]-
> Let $f\in \sqrt{ I_{X}(Y) }$, i.e. $f\in A(X)$ with $f^n\in I(Y)$. Then, $f^n(x)=0$ for all $x\in Y$. Therefore, $f(x)=0$ for all $x\in Y$. Hence, $f\in I(Y)$.

^88859e

---
> [!lemma] Theorem 5 (Hilbert's Nullstellensatz)
> For a variety $X\subseteq \mathbb{A}_{K}^n$ and a subvariety $Y\subseteq X$, 
> 1. for any ideal $I\unlhd A(X)$, $I(V(I))=\sqrt{ I }$ where $\sqrt{ I }$ is the [[Radical (Ring)|radical]].

^121639

- **Corollary**: There is a bijection between subvarieties of $X$ and radical ideals in $A(X)$ given by $I$ and $V$.  ^039994
---
> [!lemma] Proposition 6
> We have that:$$\begin{array}{ccccc}
\{ \text{Var}\subseteq \mathbb{A}_{K}^n \}&\to &\{ \text{Rad. ideals in }K[x_{1},\dots,x_{n}] \}&\to &\{ \text{fin. gen. reduced }K\text{-algebra} \}\\X&\mapsto &I(X)&\mapsto &A(X):=K[x_{1},..,x_{n}] / I(X)
\\V(I)&\gets&I\end{array}$$

^4ec3ba

> [!proof]-
> The first half is given by the Corollary above. The second half is given by [[Algebra|Lemma 1]] and [[Nilradical|Lemma 1]].

^89aa91

---
> [!lemma] Proposition 7 (Irreducible Varieties and Prime Ideals)
> For a variety $\varnothing\neq X \subseteq \mathbb{A}_{K}^n$, TFAE:
> 1. $X$ is irreducible.
> 2. $I(X)$ is [[Prime Ideal|prime]].
> 3. for all open $\varnothing\neq U_{1},U_{2}\subseteq X$ w.r.t. [[Zariski topology]], $U_{1}\cap U_{2}\neq \varnothing$.
> 4. every open subset $\varnothing\neq U\subseteq X$ is dense.

^2e6fcc

> [!proof]- 
> We have that:
> 1. (1=>2): If $I(X)$ is not prime, there exists $f,g\in K[x_{1},\dots,x_{n}]$ s.t. $fg\in I(X)$ but $f,g\notin I(X)$. Let us define $J_{1}:=(I(X),f)$ and $J_{2}:=(I(X),g)$. Then, for $X_{i}:=V(J_{i})$, we have that $X_{1},X_{2}\subseteq X_{i}$ are subvarieties. However, $X\subseteq X_{1}\cup X_{2}$ as for any $x\in X$, $fg(x)=0$ and either $f(x)=0$ or $g(x)=0$. This proves that $X$ is reducible.
> 2. (2=>1): If $X$ is reducible, i.e. $X=X_{1}\cup X_{2}$ where $X_{1},X_{2}\subseteq X$ are subvarieties, then there exists $f\in I(X_{1}) \backslash I(X)$ and $g\in I(X_{2}) \backslash I(X)$. However, as we have that $fg\in I(X)$, $I(X)$ is not prime.
> 3. (1=>3): if $U_{1}\cap U_{2}=\varnothing$, then $X\backslash U_{1}\cup X \backslash U_{2}=X$. Therefore, $X$ is reducible.
> 4. (3=>1): if $X=X_{1}\cup X_{2}$, $X \backslash X_{1},X \backslash X_{2}$ are two sets.
> 5. (3<=>4): definition of dense.

^abc38b

- **Remark**: Similarly $X$ is a point if and only if $I(X)$ is maximal.  ^da8bb5

---
> [!lemma] Proposition 8 (Tensor Product of Coordinate Rings)
> Let $X\subseteq \mathbb{A}^n_{K}$ and $Y\subseteq \mathbb{A}^m_{K}$ be varieties over $K$ s.t. $X\times Y\subseteq K^{n+m}$. Then, 
> 1. $X\times Y$ is a variety.
> 2. $A(X\times Y)\cong A(X)\otimes_{K}A(Y)$ as $K$-algebras.

^a3ca0c

> [!proof]-
> We have that:
> 1. Let $X$ be a zero locus of $S\subseteq K[x_{1},\dots,x_{n}]$ and $Y$ a zero locus of $T\subseteq K[y_{1},..,y_{m}]$. Then, $$X\times Y=\{ (x,y)\in \mathbb{A}^{n+m}_{K}:f(x)=0,g(y)=0, \forall f\in S,g\in T \}$$Hence, $X\times Y$ is a zero locus of $S\times T$. 
> 2. We define a map: $$A(X)\times A(Y)\to A(X\times Y),\quad (f+I(X),g+I(Y))\mapsto fg+I(X\times Y)$$Then, it is indeed $K$-bilinear. To show that this is well-defined, we have that if $f'-f\in I(X)$, then: $f'g-fg=(f'-f)g$ and for all $(x,y)\in X\times Y$, $$(f'-f)(x)g(y)=0$$Hence, by universal property, $$\varphi:A(X)\otimes_{K} A(Y)\to A(X\times Y),\quad \varphi(\overline{f}\otimes \overline{g})=\overline{fg}$$
> 	which has the following inverse: $$\psi:A(X\times Y)\to A(X)\otimes_{K}A(Y),\quad \overline{h}\mapsto (\overline{h_{X}}\otimes  \overline{h_{Y}})$$where $h_{X}$ is a polynomial given by sending all $y_{1},\dots,y_{m}$ to $b\in Y$ and $h_{Y}$ $x_{1},\dots,x_{n}$ to $a\in X$ which are fixed chosen elements. This is again well-defined: Indeed, if $h-h'\in I(X\times Y)$, then for all $x\in X,y\in Y$: $$(h_{X}-h'_{X})(x)=h(x,b)-h'(x,b)=0,\quad (h_{Y}-h'_{Y})(y)=h(a,y)-h'(a,y)=0$$Further, $$\psi \circ  \varphi(\overline{f}\otimes  \overline{g})=\psi(\overline{fg})=\overline{(fg)_{X}}\otimes  \overline{(fg)_{Y}}=$$

^5054fd

---
##### Hilbert's Nullstellensatz
> [!lemma] Theorem 1 (Hilbert's Nullstellensatz)
> Let $K$ be an [[Algebraic Closure|algebraically closed field]].
> 1. All [[Maximal Ideal|maximal ideals]] of $K[x_{1},\dots,x_{n}]$ are of the form: $$I(a)=(x_{1}-a_{1},\dots,x_{n}-a_{n})$$for $a=(a_{1},..,a_{n})\in \mathbb{A}^n_{K}$.

> [!proof]-
> Let $P\unlhd K[x_{1},..,x_{n}]$ be a maximal ideal. Then, $K[x_{1},\dots,x_{n}] / P$ is a field and a finitely generated $K$-algebra. Hence, by [[Algebra|Hilbert's Nullstellensatz]], $K[x_{1},\dots,x_{n}] / P \cong K$ and: $$\pi: K\to K[x_{1},\dots,x_{n}] / P,\quad c\mapsto \overline{c}$$is an isomorphism. Choosing inverse images $a_{i}:=\pi ^{-1}(\overline{x_{i}})$, we get $\overline{x}_{i}=\overline{a}_{i}$ for all $i$ and hence, $$\overline{x}_{i}-\overline{a_{i}}=0$$Therefore, $(x_{1}-a_{1},\dots,x_{n}-a_{n})\subseteq P$. However, as the LHS is a maximal ideal, we have the equality.
---
> [!lemma] Theorem 2 (Hilbert's Nullstellensatz)
> Let $K$ be a field and $R$ a finitely generated $K$-algebra. 
> 1. for any $I\unlhd R$, $\sqrt{ I }=\bigcap_{P\in \text{Max}(R), P\supseteq I}^{}P$

> [!proof]-
> The inclusion $\subseteq$ follows from [[Radical (Ring)|lemma 2]]. For the converse, let $f\in R$ with $f\notin \sqrt{ I }$. We have to find a maximal ideal $P\unlhd R$ with $P\supseteq I$ and $f\notin P$. Consider the multiplicatively closed set $S:=\{ f^n:n\in \mathbb{N} \}$ As $f\notin \sqrt{ I }$, we have that $I\cap S=\varnothing$.  Hence, $I$ is contained in the prime ideal $P$ of $R$ s.t. $P\cap S=\varnothing$ and $P_{f}:=S^{-1}P$ is maximal in $R_{f}:=S^{-1}R$. In particular, $f\notin P$. It only remains to show that $P$ is maximal.
> 
> Consider the ring extension $R_{f} / P_{f} :R / P:K$ where $R_{f} / P_{f}:R / P$ holds as $R / P$ is an integral domain. Furthermore, $R_{f} / P_{f}$ is a field as $P_{f}$ is maximal, and finitely generated as a $K$-algebra. So $R_{f} / P_{f}:K$ is a finite field extension by [[Algebra|Hilbert's Nullstellensatz]] and integral. However, this shows that $R_{f} / P_{f}:R / P$ is integral as well, which shows that $R / P$ is a field as well from [[Ring Extension|Incomparability]]. Hence, $P$ is maximal.
---
> [!lemma] Theorem 3 (Hilbert's Nullstellensatz)
> Let $X\subseteq \mathbb{A}^n_{K}$ be a variety over an algebraically closed field $K$. 
> 1. for every ideal $I\unlhd A(X)$, we have $I(V(I))=\sqrt{ I }$.
> 2. In particular, there is a one-to-one correspondence: $$\begin{array}{rcl}\{ \text{subvarieties of }X \}&\leftrightarrow &\{ \text{radical ideals of }A(X) \}\\Y&\mapsto &I(Y)\\V(I)&\gets&I\end{array}$$

> [!proof]-
> We have that:
> 1. $\subseteq$: Assume $f\notin \sqrt{ I }$. Then, by Theorem 2, there exists a maximal ideal $P\unlhd A(X)$ with $P \supseteq I$ and $f\notin P$. However, by Theorem 1, this has to be of the form: $$I(a)=(x_{1}-a_{1},\dots,x_{n}-a_{n})$$for some $a\in X$. Now, $I(a)\supseteq I$ implies that $a\in V(I)$ and as $f\notin I(a)$, $f(a)\neq 0$. Hence, $f\notin I(V(I))$. 
> 2. $\supseteq$: Let $f\in \sqrt{ I }$, i.e. $f^n\in I$ for some $n\in \mathbb{N}$. Then, $(f(a))^n = 0$ and hence $f(a)^n=0$ for all $a\in V(I)$. Hence, $f\in I(V(I))$. 
>    
> The second statement follows from Proposition 4, Lemma 2.4, and 1. 
---
##### Dimensions
> [!lemma] Proposition 1
> For a variety $X$ and an irreducible subvariety $Y$,
> 1. $\text{dim}X\geq \text{dim} Y+\text{codim}_{X}Y$

---
##### Examples 
> [!h] Example 1
> We have:
> 1. $\varnothing$ and $\mathbb{A}_{K}^n$ are varieties as $V(1)$ and $V(0)$.
> 2. $V(x_{1}^{2}+x_{2}^{2}+1)\subseteq \mathbb{A}_{\mathbb{R}}^{2}$ is the unit circle.
> 3. $V(x_{1}x_{3},x_{2}x_{3})\subseteq \mathbb{A}_{\mathbb{R}}^3$ is the $x_{1}x_{2}$-plane.

^d6893c

---
> [!h] Example 2
> We have:
> 1. $\text{SL}_{n}\subseteq \text{Mat}_{n,n}(\mathbb{R})\cong \mathbb{A}_{\mathbb{R}}^{n^{2}}$ is a variety as $V(\det - 1)$.
> 2. $V(D_{n})\subseteq \mathcal{P}_{n}$ where $D_{n}$ the discriminant denotes the subset of polynomials with multiple roots. 
> 3. $\text{GL}_{n}(\mathbb{R})= \text{Mat}_{n,n}(\mathbb{R})\backslash V(\det)$  is non-empty open, hence dense by Proposition 7.

^1e3e77

---
> [!h] Example 3 (Ideal of a Point)
> Let $X\subseteq \mathbb{A}^n_{K}$. 
>  1. if $X=\{ a \}$, then $I(a)=(x_{1}-a_{1},\dots,x_{n}-a_{n})$.
>  2. $I(a)$ is maximal in $K[x_{1},\dots,x_{n}]$.

^8bb4dc

> [!proof]-
> We have:
> 1. Let $f\in I(a)$. Then, $f(a)=0$. Hence, $f$ is zero modulo $(x_{1}-a_{1},\dots,x_{n}-a_{n})$ and $f\in (x_{1}-a_{1},\dots,x_{n}-a_{n})$.
> 	
> 	Conversely, if $f\in (x_{1}-a_{1},\dots,x_{n}-a_{n})$, then $f=\sum_{i=1}^{n}(x_{i}-a_{i})f_{i}$ for some $f_{1},\dots,f_{n}\in K[x_{1},\dots,x_{n}]$. Hence, $f(a)=0$. 
> 2. Consider the ring homomorphism: $$K[x_{1},\dots,x_{n}] / I(a)\to K,\quad \overline{f}\mapsto f(a)$$Then, this is an isomorphism and $K[x_{1},\dots,x_{n}] / I(a)\cong K$ hence is a field. Therefore, $I(a)$ is maximal. 

^8520c7

---
> [!h] Example 4 (Irreducible and Reducible Varieties)
> We have:
> 1. $V(x_{1},x_{2})\subseteq \mathbb{A}_{\mathbb{R}}^2$ is a reducible variety.
---
##### Non-Examples
> [!h] Non-Example 1
> We have:
> 1. $\mathbb{Z}\subseteq \mathbb{A}_{\mathbb{C}}^1$ is not a variety.

^cde87b

> [!proof]-
> We have:
> 1. $I(\mathbb{Z})=(0)$ by Liouville's theorem. However, $V(0)=\mathbb{A}_{\mathbb{C}}^1$.

^cc24f3

---