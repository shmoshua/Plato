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
Firstly, for $v\in T_{n}$, let $\ell(v)$ denote the level of the vertex $v$ in the tree, where the root is in level $0$. Then, for edge $(u,v)$ where $v$ is the child of $u$, we assign the weight $2^{\ell(v)}$ to $(u,v)$.

Let $i,j$ arbitrary with $i<j$. Then, let $G^{i,j}$ denote the (unique) path between $i,j$ and let $u$ be the vertex on the path with the lowest level. Then, the sum of the reciprocal of the weights of the path is at most: $2\cdot \sum_{i=1}^{d} \frac{1}{2^i}\leq 2$.

Hence, by Problem 3, we have that:$$K_{n}=\sum_{i<j}^{}G_{i,j}\preceq \sum_{i<j}^{}\left( 2\sum_{e\in G^{i,j}}w_{e}G_{e} \right) $$

Let $e=(u,v)\in T_{n}$ where $v$ is the child of $u$. Then, $e$ appears exactly $(2^{d-\ell(v)})(n-2^{d-\ell(v)})$ times in $G^{i,j}$ over $i<j$. Therefore, we have that: $$K_{n}\preceq  2\sum_{e\in G^{i,j}}2^d(n-2^{d-\ell(v)}) G_{e}\preceq K_{n}\preceq  2\sum_{e\in G^{i,j}}2^d(n-2^{d-\ell(v)}) T_{n}$$

Every edge $(u,v)$ where $u$ is a child of $v$ is in $(2^{d-\ell(u)})(n-2^{d-\ell(u)})$ paths. Hence, 

Let us give weights to the edges of $T_{n}$ where 