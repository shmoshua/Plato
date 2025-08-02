#Definition #GraphTheory 

> [!definition]
> Let $G$ be a [[graph]] and $\{ L(v) \}_{v\in V(G)}$ be a set.
> 1. A ***list coloring*** $c$ w.r.t. $L$ is a [[Graph Coloring|proper coloring]] s.t. $c(v)\in L(v)$ for all $v\in V(G)$.
> 2. A ***list edge coloring*** $c$ w.r.t. $L$ is a [[Graph Coloring|proper edge coloring]] s.t. $c(e)\in L(e)$ for all $e\in E(G)$.
> 3. $G$ is $k$-***chooseble/list-colorable*** if there exists a list coloring for any $L$ with $\left| L(v) \right|=k$. 
> 4. $G$ is $k$-***edge-chooseble/list edge-colorable*** if there exists a list edge coloring for any $L$ with $\left| L(e) \right|=k$. 
> 5. $G$ is $f$-***choosable*** for $f:V(G)\to \mathbb{N}$ if there exists a list coloring for any $L$ with $\left| L(v) \right|\geq f(v)$.

^5f6b51

- **Related definition**: the ***list/list-edge chromatic number*** is given by $\chi_{l}(G),\chi_{l}'(G)$.  ^a18db3
---
##### Properties
> [!lemma] Proposition 1
> Let $G$ be a graph. 
> 1. $\chi(G)\leq \chi_{\ell}(G)$.
> 2. $\chi_{\ell}(G)\leq \Delta(G)+1$.
> 3. $\chi_{\ell}'(G)=\chi_{\ell}(L(G))$

^9f9f8b

> [!proof]-
> We have that:
> 4. We can choose $L$ with $L(v)=[k]$. 
> 5. By [[Graph Coloring|Greedy coloring]].

^f2813a

---
> [!lemma] Theorem 2 (Erdös, Rubin, Taylor 1979)
> For $m:={2k-1 \choose k}$,
> 1. $K_{m,m}$ is not $k$-choosable.

^5be692

> [!proof]-
> We have that:
> 1. Let $K_{m,m}=(A\sqcup B, E)$. For $A,B$, let $L(v)$ be a different $k$-element subset of $[2k-1]$ over $v\in A$. Similarly for $v\in B$. Let $c$ be a choice function. Then, 
> 	1. If $c$ uses less than $k$ colors for $A$, then there is a $k$-element set $K\subseteq [2k-1]$ that is not used. In other words, for the vertex $v$ in $A$ with $L(v)=K$, no color was chosen, contradiction.
> 	2. If $c$ uses at least $k$ colors for $A$, then there is a $k-$element set $K\subseteq[2k-1]$ that is used. Then, no color can be chosen for $v\in B$ with $L(v)=K$. Contradiction.

^b06959

- **Remark**: The above theorem can be generalized: $\chi_{\ell}(G)\geq (1-\text{o}(1))\log_{2}d(G)$. ^f50ba4

---
> [!lemma] Theorem 3 (Galvin 1995)
> $\chi'_{\ell}(K_{n,n})=n$. 

^3dac14

> [!proof]-
> First note that $\chi'_{\ell}(K_{n,n})\geq \chi'(K_{n,n})=n$. For the other direction, we have that $\chi'_{\ell}(K_{n,n})=\chi_{\ell}(L(K_{n,n}))$ where $L(K_{n,n})=K_{n}\times K_{n}$, the cartesian product. 
> 
> By [[Kernel (Graph Theory)|Proposition 1]], it suffices to show that $G:=K_{n}\times K_{n}$ has a kernel-perfect orientation $D$ with indegree $d^-_{D}\equiv n-1$. Label the vertices s.t. we have: $$\begin{matrix}1&2&3&\dots&n\\2&3&\ddots &n&1\\3&\ddots&\ddots&\ddots&\vdots\\\vdots&n&\ddots&\ddots &n-2\\n&1&\dots&n-2&n-1\end{matrix}$$For each vertex $(r,s)$, we define the orientation as follows:
> 1. in row $r$, $i\to j$ for all $i< j$.
> 2. in column $s$, $j\to i$ for all $i<j$.
>  
>  Then, for any $(r,s)\in K_{n}\times K_{n}$ we have that $d^-_{D}(r,s)=n-1$. We now show that for any $U\subseteq V(K_{n}\times K_{n})$, $D[U]$ has a kernel by induction on $\left| U \right|$.
>  - For $\left| U \right|=1$, then $D[U]$ is a single node and the statement is trivial.
>  - For $\left| U \right|\geq 2$, let $S_{0}\subseteq U$ that have the minimal label in their row. If no two vertices in $S_{0}$ fall in the same column, then $S_{0}$ is an independent set and is a kernel. Otherwise, there is a column $C$ with multiple vertices in $S_{0}$. Let $u$ be the vertex in $S_{0}$ with the minimal label in $C$. Then, $D[U \backslash u]$ has a kernel $S$ by induction. Then, $S$ must contain a vertex from $C$ as the non-$u$ vertices in $C\cap S_{0}$ need incoming edges from $S$ and they can't be coming from their rows. By the choice of $u$, any such vertex in $C$ has an edge to $u$. Therefore, $S$ is a kernel for $D[U]$ as well. 

^f0574e
