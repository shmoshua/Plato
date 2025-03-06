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
