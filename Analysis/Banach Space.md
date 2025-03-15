#Definition #LST #Analysis 

> [!definition]
> A [[Analysis/Normed Space|normed space]] $(V,\|\cdot\|)$ is called ***Banach*** or ***complete*** if every [[Cauchy Sequence|Cauchy sequence]] in it converges, i.e. the underlying [[Metric Space]] $(V,d)$ is [[Complete Metric Space|complete]].
---
##### Properties

> [!lemma] Theorem 1
> Let $V$ be finite-dimensional. Then, for any norm $\|\cdot\|$, the normed space $(V,\|\cdot \|)$ is Banach.

>[!proof]-
>Suppose $F=\mathbb{R}$. Let $V$ have a basis $\{ b_{i} \}_{i\in[d]}$ s.t. for every $v\in V$ we have a representation $x\in \mathbb{R}^d$, i.e. $v=\sum_{i=1}^{d}x_{i}b_{i}$. We now define the function $\|\cdot\|_{*}:\mathbb{R}^d\to \mathbb{R}$ as follows: $$\|x\|_{*}=\left\| \sum_{i=1}^{d}x_{i}b_{i} \right\| $$
> > [!lemma] Claim 1
>> $\|\cdot\|_{*}$ is a norm on $\mathbb{R}^d$. 
>
> > [!proof]-
> > We have that 
> > 1. $\|x+y\|_{*}=\left\| \sum_{i=1}^{d}x_{i}b_{i}+\sum_{i=1}^{d}y_{i}b_{i} \right\|\leq\left\| \sum_{i=1}^{d}x_{i}b_{i} \right\|+\left\|\sum_{i=1}^{d}y_{i}b_{i} \right\|=\|x\|_{*}+\|y\|_{*}$
> > 2. $\|ax\|_{*}=\left\| a\sum_{n=1}^{d}x_{i}b_{i} \right\|=|a|\left\| \sum_{n=1}^{d}x_{i}b_{i} \right\|=|a|\|x\|_{*}$
> > 3. $\|x\|_{*}=0 \iff \left\| \sum_{i=1}^{d}x_{i}b_{i} \right\|=0 \iff x=0$
> 
> We will now show that $(\mathbb{R}^d,\mathbb{R},\|\cdot\|_{*})$ is a Banach space. As $\mathbb{R}^d$ is finite-dimensional, $\|\cdot\|_{*}$ is equivalent to $\|\cdot\|_{\infty}$. Suppose that $\{ x^i \}_{i\geq 0}$ is a Cauchy sequence. Then, for all $\varepsilon>0$ there exists $N\in \mathbb{N}$ s.t.$$\left\| x^m -x^n\right\|_{\infty}<\varepsilon $$This means, for all $i\in[d]$,  for all $\varepsilon>0$ there exists $N\in \mathbb{N}$ s.t.$$\left| x^m_{i}-x^n_{i} \right| <\varepsilon $$As $(\mathbb{R},\mathbb{R},|\cdot|)$ is Banach, we have that $\{ x^i_{j} \}_{i\geq 0}$ converges for all $j\in[d]$. Therefore, we can define $x:=(x_{1},\dots,x_{d})$ as the limit.  Therefore, for all $\varepsilon>0$ there exists $N\in \mathbb{N}$ s.t.$$\left\| x^m - x \right\|_{*} <\varepsilon$$ for all $m\geq N$. This shows that $\{ x^i \}$ is convergent and therefore, $(\mathbb{R}^d,\mathbb{R},\|\cdot\|_{*})$ is Banach.
> 
> Now, let's show that $(V,F,\|\cdot\|)$ is Banach. For a Cauchy sequence $\{ v^i\}_{i\geq 0}\subseteq V$, let $\{ x^i \}_{i\geq 0}\subseteq \mathbb{R}^d$ be the corresponding sequence wrt basis vectors. Let $v:=\sum_{j=1}^{d}x_{j}b_{j}$. Then, for all $\varepsilon>0$ there exists $N \in \mathbb{N}$ s.t. $$\|v^n-v\|=\left\| \sum_{j=1}^{d}(x^n_{j}-x_{j})b_{j} \right\| =\left\| x^n-x \right\|_{*}<\varepsilon $$ Therefore, $(V,F,\|\cdot\|)$ is Banach.
---
> [!lemma] Proposition 2
> Let $V$ be a Banach space and $E,F$ closed subspaces s.t. $E+F$ is also closed. Then, there exists $c>0$ s.t. for every $z\in E+F$, there exists $x\in E,y\in F$ for which $z=x+y$ and: 
> $$\|x\|\leq c \|z\|,\quad \|y\|\le c\|z\|$$

