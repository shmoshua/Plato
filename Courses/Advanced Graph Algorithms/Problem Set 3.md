#Series #AGAO 

#### Problem 1
1. Let the objective function be: $$h:\mathbb{R}^n\to \mathbb{R},\quad v\mapsto \phi(v)+a_{0}f(x_{0})+\braket{ a_{0}\nabla f(x_{0}) , v-x_{0} } $$Then, $v_{0}=\underset{ v\in \mathbb{R}^n }{ \arg\min }\  h(v)$. Notice that: $$\nabla h(v)=\sigma(v-x_{0})+a_{0}\nabla f(x_{0})$$Hence, $v_{0}= x_{0}-\frac{a_{0}}{\sigma}\nabla f(x_{0})$.
2. From 1, we have that: $$\begin{align}L_{0}&=\frac{1}{a_{0}}\left( \phi(v_{0})+a_{0}f(x_{0})+\braket{ a_{0}\nabla f(x_{0}) , v_{0}-x_{0} }  \right)-\frac{\phi(x^{*})}{a_{0}} \\&=\frac{1}{a_{0}}\left( \frac{a_{0}^{2}}{2\sigma}\left\|\nabla f(x_{0})\right\|^2_{2}+a_{0}f(x_{0})-\frac{a_{0}^{2}}{\sigma}\left\| \nabla f(x_{0}) \right\| ^{2}_{2} \right)-\frac{\phi(x^{*})}{a_{0}}\\&=\frac{1}{a_{0}}\left( a_{0}f(x_{0})-\frac{a_{0}^{2}}{2\sigma}\left\| \nabla f(x_{0}) \right\| ^{2}_{2} \right)-\frac{\sigma}{2a_{0}} \left\| x^{*}-x_{0} \right\| ^{2}_{2}\\&=f(x_{0})-\frac{a_{0}}{2\sigma}\left\| \nabla f(x_{0}) \right\| ^2_{2}-\frac{\sigma}{2a_{0}}\left\| x^{*}-x_{0} \right\|^2_{2} \end{align}$$

---
#### Problem 2
1. One easily sees that $m_{i}$ is twice differentiable. Hence, we have that for all $v$: $$\nabla m_{i}(v)=\sigma (v-x_{0})+\sum_{j\leq i}^{}a_{j}\nabla f(x_{j}) $$and $\text{H}_{m_{i}}(v)=\sigma I$. Hence, by Taylor and the optimality of $v_{i}$:$$m_{i}(v)=m_{i}(v_{i})+\underbrace{ \nabla m_{i}(v_{i})^\top }_{ =0 }(v-v_{i})+\frac{\sigma}{2}\left\| v-v_{i} \right\| ^2_{2}=m_{i}(v_{i})+\frac{\sigma}{2}\left\| v-v_{i} \right\| ^2_{2}$$This proves the statement.
2. We have: $$\begin{align}m_{i+1}(v) &=\phi(v)-\phi(x^{*})+\sum_{j\leq i+1}^{}a_{j}f(x_{j})+\braket{ a_{j}\nabla f(x_{j}) ,v-x_{j}  }\\&=\phi(v)-\phi(x^{*})+\sum_{j\leq i}^{}a_{j}f(x_{j})+\braket{ a_{j}\nabla f(x_{j}) ,v-x_{j}  } +a_{i+1}f(x_{i+1})+\braket{ a_{i+1}\nabla f(x_{i+1}) ,v-x_{i+1}  } \\&=m_{i}(v)+a_{i+1}f(x_{i+1})+\braket{ a_{i+1}\nabla f(x_{i+1}) ,v-x_{i+1}  } \end{align}$$
3. We have: $$\nabla m_{i+1}(v)=\nabla m_{i}(v)+ a_{i+1}\nabla f(x_{i+1})=\sigma(v-v_{i})+ a_{i+1}\nabla f(x_{i+1})$$Hence, by equating it with zero, $v_{i+1}=v-\frac{a_{i+1}}{\sigma}\nabla f(x_{i+1})$.

