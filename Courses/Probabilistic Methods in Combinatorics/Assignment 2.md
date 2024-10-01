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
We define the following two sets. $$A_{i}:=\{ k\in[n]:a_{ik}\neq b_{ik},a_{ik}=1 \},\quad B_{i}:=\{ k\in[n]:a_{ik}\neq b_{ik},b_{ik}=1 \}$$Then, one easily sees that by assumption $A_i\cap B_{i}=\varnothing$ for all $i\in[m]$. Further, $\left| A_{i}\cup B_{i} \right|=t+1$. 
1. **Claim 1: for all $i\neq j$, $(A_{i}\cap B_{j})\cup(A_{j}\cap B_{i})\neq \varnothing$.** 
   Firstly, there exists $k\in[n]$ s.t. $a_{ik}\neq b_{ik}$ and $a_{jk}\neq b_{jk}$. Assume otherwise. Then, let $k\in [n]$ s.t. $a_{ik}\neq b_{ik}$ but $a_{ik}=b_{jk}$, which exists as $w(a_{i},b_{j})\leq t$. We have then: $$a_{jk} = b_{jk}=a_{ik}\neq b_{ik}$$
   
   
   Then, $A_{i}\cap B_{j}=\varnothing$ and $A_{j}\cap B_{i}=\varnothing$. From $A_{i}$ and $B_{i}$ wlog we may assume that $\left| A_{i} \right|\geq \frac{t+1}{2}$. 
   
   for all $k\in A_{i}$, we have that either $a_{jk}=b_{jk}$ or $a_{jk}=1$ and $b_{jk}=0$ further, for 
   
   As $A_{i}\cap B_{j}=\varnothing$, either 
   
   
   Notice that from the $t+1$ indices where $a_{i}\neq b_{i}$, there needs to exist $k\in[n]$ s.t. $a_{ik}=b_{jk}$. If $a_{ik}=1$, then $k\in A_{i}\cap B_{j}$. If $a_{ik}=0$, then $b_{ik}=0$ and 
   Let $k\in [n]$ s.t. $a_{ik}\neq b_{ik}$. 
   
   Let $k\in[n]$ s.t. $a_{ik}\neq b_{jk}$. Assume that $k\notin A_{i}\cup B_{i}\cup A_{j}\cup B_{j}$. This means, 
   $$\left| (A_{i}\cap B_{j})\cup(A_{j}\cap B_{i}) \right|=\left| A_{i}\cap B_{j} \right| +\left| A_{j}\cap B_{i} \right|  $$
	
	
Now, define $S\subseteq[n]$ where $k\in[n]$ is taken with probability $1 / 2$. Then, let $E_{i}$ denote the event that $A_{i}\subseteq E_{i}$ and $B_{i} \subseteq [n] \backslash  E_{i}$. Then, from the claim above, $E_{i}$ and $E_{j}$ are disjoint for $i\neq j$. Therefore, $$1\geq\mathbb{P}\left( \bigsqcup_{i\in[m]}^{}E_{i} \right)=m\cdot \mathbb{P}(E_{1})=\frac{m}{2^{t+1}}$$This proves the statement.


---