> [!proof]-
> Consider $E\times F$ with the norm $\left\| (x,y) \right\|=\|x\|+\|y\|$. Then, $E\times F$ is a Banach space. For $$\begin{array}{cccc} {T:}&{E\times F}&\to&{E+F}\\&{(x,y)} &\mapsto & {x+y} \end{array}{}$$we have a surjective bounded operator from triangle inequality. Then, $$\text{ker }T=\{ (v,-v):v\in E\cap F \}$$which is a closed subspace of $E\times F$. Now, from the isomorphism theorem, there exists a bijection
> $$\begin{array}{cccc} {\overline{T}:}&{(E\times F)/\text{ker }T}&\to&{E+F}\\&{(x,y)+\text{ker }T} &\mapsto & {x+y} \end{array}{}$$
> Since $E+F$ is closed, it is a Banach space and by [[Bounded Linear Map|Corollary 7]], $\overline{T}^{-1}$ is bounded, i.e. there exists $c>0$ s.t. $$\left\| \overline{T}^{-1}(z) \right\|\leq c\|z\| $$ for all $z\in E+F$. In other words, if $\overline{T}^{-1}(z)=(x,y)+\text{ker }T$,
> $$\begin{align}\left\| (x,y)+\text{ker }T \right\|&=\inf\{ \left\| (x,y)+(v,-v) \right\|:v\in E\cap F  \} \\&=\inf\{ \|x+v\|+\|y-v\|:v\in E\cap F  \}\leq c\|z\|\end{align} $$
> - Case 1: $\|z\|=0$. Then, $z=x+y=0$ and $x\in E\cap F$ and $y=-x$. Therefore, $$\left\| \overline{T}^{-1}(z) \right\|=\inf\{ \|w\|+\|-w\|:w\in E\cap F  \} =0$$
> - Case 2: $\|z\|>0$. Then, there exists $v\in E\cap F$ s.t. $\|x+v\|+\|y-v\|\leq 2c\|z\|$. As $x+v+y-v=x+y=z$, this concludes the proof.
---
> [!lemma] Propostion 3
> Let $X$ be a normed space. TFAE:
> 1. $X$ is Banach.
> 2. for all $(x_{n})_{n}\subseteq X$, if $\sum_{n=1}^{\infty}\|x_{n}\|$ converges then $\sum_{n=1}^{\infty}x_{n}$ converges in $X$.
> 
---
##### Examples
> [!claim] Example 1
> For a topological space $X$, the space of all bounded continuous functions: $$C^b(X):=\{ f:X\to \mathbb{R}|f\in C^0(X), \text{sup}_{x\in X}\left| f(x) \right| <+\infty \}$$with the sup norm: $$\left\| f \right\| _{b}:=\sup_{x\in X}\left| f(x) \right| $$is a Banach space.

> [!proof]-
> Let $\{ f_{k} \}_{k}\subseteq C^b(X)$ be a Cauchy sequence. Then, for all $x\in X$, $\{ f_{k}(x) \}_{k}$ is a Cauchy sequence and there exists $f:X\to \mathbb{R}$ s.t. $f_{k}(x)\to f(x)$ for all $x\in X$.
> 1. **$f$ is bounded**: For $\varepsilon>0$, we have: $$\left\| f \right\|_{b}\leq \left\| f-f_{k} \right\|_{b} +\left\| f_{k} \right\|_{b}\leq \varepsilon+\left\| f_{k} \right\| _{b} <+\infty$$for some $k$. 
> 2. **$f_{k}\to f$ in norm**: For $\varepsilon>0$, there exists $K$ s.t. $\left\| f_{n}-f_{k} \right\|_{b}<\varepsilon$ for all $n,k\geq K$. Therefore, by $n\to \infty$$$\left\| f -f_{k}\right\|_{b} <\varepsilon$$
> 3. **$f$ is continuous**. This shows that $f_{k}$ uniformly converges to $f$ and by the uniform convergence theorem, $f$ is continuous.
> 
> This shows that $(C^b(X),\|\cdot\|_{b})$ is Banach.

> [!proof]-
> Let $\{ f_{k} \}_{k}\subseteq C^b(X)$ be a Cauchy sequence. Then, by extraction we have a subsequence $\{ f_{k_{n}} \}_{n}$ s.t. $\left\| f_{k_{n+1}}-f_{k_{n}} \right\|_{b} < \frac{1}{2^n}$ for all $n\geq 1$. By setting: $$f:=f_{k_{1}}+\sum_{n=1}^{\infty}(f_{k_{n+1}}-f_{k})$$We have: $\left\| f \right\|_{b}\leq \left\| f_{k_{1}} \right\|+1$. Therefore, $f\in C^b(X)$. Then, for $\varepsilon>0$, choose $n_{0}$ s.t. $2^{-n_{0}}< \varepsilon/2$. Then, for all $k\geq k_{n_{0}}$$$\left\| f-f_{k} \right\| \leq \left\| f-f_{k_{n_{0}}} \right\|+\left\| f_{k}-f_{k_{n_{0}}} \right\|<\left\| f-f_{k_{n_{0}}} \right\|+\varepsilon / 2 $$
> 

 $x\in X$, $\{ f_{k}(x) \}_{k}$ is a Cauchy sequence and there exists $f:X\to \mathbb{R}$ s.t. $f_{k}(x)\to f(x)$ for all $x\in X$.
