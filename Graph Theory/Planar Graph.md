#Definition #GraphTheory 
> [!definition]
> Let $G$ be a [[graph]]. 
> 1. $G$ is ***planar*** if it has a drawing without crossings.

^49eb13

- **Related definition**: A ***plane graph*** is a particular drawing of a planar graph with no crossings.  ^06ee29
- **Related definition**: For $G=(V,E)$, $\text{cr}(G)$ is the minimum number of crossing pairs of edges. ^98b3fd
---
##### Properties
> [!lemma] Theorem 1
> Let $G=(V,E)$ be a planar graph with $n\geq 3$. Then
> 1. $e(G)\leq 3n-6$.
> 2. $e(G)\leq 2n-4$ if it is triangle free.

^f8d45e

> [!proof]-
> We have:
> 1. First assume that $G$ is connected and has no leaves. 
> 	1. if $e(G)=0$, then the statement trivially holds. 
> 	2. if $e(G)\geq 1$, then as $\delta(G)\geq 2$, there exists a cycle and more than one face. Let $\{ f_{i} \}$ be the face lengths. We then have: $$2e=\sum_{i}^{}f_{i}\geq 3f$$Hence, $f\leq \frac{2}{3}e$ and plugging it back we have that: $$n-e+\frac{2}{3}e\geq 2$$and $e\leq 3n-6$. 
> 	
> 	Now, if $G$ is not connected, we can always add more edges and make it connected. Similarly, if $G$ has a leaf $v$, let $G':= G \backslash v$. Then, $$3(n-1)-6-e(G')=3n-6-e(G)-2$$Hence, we have that the statement holds. 
> 2. Similarly to 1, if $G$ is triangle free, $2e\geq 4f$ and $e\leq 2n-4$. We now conclude by showing that: $$2(n-1)-4-e(G')=2n-4-e(G)-1$$

^227361

- **Corollary**: A bipartite planar graph with $n\geq 3$ nodes has at most $2n-4$ edges. ^ec1ae0
---
![[Degenerate Graph#^03cc32]]
![[Degenerate Graph#^d44b60|p]]
![[Degenerate Graph#^b5e633]]


---
> [!lemma] Theorem 2 (Heawood 1890, Five Color Theorem)
> Every planar graph is $5$-colorable.

^cae3cc

> [!proof]-
> We show this via induction on $n$. 
> 1. If $n\leq 5$, the statement is obvious.
> 2. For $n>5$, let $v$ be a vertex with $d(v)\leq 5$ which exists as $\text{dg}(G)\leq 5$. Let $f$ be a proper $5$-coloring of $G \backslash v$ given by the induction. 
> 	1. if $f$ uses $\leq 4$ colors on $N(v)$, $f$ can be extended to a $5$-coloring on $G$.
> 	2. Suppose $f$ uses $5$ colors on $N(v)$. Fix a planar embedding of $G$ where the neighbor of $v$ are colored by $f$ with $1,\dots,5$ in clockwise order. Let $v_{1},\dots,v_{5}$ be the corresponding neighbor vertices.
> 	   
> 	   For $1\leq i< j\leq 5$, let $G_{ij}$ be the subgraph of $G \backslash v$ induced by the colors $i$ and $j$. Switching the two colors in any connected component of $G_{ij}$ again gives us a proper $5$-coloring of $G \backslash v$. 
> 		1. If there exists $i\neq j$ s.t. $v_{i},v_{j}$ are in different components in $G_{ij}$, then we can switch the two colors in the component with $v_{i}$ and $v_{i}$ will now be colored with $j$. This allows us to color $v$ with $i$. 
> 		2. Otherwise, for all pair $i\neq j$, $v_{i},v_{j}$ are in the same component in $G_{ij}$. Let $P_{ij}$ be a path from $v_{i}$ to $v_{j}$ in $G_{ij}$. Then, $P_{ij}$ is colored alternatively by $i$ and $j$. Then, we have that in the plane graph $P_{13}$ and $P_{24}$ should intersect. As $G$ is planar, they intersect in a node which is a contradiction as $P_{13}$ is colored with $1,3$ and $P_{24}$ is colored with $2,4$. 

^daeea0

- **Remark (Appel-Haken 1977, Four color theorem)**: Every planar graph is $4$-colorable. ^f3acf4
---
##### Polygons
> [!lemma] Theorem 1
> Every polygon $P$ has a triangulation.

^85aaad

> [!proof]-
> We show this via induction on the number of points $n$.
> 1. if $n=3$, then $P$ is a triangle.
> 2. if $n\geq 4$, let $x,y,z$ be three consecutive vertices of $P$ s.t. the angle $xyz$ is $\leq 180$ degress in the interior. 
> 	1. If the triangle $xyz$ does not contain $P$ besides $xy$ and $yz$, then $xz$ splits $P$ into a triangle and a polygon with $n-1$ points. The rest follows by induction. 
> 	2. If the triangle $xyz$ does cross $P\cap \triangle xyz$ besides at $xy$ and $yz$, let $w$ be the point on $P$ not on $xy$ or $yz$ s.t. $d(w,xz)$ is the largest. Then, by definition $yw$ splits the polygon into two polygons of fewer points. We can conclude using induction.

^41a1fc

---
> [!lemma] Theorem 2 (Art Gallery Theorem)
> Let $P$ be a polygon on $n$ points. Then,
> 1. there exist $\left\lfloor n / 3\right\rfloor$ points $x_{1},\dots,x_{\ell}$ inside the polygon s.t. for every $p$ inside the polygon there exists $x_{i}$ with $px_{i}\subseteq P^\circ$.

^53547d

> [!proof]-
> From Theorem 1, we know that $P$ has a triangulation. Take this as a plane graph of a planar graph $G$. We claim that this graph is $3$-colorable.
> 
> For $n=3$, there is nothing to prove. For $n\geq 4$, pick two vertices $u,v$ that are connected by a diagonal. Then, we can color each subgraph split by the diagonal where we fix $c(u)=1$ and $c(v)=2$. This gives us a $3$-coloring of the whole graph via induction.
> 
> Now, as there are $n$ vertices, at least one color class has at most $\left\lfloor n /3\right\rfloor$ vertices. Let these be the points $x_{1},\dots,x_{\ell}$. As every triangle has a vertex of this color, every triangle is covered and so is the whole polygon.

^c8dc3b

 
---
> [!lemma] Theorem 1 (Ajtai-Chvátal-Newborn-Szemerédi, Leighton)
> For any simple graph $G=(V,E)$:
> 1. $\text{cr}(G)\geq m-3n+6$.
> 2. $\text{cr}(G)\geq \frac{m^3}{64n^2}$ if $m\geq 4n$

^c09fc4

> [!proof]-
> We have:
> 1. From Theorem 1. 
> 2. Fix a particular drawing of $G$ with $\text{cr}(G)$ crossings. Let $S\subseteq V$ chosen by sampling each vertex with probability $p$ independently. Let $G':=G[S]$. Let $n',m'$ be the number of vertices and edges in $G'$, further let $c'$ be the number of crossings that occur by drawing $G'$ in the fixed drawing we have of $G$.
>    
>    Then,
>    1. $\mathbb{E}[n']=pn$.
>    2. $\mathbb{E}[m']=p^{2} m$.
>    3. $\mathbb{E}[c']=p^4 \text{cr}(G)$.
>    
>    As we have that $c'\geq \text{cr}(G')\geq m'-3n'+6$, we have that: $$p^4\text{cr}(G)=\mathbb{E}[c']\geq \mathbb{E}[m']-3\mathbb{E}[n']=p^2m-3pn$$Hence, $p^3\text{cr}(G)\geq pm-3n$ and by choosing $p:= \frac{4n}{m}$, we have that: $$\text{cr}(G)\geq \frac{m^{3}}{16n^{2}}-\frac{3m^3}{64 n^{2}}=\frac{m^3}{64n^{2}}$$

^d80cd4

---
> [!lemma] Theorem 2 (Szemerédi-Trotter, 1983)
> We have that: $$I(P,L)\leq 4(m^{2/3}n^{2/3}+m+n)$$

^b577a8

- **Remark**: This bound is tight up to a constant! ^df2625
---