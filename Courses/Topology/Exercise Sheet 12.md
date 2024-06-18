#Series #Topology 

> [!def] Problem 1
> Let $X\subseteq \mathbb{R}^{2}$ be the union of the circles $C_{n}$ with radius $\frac{1}{n}$ centered at $\left( \frac{1}{n},0 \right)$ for all $n\geq 1$. Each of them passes by the origin $(0,0)$, and we let $x_{0}:=(0,0)\in X$. The goal of this exercise is to prove that $\pi_{1}(X,x_{0})$ is an uncountable group (where $X$ has the subspace topology from $\mathbb{R}^{2}$)
> 1. Show that $X$ is path-connected.
> 2. Show that if $U$ is a neighborhood of $x_{0}$, then there exists $N$ s.t. $C_{n}\subseteq U$ for all $n\geq N$.
> 3. Let $n\geq 1$ be an integer. Show that the map $r_{n}:X\to C_{n}$ s.t. $$r_{n}(x)=\begin{cases}x&x\in C_{n}\\x_{0}&x\notin C_{n}\end{cases}$$is continuous.
> 4. Show that the induced map $r_{n*}:\pi_{1}(X,x_{0})\to \pi_{1}(C_{n},x_{0})$ is surjective. 
> 5. For $n\geq 1$, let $\gamma_{n}:[0,1]\to C_{n}$ be a loop at $x_{0}$ on $C_{n}$. Define $\gamma:[0,1]\to X$ by $$\gamma(t)=\gamma_{n}\left( n(n+1)\left( t-1+\frac{1}{n} \right)  \right) $$with $n$ s.t. $1-\frac{1}{n}\leq t<1 -\frac{1}{n+1}$ and $\gamma(1)=x_{0}$. Show that $\gamma$ is a well-defined continuous loop at $x_{0}$. 
> 6. Show that the class of $r_{n*}(\gamma)$ in $\pi_{1}(C_{n},x_{0})$ is the class of $\gamma_{n}$ in $\pi_{1}(C_{n},x_{0})$ for all $n\geq 1$. 
> 7. Conclude that there is a surjective group morphism $\pi_{1}(X,x_{0})\to \prod_{n}^{}\pi_{1}(C_{n},x_{0})$, and that $\pi_{1}(X,x_{0})$ is uncountable.

We have:
1. For any $x\in X$ let $n_{x}$ be the number s.t. $x\in C_{n_{x}}$. Then, for $x,y\in X$, there is a path from $x$ to $x_{0}$ on $C_{n_{x}}$ and $x_{0}$ to $y$ on $C_{n_{y}}$. This proves the statement.
2. Let $U$ be an open neighborhood of $x_{0}$. Then, there exists $B_{<\varepsilon}(0)\cap X\subseteq U$. Let $N\geq 1$ s.t. $\frac{2}{N}<\varepsilon$. It follows that for all $n\geq N$, $x\in C_{n}$, $$\left| x \right| \leq \left| x-\left( \frac{1}{n},0 \right) \right| +\frac{1}{n}=\frac{2}{n}<\varepsilon$$Therefore, $C_{n}\subseteq B_{<\varepsilon}(0)\cap X\subseteq U$.
3. Let $U\subseteq C_{n}$ be open. If $x_{0}\notin U$. Then, $r^{-1}_{n}(U)=U$. Otherwise, $r^{-1}_{n}(U)=U\cup(X \backslash C_{n})$, which is open.
4. $C_{n}$ is a retract of $X$. Therefore, $r_{n}\circ i:C_{n}\hookrightarrow X\to C_{n}$ is the identity. Therefore, $$(r_{n*}\circ i_{*}):\pi_{1}(C_{n},x_{0})\hookrightarrow \pi_{1}(X,x_{0})\to\pi_{1}(C_{n},x_{0})$$and the last arrow is surjective.
5. It is well-defined as for any $t$ there exists exactly one $n$ and $\gamma(0)=\gamma_{1}(0)=x_{0}=\gamma(1)$. To show the continuity, it is first continuous in $[0,1)$ as each "segment" is the continuous rescaling of continuous loops. Further, $\gamma\left( 1-\frac{1}{n} \right)=\gamma_{n}(0)=x_{0}$ and $\gamma_{n}\left( n(n+1)\left( 1-\frac{1}{n+1}  -1+\frac{1}{n}\right)\right)=\gamma_{n}(1)=x_{0}$. Finally, it is also continuous at $t=1$ as for any neighborhood of $x_{0}$, there exists $N$ s.t. $C_{n}\subseteq U$ with $n\geq N$. Therefore, $(t,1]$ is in the preimage where $1-\frac{1}{N}<t$. 
6. We have that $r_{n*}(\gamma)=r_{n}\circ \gamma=\varepsilon_{x_{0}}\gamma_{n}\varepsilon_{x_{0}}=\gamma_{n}$.
7. For $\gamma_{n}\in \pi_{1}(C_{n},x_{0})$, we can define $\gamma$ as follows and the morphism is given as $(r_{n*})_{n}$ componentwise. As $\pi_{1}(C_{n},x_{0})\cong \mathbb{Z}$, we have that $\pi_{1}(X,x_{0})$ is uncountable.
---
> [!def] Problem 2
> Let $X$ be a topological space and $x_{0}\in X$. Let $(U_{i})_{i\in I}$ be open sets in $X$, all containing $x_{0}$, such that $X$ is the union of the $U_{i}$’s and $U_{i}\cap U_{j}$ is path-connected for all $i$ and $j$ in $I$. 
> 1. Let $\gamma:[0,1]\to X$ be a loop at $x_{0}$. Show that there exists an integer $m\geq 1$ and real numbers $$t_{0}=0<t_{1}<\dots<t_{m-1}<t_{m}=1$$ s.t. for $0\leq k<m$, the subset $\gamma([t_{k},t_{k+1}])$ is contained in $U_{i(k)}$ for some $i(k)\in I$. 
> 2. Show that there exist loops $\gamma_{k}$ at $x_{0}$ for  $1\leq k\leq m$ s.t.$$\gamma \sim_{p}\gamma_{1}\dots\gamma_{m}$$and moreover $\gamma _k([0,1])\subseteq U_{i(k)}$, where $\sim_{p}$ is the relation of path-homotopy. 
> 3. If $\pi_{1}(U_{i},x_{0})=\{ \varepsilon_{x_{0}} \}$ for all $i$, deduce that $\pi_{1}(X,x_{0})=\{ \varepsilon_{x_{0}} \}$.

We have:
1. Let us define: $$D:=\{ \delta\in [0,1]: \exists m:0=t_{0}<t_{1}<\dots<t_{m}=\delta \text{ with the property as above} \}$$we need to show that $D=[0,1]$. It suffices to show that $D$ is clopen. To show that $D$ is non-empty and open, let $t\in D$ with $\gamma(t)\in U_{i}$. Then, there exists $\varepsilon>0$ s.t. $\gamma([t,t+2\varepsilon))\subseteq U_{i}$ by the continuity of $\gamma$. This shows that $D$ is open. 
2. 