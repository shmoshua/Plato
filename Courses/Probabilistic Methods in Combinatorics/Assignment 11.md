#Series #ProbabilisticMethods 

##### Problem 1
Let $X_{1},\dots,X_{n}$ be independently uniformly chosen number from $\mathbb{Z}_{7}$ and $X=(X_{1},\dots,X_{n})$.  Let $f:\Omega\to \mathbb{R}$ where $f(x):=d(x,U)$. Then, we have that $f$ is $1$-Lipschitz w.r.t. the hamming distance: Indeed, if $x,x'\in \mathbb{Z}_{7}^n$ differ in exactly one coordinate, then $x,x'$ are adjacent and their distance to $U$ can differ by at most 1. 

Now, we claim that: $\mathbb{E}[f(X)]\leq 2\sqrt{ n }$. Assume otherwise. Then, by McDiarmid:$$\mathbb{P}(f(X)=0)\leq \mathbb{P}(\left| f(X)-\mathbb{E}[f(X)] \right| \geq 2\sqrt{ n })\leq 2\cdot  \exp(-8)< 7^{-1}$$which is a contradiction as $\mathbb{P}(f(X)=0)=\frac{\left| U \right|}{\left| V \right|}=7^{-1}$. 

Therefore, by McDiarmid again, we have that: $$\mathbb{P}(f(X)\geq (2+c)\sqrt{ n })\leq\mathbb{P}(f(X)\geq \mathbb{E}[f(X)]+c\sqrt{ n })\leq \exp \left( -2c^{2}\right) $$As our distribution is uniform, $\frac{\left| W \right|}{\left| V \right|}\leq \exp(-2c^{2})$ and $\left| W \right|\leq 7^n \exp \left( -2c^{2} \right)$ and this proves the statement.

---
##### Problem 2

Let $G\sim G(n, 1/2)$ and let $\chi(G)$ be the chromatic number of $G$. Let $k$ be the smallest positive integer s.t. $\mathbb{P}(\chi(G)\leq k)> \varepsilon$. Then, by definition, $\mathbb{P}(\chi(G)\geq k)=1-\mathbb{P}(\chi(G)\leq k-1)\geq1-\varepsilon$. 


Then, with the vertex exposure martingale, i.e. we have $X_{1},\dots,X_{n}$ as random variables where $X_{i}\in\Omega_{i}:=\{ 0,1 \}^{i-1}$ where $(X_{i})_{j}$ means there is an edge $\{ i,j \}\in E$. Then, let $X:=(X_{1},\dots,X_{n})$ with $\Omega:=\prod_{i=1}^{n}\Omega_{i}$ and consider $f:\Omega\to \mathbb{R}$ where $f(X)=\min\{ |S|:S\subseteq V(G), \chi(G \backslash S) \leq k \}$. 

Then, $f$ is $1$-Lipschitz. Indeed,  from $x\in \Omega$ if we change only the $i$-th element, $|S|$ can increase by at most 1 (by adding the $i$-th node). Therefore, by McDiarmid we have that for any $\lambda>0$: $$\mathbb{P}\left( f(X)\leq \mathbb{E}[X]-\lambda \sqrt{ n }\right)\leq \exp \left( -2\lambda^{2}\right) $$ By choosing $\lambda^{2}>\frac{1}{2}\ln(1/\varepsilon)$, as $\mathbb{P}(f(X)=0)= \mathbb{P}(\chi(G)\leq k)> \varepsilon$, however, if $\mathbb{E}[f(X)]> \lambda \sqrt{ n }$, then: $$\mathbb{P}(f(X)=0)\leq \mathbb{P}(f(X)\leq \mathbb{E}[X]-\lambda \sqrt{ n } )< \varepsilon$$Therefore, we have that $\mathbb{E}[f(X)]\leq \lambda \sqrt{ n }$ and by McDiarmid: $$\mathbb{P}(f(X)\geq 2\lambda \sqrt{ n })=\mathbb{P}(f(X)\geq \mathbb{E}[X]+\lambda \sqrt{ n })\leq  \varepsilon$$Hence, with probability at least $1-\varepsilon$,  $\mathbb{P}(f(X)< 2\lambda \sqrt{ n })$ and there exists $S\subseteq V$ of size $2\lambda \sqrt{ n }$ s.t. $\chi(G \backslash S)\leq k$, i.e. $\chi(G)\leq k+\chi(G[S])$. 

