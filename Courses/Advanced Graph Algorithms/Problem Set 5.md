#Series #AGAO 

#### Problem 1

1. Let $S\subseteq V$ with  size $k$. Then, $\text{vol}(S)=k(n-1)\leq \frac{n(n-1)}{2}=\text{vol}(V) / 2$ if and only if $k\leq n /2$. Further, if $k\leq n /2$:$$\phi(S)=\frac{e(S,V \backslash S) }{k(n-1)}=\frac{k(n-k)}{k(n-1)}=\frac{n-k}{n-1}$$Hence, $$\phi(K_{n})=\min_{k\leq  n / 2}\frac{n-k}{n-1}=\frac{n-\left\lfloor n / 2\right\rfloor}{n-1}\to\frac{1}{2}$$ 
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

1. Consider the following algorithm:
	   
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

	Let $X_{1},\dots,X_{k}$ be the output of the algorithm. By construction, $G[X_{i}]$ is a $\phi$-expander for all $i$. Further, as we have at most $n$ splits, we have that the overall runtime is $O(mn\log ^{c'}n)$. Hence, it suffices to show that it is of quality $O(\phi^{-1/2}\log n)$. 

	Let $(S_{1},V_{1}),\dots,(S_{\ell},V_{\ell})$ be the pairs s.t. $S_{i}$ is the cut found by $\text{CertifyOrCut}(G[V_{i}],\phi)$ that occur in the run of the algorithm. Wlog we may assume $\text{vol}(S_{i})\leq \text{vol}(V_{i}) / 2$ for all $i$. We define the following charge function: $$c:V\to \mathbb{R}^+,\quad v\mapsto \sum_{i:v\in S_{i}}^{}\frac{e(S_{i},V_{i} \backslash S_{i})}{\text{vol}_{G[V_{i}]}(S_{i})}\cdot d_{G[V_{i}]}(v)$$Then, we have that: $$e(S_{i},V \backslash S_{i})=\sum_{v\in S_{i}}^{}\frac{e(S_{i},V_{i} \backslash S_{i})}{\text{vol}_{G[V_{i}]}(S_{i})}\cdot d_{G[V_{i}]}(v),\quad i\in[\ell]$$However, as $\text{vol}(V)=2m$ and the volume at least halves at every step, each vertex is in at most $\log(2m)$ cuts $S_{i}$. Further, $\frac{e(S_{i},V_{i} \backslash S_{i})}{\text{vol}_{G[V_{i}]}(S_{i})}\cdot d_{G[V_{i}]}(v)\leq O(\sqrt{ \phi })\cdot d(v)$. Hence, $c(v)\leq O(\sqrt{ \phi }\log n)d(v)$. We conclude by showing that: $$\sum_{i\in[k]}^{}e(X_{i}, V \backslash X_{i})=\sum_{i\in[\ell]}^{}e(S_{i}, V_{i}\backslash S_{i})=\sum_{v\in V}^{}c(v)\leq O(\sqrt{ \phi }\log n)m$$
	This shows that the quality of the decomposition is $O(\phi^{-1/2}\log n)$.
2. Consider the following algorithm:
   ```pseudo
	\begin{algorithm}\caption{CertifyOrLargeCut($G,\phi$)}\begin{algorithmic}
	\If{\Call{CertifyOrCut}{$G,\phi$} certifies that $G$ is a $\phi$-expander}
		\Return $\empty$
	\EndIf
	\State $S\gets$ the cut \Call{CertifyOrCut}{$G,\phi$} presents.
	\If{$\text{vol}_G(S),\text{vol}_G( V\backslash S) \ge m /3$}
	\Return $S$
	\Else 
	\State switch $S$ to $V\backslash S$ if necessary s.t. $\text{vol}_G(S) < m /3$.
	\Return $S\ \sqcup$ \Call{CertifyOrLargeCut}{$G[V\backslash S], \phi$}
    \EndIf
	\end{algorithmic}
	\end{algorithm}
	```
	Let $S_{1},\dots,S_{k}\subseteq V$ be the disjoint non-empty sets that are returned in each recursion. Indeed, they are disjoint as $S_{i}\subseteq V \backslash \bigcup_{j<i}^{}S_{j}$ for all $i$. Further, as we have $\left| S_{i} \right|\geq 1$ for all $i$, we remove at least one node in each recursion and therefore, we have $k\leq n$. Hence, the total runtime of the algorithm is $O(mn\log^{c'}n)$. 
	
	It remains to show that our output $S:=\bigsqcup_{i\in[k]}^{} S_{i}$ meets the desired properties. We will show that $\phi(S)=O(\sqrt{ \phi })$. We introduce the notation that $S_{i:j}:=S_{i}\sqcup\dots \sqcup S_{j}$ for any $i\leq j$. Further, we introduce that $G_{i}:=G[V \backslash S_{1:i-1}]$ with $G_{1}:=G$. We first show that 
	
	
	Now, assume that $\phi_{G[V \backslash S_{1:i}]}(S_{i+1:k})=O(\sqrt{ \phi })$.  Then, $\phi_{G[V \backslash S_{1:i-1}]}(S_{i})=O(\sqrt{ \phi })$ as $S_{i}$ is the output of $\text{CertifyOrCut}(G[V \backslash S_{1:i-1}],\phi)$. Further, $$\text{vol}_{G[V \backslash S_{1:i-1}]}(S_{i}\cup S_{i+1:k})\leq \text{vol}_{G[V \backslash S_{1:i-1}]}(S_{i})+\text{vol}_{G[V \backslash S_{1:i-1}]}(S_{i+1:k})<\frac{e(G[V \backslash S_{1:i-1}])}{3}$$
	
	From the claim, if it holds that $\text{vol}()$


---
#### Problem 6

1. Let $z{\bot}1$. Then, as $1$ spans $\text{ker }L$, $z\in \text{im }L$ and as $L=D^{1/2}ND^{1/2}$, we have:  $$z^\top L^{\dagger}z= z^\top \Pi_{L} D^{-1/2}N^{\dagger}D^{-1/2}\Pi_{L}z$$Let $\{ v_{i} \}_{i\in[n]}$ be the eigenbasis of $N$ s.t. $v_{i}$ corresponds to $\lambda_{i}$. Then by Cheeger, $\frac{\phi^{2}}{2}\leq \lambda_{2}\leq \lambda_{i}$ for all $i\geq 2$. Hence: $$w^\top N^{\dagger}w=w^\top\sum_{i\geq 2}^{}\frac{v_{i}v_{i^\top}}{\lambda_{i}}w=\sum_{i\geq 2}^{}\frac{\braket{ v_{i} , w } ^{2}}{\lambda_{i}}\leq 2\phi^{-2}\sum_{i\geq 2}\braket{ v_{i} , w } ^{2}$$Therefore, $$\begin{aligned}z^\top L^{\dagger}z&= z^\top \Pi_{L} D^{-1/2}N^{\dagger}\underbrace{ D^{-1/2}\Pi_{L}z }_{ =: w }\leq 2\phi^{-2}\sum_{i\geq 2}^{}\braket{ v_{i} ,  D^{-1/2}\Pi_{L}z } ^{2}\end{aligned}$$Now, as $z\in \text{im } L$, $\Pi_{L}z=z$ and by Bessel's inequality: $$z^\top L^{\dagger}z\leq 2\phi^{-2}\left\| D^{-1/2}z \right\| ^{2}=2\phi^{-2} z^\top D^{-1} z$$
2. We have that: $$R_{\text{eff}}(u,v)=(e_{v}-e_{u})^\top L^{\dagger}(e_{v}-e_{u})\leq 2\phi^{-2}(e_{v}-e_{u})^\top D^{-1}(e_{v}-e_{u})=2\phi^{-2}\left( \frac{1}{d(u)}+\frac{1}{d(v)} \right) $$
---
#### Problem 7
1. Let $A$ be PSD. Then, for any vector $z$, $z^\top C^\top ACz\geq 0$. This shows that $CAC$ is also PSD. The symmetry of $N$ can be shown easily by the symmetry of $D^{- 1/2}$ and $L$.
2. We have that:  $$z_{c}^\top Lz_{c}=(z-\alpha1)^\top L (z-\alpha 1)=z^\top Lz-2\alpha L  1+\alpha^{2} 1^\top L 1=z^\top Lz$$Further, $$z^\top _{c}D z_{c}=z^\top Dz -2\alpha d^\top z+\alpha^{2} \text{vol}(V)$$Now, $$\alpha \frac{\text{vol}(V)}{2}\leq \alpha\sum_{i:z_{c}(i)\geq 0}^{}d(i)\leq\sum_{i:z(i)\geq \alpha}^{}d(i)z(i)\leq d^\top z$$Therefore, $\alpha^{2}\text{vol}(V)\leq 2\alpha d^\top z$ and we have that $z_{c}^\top Dz_{c}\leq z^\top Dz$. This shows that $\frac{z^\top Lz}{z^\top Dz}\geq \frac{z_{c}^\top Lz_{c}}{z_{c}^\top Dz_{c}}$. Now for scaling, $$\frac{z_{sc}^\top Lz_{sc}}{z_{sc}^\top Dz_{sc}}=\frac{\beta^{2}z_{c}^\top Lz_{c}}{\beta^{2}z_{c}^\top Dz_{c}}=\frac{z_{c}^\top Lz_{c}}{z_{c}^\top Dz_{c}}$$
3. By definition we have that $z_{sc}(1)<0$ and $z_{sc}(n)> 0$. Hence,$$\int_{\mathbb{R}}^{} p_{\tau} \, dt =2\int_{z_{sc}(1)}^{z_{sc}(n)}\left| t \right|   \, dt=2\left( -\int_{z_{sc}(1)}^{0}t    \, dt+\int_{0}^{z_{sc}(n)}t   \, dt \right)= z_{sc}(1)^{2}+z_{sc}(n)^{2}=1$$
4. Let $a,b\in \mathbb{R}$ s.t. $a<0<b$. Then, $ab<0$ and we have that: $$a^{2}+b ^{2}<(a-b)^{2}\leq \left| a-b \right| \left| a-b \right| \leq \left| a-b \right| (\left| a \right| +\left| b \right| )$$Further, for any $a,b\in \mathbb{R}$: $$\left| a^{2}-b ^{2} \right|=\left| a-b \right| \cdot \left| a+b \right| \leq \left| a-b \right| (\left| a \right| +\left| b \right| ) $$This proves the statement.
5. Assume otherwise. Then, for all $\omega$, $X(\omega)<\mathbb{E}[X]$ and there exists $\sup X<q< \mathbb{E}[X]$. This is a contradiction as: $$\mathbb{E}[X]=\int_{\Omega}X \, d\mathbb{P}\leq \int_{\Omega} q  \, d\mathbb{P}=q< \mathbb{E}[X]  $$
6. Let $\lambda:=\sqrt{ \frac{2z^\top_{sc}Lz_{sc}}{z^\top_{sc}Dz_{sc}} }$. Then, as we have $0\leq \mathbb{E}_{\tau}[\lambda1_{S}^\top D 1_{S}-1^\top_{S} L 1_{S}]$, there exists $\tau$ and thereby $S$ s.t. $$0\leq \lambda 1_{S}^\top D 1_{S}-1_{S}^\top L 1_{S}$$This concludes the proof.

---
#### Problem 8
1. For $G=K_{n}$ and unit weight we have that: $$\left\| p_{t}-\pi \right\| _{\infty}\leq e^{-\lambda_{2}(N)t /2}$$as $d$ is constant. Hence, if $\phi(G)t\geq \lambda_{2}(N)t /2\geq  \log \frac{1}{\varepsilon}$, then $\left\| p_{t}-\pi \right\|_{\infty}\leq \varepsilon$. Therefore, we can choose e.g. $t\geq \frac{4}{3}\log (1 / \varepsilon)$ for all $n\geq 5$.
2. For $G=P_{n}$, notice that if $a$ is an end node, then $\sqrt{ d(b) / d(a) }\leq \sqrt{ 2 }$ and otherwise $\sqrt{ d(b) / d(a) }\leq 1$. Hence, we have that: $$\left\| p_{t}-\pi \right\| _{\infty}\leq e^{-\lambda_{2}(N) t / 2}\sqrt{ 2 }$$and by Cheeger, $t\geq \frac{1}{\phi(G)}\log\left( \frac{\sqrt{ 2 }}{\varepsilon} \right)$ where $\phi(G)\geq \frac{1}{n-1}$. Hence, for $t\geq (n-1)\log\left( \frac{\sqrt{ 2 }}{\varepsilon} \right)$ we have that $\left\| p_{t}-\pi \right\|_{\infty}\leq \varepsilon$.

---
#### Problem 9

1. Let $h_{i}:=\mathbb{E}[H_{i,n}]$. Then, we get: $$h_{i}=1+\frac{1}{2}h_{i+1}+\frac{1}{2}h_{i-1},\quad \forall 1<i<n$$and $h_{1}=1+h_{2}$. Hence, $$h_{i}-h_{i+1}=h_{i-1}-h_{i}+2,\quad \forall 1<i<n$$If we define $c_{i}:=h_{i}-h_{i+1}$, we have that $c_{i}=c_{i-1}+2$ and $c_{1}=1$. Therefore, $$c_{i}=1+2(i-1)$$Now, $$h_{1}=h_{1}-h_{n}=\sum_{i=1}^{n-1}c_{i}=(n-1)+(n-1)(n-2)=(n-1)^{2}$$
2. Let $a\neq b$ for $a,b\in V$. We define $h_{a}:=\mathbb{E}[H_{a,b}]$. Then, notice that by symmetry, for any other $a'\neq b$ we have that $h_{a}=h_{a'}$. Therefore, $$h_{a}=1+\frac{1}{n}\sum_{c\neq a}^{}h_{c}=1+h_{b}+\frac{n-1}{n}h_{a}=1+\frac{n-1}{n}h_{a}$$Hence, we get that $h_{a}=n$. 
3. Let $a,b$ be the two endpoints of the path graph in the Lollipop graph with $a$ being the vertex joining the path and the complete graph. Then from our result from above, we see that $\mathbb{E}[H_{ba}]=(n-1)^{2}$. Now, consider $h_{a}:=\mathbb{E}[H_{ab}]$. We will argue that $h_{a}> (n-1)^{2}$. 
   
	Let $H$ be the $n$-clique subgraph of $G$ and $a'$ be the (only) neighbor of $a$ on the path graph. Then,$$h_{a}=1+\frac{1}{n}h_{a'}+\frac{1}{n}\sum_{c\in V(H) \backslash \{ a \}}^{}h_{c}$$Now, notice that for any $c\in V(H)  \backslash \{ a \}$, $h_{c}\geq 1+h_{a}$, since in any instance of the random walk, $c$ has to go through $a$ to get to $b$. Further, notice that $h_{a'}\geq (n-2)^{2}$ as $$(n-2)^{2}=\mathbb{E}[H_{a'b}|\text{random walk does not visit }a]\leq \mathbb{E}[H_{a'b}]=h_{a'}$$given by part 1. Therefore, $$h_{a}\geq 1+\frac{1}{n}(n-2)^{2}+\frac{n-1}{n}(1+h_{a})$$and we get that: $$h_{a}\geq n+(n-2)^{2}+(n-1)=n^2-2n+3> (n-1)^{2}$$This shows that $\mathbb{E}[H_{ba}]\neq \mathbb{E}[H_{ab}]$.

---
