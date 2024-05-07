#Definition #Topology 

> [!definition]
> Let $X$ be a topological group and $x\in X$. The ***fundamental group*** of $X$ at $x$ is a [[group]] $\Lambda_{x,x}$, where for $x,y\in X$, $\Lambda_{x,y}$ denotes the set of [[Path|path homotopy]] classes of paths from $x$ to $y$ on $X$.
- **Notation**: The fundamental group of $X$ at $x$ is also denoted as $\pi_{1}(X,x)$.
- **Related definition**: For $x\in X$, let $\varepsilon_{x}:[0,1]\to X, t\mapsto x$ be the constant path at $x$.
---
##### Properties
> [!lemma] Proposition 1
> We have for $\gamma\in \Lambda_{x,y}$
> 1. $\gamma_{0}(\gamma_{1}\gamma_{2})=(\gamma_{0}\gamma_{1})\gamma_{2}$ for $\gamma_{0}\in \Lambda_{x,y},\gamma_{1}\in \Lambda_{y,z},\gamma_{2}\in \Lambda_{z,w}$.
> 2. $\varepsilon_{x}\gamma=\gamma$, $\gamma \varepsilon_{y}=\gamma$
> 4. $\gamma\overline{\gamma}=\varepsilon_{x}$, $\overline{\gamma}\gamma=\varepsilon_{y}$

> [!proof]+
> We have: 
> 1. Assuming $\gamma_{0},\gamma_{1},\gamma_{2}$ are actual paths, $$\gamma_{0}(\gamma_{1}\gamma_{2})(t)=\begin{cases}\gamma_{0}(2t)&0\leq t\leq \frac{1}{2}\\\gamma_{1}(4t-2)& \frac{1}{2}\leq t\leq \frac{3}{4}\\\gamma_{2}(4t-3)& \frac{3}{4}\leq t\leq 1\end{cases}$$and $$(\gamma_{0}\gamma_{1})\gamma_{2}(t)=\begin{cases}\gamma_{0}(4t)&0 \leq t\leq \frac{1}{4}\\\gamma_{1}(4t-1)& \frac{1}{4}\leq t\leq \frac{1}{2}\\\gamma_{2}(2t-1)& \frac{1}{2}\leq t\leq 1\end{cases}$$Consider the homotopy: $$h(t,s):=\begin{cases}\gamma_{0}\left( \frac{4t}{s+1} \right)&0\leq t\leq \frac{s+1}{4}\\\gamma_{1}(4t-s-1)& \frac{s+1}{4}\leq t\leq \frac{s+2}{4}\\\gamma_{2}\left( \frac{4t-s-2}{2-s} \right)& \frac{s+2}{4}\leq t\leq 1\end{cases}$$Then, $h(0,s)=\gamma_{0}(0)=x$ and $h(1,s)=\gamma_{2}(1)=w$. As $h$ is continuous, it is a path-homotopy and $$h(t,0)=(\gamma_{0}\gamma_{1})\gamma_{2}(t), \quad h(t,1)=\gamma_{0}(\gamma_{1}\gamma_{2})(t)$$
> 2. We have that: $$\varepsilon_{x}\gamma(t)=\begin{cases}x&0\leq t\leq \frac{1}{2}\\\gamma(2t-1)& \frac{1}{2}\leq t\leq 1\end{cases}$$with homotopy: $$h(t,s)=\begin{cases}x&0\leq t\leq \frac{1 -s}{2}\\\gamma\left(  \frac{2}{1+s}t+1 -\frac{2}{1+s} \right)& \frac{1-s}{2}\leq t\leq 1\end{cases}$$Then, $h(0,s)=x, h(1,s)=\gamma(1)$ with $h(t,0)=\varepsilon_{x}\gamma(t)$ and $h(t,1)=\gamma(t)$.
>    
>    Similarly, it holds for $\gamma \varepsilon_{y}=\gamma$.
> 3. We have: $$\gamma\overline{\gamma}(t)=\begin{cases}\gamma(2t)&0\leq t \leq \frac{1}{2}\\\gamma(2-2t)& \frac{1}{2}\leq t\leq 1\end{cases}$$Then, $$h(t,s):=\begin{cases}\gamma(2st)&0\leq t\leq 1 /2\\\gamma(2s(1-t))& 1/\end{cases}$$

- **Corollary**: $\Lambda_{x,x}$ is indeed a group with path composition and path inversion.