#Definition #InformationTheory 

> [!definition]
> For a finite set $\mathcal{X}$, a ***code*** is a map $C:\mathcal{X}\to \{ 0,1 \}^{+}$ where for a set $A$, $A^+:=\bigcup_{i=1}^{\infty}A^i$.

^bc3afd

- **Related definition**: the ***length*** of a code $C$ is a map $\ell:\mathcal{\mathcal{X}}\to \mathbb{N}$ given by $\ell(x)=\left| C(x) \right|$. ^a0f71e
- **Related definition**: the ***expected description length*** of a code is given as: $$L(C):=\mathbb{E}_{X}[\ell(X)]$$ ^f40365
- **Related definition**: a code $C$ is ***non-singular*** if $C$ is injective. ^e75eeb
- **Related definition**: an ***extension*** of the code $C$ is a map $$C^+:\mathcal{X}^+\to \{ 0,1 \}^+,\quad x_{1}\dots x_{n}\mapsto C(x_{1})\dots C(x_{n})$$
	A code $C$ is ***uniquely decodable*** if its extension is non-singular. ^8239b2
- **Related definition**: A code $C$ is ***prefix-free*** or ***instantaneous*** if no codeword is the prefix of another.  ^92dedb

---
##### Properties
> [!lemma] Proposition 1
> For any prefix-free code $C:\mathcal{X}\to \{ 0,1 \}^+$,
> 1. $C$ is uniquely decodable.
> 2. $C$ is equivalent to a [[Tree|binary tree]] where $C(\mathcal{X})$ are leaves.

^866846

> [!proof]-
> We have: 
> 1. Assume $C$ is not uniquely decodable. Then, there exists $x_{1}\dots x_{n}$, $y_{1},\dots,y_{m}\in \mathcal{X}$ s.t. $$C(x_{1})\dots C(x_{m})=C(y_{1})\dots C(y_{m})$$Wlog we may assume that $x_{1}\neq y_{1}$ and $\ell(x_{1})\leq \ell(y_{1})$. Then, $C(x_{1})$ is clearly a prefix of $C(y_{1})$ and $C$ is not prefix-free.
> 2. Let $C$ be a code with maximum length $k$. We then generate a tree $T$ on $$D:=\left\{   v\in \bigcup_{i=1}^{k} \{ 0,1 \}^i: \forall x\in \mathcal{X},C(x)\text{ is not a prefix of }v\right\}\cup C(\mathcal{X})$$where between $x\to(x,0)$ and $x\to(x,1)$ if they exist in $D$. Then, this is by construction a binary tree. To show that $\mathcal{X}$ are leaves, we have that for all $x\in \mathcal{X}$, there is no $C(x)\neq y\in D$ s.t. $C(x)$ is a prefix of $y$. Hence, $C(x)$ is a leaf. 

^dd6b98