> 1. **$f$ is bounded**: For $\varepsilon>0$, we have: $$\left\| f \right\|_{b}\leq \left\| f-f_{k} \right\|_{b} +\left\| f_{k} \right\|_{b}\leq \varepsilon+\left\| f_{k} \right\| _{b} <+\infty$$for some $k$. 
> 2. **$f_{k}\to f$ in norm**: For $\varepsilon>0$, there exists $K$ s.t. $\left\| f_{n}-f_{k} \right\|_{b}<\varepsilon$ for all $n,k\geq K$. Therefore, by $n\to \infty$$$\left\| f -f_{k}\right\|_{b} <\varepsilon$$
> 3. **$f$ is continuous**. This shows that $f_{k}$ uniformly converges to $f$ and by the uniform convergence theorem, $f$ is continuous.
> 
> This shows that $(C^b(X),\|\cdot\|_{b})$ is Banach.
---
> [!claim] Example 2
> For $\alpha>0$, let $$\Lambda^\alpha(\mathbb{R}):=\{ f\in C^b(\mathbb{R}):\sup_{t_{1} \neq t_{2}} \frac{\left| f(t_{2})-f(t_{1}) \right|}{|t_{2}-t_{1}|^\alpha} <+\infty \}$$Then, we can define a norm: $$\left\| f \right\| _{\Lambda^\alpha}:=\sup_{x\in \mathbb{R}}\left| f(x) \right| +\sup_{y\neq z} \frac{\left| f(y)-f(z) \right|}{\left| y-z \right|^\alpha }  $$and $(\Lambda^a(\mathbb{R}),\|\cdot\|_{\Lambda^\alpha})$ is a Banach space.

