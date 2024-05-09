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
3. We see that $V=B_{<\varepsilon}((0,1))\cap C$ where the ball is with respect to the norm $\|(x,y)\|:=\left| x \right|+\left| y \right|$. Therefore, $V$ is open as a continuous preimage of an open set in $C$ and $\gamma ^{-1}(V)$ is open in $[0,1]$. Assume that $t_{0}\in Y$. Then, as $(0,1)\in V$, $t_{0}\in \gamma ^{-1}(V)$ and there exists $a,b\in \mathbb{R}$ s.t. $t_{0}\in(a,b)\cap[0,1]\subseteq \gamma ^{-1}(V)$. Therefore, $\gamma((a,b)\cap[0,1])\subseteq V$.
4. $(a,b)\cap[0,1]$ is connected and $\gamma$ is continuous. Therefore, $\gamma((a,b)\cap[0,1])$ is connected.
5. We show that the connected component of $(0,1)$ in $V$ is $\{ (0,1) \}$. Let $C_{(0,1)}$ be the connected component of $(0,1)$ and assume there was another point $p\in C_{(0,1)}\subseteq V$. As $\varepsilon< 1/2$, we have that $p=(1 / n,z)$ for some $n\geq 2$. Then, it is easy to see that $C_{(0,1)}$ is not connected by splitting it at $\frac{1}{n+1}<k< \frac{1}{n}$ into two disjoint non-empty open subsets. Therefore, $C_{(0,1)}=\{ (0,1) \}$ and as $\gamma(t_{0})=(0,1)$ and $\gamma((a,b)\cap[0,1])$ is connected, $(0,1)\in\gamma((a,b)\cap[0,1])\subseteq C_{(0,1)}=\{ (0,1) \}$, which proves the statement.
6. For any $t_{0}\in Y$, we have found an open neighborhood $U$ of $t_{0}$ in $[0,1]$ s.t. $U\subseteq Y$. Therefore, $Y$ is open in $[0,1]$. 
7. As $[0,1]$ is connected and $Y\subseteq[0,1]$ is both open and closed, $Y=[0,1]$. Therefore, there cannot be a path $\gamma$ from $(0,1)$ to any other point.
---
> [!def] Problem 3
> Let $X$ and $Y$ be topological spaces. A continuous map $f:X\to Y$ is called a homotopy equivalence if there exists a continuous map $g:Y\to X$ such that $f\circ g$ is homotopic to $\text{id}_{Y}$ and $g\circ f$ is homotopic to $\text{id}_{X}$. If there exists a homotopy equivalence from $X$ to $Y$, then $X$ and $Y$ are said to have the same homotopy type.
> 1. Show that the relation ”$X$ has the same homotopy type as $Y$” is an equivalence relation on topological spaces.
> 2. If $f:X\to Y$ is a homotopy equivalence, show that the homotopy class in $[Y,X]$ of a map $g:Y\to X$ s.t. $f\circ g \sim \text{id}_{Y}$ and $g\circ f \sim \text{id}_{X}$ is unique. This class is called the homotopy inverse of $f$.
> 3. Show that if $f:X\to Y$ is a homotopy equivalence with homotopy inverse $g$ and $f':Y\to Z$ is a homotopy equivalence with homotopy inverse $g'$, then $f'\circ f$ is a homotopy equivalence, with homotopy inverse $g\circ g'$.
> 4. Show that $X$ has the same homotopy type as a one-point space $\{ x_{0} \}$ if and only if $X$ is contractible.
> 5. Show that if $X$ has the same homotopy type as a point, then for any space $Y$, any continuous map $Y\to X$ is homotopic to a constant map, and any continuous map $X\to Y$ is homotopic to a constant map.

We have:
1. For topological space $X$, $\text{id}_{X}:X\to X$ is a homotopy equivalence. For $X$ with the same homotopy type as $Y$ with homotopy equivalence $f$, there exists $g$ by definition for which $g$ is a homotopy equivalence and $Y$ has the same homotopy type as $X$. Lastly, let $f:X\to Y$ and $f':Y\to Z$ be homotopic equivalences with $g,g'$ respectively. Then, consider $f'\circ f:X\to Z$ and $g\circ g':Z\to X$. We have that: $$\begin{array}{cccc} {h_{Z}:}&{Z\times[0,1]}&\to&{Z}\\&{(z,t)} &\mapsto & {f'(h_{f\circ g}(g'(z),t))} \end{array}{}$$is a homotopy from $f'\circ f\circ g\circ g'$ to $f'\circ g'$, where $h_{f\circ g}$ is the homotopy from $f\circ g$ to $\text{id}_{Y}$. As homotopies form an equivalence relation, $f'\circ f\circ g\circ g'$ is homotopic to $\text{id}_{Z}$. By symmetry, $X$ has the same homotopy type as $Z$.
2. Let $g,h:Y\to X$ s.t. $f\circ g \sim \text{id}_{Y}$, $g\circ f\sim \text{id}_{X}$, $f\circ h\sim \text{id}_{Y}$ and $h\circ f\sim \text{id}_{X}$. Then, $$g=g\circ \text{id}_{Y}\sim g\circ f\circ h\sim \text{id}_{X}\circ h=h$$This proves the statement.
3. Shown in 1. 
4. Let $X$ have the same homotopy type as $\{ x_{0} \}$ and $f:X\to \{ x_{0} \}$ be the homotopy equivalence with homotopy inverse $g$ s.t. $f \circ g\sim \text{id}_{\{ x_{0} \}}$ and $g\circ f\sim \text{id}_{X}$. Then, $g\circ f:X\to X$ is a constant function homotopic to $\text{id}_{X}$ and $X$ is contractible. 
   
   Conversely, assume $X$ is contractible and let $f:X\to X$ be the constant function homotopic to $\text{id}_{X}$ with $\text{Im }f=\{ x \}$. Then, we can define a constant functions $f':X\to \{ x_{0} \}$ and $g':\{ x_{0} \}\to X, x_{0}\mapsto x$ s.t. $g'\circ f'=f$. Finally, $f'\circ g'(x_{0})=x_{0}$ and we have that $f'\circ g'\sim \text{id}_{\{ x_{0} \}}$ from reflexivity.
