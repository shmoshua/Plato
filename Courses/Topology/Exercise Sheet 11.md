#Series #Topology 

> [!def] Problem 1
> A topological space $X$ is called ***path-connected*** if, for every $x$ and $y$ in $X$, there exists a path $\gamma:[0,1]\to X$ s.t. $\gamma(0)=x$ and $\gamma(1)=y$.
> 1. Show that if $X$ is path-connected, then it is connected. 
> 2. Show that the relation $\sim$ defined by $x\sim y$ if and only if there exists a path in $X$ from $x\sim y$ is an equivalence relation. 
> 3. Show that the equivalence class of some $x\in X$ for the relation $\sim$ is contained in the connected component of $x\in X$. This equivalence class is called the path-connected component of $x$. 
> 4. We now assume that $X$ is a connected topological manifold. Show that the path-connected component of any $x\in X$ is open. 
> 5. Let $X$ be a contractible space. Show that $X$ is path connected. 

We have:
1. let $x\in X$. Then, for any $y\in X$, there exists a path $\gamma_{y}$ from $x$ to $y$ and as $\gamma_{y}$ is continuous and $[0,1]$ is connected, $\text{im }\gamma_{y}$ is connected. Then, $X=\bigcup_{y\in X}^{}\text{im }\gamma_{y}$ is connected as $x\in \text{im }\gamma_{y}$ for all $y\in X$.
2. we have that $\gamma:[0,1]\to X,t\mapsto x$ is a path from $x$ to $x$ for any $x\in X$. Therefore, $x \sim x$. For $x\sim y$ with a path $\gamma$, $\overline{\gamma}$ is a path from $y$ to $x$. Lastly, for $x\sim y$ and $y\sim z$ with paths $\gamma_{1}$ and $\gamma_{2}$, $\gamma_{1}\gamma_{2}$ is a path from $x$ to $z$.
3. The path-connected component of $X$ is by 1 connected. As the connected component of $x$ is the largest connected set containing $x$, this proves the statement.
4. Let $x\in X$ and $P\subseteq X$ be the path-connected component of $x$. For $p\in P$, let $U$ be the open neighborhood of $p$ and $\varphi:U\to\varphi(U)$ the homeomorphism. Then, for $\varphi(p)$, from normality, there exists $\varepsilon>0$ s.t. $B:=B_{<\varepsilon}(\varphi(p))\subseteq\varphi(U)$ and $B$ is path-connected. As $\varphi$ is a homeomorphism, $\varphi ^{-1}(B)\subseteq U$ is also path-connected and open. Therefore, $\varphi ^{-1}(B)\subseteq P$. This shows that $P$ is open.
5. let $h:X\times[0,1]\to X$ be a homotopy from $\text{id}_{X}$ to a constant map $x_{0}$. Then, for any $x\in X$, $$\begin{array}{cccc} {\gamma_{x}:}&{[0,1]}&\to&{X}\\&{t} &\mapsto & {h(x,t)} \end{array}{}$$is a path from $x$ to $x_{0}$ as $\gamma_{x}(0)=h(x,0)=\text{id}_{X}(x)=x$ and $\gamma_{x}(1)=h(x,1)=x_{0}$. Therefore, $x_{0}$ is path connected with every point $x\in X$. As being path-connected is an equivalence relation, this proves the statement.
---
> [!def] Problem 2
> Let $X$ be the subspace $$C=\{ (0,1) \}\cup \bigcup_{n\geq 1}^{}\left( \left\{  \frac{1}{n}  \right\}\times[0,1] \right)\cup([0,1]\times\{ 0 \})\subseteq \mathbb{R}^{2}$$
> of the plane, with the induced topology. 
> 1. Prove that $C$ is connected. 
> 2. Let $\gamma:[0,1]\to C$ be a path with $\gamma(0)=(0,1)$ and let $Y=\gamma ^{-1}(\{ (0,1) \})$. Show that $Y\subseteq[0,1]$ is closed and not empty. 
> 3. Let $t_{0}\in Y$. Let $\varepsilon>0$ be a real number with $\varepsilon<1/2$ and let $$V:=\{ (x,y)\in C:\left| x \right| +\left| y-1 \right| <\varepsilon \}$$Show that there exist real numbers $a,b$ with $0<a<t_{0}<b<1$ s.t. $\gamma((a,b))\subseteq V$.
> 4. Show that $\gamma((a,b))\subseteq V$ is connected. 
> 5. Deduce that $\gamma((a,b))=\{ (0,1) \}$
> 6. Deduce that $Y$ is open in $[0,1]$. 
> 7. Conclude that $C$ is not path-connected.

We have that:
1. Firstly, one can easily show that $C \backslash \{ (0,1) \}$ is connected. Indeed, $(\{ 1 / n \}\times[0,1])\cup([0,1]\times \{ 0 \})$ is connected as they share a point $(1/n, 0)$ and $C\backslash\{ (0,1) \}$ is a union of all such connected components with $[0,1]\times \{ 0 \}$ as intersection. 
   
   Let $U_{1}\sqcup U_{2}=C$ be open sets in $C$ with $(0,1)\in U_{1}$ wlog. As $U_{1}$ is open, $U_{1}\cap (C \backslash \{ (0,1) \})\neq \varnothing$ and by connectedness of $C \backslash\{ (0,1) \}$, $U_{2}\cap C\backslash\{ (0,1) \}=\varnothing$. However, as $(0,1)\in U_{1}$, $U_{2}\cap C=\varnothing$. This shows the statement.
2. $Y$ is not empty as $0\in Y$. We also know that $\{ (0,1) \}$ is closed in $C$. Therefore, $Y$ is closed by continuity.
3. We see that $V=B_{<\varepsilon}((0,1))\cap C$ where the ball is with respect to the norm $\|(x,y)\|:=\left| x \right|+\left| y \right|$. Therefore, $V$ is open as a continuous preimage of an open set in $C$ and $\gamma ^{-1}(V)$ is open in $[0,1]$. Assume that $t_{0}\in Y$ and $t_{0}\neq 0$. Then, as $(0,1)\in V$, $t_{0}\in \gamma ^{-1}(V)$ and there exists $\varepsilon>0$ s.t. $(t_{0}-\varepsilon,t_{0}+\varepsilon)\subseteq\gamma ^{-1}(V)$ and $0<t_{0}-\varepsilon$. This proves the statement.
4. $(a,b)$ is connected and $\gamma$ is continuous.
5. We show that the connected component of $(0,1)$ in $V$ is $\{ (0,1) \}$. Let $C_{(0,1)}$ be the connected component of $(0,1)$ and assume there was another point $p\in C_{(0,1)}\subseteq V$. As $\varepsilon< 1/2$, we have that $p=(1 / n,z)$ for some $n\geq 2$. Then, it is easy to see that $C_{(0,1)}$ is not connected by splitting it at $\frac{1}{n+1}<k< \frac{1}{n}$ into two disjoint non-empty open subsets. Therefore, $C_{(0,1)}=\{ (0,1) \}$ and as $\gamma(t_{0})=(0,1)$ and $\gamma((a,b))$ is connected, $(0,1)\in\gamma((a,b))\subseteq C_{(0,1)}=\{ (0,1) \}$, which proves the statement.
6. For any $t_{0}\in Y$, we have found an open neighborhood 