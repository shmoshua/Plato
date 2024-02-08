#Series #FunctionalAnalysis 

##### Problem 2
We define the function: $$\begin{array}{cccc} {g:}&{F}&\to&{E^{*}}\\&{y} &\mapsto & {f(\cdot ,y)} \end{array}{}$$
1. **Showing $\text{graph}(g)$ is closed**:
	Let $(y,z)\in \overline{\text{graph}(g)}$. Then, there exists $(y_{n})_{n}\subseteq F$ s.t. $y_{n}\to y$ in $F$ and $f(\cdot,y_{n})\to z$ in $E^{*}$. For any $x\in E$: $$\left| f(x,y_{n})-z(x) \right|\leq \left\| f(\cdot ,y_{n})-z \right\|\|x\| $$and $f(x,y_{n})\to z(x)$ as $n\to \infty$. However, as $f(x,\cdot)$ is continuous for every $x$, $f(x,y_{n})$ converges to $f(x,y)$ and we have $z(x)=f(x,y)$, i.e. $z=f(\cdot,y)$. This shows that $(y,z)\in \text{graph}(g)$ and by the [[Bounded Linear Map|closed graph theorem]], $g$ is bounded.
2. **Showing that the bilinear map is bounded**:
	We have that: $$\left| f(x,y) \right| \leq \left\| f(\cdot ,y) \right\|\|x\|\leq \left\| g \right\| \|x\|\|y\|$$
This proves the statement.
---
##### Problem 3
The assumption states that: $$\begin{array}{cccc} {f:}&{(V,\|\cdot \|_{2})}&\to&{(V,\|\cdot \|_{1})}\\&{v} &\mapsto & {v} \end{array}{}$$is bounded. Therefore, it's inverse is also bounded and $\|v\|_{2}\leq\|f^{-1}\|\|v\|_{1}$ for all $v\in V$.

---
##### Problem 4
Consider $f_{n}(x)=\sin(2n\pi  x)$ for $n\geq 1$. Then, $\left\| f_{n} \right\|_{\infty}=1$ but $$\left\| f'_{n} \right\|_{\infty}=\left\| 2n\pi \cos(2n\pi x) \right\|_{\infty}=2n\pi  $$Therefore, the differentiation operator is unbounded. We will show however, that the graph is closed. 

Let $(f,g)\in \overline{\text{graph}(L))}$ and $(f_{n})_{n}\subseteq C_{1}([0,1])$ s.t. $f_{n}\to f$ and $f'_{n}\to g$ both in $\|\cdot\|_{\infty}$. Then, for $x$, $$f'(x)=\lim_{ h \to 0 } \frac{f(x+h)-f(x)}{h}$$
