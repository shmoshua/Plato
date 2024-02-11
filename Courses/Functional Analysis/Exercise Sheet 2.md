#Series #FunctionalAnalysis 

##### Problem 1
Assume that there exists $\varepsilon>0$ s.t. for all $v\in V$, we have that: $d(v,W)\leq \|v\|(1-\varepsilon)$. Let $v_{0}\in V$. Then, there exists $w_{0}\in W$ s.t. $\left\| v_{0}-w_{0} \right\|\leq \left\| v_{0} \right\|(1-\varepsilon)$. We can iteratively define: 
1. $v_{i+1}:=v_{i}-w_{i}$
2. $w_{i+1}\in W$ s.t. $\left\| v_{i+1}-w_{i+1} \right\|\leq \left\| v_{i+1} \right\|(1-\varepsilon)$
   
Then, we have $$ \left\| v_{n} \right\| \leq (1-\varepsilon)^n\left\| v_{0} \right\| $$and therefore, $\lim_{ n \to \infty }\left\| v_{0}-v_{n} \right\|=0$ and $\lim_{ n \to \infty }v_{0}-v_{n}=v_{0}$. As $(v_{0}-v_{n})_{n} \subseteq W$, and $W$ is closed, $v_{0}\in W$. As $v_{0}$ is arbitrary, we have that $V=W$.

---
##### Problem 2
1. Suppose $(w_{n})_{n}\subseteq W$ with limit $w$. Then, we have $\left\| w+W \right\|\leq \left\| w-w_{n} \right\|$ for all $n$. By taking the limit, we have that $\left\|  w+W \right\|=0$. Then, this means that $w+W=W$, i.e. $w\in W$. Therefore, $W$ is closed.
	
	Now, assume that $W$ is closed. Consider $\left\| v+W \right\|=0$. Then, by definition there exists $(w_{n})_{n}\subseteq W$ s.t. $\left\| v-w_{n} \right\|< \frac{1}{n}$. Then, $(w_{n})_{n}$ converges to $v$ and $v\in W$. This proves that $v+W = W$.
2. Suppose we have a Cauchy sequence $(v_{n}+W)_{n}\subseteq V/W$. We first show that $(v_{n})_{n}$ is Cauchy. For any $\varepsilon>0$, $$\left\| v_{n}-v_{m} \right\| \leq$$
---
##### Problem 3
Consider the map $T: \ell^{2}(\mathbb{Z})\to \ell^{2}(\mathbb{Z})$ where: $$Tf(n)=\begin{cases}f\left( \frac{n}{2} \right)&n\text{ is even}\\0& n \text{ is odd}\end{cases}$$
Then, 
$$ \left\| T f \right\| ^2_{2} = \sum_{n}^{}\left| Tf(n) \right| ^{2}=\sum_{n\text{ even}}^{}\left| f\left( \frac{n}{2} \right) \right| ^{2}=\sum_{n}^{}\left| f(n) \right| ^{2}=\left\| f \right\| ^{2}_{2}$$The image is $R(T)=\{ f\in \ell^{2}(\mathbb{Z}):f(n)=0 \text{ for all even }n \}$
---
##### Problem 4
---
We have that:
> [!proof]+
> From $f_{n}\xrightarrow{w^{*}}f$, we have:
> $$\limsup_{ n \to \infty } \left| \int_{\Omega}^{} (f_{n}-f)g \, d\mu \right|=0,\quad \forall g\in L^1(\Omega) $$
> We need to show that $\limsup_{ n \to \infty }\left| V(f_{n})-V(f) \right|=0$.
> 1. For every $h\in L^\infty(\Omega)$,$$\left| (g*h)(x) \right| \leq\int_{\Omega}^{} \left| g(x-y)h(y) \right|  \, dy \leq \left\| h \right\| _{\infty}\left\| g \right\| _{1}$$Therefore, $$\begin{array}{cccc} {K:}&{L^\infty(\Omega)}&\to&{L^\infty(\Omega)}\\&{h} &\mapsto & {g*h} \end{array}{}$$ is well defined, $\left\| g*h \right\|_{\infty}\leq \left\| h \right\|_{\infty}\left\| g \right\|_{1}$ and $\left\| K \right\|\leq \left\| g \right\|_{1}$ with $Kh\in L^1(\Omega)$. Then, $$V(f)=\int_{\Omega}^{} Kf(x) f(x) \, dx $$
> 2. We have for all $x\in \Omega$: $$\limsup_{ n \to \infty } \left| Kf_{n}(x)-Kf(x) \right| =\limsup_{ n \to \infty } \left| \int_{\Omega}^{} g(x-y)(f_{n}-f)(y) \, dy  \right| =0$$
> 3. Finally, $$\begin{align}\limsup_{ n \to \infty } \left| V(f_{n})-V(f) \right|  &=\limsup_{ n \to \infty }\left| \int_{\Omega}^{} (g*f_{n})f_{n} \, d\mu- \int_{\Omega}^{} (g*f)f \, d\mu  \right|\\&\leq\limsup_{ n \to \infty }\left| \int_{\Omega}^{} (g*(f_{n}-f))f_{n} \, d\mu \right| +\underbrace{ \limsup_{ n \to \infty }  \left|\int_{\Omega}^{} (g*f)(f_{n}-f )\, d\mu  \right| }_{ =0 } \\&\leq\limsup_{ n \to \infty }\left\| g*(f_{n}-f) \right\| _{1}\left\| f_{n} \right\| _{\infty}  \end{align}$$