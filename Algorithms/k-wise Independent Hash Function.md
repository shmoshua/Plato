#Definition #Algorithms 

> [!definition]
> A ***uniform, $k$-wise independent family of hash functions***  is a distribution $\mathcal{H}_{k,U,m}$ on $[m]^U$ s.t. for $h\sim \mathcal{H}_{k,U,m}$,
> 1. for all $x\in \{ 0,\dots,U \},i\in\{ 0,\dots,m \}$, $\mathbb{P}(h(x)=i)=\frac{1}{m}$
> 2. for any $x_{1},\dots,x_{n}\in \{ 0,\dots,U \}$, $h(x_{1}),\dots,h(x_{n}):\Omega\to[m]$ are [[Independence|$k$-wise independent]] [[Random Variable|random variables]].
- **Related definition**: A $k$-wise independent family of hash functions $\mathcal{H}_{k,U,m}$ has ***uniformity $u\geq 1$*** if:
	1. for all $x\in \{ 0,\dots,U \},i\in\{ 0,\dots,m \}$, $\mathbb{P}(h(x)=i)\leq\frac{u}{m}$
---
##### Examples
> [!h] Example 1
> Let $p$ be prime. Then, $\mathcal{G}_{2,p,p}:=\text{Uni}\left( \bigcup_{a,b\in \mathbb{F}_{p}}^{}\{ h_{a,b} \} \right)$  for $h_{a,b}(x)=ax+b$ is a uniform, $2$-wise independent family of hash functions.

> [!proof]-
> Let $h\sim \mathcal{G}_{2,p,p}$. Then, 
> 1. Let $x,y\in [p]$ with $x\neq y$. Now, for any $i,j\in[p]$, $h_{a,b}(x)=i$ and $h_{a,b}(y)=j$ can be written as the linear system: $$\begin{bmatrix}1&x\\1&y\end{bmatrix}\begin{bmatrix}b\\a \end{bmatrix}=\begin{bmatrix}i\\j\end{bmatrix}$$Since this matrix is invertible, there is a unique solution $a^{*},b^{*}$. Hence, we have: $$\mathbb{P}(h_{a,b}(x)=i,h_{a,b}(y)=j)=\mathbb{P}(a=a^{*},b=b^{*})=\frac{1}{p^{2}}$$Hence, we have that: $$\mathbb{P}(h_{a,b}(x)=i)=\sum_{j\in[p]}^{}\mathbb{P}(h_{a,b}(x)=i,h_{a,b}(y)=j)=\frac{1}{p}$$Further, $\mathcal{G}_{2,p,p}$ is $2$-wise independent.
---
> [!h] Example 2
> For a prime $p$ and $k\in \mathbb{N}$, $\mathcal{G}_{k,p,p}:=\text{Uni}\left( \bigcup_{a_{1},\dots,a_{k}\in \mathbb{F}_{p}}^{}\left\{  x\mapsto \sum_{i=1}^{k}a_{i}x^{i-1}  \right\} \right)$ is a uniform $k$-wise independent family of hash functions.

> [!proof]-
> For distinct $x_{1},\dots,x_{k}\in [p]$ and $i_{1},\dots,i_{k}\in[p]$, we can write: $$\begin{bmatrix}x_{1}^0&x_{1}^0&\dots&x_{1}^k\\x_{2}^0&x_{2}^0&\dots&x_{2}^k\\ \vdots&\vdots&&\vdots\\x_{k}^0&x_{k}^1&\dots&x_{k}^k\end{bmatrix}\begin{bmatrix}a_{1}\\a_{2}\\\vdots\\a_{k}\end{bmatrix}=\begin{bmatrix}i_{1}\\i_{2}\\\vdots\\i_{k}\end{bmatrix}$$As $x_{1},\dots,x_{k}$ are distinct the Vandermonde matrix is invertible and there exists a unique solution $(a^{*}_{1},\dots,a^{*}_{k})$. Hence, $$\mathbb{P}(h_{k}(x_{j})=i_{j}, \forall j\in[k])= \frac{1}{p^k}$$The rest follows from  Example 1.
---
> [!h] Example 3
> For $m$ and $k\in \mathbb{N}$, let $p$ be a prime s.t. $4cm\geq p\geq 2cm$. Then, 
> 1. $\mathcal{G}_{k,m,m}:= \text{Uni}\left( \bigcup_{a_{1},\dots,a_{k}\in \mathbb{F}_{p}}^{}\left\{  x\mapsto \sum_{i=1}^{k}a_{i}x^{i-1}  \mod m  \right\}\right)$ is a $k$-wise independent family of hash functions with uniformity $1+\frac{1}{2c}$.

> [!proof]-
> From Example 2, we have that: for $h_{a_{1:n}}(x):=\sum_{i=1}^{k}a_{i}x^{i-1}$, we have that: $$\mathbb{P}(h_{a_{1:n}}(x_{1})=i_{1},\dots,h_{a_{1:n}}(x_{k})=i_{k})=\frac{1}{p^k}$$Further, we have that $\mathbb{P}(h_{a_{1:n}}(x_{1})=i_{1})=1/p$.
> 
> Now, let $p'\in[m]$ s.t. $p':=p \mod m$. Further, for $x\in[m]$, let $m(x)$ denote the number of integers $y\in[p]$ s.t. $y=x\mod m$. Then, $$m(x)=\begin{cases}\left\lfloor p/m\right\rfloor &x<p'\\\left\lfloor p/m\right\rfloor +1&x\geq p'\end{cases}$$Hence, we have for $g_{a_{1:n}}(x):=h_{a_{1:n}}(x)\mod m$,  $$\begin{align}\mathbb{P}(g_{a_{1:k}}(x)=j)&=\sum_{i\in[p]:i = j\mod m}^{}\mathbb{P}(h_{a_{1:k}}(x)=i)\\&=m(j)\cdot p ^{-1}\\&\leq p ^{-1}(\left\lfloor p / m\right\rfloor +1 )\\&\leq \frac{1}{m}+\frac{1}{p}\\&\leq \left( 1+\frac{1}{2c} \right) \frac{1}{m} \end{align}$$Further, $$\begin{align}\mathbb{P}(g_{a_{1:n}}(x_{1})=i_{1},\dots,g_{a_{1:n}}(x_{k})=i_{k})&=p^{-k}\prod_{j=1}^{k}m(i_{j})\end{align}=\prod_{j=1}^{k}m(i_{j})p^{-1}=\prod_{j=1}^{k}\mathbb{P}(g_{a_{1:n}}(x_{j})=i_{j})$$
---
