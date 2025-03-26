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

Now, let $S\in {V \choose k}$ where $k\leq n /2$, we have that: $e(S, V \backslash S)\sim \text{Bin}(k(n-k),p)$. Hence, for $\eta:=k(n-k)p$, we have that $n-k\geq n/2$ and therefore, $\eta\geq \frac{1}{2} knp$.  Hence:
$$\mathbb{P}\left( \left| e(S,V \backslash S) -\eta\right|> \frac{1}{2}\eta  \right)\leq 2\exp \left( -\frac{\eta}{12} \right) \leq 2\exp \left( -\frac{knp}{24} \right)\leq 2n^{-\frac{c}{24} k}$$It follows that there exists a constant $\lambda>0$ s.t. $\mathbb{P}\left( \left| e(S,V \backslash S) -\eta\right|> \frac{1}{2}\eta  \right)< n^{-\lambda k}$ for all $S$. This shows that $$\mathbb{P}(e(S, V \backslash S)=\Theta(kpn))> 1-n^{-\lambda k}$$ as $\eta\leq knp$ and $\eta=\Theta(knp)$.


Let $0<\phi<1$ be a fixed constant. Then,  $$\mathbb{P}(\phi(G)< \phi)=\mathbb{P}(\exists S\subseteq V,\left| S \right| \leq n /2:\phi(S)< \phi)\leq \sum_{1\leq k\leq n /2}{n \choose k}\mathbb{P}(\phi(S)< \phi)$$Now, w.h.p we have that $d(u)=\Theta(np)$ for all $u\in V$. Hence, for any $S\subseteq V$ with $k\leq n /2$ vertices, we have that: $\text{vol}(S)\leq \text{vol}(V \backslash S)$ for large $n$ and we have: $$\phi(S)< \phi \iff e(S, V \backslash S)< \phi\Theta(knp)$$
Therefore, $$\mathbb{P}(\phi(G)<\phi)\leq \sum_{1\leq k\leq n /2}^{}{n \choose k}n^{-\lambda k}+o(1)=o(1)$$This concludes the proof.

---
#### Problem 5

Consider the following algorithm:
```pseudo
\begin{algorithm}\caption{ExpanderDecomposition($G,\phi$)}\begin{algorithmic}
\If{\Call{CertifyOrCut}{$G,\phi$} certifies that $G$ is a $\phi$-expander}
	\Return $V(G)$
\EndIf
\State $S\gets$ the cut \Call{CertifyOrCut}{$G,\phi$} presents.
\Return \Call{ExpanderDecomposition}{$G[S], \phi$}$\cup$\Call{ExpanderDecomposition}{$G[V\backslash S], \phi$}

\end{algorithmic}
\end{algorithm}
```

Let $X_{1},\dots,X_{k}$ be the output of the algorithm. By construction, $G[X_{i}]$ is a $\phi$-expander for all $i$.

Now, let $(S,V \backslash S)$ be a cut in $G$ given in the algorithm where wlog $\text{vol}(S)\leq \text{vol}( V) / 2$. Then, we have that $e(S, V \backslash S)=O(\sqrt{ \phi })\cdot \text{vol}(S)$. We show that 


Then, we charge each vertex $u\in S$ with $\phi \cdot d(u)$ charge. Then, we have that: $$e(S, V \backslash S)<\phi \text{vol}(S)=\sum_{v\in S}^{}\text{charge}(v)$$
> 
> As $\text{vol}(V)=2m$ and the volume at least halves at every step, each vertex receives charges in at most $\log (2m)$ iterations. Hence, we have that $\text{charge}(v)\leq \phi \cdot d(v)\cdot \log(2m)$. Hence, we have that: $$\sum_{i\in[\ell]}^{}e(V_{i}, V \backslash V_{i})\leq \sum_{v\in V}^{}\text{charge}(v)\leq 2m\phi \log(2m)$$

---
#### Problem 6
Let $z{\bot}1$. Then, as $1$ spans $\text{ker }L$, $z\in \text{im }L$ and as $L=D^{1/2}ND^{1/2}$, we have:  $$z^\top L^{\dagger}z= z^\top \Pi_{L} D^{-1/2}N^{\dagger}D^{-1/2}\Pi_{L}z$$Let $\{ v_{i} \}_{i\in[n]}$ be the eigenbasis of $N$ s.t. $v_{i}$ corresponds to $\lambda_{i}$. Then by Cheeger, $\frac{\phi^{2}}{2}\leq \lambda_{2}\leq \lambda_{i}$ for all $i\geq 2$. Hence: $$w^\top N^{\dagger}w=w^\top\sum_{i\geq 2}^{}\frac{v_{i}v_{i^\top}}{\lambda_{i}}w=\sum_{i\geq 2}^{}\frac{\braket{ v_{i} , w } ^{2}}{\lambda_{i}}\leq 2\phi^{-2}\sum_{i\geq 2}\braket{ v_{i} , w } ^{2}$$Therefore, $$\begin{aligned}z^\top L^{\dagger}z&= z^\top \Pi_{L} D^{-1/2}N^{\dagger}\underbrace{ D^{-1/2}\Pi_{L}z }_{ =: w }\leq 2\phi^{-2}\sum_{i\geq 2}^{}\braket{ v_{i} ,  D^{-1/2}\Pi_{L}z } ^{2}\end{aligned}$$