> [!proof]-
> Let $\{ f_{k} \}_{k}$ be a Cauchy sequence. Then, for $\varepsilon>0$, there exists $K$ s.t. $$\left\| f_{n}-f_{m} \right\| _{\Lambda^\alpha}=\sup_{x\in \mathbb{R}}\left| f_{n}(x)-f_{m}(x) \right| +\sup_{y\neq z} \frac{\left| f_{n}(y)-f_{n}(z)-f_{m}(y)+f_{m}(z) \right|}{\left| y-z \right| ^\alpha} <\varepsilon$$Therefore, $(f_{n}(x))_{n}$ is Cauchy and there exists $f:\mathbb{R}\to \mathbb{R}$ s.t. $f_{n}(x)\to f(x)$ for all $x\in \mathbb{R}$.
> 1. $f\in \Lambda^\alpha(\mathbb{R})$:  As $(f_{n})_{n}$ is Cauchy, there exists $M\in \mathbb{R}$ s.t. $\left\| f_{n} \right\|_{\Lambda^\alpha}\leq M$ for all $n$. Then, for all $y,z\in\mathbb{R}$ with $y\neq z$, $$\left| f_{n}(y)-f_{n}(z) \right| \leq M\left| y-z \right| ^\alpha$$By $n\to \infty$, we get $\left| f(y)-f(z) \right|\leq M\left| y-z \right|^\alpha$ for all $y,z\in \mathbb{R}$ and $f\in \Lambda^\alpha(\mathbb{R})$.
> 2. $\left\| f-f_{n} \right\|_{\Lambda^\alpha}\to 0$: Let $\varepsilon>0$. Then there exists $N$ s.t. for all $m,n\geq N$ we have $\left\| f_{n}-f_{m} \right\|<\varepsilon$.  For $x,y,z\in \mathbb{R}$ with $y\neq z$, there exists $M>0$ s.t. for all $m\geq M$, we have: 
> 	- $\left| f(x)-f_{m}(x) \right|<\varepsilon$
> 	- $\left| f(y)-f_{m}(y) \right|<\varepsilon \left| y-z \right|^\alpha$ and
> 	- $\left| f(z)-f_{m}(z) \right|<\varepsilon \left| y-z \right|^\alpha$
> 	  
> 	For all $n\geq N$ and $m\geq \max\{ N,M \}$, $$\begin{align}\left| f(x)-f_{n}(x) \right| + \frac{\left| (f(y)-f_{n}(y))-(f(z)-f_{n}(z)) \right|}{\left| y-z \right| ^\alpha} &\leq\end{align}$$
---
We have
1. The real numbers space $(\mathbb{R},\mathbb{R},|\cdot|)$ is Banach.
2. The normed space $(C([-1,1],\mathbb{R}),\mathbb{R},\|\cdot\|_{1})$ is not Banach. We define the sequence $\{ f_{i} \}_{i\geq 1}$ where $$f_{i}(t)=\begin{cases}0&t<0\\it&0\leq t< 1/i\\1&1/i \leq t\end{cases}$$ For any $N,m\in \mathbb{N}$ and $m\geq N$, we have: $$\begin{align}\|f_{m}-f_{N}\|_{1}&=\int_{-1}^{1} \left| f_{m}(t)-f_{N}(t) \right|  \, dt =\int_{0}^{1/m} (m-N)t \, dt+\int_{1/m}^{1/n}  1-Nt\, dt\\&=  \frac{m-N}{2mN}\leq \frac{1}{2N}\end{align}$$Therefore, for $\varepsilon>0$, we can take $N> \frac{1}{2\varepsilon}$ and $\{ f_{i} \}_{i\geq 1}$ is therefore Cauchy. However, the sequence converges to $f$ where: $$f(t)=\begin{cases}0&t<0\\1&0 \leq t\end{cases}$$As $$\left\| f_{i}-f \right\| _{1}=\int_{0}^{1/i} 1-it \, dt= \frac{1}{i}-\frac{1}{2i}=\frac{1}{i} \to 0 $$However, $f\notin C([-1,1],\mathbb{R})$. Therefore, this space is not Banach.
3. The normed space $(C([t_{0},t_{1}],\mathbb{R}^n),\mathbb{R},\|\cdot\|_{\infty})$ is Banach. For a Cauchy sequence $\{ f_{i} \}_{i\geq 1}$ and $t\in[t_{0},t_{1}]$, $\{ f_{i}(t) \}_{i\geq 1}$ is also a Cauchy sequence in $\mathbb{R}^n$. Therefore, we can define the function $f$ as: $$f(t)=\lim_{ i \to \infty } f_{i}(t)$$Then, $\{ f_{i} \}_{i\geq 1}$ converges to $f$: For every $\varepsilon>0$, we have $N\in \mathbb{N}$ s.t. $\|f_{i}(t)-f_{j}(t)\|_{2}\leq\left\| f_{i}-f_{j} \right\|_{\infty}<\varepsilon$ for all $t\in[t_{0},t_{1}]$ and $i,j\geq N$. Then, for every $\varepsilon>0$, we have $N\in \mathbb{N}$ s.t. $\|f_{i}(t)-f(t)\|_{2}<\varepsilon$ for all $t\in[t_{0},t_{1}]$ and $i\geq N$. Therefore, $\|f_{i}-f\|_{\infty}<\varepsilon$ for all $i\geq N$.
  
	  We can finally prove that $f\in C[(t_{0},t_{1}],\mathbb{R}^n)$. For arbitrary $t,t'\in[t_{0},t_{1}]$, we have: $$\|f(t)-f(t')\|_{2}\leq \left\| f(t)-f_{i}(t) \right\|_{2}+\left\| f_{i}(t)-f_{i}(t') \right\|_{2} +\left\| f(t')-f_{i}(t') \right\| $$Fix $\varepsilon>0$. As $\{ f_{i} \}_{i}$ converges to $f$, there exists $f_{i}$ s.t. $\|f(t)-f_{i}(t)\|_{2} < \frac{\varepsilon}{3}$ for all $t$. On the other hand, as $f_{i}$ is continuous, there exists $\delta$ s.t. $\|f_{i}(t)-f_{i}(t')\|< \frac{\varepsilon}{3}$ if $|t-t'|<\delta$. Therefore, if $|t-t'|<\delta$, we have: $$\left\| f(t) -f(t')\right\|<3\cdot \frac{\varepsilon}{3}=\varepsilon $$This proves the continuity of $f$. This proves that $(C([t_{0},t_{1}],\mathbb{R}^n),\mathbb{R},\|\cdot\|_{\infty})$ is Banach.

> [!lemma]  Theorem 
> The set of nowhere differentiable functions in $(C([0,1]),\|\cdot\|_{\infty})$ is [[Meager Set|generic]].
  
> [!proof]-
> Stein-Shakarski 4.1.2
  
4. Let $X$ be a [[Topological Space|topological space]] and: $$C^b(X):\{ f:X \to \mathbb{R}|f\text{ is continuous and bounded} \}$$Then, we can define a norm for $f\in C^b(X)$: $$\left\| f \right\| _{b}:=\sup_{x\in X}\left| f(x) \right| $$We have that $(C^b(X),\|\cdot\|_{b})$ is a Banach space.
5. 
--- 