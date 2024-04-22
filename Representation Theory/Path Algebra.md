#Definition #RepresentationTheory 

> [!definition]
> For a [[quiver]] $Q$, the ***path algebra*** $P_{Q}$ of $Q$ is an algebra, whose basis is formed by oriented paths in $Q$, including the trivial paths $\{ p_{i} \}_{i\in I}$. The multiplication of $a,b\in P_{Q}$ is defined as concatenation $ab$ obtained by first tracing $b$, then $a$. If this is not possible, $ab=0$.

---
##### Properties
> [!lemma] Lemma 1
> Let $Q$ be a finite [[quiver]]. Consider $P_{Q}$ with $p_{i}$ for $i\in I$ as trivial paths and $a_{h}$ for $h\in E$ as basis paths. Then,
> 1. $\sum_{i\in I}^{}p_{i}=1$.
> 2. $p_{i}^{2}=p_{i}$, $p_{i}p_{j}=0$ for $i\neq j$.
> 3. $a_{h}p_{h'}=a_{h}$ and $a_{h}p_{j}=0$ for $j\neq h'$.
> 4. $p_{h''}a_{h}=a_{h}$ and $p_{h''}a_{h}=0$ for $i\neq h''$.

> [!proof]-
> We have: 
> 1. Let $a\in P_{Q}$ and let $i$ and $j$ as the beginning and the end vertices of $a$. Then, $$\left( \sum_{k\in I}^{}p_{k} \right)a=\sum_{k\in I}^{}a\delta_{ik}=a=\sum_{k\in I}^{}a\delta_{jk}=a\left( \sum_{k\in I}^{}p_{k} \right)$$
> 2. 