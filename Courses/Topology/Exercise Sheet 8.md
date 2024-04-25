#Series #Topology 

> [!def] Problem 1
> Let $X:=L^2([0,1])$ with the topology defined by the distance $$d(f,g):=\left( \int_{0}^{1} \left| f-g \right| ^{2} \, dx  \right) ^{1/2}$$
> 1. For $f\in X$ and $\varepsilon>0$, show that the closed ball $$B_{\leq \varepsilon}(f):=\{ g\in X:d(f,g)\leq \varepsilon \}$$ is not compact. (Hint: start with f = 0 and ε = 1, which was an example in the lecture.) 
> 2. Deduce that $X$ is not locally compact, and in fact that there is no $f\in X$ which has any compact neighborhood.
---
> [!def] Problem 2
> Let $(X_{i})_{i\in I}$ be a family of topological spaces and let $$X:=\prod_{i\in I}^{}X_{i}$$ with the product topology. 
> 1. If $X_{i}$ is Hausdorff for all i, prove that X is also Hausdorff. 
> 2. Let $Y_{i}\subseteq X_{i}$ be an arbitrary subset for each $i$. Show that the subspace topology on $$Y:=\prod_{i\in I}^{}Y_{i}\subseteq X$$ is the product of the subspace topologies of $Y_{i}$. 
> 3. Let $Y_{i}\subseteq X_{i}$ be an arbitrary subset for each $i$. Show that $$\overline{\prod_{i\in I}Y_{i}}=\prod_{i\in I}^{}\overline{Y_{i}}$$
> 4. If $C_{i}\subseteq X_{i}$ is closed for all $i$ show that the subset $\prod_{i\in I}^{}C_{i}$ is closed in $X$.
> 5. Give an example of a set $I$, spaces $X_{i}$ and open subsets $U_{i}\subseteq X_{i}$ s.t. $\prod_{i\in I}^{}U_{i}$ is not open in $X$. 
> 6. Let $x_{n}=(x_{n,i})_{i\in I}$ be elements of $X$ for all $n\geq 1$. Show that the sequence $x_{n}\to x=(x_{i})_{i\in I}$ if and only if $x_{n,i}\to x_{i}$ for all $i\in I$.
> 7. For any $x=(x_{i})_{i}$ in $X$, show that the connected component of $X$ is equal to the product of the connected components $Y_{i}$ of $x_{i}$ in $X_{i}$.
---
> [!def] Problem 3
> Let $(X_{n},d_{n})_{n\geq 1}$ be a sequence of metric spaces. Denote $X:=\prod_{n\geq 1}^{}X_{n}$. 
> 1. Show that for $x=(x_{n})_{n}$ and $y=(y_{n})_{n}$ in $X$, the series $$d(x,y):=\sum_{n\geq 1}^{} \frac{1}{2^n}\frac{d_{n}(x_{n},y_{n})}{1+d_{n}(x_{n},y_{n})}$$ is (absolutely) convergent and that the function $d:X\times X\to[0,+\infty)$ defines is a distance on $X$. 
> 2. Show that the topology defined by $d$ is the product topology on $X$. 
> 3. Show that if $X_{n}$ is complete for all $n$, then $X$ is complete. 
> 4. Assume that $X_{n}$ is compact for all $n$. Show that if $x_{m}:=(x_{m,n})_{n\geq 1}$ is an element of $X$ for all $m\geq 1$, then the sequence $(x_{m})_{m\geq 1}$ has a convergent subsequence. 
> 5. Deduce that $X$ is compact without using Tychonov’s Theorem.
---
> [!def] Problem 4
> Let $X_{1}$ and $X_{2}$ be topological spaces and $X=X_{1}\times X_{2}$ with the product topology. 
> 1. Let $Y$ be a topological space and $f:X\to Y$ a continuous map. For any $(x_{1},x_{2})\in X_{1}\times X_{2}$, show that the maps $$\begin{array}{cccc} {f_{x_{2}}:}&{X_{1}}&\to&{Y}\\&{x} &\mapsto & {f(x,x_{2})} \end{array}{},\quad \begin{array}{cccc} {g_{x_{1}}:}&{X_{2}}&\to&{Y}\\&{x} &\mapsto & {f(x_{1},x)} \end{array}{}$$are continuous. 
> 2. Let $X_{1}=X_{2}=\mathbb{R}$ and define $f:X\to \mathbb{R}$ by $$f(x_{1},x_{2}):=\begin{cases}\frac{x_{1}x_{2}}{x_{1}^2+x_{2}^2}&(x_{1},x_{2})\neq(0,0)\\0&(x_{1},x_{2})=(0,0)\end{cases}$$Show that $f_{x_{2}}$ and $g_{x_{1}}$ are all continuous but that $f$ is not continuous. 
> 
> Let $X_{1}=X_{2}=Y=\mathbb{R}$. Assume that the functions $f_{x_{2}}$ and $g_{x_{1}}$ are continuous for all $(x_{1},x_{2})\in \mathbb{R}^2$. Let $(x_{1},x_{2})\in \mathbb{R}^2$ and $y=f(x_{1},x_{2})$. 
> 1. For $\varepsilon>0$, show that there exist $y_{1}<y_{2}$ in $\mathbb{R}$ with $y_{1}<x_{2}<y_{2}$ such that $y-\varepsilon<f(x_{1},x)<y+\varepsilon$ if $y_{1}<x<y_{2}$.
> 2. Let $v_{1}<v_{2}$ be such that $y_{1}<v_{1}<x_{2}<v_{2}<y_{2}$. Show that there exists $\delta>0$ s.t. $y-\varepsilon<f(x,v_{1})<y+\varepsilon$ and $$y-\varepsilon<f(x,v_{2})<y+\varepsilon$$ for $x_{1}-\delta<x<x_{1}+\delta$.
> 3. Assume furthermore that $g_{x_{1}}:\mathbb{R}\to \mathbb{R}$ is non-decreasing for all $x_{1}\in \mathbb{R}$. Deduce that $f$ is continuous.