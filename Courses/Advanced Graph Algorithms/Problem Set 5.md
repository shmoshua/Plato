#Series #AGAO 

#### Problem 1

1. Let $S\subseteq V$ with  size $k$. Then, $\text{vol}(S)=k(n-1)\leq \frac{n(n-1)}{2}=\text{vol}(V) / 2$ if and only if $k\leq n /2$. Further, if $k\leq n /2$:$$\phi(S)=\frac{e(S,V \backslash S) }{k(n-1)}=\frac{k(n-k)}{k(n-1)}=\frac{n-k}{n-1}$$Hence, $$\phi(K_{n})=\min_{k\leq  n / 2}\frac{n-k}{n-1}=\frac{n-\left\lfloor n / 2\right\rfloor}{n-1}\approx\frac{1}{2}$$ 
2. Let $u,v$ be the endpoints of $P_{n}$. Let $S\subseteq V$ with size $k$. Then, $\text{vol}(S)=2k-\left| \{ u,v \}\cap S \right|$. Now, we can do the following case distinctions:
	1. Let $\left| \{ u,v \}\cap S \right|=0$. Then, $\text{vol}(S)=2k$ and $\text{vol}(S) \leq \text{vol}(V) / 2=n-1$ if and only if $k\leq \frac{n-1}{2}$. However, in this case, $e(S, V \backslash S)\geq 2$. Hence, $$\min_{S,\left| \{ u,v \}\cap S \right| =0} \frac{e(S, V \backslash S)}{ \text{vol}(S)}\geq\frac{1}{\left\lfloor \frac{n-1}{2}\right\rfloor }$$
	2. Let $\left| \{ u,v \}\cap S \right|=1$. Then, $\text{vol}(S)=2k -1$ and $\text{vol}(S) \leq \text{vol}(V) / 2=n-1$ if and only if $k\leq \frac{n}{2}$. Further, for any $k\leq n /2$, we can find $S$ s.t. $e(S, V \backslash S)=1$. Hence, $$\min_{S,\left| \{ u,v \}\cap S \right| =0} \frac{e(S, V \backslash S)}{ \text{vol}(S)}\geq\frac{1}{\left\lfloor \frac{n-1}{2}\right\rfloor }$$
   
   
   As we aim to find $S$ with the minimum conductance, we notice that if $S$ is a subpath that contains exactly one of $\{ u,v \}$, then $e(S,V \backslash S)=1$. Such $S$ also has $\text{vol}(S)=2k-1$. Therefore, $$\phi(P_{n})\leq \min_{k\leq n /2} \frac{1}{2k-1}=\frac{1}{2\left\lfloor n /2\right\rfloor -1}$$
   
   
   . Then, the volume is given as $2k-2\leq\text{vol}(S)\leq 2k$. If $\text{vol}(S)=2k$, then we have that $2\leq e(S,\overline{S})$. However, if $2k-1$, by taking the first $k$ vertices as $S$, we have that: $$\text{vol}(S)=1$$Therefore, we have that: $$\phi(P_{n})=\frac{1}{2\left\lfloor n  / 2\right\rfloor -1}$$
---