---
> [!lemma] Theorem 2 (Kraft's inequality)
> We have that:
> 1. For a uniquely decodable code $C$, $\sum_{x\in \mathcal{X}}^{}2^{-\ell(x)}\leq 1$.
> 2. For positive integers $\ell_{1},\dots,\ell_{n}$ s.t. $\sum_{i=1}^{m}2^{-\ell_{i}}\leq 1$, there exists a prefix-free code with $\ell_{1},\dots,\ell_{n}$ as lengths. 

^25cc1f

> [!proof]-
> We have:
> 1. For any $k\geq 1$, we have that: $$\begin{align}\left( \sum_{x\in \mathcal{X}}^{}2^{-\ell(x)} \right)^k&=\sum_{x_{1},\dots,x_{k}}^{}2^{-\sum_{i=1}^{k}\ell(x_{i})}=\sum_{x\in \mathcal{X}^k}^{}2^{-\ell(x)}=\sum_{m=1}^{k\cdot \ell_{\max}}a(m)\cdot 2^{-m}\leq k\cdot \ell_{\max}\end{align}$$where $a(m)$ denotes the number of elements in $\mathcal{X}^k$ with code length $m$ and $a(m)\leq 2^m$ as $C$ is uniquely decodable. Therefore, $$ \sum_{x\in \mathcal{X}}^{}2^{-\ell(x)} \leq(k\cdot \ell_{\max})^{1/k}\to 1$$
> 2. Modulo reordering assume that $\ell_{1}\leq\dots\leq \ell_{n}$. Let $S_{k}:=\{ 0,1 \}^k$ with lexicographical ordering. Then, we have the following algorithm.
> 	```pseudo
>    \begin{algorithm} \caption{Kraft($\ell_{1},\dots,\ell_{n}$)} 
>    \begin{algorithmic}
>    \For{$i\in [n]$}
>    \State $c_i\gets $ first element in $S_{\ell_{i}}$ that does not have $c_{1},\dots,c_{i-1}$ as prefix.
>    \EndFor
>    \Return $c_{1},\dots,c_{n}$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    
>    By definition this is always prefix-free. We will show that there exists such a $c_{i}$ at every step. Let $i<j$. Then, the number of elements in $S_{\ell_{j}}$ that does not have $c_{i}$ as prefix is given by $2^{\ell_{j}-\ell_{i}}$. Therefore, there are at least $2^{\ell_{i}}-\sum_{k=1}^{i-1}2^{\ell_{i}-\ell_{k}}$ codewords to choose from. However, we have $\sum_{k=1}^{i-1}2^{-\ell_{k}}\leq 1-2^{-\ell_{i}}$
>    
>    $$2^{\ell_{i}}\left( 1-\sum_{k=1}^{i-1}2^{-\ell_{k}} \right)\geq 2^{\ell_{i}}\cdot 2^{-\ell_{i}}=1 $$This proves the statement.

^74678f

---
> [!lemma] Theorem 3 (Optimal Length)
> Let $\left| \mathcal{X} \right|=:n$ and $p_{1},\dots,p_{n}$ denote a probability distribution on $\mathcal{X}$, i.e. $\sum_{i=1}^{n}p_{i}=1$. Then, for:
> $$\begin{align}L^{*}:=\underset{ \ell_{1},\dots,\ell_{n}\in \mathbb{Z}_{> 0} }{ \min }\quad &\sum_{i=1}^{n}p_{i}\ell_{i}\\\text{subject to}\quad&\sum_{i=1}^{n}2^{-\ell_{i}}\leq 1\end{align}$$
> Then, 
> 1. $H(X)\leq L^{*}< H(X)+1$.
> 2. $L^{*}$ is the minimal expected length over all uniquely decodable codes.

^c8b0bf

> [!proof]-
> We have:
> 1. Firstly, we will consider the relaxation of the problem where $\ell_{1},\dots,\ell_{n}$ are not necessarily integers. Then, by Lagrange, we have: $$\begin{align}0&=\frac{ \partial  }{ \partial \ell_{i} } \sum_{i=1}^{n}p_i\ell_{i}+\lambda \left( \sum_{i=1}^{n}2^{-\ell_{i}} -1\right)\\&=p_{i}-\lambda \ln 2 \cdot 2^{-\ell_{i}} \end{align}$$Hence, $\ell_{i}=-\log_{2}(p_{i} / \lambda \ln 2)$ for some $\lambda>0$. Then, $$\sum_{i=1}^{n}p_{i} \ell_{i}=\sum_{i=1}^{n}p_{i} \log_{2}\left( \frac{\lambda \ln 2}{p_{i}} \right) =\log_{2}(\lambda \ln 2)-\sum_{i=1}^{}p_{i}\log_{2} p_{i} \geq -\sum_{i=1}^{}p_{i}\log_{2} p_{i} $$where the equality is given when $\lambda=1 / \ln 2$. Hence, $L^{*}\geq-\sum_{i=1}^{n}p_{i}\log_{2}(p_{i})=H(X)$.
> 
> 	Conversely, assume $\ell_{i}:= \left\lceil \log_{2} \frac{1}{p_{i}}\right\rceil$. Then, $$L^{*}\leq\sum_{i=1}^{n}p_{i}\ell_{i}<\sum_{i=1}^{n}p_{i}\left( \log_{2} \frac{1}{p_{i}}+1 \right)=H(X)+1$$
> 2. Let $L'$ denote the optimal length over all uniquely decodable codes. Let $\ell_{1},\dots,\ell_{n}$ generate $L^{*}$. Then, by Kraft, there exists a prefix code with $L^{*}$ as expected length. Hence, by Proposition 1.1, $L'\leq L^{*}$. 
>    
>    The converse also holds by Kraft. Therefore, $L'=L^{*}$.

^0a6de9

- **Corollary**: By defining the code to be $\kappa$-to-variable, i.e. $C:\mathcal{X}^\kappa\to \{ 0,1 \}^+$, we can reduce the additive error by $H(X)\leq L^{*} / \kappa < H(X)+ 1/\kappa$ ^7f2436
---
> [!lemma] Proposition 4 (Code Intervals)
> Let $C:\mathcal{X}\to \{ 0,1 \}^+$ be a binary code. We define for $c\in \{ 0,1 \}^+:$ $$J(c):=[0.c,0.c+2^{-\left| c \right| })$$Then, for any $c,c'\in \{ 0,1 \}^+$
> 1. $c'$ is a prefix of $c$ if and only if $J(c')\supseteq J(c)$.

^c590a0

> [!proof]-
> We have:
> 1. If $c'=c$, it's trivial. Otherwise, assume that $c'$ is a prefix of $c$. Then, $0.c'\leq 0.c$. Further, let $b\in \{ 0,1 \}^+$ s.t. $(c',b)=c$. Then, $$0.c+2^{-\left| c \right| }\leq 0.c'+0.b\cdot 2^{-\left| c' \right| }+2^{-\left| b \right| }2^{-\left| c' \right|  }=0.c'+\underbrace{ (0.b+2^{-\left| b \right| }) }_{ \leq 1 }\cdot 2^{-\left| c' \right| }\leq 0.c'+2^{-\left| c' \right| }$$
>    Conversely, $0.c'+2^{-\left| c' \right|}=0.(c'+1)$. Hence, if $J(c)\subseteq J(c')$, then $0.c'\leq 0.c < 0.(c'+1)$. This proves the statement.

^a729b7

---

> [!lemma] Theorem 5 (Huffman Codes)
> Consider the algorithm:
>  ```pseudo
>    \begin{algorithm} \caption{HuffmanRecursion($\mathcal{X},p:\mathcal{X}\to[0,1]$)} 
>    \begin{algorithmic}
>    \If{$\left| \mathcal{X} \right|=1$} 
>    \Return $G:=(\mathcal{X},\varnothing)$ as a graph.
>    \EndIf
>    \State Choose $x,y\in \mathcal{X}$ with the smallest $p$ values.
>    \State $\mathcal{X}'\gets \{ x' \}\cup \mathcal{X} \backslash \{ x,y \}$
>    \State $p'(z)\gets \begin{cases}p(z)&z\in \mathcal{X}\\p(x)+p(y)&z=x'\end{cases}$
>    \State $G'\gets $\Call{HuffmanRecursion}{ $\mathcal{X}',p'$}
>    \State $G\gets (V(G')\cup \{ x,y \},E(G')\cup \{ (x',x),(x',y) \})$
>    \Return $G$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    Then, let $G$ be the output of $\text{HuffmanRecursion}(\mathcal{X},p)$. 
>    1. $G$ is a rooted binary tree with $\mathcal{X}$ exactly as leaves.
>    2. the corresponding prefix free code is optimal. 

