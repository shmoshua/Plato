#Series #DiscreteOptimization 

##### Problem 2.1: Consecutive-Ones Property
Let $A\in \{ 0,1 \}^{m,n}$ be a matrix with the consecutive-ones property. Now, let $J$ be a collection of columns of $A$. Let $j_{1}<\dots<j_{k}$ be the indices of the columns in $J$. We show that for all $i\in[m]$: $$\sum_{\ell \text{ odd}}^{}A_{i,j_{\ell}}-\sum_{\ell \text{ even}}^{}A_{i,j_{\ell}}\in\{ -1,0,1 \}$$By the consecutive-ones property, there exists $1\leq a\leq b\leq k$ s.t. $A_{i,j_{\ell}}=1$ if and only if $a\leq \ell \leq b$. Then, $$\sum_{\ell \text{ odd}}^{}A_{i,j_{\ell}}-\sum_{\ell \text{ even}}^{}A_{i,j_{\ell}}=\begin{cases}1&\text{if }b-a+1\text{ odd and }a\text{ odd}\\-1&\text{if }b-a+1\text{ odd and }a\text{ even}\\0&\text{if }b-a+1\text{ even}\end{cases}$$
This shows that $A$ is totally unimodular.

---
##### Problem 2.2: Unbounded Integer Program
1. Suppose there exist $x,v\in \mathbb{Q}^n$ with $Ax\leq b$, $Av \leq 0$ and $c^\top v > 0$. Then, for any $k\in \mathbb{Z}_{\geq 0}$, $$A(x+k v)\leq b + k \cdot  0 = b$$i.e. $x+k v\in P$ for all $k\in \mathbb{Z}_{+}$. However, as $c^\top v >0$, the LP is unbounded. 
   
   Conversely, let the LP be unbounded. Then, by the weak duality we have that there is no $y\geq 0$ s.t. $A^\top y = c$. Otherwise, $M\leq c^\top x \leq b^\top y$ for all $M\in \mathbb{R}$. Hence, by Farkas, there exists $v\in \mathbb{R}^n$ s.t. $Ax\leq v$ and $c^\top v > 0$. By picking an arbitrary $x\in P$ as $P$ is nonempty, we conclude the proof.
1. Suppose the IP is unbounded. Then, trivially the LP is unbounded. Conversely, if the LP is unbounded, we have from 1, $v\in \mathbb{Q}^n$ with $Av\leq 0$ and $c^\top v> 0$. Modulo multiplying by an integer, we may assume that $v\in \mathbb{Z}^n$ with $Av\leq 0$ and $c^\top v > 0$. As the IP admits a feasible point $x\in \mathbb{Z}^n$ with $Ax\leq b$, we can conclude that the IP is unbounded analogously as above by considering $x+kv\in \mathbb{Z}^n$ for all positive integer $k$.
---
##### Problem 2.3: Low Discrepancy Coloring
1. Let $x\in \{ 0,1 \}^n$. Then, the condition can be rewritten as follows: for $i\in \{ 1,2 \}$ and $t\in\left[ \frac{n}{2} \right]$, $x_{\sigma_{i}(2t - 1)}+x_{\sigma_{i}(2t)}=1$. Hence, we have that:$$P=\{ x\in \mathbb{R}^n: A^1x = \mathbb{1},A^2x = \mathbb{1},0\leq x\leq 1 \}$$where $A^1,A^2\in \{ 0,1 \}^{n / 2 , n}$ is given by $A^i_{t,j}:= \mathbb{1}_{j\in \{ \sigma_{i}(2t-1), \sigma_{i}(2t) \}}$. Then, we have that: $$(A^ix)_{t}=\sum_{j\in[n]}^{}\mathbb{1}_{j\in \{ \sigma_{i}(2t-1), \sigma_{i}(2t) \}} \cdot  x_{j}=\left| \text{supp}(x)\cap \{  \sigma_{i}(2t-1), \sigma_{i}(2t) \} \right| $$
2. Notice that each row in $A:=\begin{bmatrix}A^1\\A^2\end{bmatrix}$ has exactly two $1$'s. Hence, $\frac{1}{2}\cdot \mathbb{1}\in P$ and $P$ is non-empty. Now, notice that $A^\top\in \{ 0,1 \}^{n,n}$ can be viewed as a vertex-edge incidence matrix, where the edges are given by $\{ \sigma_{i}(2t-1),\sigma_{i}(2t) \}$. We show that the underlying graph $G$ is bipartite, which implies that $A^\top$ is totally unimodular. As each vertex is in exactly one edge induced by $A^1$ and one edge induced by $A^2$, any cycle in $G$ needs to have edges alternating from $A^1$ and $A^2$. This implies that any cycle in $G$ needs to be even and $G$ is bipartite. 
   
   As $A^\top$ is TU, so is $A$ and therefore $P$ is integral. This shows the existence of a good set $R$. Then, for $i\in\{ 1,2 \}$ and $l,u\in[n]$ with $l<u$, we have that every second node in the interval $I$ is in $R$. This implies the coloring with discrepancy $2$. 

---

   
   