---
#### Problem 3
Let $i,j\in[n]$ with $i<j$. Then, one sees that: $$L_{G_{i,j}}(u,v)=\begin{cases}1&u=v\in\{ i,j \}\\-1&\{ u,v \}=\{ i,j \}\\0&\text{otherwise}\end{cases}$$
Let $x\in \mathbb{R}^n$ be arbitrary. Then, $$x^\top L_{G_{i,j}}x=(x_{i}-x_{j})^{2}$$

Then, by Cauchy-Schwarz:$$\begin{align}(x_{n}-x_{1})^{2}=\left( \sum_{i=1}^{n-1}x_{i+1}-x_{i} \right)^{2}=\left( \sum_{i=1}^{n-1} \frac{1}{\sqrt{ w_{i} }}\sqrt{ w_{i} }(x_{i+1}-x_{i}) \right)^{2}\leq\left( \sum_{i=1}^{n-1} \frac{1}{w_{i}} \right) \left( \sum_{i=1}^{n-1}w_{i}(x_{i+1}-x_{i})^{2} \right) \end{align} $$This shows that $G_{1,n}\preceq \left( \sum_{i=1}^{n-1} \frac{1}{w_{i}} \right)\sum_{i=1}^{n-1}w_{i}G_{i,i+1}$.

---
#### Problem 4
Firstly, for $v\in T_{n}$, let $\ell(v)$ denote the level of the vertex $v$ in the tree, where the root is in level $0$. 

Let $i,j$ arbitrary with $i<j$. Then, let $G^{i,j}$ denote the (unique) path between $i,j$. For any edge $e=(u,v)$ with $\ell(v)\geq \ell(u)$, we let $p(u,v)$ as the number of $(i,j)$ with $i<j$ s.t. $e$ is in $G^{i,j}$. We compute that: $$p(u,v)=(2^{d-\ell(v)+1}-1)(n-2^{d-\ell(v)+1}+1)$$Notice that $p(u,v)$ only depends on the level of the vertices. 

Now, let $i<j$ be arbitrary, we have that: $$\sum_{e\in G^{i,j}}^{} p(e)\leq 2\cdot \sum_{k=1}^{d}(2^{d-k+1}-1)(n-2^{d-k+1}+1)< 2n\sum_{k=1}^{d}2^{d-k+1}=2n^2$$Hence, by setting the weight of each edge $e$ as $\frac{1}{p(e)}$, we have that by Problem 3, $$K_{n}=   \sum_{i<j} G_{i,j}\preceq   2n^{2}\sum_{i<j}^{}\sum_{e\in G^{i,j}} \frac{1}{p(e)}G_{e}=2n^{2}\sum_{ e\in T_{n}}^{}G_{e}=2n^{2} T_{n}$$Therefore, $n\leq 2n^{2} \lambda_{2}(T_{n})$ and this proves the statement.

---
#### Problem 5

1. Let $S\subseteq V$ with  size $k$. Then, $$\phi_{S}=\frac{e(S,\overline{S}) }{\text{vol}(S)}=\frac{k(n-k)}{k(n-1)}=\frac{n-k}{n-1}$$Hence, $\phi(K_{n})=\frac{n-\left\lfloor n / 2\right\rfloor}{n-1}\approx\frac{1}{2}$. 
2. Let $S\subseteq V$ with size $k$. Then, the volume is given as $2k-2\leq\text{vol}(S)\leq 2k$. If $\text{vol}(2k)=2k$, then we have that $2\leq e(S,\overline{S})$. However, if $2k-1$, by taking the first $k$ vertices as $S$, we have that: $$\text{vol}(S)=1$$Therefore, we have that: $$\phi(P_{n})=\frac{1}{2\left\lfloor n  / 2\right\rfloor -1}$$
---