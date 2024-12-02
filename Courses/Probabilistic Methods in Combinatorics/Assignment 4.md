#Series #ProbabilisticMethods 

##### Problem 1
Let $\varepsilon_{n}$ be uniformly randomly chosen between $\{ +1,-1 \}$. Let $X:=\| \sum_{i=1}^{n}\varepsilon_{i}v_{i} \|^2_{2}$. Further, let $v_{ij}$ denote the $j$-th element of $v_{i}$. Then, $X=\sum_{j=1}^{n}\left( \sum_{i=1}^{n}\varepsilon_{i}v_{ij} \right) ^{2}$ and $$\mathbb{E}[X]=\sum_{j=1}^{n}\sum_{i,i'=1}^{n}\mathbb{E}[\varepsilon_{i}\varepsilon_{i'}]v_{ij}v_{i'j}=\sum_{j=1}^{n}\sum_{i=1}^{n}v_{ij}^2=\sum_{i=1}^{n}\left\| v_{i} \right\| ^{2}_{2}=n$$where for $i\neq i'$, $\mathbb{E}[\varepsilon_{i}\varepsilon_{i'}]=\mathbb{E}[\varepsilon_{i}]\mathbb{E}[\varepsilon_{i'}]=0$. Hence, there exists $\varepsilon_{1},\dots,\varepsilon_{n}$ s.t. $X\leq n$, i.e. $\sqrt{ X }\leq \sqrt{ n }$.

---
##### Problem 2
Let $H$ be a bipartite graph as given. By Lemma 4.4, it suffices to show that there exists a constant $c$ s.t. any graph $G$ on $n$ vertices with at least $cn^{2-1/r}$ edges has a subset $U\subseteq V$ with $\left| U \right|=a$ and all subsets of size $r$ have at least $a+b$ common neighbors. 

Then, by dependent random choice, for $d\geq 2cn^{1-1/r}$:$$\frac{d^r}{n^{r-1}}-{n \choose r}\left( \frac{a+b}{n} \right) ^r\geq(2c)^r-(a+b)^r\geq a$$for $c$ large enough that depends only on $a+b$ and $r$. Then, by Lemma 4.3 we have the statement.

---
##### Problem 3
1. Let $G=(A\cup B,E)$ be a bipartite digraph with outdegree at least $1$. Now, let $x_{1},x_{2},\dots$ be an infinite walk where $x_{i}\to x_{i+1}\in E$. This exists as the outdegree is at least 1. However, as $G$ is finite, there exists $i<j$ s.t. $x_{i}=x_{j}$. By choosing the pair that appears first, we have that $x_{i},\dots,x_{j}$ is a directed cycle. Notice that this cannot be an odd cycle due to bipartiteness.
2. 