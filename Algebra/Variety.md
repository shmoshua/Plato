#Algebra #Definition 

> [!definition]
> Let $K$ be a [[field]] and $S\subseteq K[x_{1},\dots,x_{n}]$. Then, $$V(S):=\{  x\in \mathbb{A}_{K}^n:f(x)=0, \forall f\in S \}\subseteq \mathbb{A}_{K}^n$$is called the ***zero locus*** of $S$, where $\mathbb{A}_{K}^n$ is the [[affine space]] over $K$. Subsets of $\mathbb{A}_{K}^n$ like these are called ***varities***.

^1a7b97

- **Related definition**: For any $X\subseteq \mathbb{A}_{K}^n$, the ***ideal*** of $X$ is defined as:$$I(X):=\{  f\in K[x_{1},\dots,x_{n}]:f(x)=0,\forall x\in X \}$$ ^d9dae1

- **Related definition**: For a variety $X\subseteq \mathbb{A}_{K}^n$ and $S\subseteq A(X)$ the [[ring of polynomial functions]], a ***subvariety*** of $X$ is given by: $$V_{X}(S):=\{  x\in X: f(x)=0, \forall f\in S \}\subseteq X$$with ideal $I_{X}(Y)=\{ f\in A(X): f(y)=0, \forall y\in Y \}$. Subvarieties of $X$ are exactly the varieties in $\mathbb{A}_{K}^n$ contained in $X$.
- **Related definition**: A variety $X$ is ***irreducible*** if there is no proper decomposition into subvarieties $X=X_{1}\cup X_{2}$ s.t. $X_{1},X_{2}\subsetneq X$. Otherwise, $X$ is ***reducible***.

---
##### Properties
> [!lemma] Proposition 1
> For $X\subseteq \mathbb{A}_{K}^n$, 
> 1. $I(X)\unlhd K[x_{1},\dots,x_{n}]$.

^35d70d

> [!proof]-
> We have:
> 1. for any $f\in I(X)$ and $g\in K[x_{1},\dots,x_{n}]$, $fg(x)=0$ for $x\in X$. Further, $I(X)$ is an additive subgroup.

^c6655d

---
> [!lemma] Lemma 2
> For a variety $X\subseteq \mathbb{A}_{K}^n$ with its [[Ring of Polynomial Functions|coordinate ring]] $A(X)$, $Y,Y'\subseteq X$ and $S,S'\subseteq A(X)$:
> 1. if $Y\subseteq Y'$, $I_{X}(Y')\subseteq I_{X}(Y)$. 
> 2. if $S\subseteq S'$, $V_{X}(S')\subseteq V_{X}(S)$. 
> 3. $Y\subseteq V(I(Y))$ and $S\subseteq I(V(S))$.
> 4. if $Y\subseteq X$ is a subvariety, $Y=V(I(Y))$.

^dfb872

> [!proof]-
> We have: 
> 1. if $f\in I_{X}(Y')$, then $f(x)=0$ for all $x\in Y'$ and thereby $Y$.
> 2. if $x\in V_{X}(S')$, then $f(x)=0$ for all $f\in S'$ and thereby $S$.  
> 3. for $x\in Y$ and $f\in I(Y)$, $f(x)= 0$. Therefore, $x\in V(I(Y))$. Similarly, for $f\in S$ and $x\in V(S)$, $f(x)=0$. Therefore, $S\subseteq I(V(S))$. 
> 4. One direction is clear from 3. If $Y$ is a subvariety, $Y=V(S)$ and as $S\subseteq I(V(S))$, we have by 2, $V(S)\supseteq V(I(V(S)))$.

^c712ee

- **Corollary**: there are maps between subvarieties of $X$ and ideals in $A(X)$ given by $I$ and $V$. ($I$ is injective but $V$ is not. e.g. $V(x)=V(x^2))\subseteq \mathbb{A}_{K}^1$)   ^df9fc7
---
> [!lemma] Proposition 3
> For a variety $X\subseteq \mathbb{A}_{K}^n$ and $Y\subseteq X$ a subvariety. Then, 
> 1. $I_{X}(Y)\unlhd A(X)$ is [[Radical (Ring)|radical]].

^4f0f2a

> [!proof]-
> Let $f\in \sqrt{ I_{X}(Y) }$, i.e. $f\in A(X)$ with $f^n\in I(Y)$. Then, $f^n(x)=0$ for all $x\in Y$. Therefore, $f(x)=0$ for all $x\in Y$. Hence, $f\in I(Y)$.

^88859e

---
> [!lemma] Theorem 4 (Hilbert's Nullstellensatz)
> For a variety $X\subseteq \mathbb{A}_{K}^n$ and a subvariety $Y\subseteq X$, 
> 1. for any ideal $I\unlhd A(X)$, $I(V(I))=\sqrt{ I }$ where $\sqrt{ I }$ is the [[Radical (Ring)|radical]].

^121639

- **Corollary**: There is a bijection between subvarieties of $X$ and radical ideals in $A(X)$ given by $I$ and $V$.  ^039994
---
> [!lemma] Proposition 5
> We have that:$$\begin{array}{ccccc}
\{ \text{Var}\subseteq \mathbb{A}_{K}^n \}&\to &\{ \text{Rad. ideals in }K[x_{1},\dots,x_{n}] \}&\to &\{ \text{fin. gen. reduced }K\text{-algebra} \}\\X&\mapsto &I(X)&\mapsto &A(X):=K[x_{1},..,x_{n}] / I(X)
\\V(I)&\gets&I\end{array}$$

^4ec3ba

> [!proof]-
> The first half is given by the Corollary above. The second half is given by [[Algebra|Lemma 1]] and [[Nilradical|Lemma 1]].

^89aa91

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

^1e3e77

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