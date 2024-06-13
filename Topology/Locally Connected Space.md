#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***locally connected***, if every $x\in X$ has a [[Local Base of Topology|local base]] of [[Connected Space|connected]] sets.
---
##### Properties
> [!lemma] Proposition 1
> Let $X$ be a topological space. The following are equivalent:
> 1. $X$ is locally connected.
> 2. for all $U\subseteq X$ open, all $x\in U$, the connected component of $x$ in $U$ is open.

> [!proof]-
> Let $U\subseteq X$ be open and $x\in U$. Let $V$ be a connected component of $x$ in $U$. Let $y\in V$ and $W$ be the connected neighborhood of $y$ in $U$. Then, $W\subseteq V$ by the definition of a connected component. Therefore, $V$ is open.
> 
> Conversely, let $x\in X$ and $U$ is an open neighborhood of $x$. Since the connected component of $x$ in $U$ is open, it is an open neighborhood of $x$ contained in $U$.
- **Remark**: If $X$ is locally connected, the connected components of $X$ are open and closed.

---
##### Examples

> [!h] Example 1
> We have: 
> 1. Any discrete space $X$ is locally connected.
> 2. $\mathbb{R}^n$ is locally connected.
> 3. Any topological manifold is locally connected.
---
> [!h] Example 2
>  $L^2([0,1])$ is locally connected.
---
###### Non-Examples
> [!h] Non-Example 1 (Connected but not Locally Connected)
> Let $$X:=(\{ 0 \}\times[-1,1])\cup \bigcup_{n\geq 1}^{}\left\{  \frac{1}{n}  \right\}\times[-1,1]\cup([0,1]\times \{ 1 \})\subseteq \mathbb{R}^{2}$$ with the subspace topology from the euclidean topology of $\mathbb{R}^{2}$. It is a metric space.
> 1. $X$ is connected.
> 2. $X$ is not locally connected.

^62ae51

> [!proof]-
> We have:
> 1. We define the following functions: $$\begin{array}{cccc} {f_{n}:}&{\left[ 0,2+\frac{1}{n} \right]}&\to&{\mathbb{R}^{2}}\\&{x} &\mapsto & {\begin{cases}\left( \frac{1}{n},x-1 \right)&x\in[0,2]\\\left( 2+\frac{1}{n}-x,1 \right)&\text{otherwise}\end{cases}} \end{array}{}$$and $f_{0}:[0,2]\to \mathbb{R}^{2},x\mapsto(0,x-1)$. Then, one can easily see that the functions are continuous and as the domains are all intervals, $\text{im }f_{n}$ for all $n\geq 0$ is connected. As $(0,1)\in \bigcap_{n\geq 0}^{}\text{im }f_{n}$, $X=\bigcup_{n\geq 0}^{}\text{im }f_{n }$ is connected.
> 2. Let $x_{0}=(0,0)\in X$. Then, we claim that: $$U_{\delta}:=X\cap \{ (x,y)\in \mathbb{R}^{2}:\left| x \right| <\delta,\left| y \right| <\delta \}$$for $0<\delta<1$ forms an open local base at $x_{0}$ in $X$. Let $V$ be an open neighborhood of $x_{0}$ in $X$. Then, there exists $U$ open in $\mathbb{R}^{2}$ s.t. there exists $r>0$ s.t. $B_{<r}(x_{0})\subseteq U$. Therefore, $U_{r /\sqrt{ 2 }}\subseteq V$. One can also easily see that $U_{\delta}$ is open for any $0<\delta<1$. 
>    
>    However, we also claim that the connected compotent of $x_{0}$ in $U_{\delta}$ is $\{ 0 \}\times(-\delta,\delta)$. Assume there exists a larger connected component $V$ of $x_{0}$ in $U_{\delta}$. Then, $y_{0}\in V$ s.t. $y_{0}\notin U_{\delta}\backslash(\{ 0 \}\times(-\delta,\delta))$. This means $y_{0}=\left( \frac{1}{n},y \right)\in \mathbb{R}^{2}$ where $0<\frac{1}{n}<\delta$. Let $f:V\to \{ 0,1 \}$ where $f((x,y))=0$ if $x= \frac{1}{n}$ and $f((x,y))=1$ if $x\neq \frac{1}{n}$. Then, $f^{-1}(\{ 0 \})=U_{\delta}\cap \left( \frac{1}{n+1} ,\frac{1}{n-1}\right)\times(-\delta,\delta)$ is open and $f^{-1}(\{ 1 \})=U_{\delta}\cap\left(  \mathbb{R}^{2} \backslash\left\{  \frac{1}{n}  \right\}\times[-\delta,\delta] \right)$ which is open. Therefore, $f$ is a non-constant continuous function. This is a contradiction to $V$ being connected.
>    
>    Finally, assume $X$ is locally connected. Then, for all $\delta>0$, $\{ 0 \}\times(-\delta,\delta)$ is open in $X$. Therefore, there exists $r>0$ s.t. $B_{<r}(0)\cap X\subseteq \{ 0 \}\times(-\delta,\delta)$. This is a contradiction as there exists $n\geq 1$ s.t. $\frac{1}{n}<r$ and $\left( \frac{1}{n},0 \right)\in B_{<r}(0)\cap X$.

^35d8ef

- **Remark**: Conversely, any discrete space $X$ with $\left| X \right|\geq 2$ is locally connected but not connected.
---
