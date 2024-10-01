#Series #ProbabilisticMethods 

#### Problem 1
Let $H$ be a hypergraph with $m\leq 4^{n-1} / 3^n$ edges. We will color each vertex uniformly randomly. Then, for an edge $e$, let $A_{e}$ denote the event that $e$ contains all $4$ colors. We have that:
   $$\mathbb{P}(A_{e})=4!\cdot\left\{\begin{matrix}n\\4\end{matrix} \right\}\cdot \frac{1}{4^n}=\frac{1}{4^n}\sum_{r=0}^{4}(-1)^r {4 \choose r } (4-r)^n=\frac{1}{4^n}\left( 4^n-4\cdot 3^n+6\cdot 2^n-4 \right)> 1-\frac{3^n}{4^{n-1}} $$Therefore, $$\mathbb{P}(\exists \text{edge that has }\leq 3\text{ colors})=\mathbb{P}\left( \bigcup_{e\in E}^{}A_{e}^c \right) < m\cdot \frac{3^n}{4^{n-1}} =1$$This shows that the coloring of $H$ is valid with positive probability and hence there exists such a coloring.
---
#### Problem 2
Let $X:=\bigcup_{v\in V}^{}S(v)$ be the set of all colors. Let $X'\subseteq X$ where: $\mathbb{P}(c\in X')=\frac{1}{2}$ for all $c\in X$. Let $A\sqcup B$ be the bipartite graph and consider that for every $v\in A$, $E_{v}$ denotes the event that $X'\cap S(v)=\varnothing$. Similarly, for every $v\in B$, $E_{v}$ denotes the event that $X\backslash X' \cap S(v)=\varnothing$. (This is well-defined as $A,B$ are disjoint). Then, $\mathbb{P}(E_{v})=\frac{1}{2^\left| S(v) \right|}$. $$\mathbb{P}\left( \bigcup_{v\in V}^{}E_{v} \right)\leq \sum_{v\in V}^{} \frac{1}{2^{\left| S(v) \right| }}<\sum_{v\in V}^{} \frac{1}{n}=1$$Therefore, there exists a proper coloring of $G$. 

---
#### Problem 3
We use Bollobás' theorem. Let $\{ e_{1},\dots,e_{k} \}$ be the edges on $V$ not in $G$. Then, for each $e_{i}$ let $K_{10}^i$ be a complete graph found in $G\cup \{ e_{i} \}$, which exists by assumption. Then, for each $i\in[k]$, we define $A_{i}:=e_{i}$ and $B_{i}:=V \backslash V(K^i_{10})$. Then,  $\left| A_{i} \right|=2$ and $\left| B_{i} \right|=n-10$ for all $i\in[k]$. Further, as $e_{i}\subseteq V(K^i_{10})$, $A_{i}\cap B_{i}=\varnothing$. Lastly, assume that $A_{i}\cap B_{j}=\varnothing$ for $i\neq j$. Then, $e_{i}\subseteq V(K^j_{10})$ which is a contradiction as $K^j_{10} \backslash e_{j}$ is in $G$ but $e_{i}$ is not. 

Therefore, from Bollobás, we have: $$E(G)={n\choose 2}-k\geq {n\choose 2}-{n-8 \choose 2}=\frac{n(n-1)-(n-8)(n-9)}{2}=8n-36$$

---
#### Problem 4

From $a_{i}$ we can create $\overline{a}_{i}\in  \{ 0,1 \}^{t+1}$ by taking only the elements where $a_{i}\neq b_{i}$. Then, consider $A_{i}:=\{ \overline{a}_{i} \}$ and $B_{i}:= \{ 0,1 \}^{t+1} \backslash  A_{i}$. Trivially it holds that $A_{i}\cap B_{i}=\varnothing$.

Now, assume that $A_{i}\cap B_{j}=\varnothing$ for $i\neq j$. Then, $\overline{a}_{i}\notin B_{j}$ and this means that $\overline{a}_{i}=\overline{a}_{j}$. Let $S_{i}\subseteq[n]$ define the $t+1$ indices where $a_{i}\neq b_{i}$. Then, we consider the following two cases:
1. Case 1: $S_{i}=S_{j}$. But, then $a_{i}=a_{j}$ and  $t+1=w(a_{i}-b_{j})=w(a_{j}-b_{j})\leq t$ which is a contradiction.
2. Case 2: $S_{i}\neq S_{j}$. Let $T$ be the indices where $a_{i}\neq b_{j}$. Then, $\left| T \right|\leq t$ and for $k\in T\cap S_{i}$, $$a_{k}$$
   
   Then, $t+3\leq\left| S_{i}\cup S_{j} \right|\leq 2t+2$. For all $k\in S_{i}\cap S_{j}$, 
   
   For all $k\notin S_{i}\cup S_{j}$, $a_{i}$
3. $w(a_{i}-b_{j})\leq t$. 
   
   Also, there exists $k\in S_{i}$ s.t. $a_{ik}\neq a_{jk}$. As $k\notin S_{j}$, $a_{ik}\neq b_{jk}$. 


---



Let $A_{i}:=\{ a_{i} \}$ and let $S_{i}:=\{ k\in[n]:a_{ik}\neq b_{ik}\}$. Then, $\left| S_{i} \right|=t+1$ and let $B_{i}$ be the set of all vectors that are equal to $a_{i}$ on indices $[n] \backslash S_{i}$ and different on $S_{i}$. Then, $\left| B_{i} \right|=2^{t+1}-1$.

Now, by definition, $A_{i}\cap B_{i}=\varnothing$. We aim to show that $A_{i}\cap B_{j}\neq \varnothing$ for all $i\neq j$. Assume $A_{i}\cap B_{j}=\varnothing$. Then, $a_{i}$ is not in $B_{j}$. However, we know that $w(a_{i}-b_{j})\leq t$. Therefore, 

Then, we have the two following cases:
1. Case 1: $a_{i}=a_{j}$. But, then $t+1=w(a_{i}-b_{j})=w(a_{j}-b_{j})\leq t$ which is a contradiction.
2. Case 2: there exists $k\notin S_{j}$ s.t. $a_{ik}\neq a_{jk}$. As $k\notin S_{j}$, $a_{ik}\neq b_{jk}$. 


 $2^{t+1}-1$ different bit-vectors 

 be the $$
Let $A_{i}:=\{ (k,a_{ik}):k\in[n], a_{ik}\neq b_{ik} \}$ and $B_{i}:=\{ (k,b_{ik}):k\in[n], a_{ik}\neq b_{ik} \}$. Then, as $w(a_{i}-b_{i})=t+1$, we have that there are exactly $t+1$ indices $k\in[n]$ s.t. $a_{ik}\neq b_{ik}$. Therefore, $\left| A_{i} \right|=t+1$ and $\left| B_{i} \right|=t+1$. Further, for $i\neq j$ assume that $A_{i}\cap B_{j}=\varnothing$. Then, 

$w(a_{i}-b_{j})\leq t$ and therefore, there exists at least 


Let $a_{ik}=b_{ik}$ but $a_{jk}\neq b_{jk}$. 
1. If $a_{ik}=b_{jk}$ then $b_{ik}=a_{ik}=b_{jk}\neq a_{jk}$.
2. if $a_{ik}\neq b_{jk}$ then $a_{ik}=a_{jk}$.

Therefore, we have $a_{ik}=a_{jk}$ or $b_{ik}=b_{jk}$. 
