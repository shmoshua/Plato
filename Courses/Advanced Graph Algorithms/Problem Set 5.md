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
2. We know that $\lambda_{2}(N)= \Theta(n^{-2})$. Now, by Problem 1.2, we have: $$\phi(P_{n})^{2}< \frac{1}{(n-3)^{2}}\leq C\cdot \frac{1}{n^{2}}\leq C'\cdot  \lambda_{2}(N)$$which is what we want to show.
---
#### Problem 3
By symmetry again, i.e. $\sigma(S)=\sigma(V \backslash S)$, we have that $\sigma(G)=\min_{S\subseteq V, \left| S \right|\leq n /2}\sigma(S)$. Note that we have by Courant-Fischer: $$\lambda_{2}(L)=\min_{0\neq x \bot 1}\frac{x^\top Lx}{x^\top x}$$
Now, let $S\subseteq V$ with $\left| S \right|\leq n /2$. Let $z_{S}:= 1_{S}-\alpha1$ with $\alpha:=\frac{\left| S \right|}{\left| V \right|}$. Then, $$1^\top z_{S}=\left| S \right| -\frac{\left| S \right| }{\left| V \right| }\left| V \right| =0$$Further, as $L 1= 0$:$$z_{S}^\top L z_{S}=1_{S}^\top L 1_{S}-2\alpha 1^\top _{S}L 1+\alpha^{2} 1^\top L 1= 1_{S}^\top L 1_{S}$$and $$z_{S}^\top z_{S}=\left| S \right| -2\alpha \left| S \right| +\alpha^{2}\left| V \right| =\left| S \right| -\frac{\left| S \right| ^{2}}{\left| V \right| }\geq \frac{1}{2}\left| S \right| =\frac{1}{2}1_{S}^\top 1_{S}$$Therefore, $$\sigma(G)=\min_{S\subseteq V, \left| S \right| \leq n /2}\frac{e(S, V \backslash S)}{\left| S \right| }=\min_{S\subseteq V, \left| S \right| \leq n /2}\frac{1_{S}^\top L 1_{S}}{1_{S}^\top 1_{S} }\geq \frac{1}{2}\min_{S\subseteq V, \left| S \right| \leq n /2}\frac{z_{S}^\top L z_{S}}{z_{S}^\top z_{S} }\geq \frac{1}{2}\lambda_{2}(L)$$

---
#### Problem 4
Let $G\sim G(n,p)$ with $G=(V,E)$. Further, let $p\geq c\frac{\log n}{n}$ for some $c>0$. Then, as $d(v)\sim \text{Bin}(n-1,p)$, for $\mu:=(n-1)p$ by Chernoff:$$\begin{aligned}\mathbb{P}\left( \exists v\in V: \left| d(v)-\mu \right| \geq \frac{1}{2}\mu \right)&\leq \sum_{v\in V}^{}  \mathbb{P}( \left| d(v)-\mu \right| \geq \mu /2)\leq 2n\cdot \exp \left( -\frac{\mu}{12} \right) \\&\leq 2\exp \left(  \left( \frac{c}{12} \frac{n-1}{n}-1 \right)\log \frac{1}{n} \right)\xrightarrow{n\to \infty} 0\end{aligned} $$Hence, w.h.p we have that for all $v\in V$: $\frac{1}{2}\mu\leq d(v)\leq \frac{3}{2}\mu$. 

Now, let $S\in {V \choose k}$ where $k\leq n /2$, we have that: $e(S, V \backslash S)\sim \text{Bin}(k(n-k),p)$. Hence,
 $$\mathbb{P}(\left|  \right| )$$