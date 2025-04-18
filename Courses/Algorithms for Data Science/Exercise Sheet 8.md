#Series #Algorithms 

##### Problem 1
We define a diagonal matrix $D\in \mathbb{R}^{r,r}$ where: $D_{ii}:= \sum_{j\in[n]}^{}A_{ji}$. As $A$ has rank $r$ and have only non-negative elements, we have that $D_{ii}> 0$ for all $i\in[r]$. Therefore, $D$ is invertible. Now, by defining: $$\tilde{A}:= A D^{-1},\quad \tilde{W}:= DW$$we have that $\tilde{A} \tilde{W}=AW=M$ where: $$\sum_{j\in[n]}^{}\tilde{A}_{ji}=\left( \sum_{j\in [n]}^{}A_{ji} \right) / D_{ii}=1,\quad \sum_{k\in[r]}^{}\tilde{W}_{kj}=\sum_{i\in[n]}^{}\tilde{A}_{ik}\sum_{k\in[r]}^{}\tilde{W}_{kj}=\sum_{i\in[n]}^{}(\tilde{A} \tilde{W})_{ij}=\sum_{i\in[n]}^{}M_{ij}=1$$
This proves the statement.

---
