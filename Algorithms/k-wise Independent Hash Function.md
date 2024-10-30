#Definition #Algorithms 

> [!definition]
> A ***uniform, $k$-wise independent family of hash functions***  is a distribution $\mathcal{H}_{k,U,m}$ on $[m]^U$ s.t. for $h\sim \mathcal{H}_{k,U,m}$,
> 1. for all $x\in \{ 0,\dots,U \},i\in\{ 0,\dots,m \}$, $\mathbb{P}(h(x)=i)=\frac{1}{m}$
> 2. for any $x_{1},\dots,x_{n}\in \{ 0,\dots,U \}$, $h(x_{1}),\dots,h(x_{n}):\Omega\to[m]$ are [[Independence|$k$-wise independent]] [[Random Variable|random variables]].
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