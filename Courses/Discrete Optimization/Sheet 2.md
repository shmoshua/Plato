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

