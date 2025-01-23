#Definition #InformationTheory 

> [!definition]
> For a finite set $\mathcal{X}$, a ***code*** is a map $C:\mathcal{X}\to \{ 0,1 \}^{+}$.

^bc3afd

- **Related definition**: the length is a function $L:\mathcal{\mathcal{X}}\to \mathbb{N}$ given by $L(x)=\left| C(x) \right|$. ^a0f71e
- **Related definition**: a code $C$ is ***non-singular*** if $C$ is injective.
- **Related definition**: an ***extension*** of the code $C$ is a map $$\mathcal{X}^+\to \{ 0,1 \}^+,\quad x_{1}\dots x_{n}\mapsto C(x_{1})\dots C(x_{n})$$
	A code $C$ is ***uniquely decodable*** if its extension is non-singular.
- **Related definition**: A code $C$ is ***prefix-free*** or ***instantaneous*** if no codeword is the prefix of another. 

---
##### Properties
> [!lemma] Proposition 1
> For any prefix-free code $C:\mathcal{X}\to \{ 0,1 \}^+$,
> 1. $C$ is uniquely decodable.
> 2. $C$ is equivalent to a binary tree where $\mathcal{X}$ are leaves.

> [!proof]-
> Assume $C$ is not uniquely decodable. Then, there exists $x_{1}\dots x_{n}$, $y_{1},\dots,y_{m}\in \mathcal{X}$ s.t. $$C(x_{1})\dots C(x_{m})=C(y_{1})\dots C(y_{m})$$Wlog we may assume that $x_{1}\neq y_{1}$ and $L(x_{1})\leq L(y_{1})$. Then, $C(x_{1})$ is clearly a prefix of $C(y_{1})$ and $C$ is not prefix-free.
---
> [!lemma] Theorem 2 (Kraft's inequality)
> We have that:
> 1. For a uniquely decodable code $C$, $\sum_{x\in \mathcal{X}}^{}2^{-L(x)}\leq 1$.
> 2. For positive integers $\ell_{1},\dots,\ell_{n}$ s.t. $\sum_{i=1}^{m}2^{-\ell_{i}}\leq 1$, there exists a prefix-free code with $\ell_{1},\dots,\ell_{n}$ as lengths. 

> [!proof]-
> We have:
> 1. For any $k\geq 1$, we have that: $$\begin{align}\left( \sum_{x\in \mathcal{X}}^{}2^{-L(x)} \right)^k&=\sum_{x_{1},\dots,x_{k}}^{}2^{-\sum_{i=1}^{k}L(x_{i})}=\sum_{x\in \mathcal{X}^k}^{}2^{-L(x)}=\sum_{m=1}^{k\cdot \ell_{\max}}a(m)\cdot 2^{-m}\leq k\cdot \ell_{\max}\end{align}$$where $a(m)$ denotes the number of elements in $\mathcal{X}^k$ with code length $m$. Therefore, $$ \sum_{x\in \mathcal{X}}^{}2^{-L(x)} \leq(k\cdot \ell_{\max})^{1/k}\to 1$$
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
>    By definition this is always prefix free. We will show that there exists such a $c_{i}$ at every step. Let $i<j$. Then, the number of elements in $S_{\ell_{j}}$ that does not have $c_{i}$ as prefix is given by $2^{\ell_{j}-\ell_{i}}$. Therefore, there are at least $2^{\ell_{i}}-\sum_{k=1}^{i-1}2^{\ell_{i}-\ell_{k}}$ codewords to choose from. However, we have $\sum_{k=1}^{i-1}2^{-\ell_{k}}\leq 1-2^{-\ell_{i}}$
>    
>    $$2^{\ell_{i}}\left( 1-\sum_{k=1}^{i-1}2^{-\ell_{k}} \right)\geq 2^{\ell_{i}}\cdot 2^{-\ell_{i}}=1 $$This proves the statement.
---
> [!lemma] Theorem 3 (Optimal Length)
> Consider $L^{*}$ to be the optimal solution of the following optimization problem.
> $$\begin{align}\underset{ \ell_{1},\dots,\ell_{n}\in \mathbb{Z}_{> 0} }{ \min }\quad &\sum_{i=1}^{n}p_{i}\ell_{i}\\\text{subject to}\quad&\sum_{i=1}^{n}2^{-\ell_{i}}\leq 1\end{align}$$
> Then, 
> 1. $H(X)\leq L^{*}< H(X)+1$.

> [!proof]-
> Firstly, we will consider the relaxation of the problem where $\ell_{1},\dots,\ell_{n}$ are not necessarily integers. Then, by Lagrange, we have: $$\begin{align}0&=\frac{ \partial  }{ \partial \ell_{i} } \sum_{i=1}^{n}p_i\ell_{i}+\lambda \left( \sum_{i=1}^{n}2^{-\ell_{i}} -1\right)\\&=p_{i}-\lambda \ln 2 \cdot 2^{-\ell_{i}} \end{align}$$Hence, $\ell_{i}=-\log_{2}(p_{i} / \lambda \ln 2)$ for some $\lambda>0$. Then, $$\sum_{i=1}^{n}p_{i} \ell_{i}=\sum_{i=1}^{n}p_{i} \log_{2}\left( \frac{\lambda \ln 2}{p_{i}} \right) =\log_{2}(\lambda \ln 2)-\sum_{i=1}^{}p_{i}\log_{2} p_{i} \geq -\sum_{i=1}^{}p_{i}\log_{2} p_{i} $$where the equality is given when $\lambda=1 / \ln 2$. Hence, $L^{*}\geq-\sum_{i=1}^{n}p_{i}\log_{2}(p_{i})=H(X)$.
> 
> Conversely, assume $\ell_{i}:= \left\lceil \log_{2} \frac{1}{p_{i}}\right\rceil$. Then, $$L^{*}\leq\sum_{i=1}^{n}p_{i}\ell_{i}<\sum_{i=1}^{n}p_{i}\left( \log_{2} \frac{1}{p_{i}}+1 \right)=H(X)+1$$
> 

---

> [!lemma] Theorem 4 (Huffman Codes)
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

> [!proof]-
> Notice that:
> 1. hihi
> 2. For a code $C$, let $L(C)$ denote the average length of $C$. 
>    
>    We show by induction over $n:=\left| \mathcal{X} \right|$. Let $n=2$. Then, $G$ is a binary tree with two leaves and $\ell_{\max}=1$. This has to be optimal.
>    
>    Let $\mathcal{X}=\{ x_{1},\dots,x_{n} \}$ with $p_{1},\dots,p_{n}$ and without loss of generality, assume that $p_{n-2}\geq p_{n-1}\geq p_{n}$. Then, consider $G'$ in the algorithm. Now, let $C,C'$ denote the code given from $G,G'$ respectively. We have that by assumption $C'$ is optimal.
>    
>    Suppose we have another code $D$ on $\mathcal{X}$ s.t. $L(D)<L(C)$. Then, wlog we may assume that $L(x_{n-1})=L(x_{n})=\ell_{\max}(D)$. (otherwise we can always swap them and achieve lower average length). Then, by switching between leaves at level $\ell_{\max}(D)$, we have that there exists $y\in \{ 0,1 \}^+$ s.t. $\{ D(x_{n-1}),D(x_{n}) \}=\{ y0,y 1 \}$.
>    
>    Then, we now construct $D'$ on $\mathcal{X'}$ given as: $$D'(z):=\begin{cases}D(z)&\text{if }z\in \mathcal{X}\\y&\text{otherwise}\end{cases}$$We have that this is prefix free and $$L(D')=L(D)-p_{n}-p_{n-1}<L(C)-p_{n}-p_{n-1}=L(C')$$which is a contradiction to the optimality of $C'$. 
>    
---

##### Examples
> [!h] Example 1 (Not Prefix-Free but Uniquely Decodable Code)
> Consider $\mathcal{X}:=\{ a,b,c,d \}$ where: $$\begin{align}a&\mapsto 10\\b&\mapsto 00\\c&\mapsto 11\\b&\mapsto 110\end{align}$$
---