^eb82e8

> [!proof]-
> Notice that:
> 1. Obvious by construction.
> 2. For a code $C$, let $\ell(C)$ denote the expected length of $C$. 
>    
>    We show by induction over $n:=\left| \mathcal{X} \right|$. Let $n=2$. Then, $G$ is a binary tree with two leaves and $\ell_{\max}=1$. This has to be optimal.
>    
>    Let $\mathcal{X}=\{ x_{1},\dots,x_{n} \}$ with $p_{1},\dots,p_{n}$ and without loss of generality, assume that $p_{n-2}\geq p_{n-1}\geq p_{n}$. Then, consider $G'$ in the algorithm. Now, let $C,C'$ denote the code given from $G,G'$ respectively. We have that by assumption $C'$ is optimal.
>    
>    Suppose we have another code $D$ on $\mathcal{X}$ s.t. $\ell(D)<\ell(C)$. Then, wlog we may assume that $\ell(x_{n-1})=\ell(x_{n})=\ell_{\max}(D)$. (otherwise we can always swap them and achieve lower average length). Then, by switching between leaves at level $\ell_{\max}(D)$, we have that there exists $y\in \{ 0,1 \}^+$ s.t. $\{ D(x_{n-1}),D(x_{n}) \}=\{ y0,y 1 \}$.
>    
>    Then, we now construct $D'$ on $\mathcal{X'}$ given as: $$D'(z):=\begin{cases}D(z)&\text{if }z\in \mathcal{X}\\y&\text{otherwise}\end{cases}$$We have that this is prefix free and $$L(D')=L(D)-p_{n}-p_{n-1}<L(C)-p_{n}-p_{n-1}=L(C')$$which is a contradiction to the optimality of $C'$. 
>    

^6a34a3

---
> [!lemma] Theorem 6 (Arithmetic Codes)
> Let $\mathcal{X}:=[n]$ and $p\in \Delta(\mathcal{X})$. We define: $$F:\mathcal{X}\to[0,1],\quad x\mapsto \sum_{x'<x}^{}p(x')$$
> Then, 
> 1. $C:\mathcal{X}\to \{ 0,1 \}^+, x\mapsto \left\lceil F(x)2^{\ell}\right\rceil 2^{-\ell}$ where $\ell:=1+\left\lceil \log \frac{1}{p(x)}\right\rceil$ is prefix free. 

^816bcd

> [!proof]-
>
> We have that:
> 1. We show that $J(C(x))$ and $J(C(x'))$ are disjoint for all $x,x'\in \mathcal{X}$. Let $c:=C(x)$. Notice that: $$F(x)\leq0.c$$and we have that: $$0.c+2^{-\ell}=F(x)+2^{-\ell }+2^{-\ell}=F(x)+2^{-\left\lceil \log 1/p(x)\right\rceil }\leq F(x)+p(x)$$Hence, $J(C(x))\subseteq[F(x),F(x)+p(x))$ and as $[F(x),F(x)+p(x))$ are disjoint by definition, $J(C(x))$ and $J(C(x'))$ are disjoint.
>    
>    By Proposition 4, this shows that the code is prefix free.

^9ef8e6

- **Remark**: As arithmetic coding depends only on $F,p$, this is useful when we want a $\kappa$-to-variable coding when $\kappa$ is large. Without constructing the binary tree, we can find the codeword for each word on the fly. Notice that $F(x_{1:\kappa}),p(x_{1:\kappa})$ can also easily be found from $F(x_{1:\kappa-1}),p(x_{1:\kappa-1})$ given iid source or Markov source. ^5c5f45
---

##### Examples
> [!h] Example 1 (Not Prefix-Free but Uniquely Decodable Code)
> Consider $\mathcal{X}:=\{ a,b,c,d \}$ where: $$\begin{align}a&\mapsto 10\\b&\mapsto 00\\c&\mapsto 11\\b&\mapsto 110\end{align}$$
---
