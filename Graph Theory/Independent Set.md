
##### Properties
> [!lemma] Theorem 1 (Shearer)
> Let $G$ be a triangle free graph on $n$ nodes with $\Delta(G)\leq d$.
> 1. $\alpha(G)\geq c\frac{n}{d}\log d$

> [!proof]+
> Assume that $4\leq \log d\leq \sqrt{ d }$.
> 
> Let $I$ be a uniformly randomly chosen independent set. For a vertex $v\in V$, we define the random variable: $$X_{v}:=d \cdot \mathbb{1}_{v\in I}+\left| N(v)\cap I \right| $$Then, $$X:=\sum_{v\in V}^{}X_{v}=d\left| I \right| +\sum_{v\in V}^{}\left| N(v)\cap I \right| =d\left| I \right|+\sum_{v\in I}^{}\left| d_{G}(v) \right| \leq 2d\left| I \right|  $$Therefore, $\mathbb{E}[X]\leq 2d\mathbb{E}[\left| I \right|]$. We now claim that $\mathbb{E}[{X_{v}}]\geq c \log d$ for all $v\in G$. 
> 
> Fix $v\in V$ and define $W:=\{ v \}\cup N(v)$. Now, let $I_{0}$ be an independent set in $V$ and assume that $I \backslash W=I_{0}$. Let $U$ denote the set of vertices in $N(v)$ which don't have a neighbor in $I_{0}$, and let $u=\left| U \right|$. Since $G$ is triangle-free, $N(v)$ is an independent set, and hence so is $U$. Now, since $I$ is independent and $I_{0}\subseteq I$,  we must have $I \cap N(v)\subseteq U$. Furthermore, if $v\in I$ then $I\cap N(v)=\varnothing$. 
> 
> We see that conditioning on $I \backslash W=I_{0}$, there are exactly $1+2^u$ possibilities for $I$: one in which $I=I_{0}\cup \{ v \}$, and $2^u$ in which $I$ is the union of $I_{0}$ and some subset of $U$ (each of these possibilities indeed yields an independent set by the definition of $U$). We deduce that: $$\mathbb{E}[X_{v}|I \backslash W=I_{0}]= \frac{d}{1+2^u}+\frac{\sum_{i=0}^{u}i {u \choose i}}{1+2^u}= \frac{d}{1+2^u}+\frac{u 2^{u-1}}{1+2^u}\geq \frac{d}{2^{u+1}}+\frac{u}{4}$$ 
> Finally, we simply have to check that either of the terms $\frac{d}{2^{u+1}}$ or $\frac{u}{4}$ is large enough. 
> 1. if $u\geq \frac{1}{4}\log d$, then we are done since the second term is large enough. 
> 2. if $u\leq \frac{1}{4}\log d$. Then we have $u+1\leq \frac{1}{2}\log d$ and hence $2^{u+1}\leq \sqrt{ d }$, which implies that the first term is at least $\frac{d}{\sqrt{ d }}\geq \sqrt{ d }\geq \log d$.
> 
> Then, $$\mathbb{E}[\left| I \right| ]\geq \frac{\mathbb{E}[X]}{2d}\geq \frac{cn}{2d}\log d$$