#Series #AGAO 

#### Problem 1

1. Let $S\subseteq V$ with  size $k$. Then, $\text{vol}(S)=k(n-1)\leq \frac{n(n-1)}{2}=\text{vol}(V) / 2$ if and only if $k\leq n /2$. Further, if $k\leq n /2$:$$\phi(S)=\frac{e(S,V \backslash S) }{k(n-1)}=\frac{k(n-k)}{k(n-1)}=\frac{n-k}{n-1}$$Hence, $$\phi(K_{n})=\min_{k\leq  n / 2}\frac{n-k}{n-1}=\frac{n-\left\lfloor n / 2\right\rfloor}{n-1}\approx\frac{1}{2}$$ 
2. Let $u,v$ be the endpoints of $P_{n}$. Let $S\subseteq V$ with size $k$. Then, $\text{vol}(S)=2k-\left| \{ u,v \}\cap S \right|$. Now, we can do the following case distinctions:
	1. Let $\left| \{ u,v \}\cap S \right|=0$. Then, $\text{vol}(S)=2k$ and $\text{vol}(S) \leq \text{vol}(V) / 2=n-1$ if and only if $k\leq \frac{n-1}{2}$. However, in this case, $e(S, V \backslash S)\geq 2$. Hence, $$\min_{S,\left| \{ u,v \}\cap S \right| =0} \frac{e(S, V \backslash S)}{ \text{vol}(S)}\geq\frac{1}{\left\lfloor \frac{n-1}{2}\right\rfloor }$$
	2. Let $\left| \{ u,v \}\cap S \right|=1$. Then, $\text{vol}(S)=2k -1$ and $\text{vol}(S) \leq \text{vol}(V) / 2=n-1$ if and only if $k\leq \frac{n}{2}$. Further, for any $k\leq n /2$, we can find $S$ s.t. $e(S, V \backslash S)=1$. Hence, $$\min_{S,\left| \{ u,v \}\cap S \right| =1} \frac{e(S, V \backslash S)}{ \text{vol}(S)}=\frac{1}{2\left\lfloor n /2\right\rfloor -1}$$
	3. Let $\left| \{ u,v \}\cap S \right|=2$. Then, $\text{vol}(S)=2k -2$ and $\text{vol}(S) \leq \text{vol}(V) / 2=n-1$ if and only if $k\leq \frac{n+1}{2}$. Further, for any $k\leq n /2$, we have that $e(S, V \backslash S)\geq 2$. Hence, $$\min_{S,\left| \{ u,v \}\cap S \right| =1} \frac{e(S, V \backslash S)}{ \text{vol}(S)}\geq \frac{1}{\left\lfloor \frac{n+1}{2}\right\rfloor -1}$$
   
   Therefore, we have that $\phi(P_{n})=\frac{1}{2\left\lfloor n / 2\right\rfloor-1}$ for all $n\geq 5$. 
   
---
#### Problem 2
1. We have that as $D=I$,  $$N=L=\begin{bmatrix}1&-1\\-1&1 \end{bmatrix},\quad \lambda_{2}(N)=2$$However, if $S$ is a single vertex, then: $\phi(S)=1$. Hence, $\phi(G)=1= \lambda_{2}(N) / 2$.
2. Let $G:=C_{n}$ be a cycle. We 