5. Let $X$ have the same homotopy type as $\{ x_{0} \}$, then $X$ is contractible and there exists a constant map $f:X\to X$ s.t. $f\sim \text{id}_{X}$. Then, for any continuous $\varphi:Y\to X$, $\varphi=\text{id}_{X}\circ\varphi \sim f\circ\varphi$ which is a constant map. Similarly, for any continuous $\varphi:X\to Y$, $\varphi=\varphi \circ\text{id}_{X}\sim\varphi \circ f$, which is a constant map.
---
> [!def] Problem 4
> A subspace $Y$ of a topological space $X$ is called a ***retract*** of $X$ if there exists a continuous map $r:X\to Y$ such that $r(y)=y$ for all $y\in Y$. 
> 1. If $Y$ is a retract of $X$ and $y_{0}\in Y$, show that the group morphism $$\pi_{1}(Y,y_{0})\to \pi_{1}(X,y_{0})$$induced by the inclusion $Y\to X$ is injective. 
> 2. For $n\geq 1$, show that $$S_{n-1}:=\{ x\in \mathbb{R}^n:\|x\|=1 \}$$is a retract of $\mathbb{R}^n \backslash\{ 0 \}$. 
> 3. Show that the fundamental group of $\mathbb{R}^2\backslash\{ 0 \}$ is not trivial. 
> 4. Show that $S_{1}$ is not a retract of $\mathbb{R}^2$. 

We have:
1. let $\gamma$ and $\gamma'$ be two paths from $y_{0}$ to $y_{0}$ on $Y$. Assume that $\gamma$ and $\gamma'$ are path-homotopic on $X$, i.e. there exists $h:[0,1]\times[0,1]\to X$ s.t. $h(x,0)=\gamma(x), h(x,1)=\gamma'(x)$ and $h(0,t)$ and $h(1,t)$ are constant. Then, $r\circ h$ is a path homotopy from $\gamma$ to $\gamma'$ as $r(h(x,0))=r(\gamma(x))=\gamma(x)$ and $r(h(x,1))=r(\gamma'(x))=\gamma'(x)$. This shows that $\gamma \sim_{p}\gamma'$.
2. Let us define: $$\begin{array}{cccc} {r:}&{\mathbb{R}^n\backslash\{ 0 \}}&\to&{S_{n-1}}\\&{x} &\mapsto & {x / \|x\|} \end{array}{}$$Then, for all $x\in S_{n-1}$, $\|r(x)\|=1$ and $r(x)\in S_{n-1}$. The continuity follows from that of the norm. 
3. For simplicity, we borrow notations from complex numbers and treat $\mathbb{R}^{2}$ as $\mathbb{C}$. Let $x\in S_{1}$. By composing with rotation, we may assume that $x=1$. Let $\gamma:[0,1]\to S_{n-1},t\mapsto \exp(2\pi it)$. We will show that $\gamma$ is not path-homotopic to $\varepsilon_{1}$, the constant path at $1$. Assume that $\gamma \sim \varepsilon_{1}$. Then, consider the following: $$\begin{array}{cccc} {\varphi:}&{X}&\to&{[0,1]}\\&{\exp(2\pi it)} &\mapsto & {t\mod 1} \end{array}{}$$From analysis, this map is continuous and therefore, $\gamma \circ\varphi \sim\gamma \circ \varepsilon_{1}$ where $\gamma \circ\varphi=\text{id}_{S_{1}}$ and $\gamma \circ \varepsilon_{1}$ is constant. Therefore, $S_{1}$ is contractable, which is a contradiction. Then, by injectivity of the group morphism in 1, the fundamental group at $1$ on $\mathbb{R}^2\backslash\{ 0 \}$ is not trivial. 
4. Assume that it is. Then, it is a contradiction to 1, as the fundamental group of $\mathbb{R}^{2}$ is trivial. Therefore, there cannot be such injection. 
---
> [!def] Problem 5
> Let $D=\{ z\in \mathbb{C}:\left| z \right|\leq 1 \}$ be the unit disc in $\mathbb{C}$. Let $f:D\to D$ be a continuous map. We assume that $f(z)\neq z$ for all $z\in D$. 
> 1. Show that there is a well-defined map $g:D\to S_{1}$ which maps $z$ to the intersection point of the line joining  $z$ and $f(z)$ with $S_{1}$. 
> 2. Show that $g$ is continuous. 
> 3. Deduce a contradiction and conclude that there must exist a fixed point of $f$.

We have:
1. let $z\in D$. Then, $g(z)$ is the intersection of the half-line from $f(z)$ passing through $z$ and $S_{1}$. As $f(z)\in D$ and $f(z)\neq z$, such an intersection point always exists.
2. Let $z\in D$ and $\varepsilon>0$. Then, $$\left| g(z)-g(y) \right| <$$