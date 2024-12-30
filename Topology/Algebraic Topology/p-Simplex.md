> [!definition]
> Let $\mathbb{R}^\infty:=\bigoplus_{i\geq 0}\mathbb{R}$ be the direct sum. Let $X$ be a [[topological space]]. Then,
> 1. The ***standard $p$-simplex*** is given as: $$\Delta_{p}:=\left\{  \sum_{i=0}^{p}\lambda_{i}e_{i}: \lambda_{i}\geq 0,\sum_{i=0}^{p}\lambda_{i}=1  \right\}=\text{ConvexHull}(e_{0},\dots,e_{p})$$endowed with the [[subspace topology]] from $\mathbb{R}^{p+1}$.
> 2. A ***singular $p$-simplex*** in $X$ is a continuous map $\sigma:\Delta_{p}\to X$.
> 3. A ***singular $p$-chain*** in $X$ is a finite formal sum of singular $p$-simplices. $S_{p}(X)$ denotes the group of singular $p$-chains (or equivalently, the free abelian group of singular $p$-simplices)

^702d30

- **Related definition**: For $v_{0},\dots,v_{p}\in \mathbb{R}^\infty$,  ^a6188b
	1. the ***affine $p$-simplex*** is a map $[v_{0},\dots,v_{p}]:\Delta_{p}\to \mathbb{R}^\infty,\sum_{i=0}^{p}\lambda_{i}e_{i}\mapsto \sum_{i=0}^{p}\lambda_{i}v_{i}$.
	2. the ***$i$-th face map*** $F_{i}^p:=[e_{1},\dots,\widehat{e_{i}},\dots,e_{p}]:\Delta_{p-1}\hookrightarrow \Delta_{p}$
	3. the ***$i$-th face map of a singular $p$-simplex*** $\sigma$, is $\sigma^{(i)}:=\sigma \circ F_{i}^p:\Delta_{p-1}\to X$
	4. the ***boundary of a singular $p$-simplex*** $\sigma$, $$\partial_{p}\sigma:=\sum_{i=0}^{p}(-1)^i\sigma^{(i)}$$
	5. the ***boundary operator*** is then given by linearly extending the boundary for simplices: $\partial_{p}:S_{p}(X)\to S_{p-1}(X)$.
	6. for a continuous map $f:X\to Y$, $f_{c}:S_{p}(X)\to S_{p}(Y)$ is a homomorphism defined as: $f_{c}\left( \sum_{\sigma}^{}n_{\sigma}\cdot\sigma \right)=\sum_{\sigma}^{}n_{\sigma}(f\circ\sigma)$.
- **Related definition**: For all $p<0$, we define $S_{p}(X):= 0$. For all $p\leq 0$, we define $\partial_{p}:=0$. ^2c4bf0
- **Related definition**: We denote that: ^ff8cc1
	1. $Z_{p}(X):=\text{ker }\partial_{p}\leq S_{p}(X)$ is the **$p$-cycles**.
	2. $B_{p}(X):=\text{im }\partial_{p+1}\leq S_{p}(X)$ is the **$p$-boundaries**
	3. $H_{p}(X):= Z_{p}(X) / B_{p}(X)$ is the **$p$-homology**.
	4. $c_{1},c_{2}\in Z_{p}(X)$ are ***homologous***, if $[c_{1}]=[c_{2}]\in H_{p}(X)$.
---
##### Properties
> [!lemma] Proposition 1
> For all $x\in \Delta_{p}$, 
> 1. the barycentric coordinates $\lambda_{i}$ are unique.
> 2. for any $v_{0},\dots,v_{p}\in \mathbb{R}^\infty$, $[v_{0},\dots,v_{p}]$ is continuous.
> 3. $F^p_{i}\left( \sum_{k=0}^{p-1}\lambda_{k}e_{k} \right)=\sum_{k=0}^{i-1}\lambda_{k}e_{k}+\sum_{k=i}^{p-1}\lambda_{k}e_{k+1}$
> 4. $F^{p+1}_{j}\circ F_{i}^p=F_{i+1}^{p+1}\circ F_{j}^p$ if $j\leq i$.
> 5. We have that: $$F_{j}^{p+1}\circ F_{i}^p=\begin{cases}[e_{0},\dots,\widehat{e_{i}},\dots,\widehat{e_{j}},\dots,e_{p}]&i<j\\ [e_{0},\dots,\widehat{e_{j}},\dots,\widehat{e_{i+1}},\dots,e_{p}]&j\leq i\end{cases}$$

^f65700

> [!proof]-
> We have that:
> 1. Assume we have $\lambda_{i}$ and $\xi_{i}$ both barycentric coordinates. Then, $$\sum_{i=0}^{p}(\lambda_{i}-\xi_{i})e_{i}=0$$Then, from linear independence, $\lambda_{i}=\xi_{i}$ for all $i\in[p]$.
> 2. Obvious.
> 3. By construction.
> 4. We have that: $$\begin{align}F^{p+1}_{j}\left( F_{i}^p\left( \sum_{k=0}^{p-1}\lambda_{k}e_{k} \right) \right)&=F^{p+1}_{j}\left( \sum_{k=0}^{i-1}\lambda_{k}e_{k}+\sum_{k=i}^{p-1}\lambda_{k}e_{k+1}\right)\\&=\sum_{k=0}^{j-1}\lambda_{k}e_{k}+\sum_{k=j}^{i-1}\lambda_{k}e_{k+1}+\sum_{k=i}^{p-1}\lambda_{k}e_{k+2}\\&\end{align}$$$$F_{i+1}^{p+1}\left( F_{j}^p\left( \sum_{k=0}^{p-1}\lambda_{k}e_{k} \right)  \right) =F^{p+1}_{i+1}\left( \sum_{k=0}^{} \right) $$
> 5. From 3 and 4.

^21d685

---
> [!lemma] Lemma 2 (Boundary Lemma)
> We have that:
> 1. $\partial_{p}\circ\partial_{p+1}=0$, i.e. $B_{p}(X)\unlhd Z_{p}(X)$

^71f3bb

> [!proof]-
> We have that:
> 1. it suffices to show that $\partial_{p}(\partial_{p+1}(\sigma))=0$ for all singular $(p+1)$-simplex $\sigma$. We have that: $$\begin{align}\partial_{p}(\partial_{p+1}(\sigma))&=\partial_{p}\left( \sum_{j=0}^{p+1}(-1)^j \sigma \circ F^{p+1}_{j}\right) =\sum_{j=0}^{p+1}(-1)^j\sum_{i=0}^{p}(-1)^i\sigma \circ F^{p+1}_{j}\circ F^p_{i}\\&=\sum_{0\leq i < j\leq p+1}^{}(-1)^{i+j}\sigma \circ F^{p+1}_{j}\circ F^p_{i}+\sum_{0\leq j\leq i\leq p}^{}(-1)^{i+j}\sigma \circ \underbrace{ F^{p+1}_{j}\circ F^p_{i} }_{ =F_{i+1}^{p+1}\circ F_{j}^p }\\&=\sum_{0\leq i < j\leq p+1}^{}(-1)^{i+j}\sigma \circ F^{p+1}_{j}\circ F^p_{i}+\sum_{0\leq j< i'\leq p+1}^{}(-1)^{i'+j-1}\sigma \circ F_{i'}^{p+1}\circ F_{j}^p\\&=0\end{align}$$


^bbbdc3

---
> [!lemma] Theorem 3 (Functoriality)
> Let $f:X\to Y$ and $g:Y\to Z$ be continuous. Then,
>  1. $f_{c}\circ \partial_{p}=\partial_{p}\circ f_{c}$.
>  2. $f_{c}(Z_{p}(X))\subseteq Z_{p}(Y)$.
>  3. $f_{c}(B_{p}(X))\subseteq B_{p}(Y)$.
>  4. $f_{*}:H_{p}(X)\to H_{p}(Y),[a]\mapsto [f_{c}(a)]$ is a group homomorphism.
>  5. $(g\circ f)_{*}=g_{*}\circ f_{*}$
>  6. $\text{id}_{*}=\text{id}_{H_{p}(X)}$
>  7. if $f$ is a homeomorphism, then $f_{*}$ is a group isomorphism.

^5b9b18

> [!proof]-
> We have:
> 1. Let $\sigma$ be a singular $p$-simplex in $X$. Then, $$f_{c}(\partial_{p}(\sigma))=f_{c}\left( \sum_{i=0}^{p}(-1)^i\sigma \circ F^p_{i} \right) =\sum_{i=0}^{p}(-1)^if\circ \sigma \circ F_{i}^p=\partial_{p}(f\circ \sigma)=\partial_{p}(f_{c}(\sigma))$$
> 2. If $a\in Z_{p}(X)$, then $\partial_{p}(f_{c}(a))=f_{c}(\partial_{p}a)=f_c(0)=0$. Hence, $f_{c}(a)\in Z_{p}(Y)$.
> 3. If $a\in B_{p}(X)$, then there exists $a'\in S_{p+1}(X)$ with $\partial_{p+1}(a')=a$. Hence,$$\partial_{p+1}(f_{c}(a'))=f_{c}(\partial_{p+1}(a'))=f_{c}(a)$$ Hence, $f_{c}(a)\in B_{p}(Y)$.
> 4. We have that $f_{*}$ is well-defined. Indeed, if $a,a'\in Z_{p}(X)$ with $[a]=[a']$, then, $a-a'\in B_{p}(X)$ and $f_{c}(a)-f_{c}(a')\in B_{p}(Y)$ by 3. Further, $$f_{*}([a]+[b])=f_{*}([a+b])=[f_{c}(a+b)]=[f_{c}(a)]+[f_{c}(b)]$$
> 5. Let $a\in Z_{p}(X)$. Then, $$ (g\circ f)_{*}([a])=[(g\circ f)_{c}(a)]=[g\circ f\circ a]=g_{*}([f\circ a])=g_{*}(f_{*}([a]))$$
> 6. Similarly, $\text{id}_{*}([a])=[a]$.
> 7. Follows from 4,5,6 and the fact that $f\circ f^{-1}=\text{id}_{Y}$ and $f^{-1}\circ f=\text{id}_{X}$. 

^a0e972

---
> [!lemma] Theorem 4
> Let $X\neq \varnothing$ and $X=\bigsqcup_{\alpha}^{}X_{\alpha}$ are the path-connected components of $X$. Then, for all $p\in \mathbb{Z}$, $$H_{p}(X)\cong \bigoplus_{\alpha}H_{p}(X_{\alpha}) $$

^c93e58

> [!proof]-
> As a singular simplex $\sigma:\Delta_{p}\to X$ always has a path-connected image, we have that $S_{n}(X):=\bigoplus_{\alpha}S_{n}(X_{\alpha})$, which is also preserved by $\partial$. Hence, the homology groups also split. 

^c9a19c

---
> [!lemma] Lemma 5 
> Let $f,g:I\to X$ be two paths with $f(1)=g(0)$. Then, 
> 1. $f*g-f-g\in S_{1}(X)$ is a boundary.
> 2. a constant path $c:I\to X$ is a boundary.
> 3. $f+f^{-1}$ is a boundary.

^0b9390

> [!proof]-
> We have that:
> 1. Let $c:=f*g-f-g$. We first define a singular $2$-simplex $\sigma:\Delta_{2}\to X$ as follows: 
>    ```tikz
>    \usepackage{tikz}
>    \usetikzlibrary{decorations.markings}
>    \newcommand{\midarrow}{\tikz \draw[-triangle 90] (0,0) -- +(.1,0);}
>    \begin{document}
>    \begin{tikzpicture}
>    \begin{scope}[very thick,decoration={markings,mark=at position 0.55 with {\arrow{>}}}] 
>    \draw[postaction={decorate}] (0,-1)--(1.73,0);
>    \draw[postaction={decorate}] (1.73,0)--(0,1);
>    \end{scope}
>    
>    \tikzset{edge/.style = {->,> = latex'}}
>    \path[draw, ultra thick] (0,1) node[anchor=east]{$e_{2}$}
>    -- (0,-1)  node[anchor=east] {$e_{0}$}
>    --node[below right]{$f$} (1.73,0) node[anchor=west]{$e_{1}$}
>    --node[above right]{$g$} cycle;
>    \path[clip] (0,1) -- (0,-1) -- (1.73,0) -- cycle; 
>    \foreach \y in{-1,-0.9,...,1}
> 	   \draw (0,\y) -- (10,\y);
>    
>    \node (a) at  (0,1) {};
>    \node (b) at  (0,-1) {};
>    \node (c) at  (1.73,0) {};
>    
>    
>    \end{tikzpicture}
>    \end{document} 
>    ```
>    
>    where on every horizontal line in the triangle, $\sigma$ is constant. Then, $\sigma$ is continuous and we also have that $\sigma|_{e_{0} e_{2}}=f*g$. Hence, 
>    $$\partial \sigma=\sigma|_{e_{1}e_{2}}-\sigma|_{e_{0}e_{2}}+ \sigma|_{e_{0}e_{1}}=g-f*g+f=-c$$ is a boundary. Hence, $c$ is a boundary.
> 2. Let $\sigma:\Delta_{2}\to X$ be the constant $2$-simplex s.t. $\sigma(\Delta_{2})=c(I)$. Then, $$\partial\sigma=c-c+c=c$$
> 3. Let $\sigma:\Delta_{2}\to X$ defined as follows:
>    ```tikz
>    \usepackage{tikz}
>    \usetikzlibrary{decorations.markings}
>    \newcommand{\midarrow}{\tikz \draw[-triangle 90] (0,0) -- +(.1,0);}
>    \begin{document}
>    \begin{tikzpicture}
>    \begin{scope}[very thick,decoration={markings,mark=at position 0.55 with {\arrow{>}}}] 
>    \draw[postaction={decorate}] (0,-1)--(1.73,0);
>    \draw[postaction={decorate}] (0,1)--(1.73,0);
>    \end{scope}
>    
>    \tikzset{edge/.style = {->,> = latex'}}
>    \path[draw, ultra thick] (0,1) node[anchor=east]{$e_{2}$}
>    -- (0,-1)  node[anchor=east] {$e_{0}$}
>    --node[below right]{$f$} (1.73,0) node[anchor=west]{$e_{1}$}
>    --node[above right]{$f$} cycle;
>    \path[clip] (0,1) -- (0,-1) -- (1.73,0) -- cycle; 
>    \foreach \y in{0,0.1,...,2}
> 	   \draw (\y,-1) -- (\y,1);
>    
>    \node (a) at  (0,1) {};
>    \node (b) at  (0,-1) {};
>    \node (c) at  (1.73,0) {};
>    
>    
>    \end{tikzpicture}
>    \end{document} 
>    ```
>    where on every vertical line in the triangle, $\sigma$ is constant. Then, $\sigma$ is continuous and we also have that $\sigma|_{e_{0}e_{2}}=:c$ is a constant path. Hence, $$\partial\sigma=f+f^{-1}-c\in B_{1}(X)$$However as $c\in B_{1}(X)$ from 2, we have that $f+f^{-1}\in B_{1}(X)$. 
>    
> 

^9bd3fa

---
> [!lemma] Theorem 6 (Hurewicz)
> Let $X\neq \varnothing$ be a path connected. Let $G:=\pi_{1}(X)$ be its [[fundamental group]]. Then, 
> 1. $H_{1}(X)\cong G / [G,G]$ where $[G,G]$ is the [[commutator subgroup]].

^f7f1b8

> [!proof]-
> We have that:
> 1. **Lemma 1**: Let $f,g:I\to X$ be two paths with $f(0)=g(0)$ and $f(1)=g(1)$. If $f\sim g$ (rel $\partial I$), then $f$ and $g$ are homologous.
>    
>    Let $F:I\times I\to X$ be the homotopy from $f$ to $g$ relative to $\partial I$. Then, $F|_{0\times I}=f(0)$ and $F|_{1\times I}=f(1)$ are both constant. 
>    
>    Consider the continuous map $p:I\times I\to\Delta_{2}$ that collapses $0\times I$ to $e_{0}$, i.e. 
>    
>    ```tikz
>    \usepackage{tikz}
>    \usetikzlibrary{decorations.markings}
>    \usetikzlibrary{arrows}
>    \begin{document}
>    \begin{tikzpicture}
>    \begin{scope}[very thick,decoration={markings,mark=at position 0.55 with {\arrow{>}}}] 
>    \draw[postaction={decorate}] (0,0)--(2,0);
>    \draw[postaction={decorate}] (0,2)--(2,2);
>    \draw[postaction={decorate}] (4,1)--(5.73,0);
>    \draw[postaction={decorate}] (4,1)--(5.73,2);
>    \end{scope}
>    
>    \tikzset{edge/.style = {->,> = latex'}}
>    \path[draw, ultra thick] 
>    (0,0) node[anchor=east]{$(0,0)$}
>    -- (0,2) node[anchor=east]{$(0,1)$}
>    -- (2,2) node[anchor=west]{$(1,1)$}
>    -- (2,0) node[anchor=west]{$(1,0)$}
>    --cycle;
>    
>    \path[red, draw, ultra thick] 
>    (0,0) node{}
>    -- (0,2) node{};
>    \path[draw, ultra thick] 
>    (4,1) node[anchor=east]{$e_{0}$}
>    -- (5.73,0)  node[anchor=west] {$e_{1}$}
>    -- (5.73,2) node[anchor=west]{$e_{2}$}
>    -- cycle;
>    
>    \path[red, draw, ultra thick] 
>    (4,0.95) node{}
>    -- (4,1.05) node{};
>    
>    \tikzset{edge/.style = {->,> = latex'}}
>    \node (a) at  (2.5,1) {};
>    \node (b) at  (3.5,1) {};
>    \draw[edge] (a) tonode[anchor=south]{$p$} (b);
>    
>    \begin{scope}
>    \path[clip] (4,1) -- (5.73,0) -- (5.73,2) -- cycle; 
>    \foreach \y in{4,4.1,...,6}
> 	   \draw (\y,0) -- (\y,4);
>    \end{scope}
>   \path[clip] (0,0) -- (0,2) -- (2,2) -- (2,0) -- cycle; 
>   \foreach \y in {0,0.1,...,2}
> 	   \draw (\y,0) -- (\y,4);
> 	   
>    \end{tikzpicture}
>    \end{document} 
>    ```
>    Further, we can choose $p$ s.t. it induces a homeomoprhism from $I\times I /\sim$ to $\Delta_{2}$. Then, $F$ can be written as a composition $\sigma \circ p$ where $\sigma:\Delta_{2}\to X$ is a singular $2$-simplex with $\sigma|_{e_{0}e_{1}}=f$, $\sigma|_{e_{0}e_{2}}=g$ and $\sigma|_{e_{1}e_{2}}=:c$ is constant. Hence, $$\partial\sigma=c-g+f\in B_{1}(X)$$and we have from Lemma 5.2 that $f-g\in B_{1}(X)$. Hence, $f$ and $g$ are homologous.
>    
>  Now, let $G:=\pi_{1}(X,x_{0})$. We will define $\phi:G\to H_{1}(X)$ as follows. Let $a\in G$ and choose $f:I\to X$ with $f(0)=f(1)=x_{0}$ s.t. $[f]=a\in G$. Then, we define: $$\phi(a)=[f]$$Then, $\phi$ is well-defined by Lemma 1 above. We now show that $\phi$ is a homomorphism. 
>  
>  Let $a,b\in G$ with $f,g:I\to X$ with $[f]=a$ and $[g]=b$. Then, by Lemma 5.1,$$\phi(ab)=\phi([f*g])=[f*g]=[f+g]=[f]+[g]=\phi(a)+\phi(b)$$As $H_{1}(X)$ is abelian, $\phi$ sends $[G,G]$ to $0\in H_{1}(X)$. Hence, $\phi$ induces a map $\phi_{*}:G / [G,G]\to H_{1}(X)$. To show that this is an isomorphism, we will construct $\psi_{*}:H_{1}(X)\to G / [G,G]$ with $\phi_{*}\circ\psi_{*}=\text{id}$ and $\psi_{*}\circ\phi_{*}=\text{id}$. 
>  
>  For all $x\in X$, pick a path $\lambda_{x}:I\to X$ with $\lambda_{x}(0)=x_{0}$ and $\lambda_{x}(1)=x$, which exists as $X$ is path connected. Wlog we may assume that $\lambda_{x_{0}}$ is the constant path at $x_{0}$. 
>  
>  Now, we define: $\psi:S_{1}(X)\to G / [G,G]$ where for a singular $1$-simplex $f:I\to X$, $$\psi(f):=[\lambda_{f(0)}*f*\lambda_{f(1)}^{-1}]$$where we abuse the notation of chaining $*$s, which we can as we only look at the path homotopy class of it.
>  
>  As $S_{1}(X)$ is a free abelian group and $G / [G,G]$ is abelian, we can extend this definition by linearity to a homomorphism $\psi:S_{1}(X)\to G / [G,G]$.  
>  
>  1. **Claim 1**: For all $b\in B_{1}(X)$, we have that $\psi(b)=1\in G / [G,G]$. 
>     
>     Let $\sigma:\Delta_{2}\to X$ be a singular $2$-simplex in $X$. Let $f:=\sigma|_{e_{0}e_{1}}, g:=\sigma|_{e_{1}e_{2}}$ and $h:=\sigma|_{e_{2}e_{0}}$. Then, $$\psi(\partial\sigma)=\psi(g-h^{-1}+f)=\psi(g)(\psi(h^{-1}))^{-1}\psi(f)=\psi(f)\psi(g)(\psi(h^{-1}))^{-1}$$Hence, by defining $y_{i}:=\sigma(e_{i})$, we have that: $$\psi(\partial\sigma)=\{ \lambda_{y_{0}}*f*\lambda_{y_{1}}^{-1}*\lambda_{y_{1}}*g*\lambda_{y_{2}}^{-1}*(\lambda_{y_{0}}*h^{-1}*\lambda_{y_{2}}^{-1})^{-1} \}=\{ \lambda_{y_{0}}* f*g*h*\lambda_{y_{0}} \}$$However, using the path homotopy from $f*g*h$ to the constant path at $e_{0}$ in $\Delta_{2}$, we get that $\psi(\partial\sigma)=\{ \lambda_{y_{0}}*\lambda_{y_{0}}^{-1} \}=1\in G / [G,G]$. Therefore, $\psi$ induces a homomorphism $\psi_{*}:H_{1}(X)\to G / [G,G]$.
>     
>  Now, it is only left to show that $\psi_{*}$ is the inverse homomorphism of $\phi_{*}$. Let $f:I\to X$ be a loop at $x_{0}$. Then, $$\psi_{*}\phi_{*}(\{ f \})=\psi_{*}([f])=\{ \lambda_{x_{0}}*f*\lambda_{x_{0}}^{-1} \}=\{ f \}$$To show that $\phi_{*}\circ\psi_{*}=\text{id}$, consider the group homomorphism $\lambda:S_{0}(X)\to S_{1}(X)$ defined through $\lambda\left( \sum_{x}^{}n_{x}x \right)=\sum_{x}n_{x}\lambda_{x}$. 
>  1. **Lemma 2**: For a singular $1$-simplex $\sigma:I\to X$, $\phi_{*}(\psi(\sigma))=[\sigma-\lambda_{\partial\sigma}]$.
>     
>     We have that by Lemma 5: $$\phi_{*}(\psi(\sigma))=\phi_{*}(\{ \lambda_{\sigma(0)}*\sigma*\lambda_{\sigma(1)}^{-1} \})=[\lambda_{\sigma(0)}*\sigma*\lambda_{\sigma(1)}^{-1} ]=[\lambda_{\sigma(0)} ]+[\sigma]-[\lambda_{\sigma(1)}]=[\sigma-\lambda_{\partial\sigma}]$$
>  2. **Lemma 3**: For a singular $1$-chain $c\in S_{1}(X)$, $\phi_{*}(\psi(c))=[c-\lambda_{\partial c}]$ which follows by linearity. 
>  
>  Therefore, for any cycle $c\in Z_{1}(X)$, we have that: $$\phi_{*}(\psi(c))=[c-\lambda_{\partial c}]=[c]$$and $\phi_{*}(\psi_{*}([c]))=[c]$, which proves the theorem.
>  


^f68c2d

---
##### Examples
> [!h] Example 1 (Point Space)
> For a point space $X=\{ x_{0} \}$, 
> 1. $Z_{p}(X)=\begin{cases}\mathbb{Z}\sigma_{p}&p>0\text{ odd}\\0&p>0\text{ even}\\\mathbb{Z}\sigma_{p}&p=0\\0&p<0\end{cases}$
> 2. $B_{p}(X)=\begin{cases}\mathbb{Z}\sigma_{p}&p>0\text{ odd}\\0&p>0\text{ even}\\0&p\leq0\end{cases}$
> 3. $H_{p}(X)\cong\begin{cases}\mathbb{Z}&p=0\\0&\text{otherwise}\end{cases}$

^8095bc

> [!proof]-
> Fix $p=0$. We have that the only singular $p$-simplex $\sigma_{p}:\Delta_{p}\to X$ is given by the constant map. Therefore, $S_{p}(X)\cong \mathbb{Z}$ for all $p\geq 0$. 
> 
> Further, $\partial_{p}(\sigma_{p})$ is an alternating sum of $(p+1)$ summands of which is up to $\sigma_{p-1}$. Hence, $$\partial_{p}(\sigma_{p})=\begin{cases}0&p>0\text{ odd}\\\pm\sigma_{p-1}&p>0\text{ even}\\0&p\leq 0\end{cases}$$Hence, $\partial_{p}$ is an isomorphism if and only if $p>0$ and even. The rest then follows.

^a5f87b

---
> [!h] Example 2 (Path-Connected Space)
> If $X\neq \varnothing$ and $X$ is [[Path-Connected Space|path-connected]], then:
> 1. $H_{0}(X)=\mathbb{Z}[x]\cong \mathbb{Z}$ for any $x\in X$.

^1342f9

> [!proof]-
> Consider a singular $0$-simplex $\sigma$ in $X$. Then, as $\Delta_{0}$ is a point, we have that $S_{0}(X)$ is a set of finite formal sum of points in $X$. 
> 
> Let $\varepsilon:S_{0}(X)\to \mathbb{Z},\sum_{x}^{}n_{x}x\mapsto \sum_{x}^{}n_{x}$. Then, notice that $\varepsilon$ is a homomorphism. 
> 
> Let $\sigma:\Delta_{1}\to X$ now be a singular $1$-simplex in $X$. Then, for $x_{0}:=\sigma(e_{0})$ and $x_{1}:=\sigma(e_{1})$, we have that: $$\partial_{1}\sigma=\sigma(e_{1})-\sigma(e_{0})=x_{1}-x_{0}$$and $\varepsilon \partial_{1}(\sigma)=1-1=0$. Hence, $\varepsilon(\partial_{1}d)=0$ for all $d\in S_{1}(X)$ and $\varepsilon(B_{0}(X))=0$. Therefore, we have that: $$\varepsilon_{*}:H_{0}(X)\to \mathbb{Z}$$induces a homomorphism. 
> 
> Now, clearly we have $\varepsilon_{*}([y])=1$ for all $y\in X$ and $\varepsilon_{*}$ is surjective. To show that $\varepsilon_{*}$ is also injective, let $x_{0}\in X$ and for all $x\in X$ let $\lambda_{x}:I\to X$ be a path from $\lambda_{x}(0)=x_{0}$ and $\lambda_{x}(1)=x$. By viewing these paths as singular $1$-simplices, we have that: $$\partial_{1}\lambda_{x}=x-x_{0}\in S_{0}(X)$$Let $c\in S_{0}(X)$ with $c=\sum_{x}n_{x}x$ be a $0$-chain and assume that $\varepsilon_{*}([c])=0$. Then, for $d:=\sum_{x}^{}n_{x}\lambda_{x}\in S_{1}(X)$, we have that: $$\partial_{1}d=\sum_{x}n_{x}(x-x_{0})=\sum_{x}n_{x}x-\varepsilon_{*}([c])x_{0}=c$$Hence, $c\in B_{0}(X)$ and $\varepsilon_{*}([c])=0$. 

^909e9b

---
> [!h] Example 3 
> We have that: 
> 1. $H_{1}(S^n)\cong\begin{cases}\mathbb{Z}&n=1\\0&n\geq 2\end{cases}$
> 2. $H_{1}(\mathbb{T}^n)\cong\bigoplus_{i=1}^n \mathbb{Z}$
> 3. $H_{1}(\mathbb{R}\mathbb{P}^n)\cong \mathbb{Z} / 2\mathbb{Z}$ for $n\geq 2$.
> 4. $H_{1}(X)\cong \mathbb{Z}\oplus\dots \oplus \mathbb{Z}$ ($n$ times) where $X$ is a bouquet of $n$-circles.

^6d8abe

> [!proof]-
> From Hurewicz, we have that:
> 1. As $\pi_{1}(S^n)=\begin{cases}\mathbb{Z}&n=1\\0&n\geq 2\end{cases}$ and both are comnmutative, $H_{1}(S^n)\cong \pi_{1}(S^n)$.
> 2. As $\mathbb{T}^{n}:=\bigoplus_{i=1}^n S^1$, we have that by [[Fundamental Group|Proposition 3]]: $$\pi_{1}(\mathbb{T}^n)\cong \pi_{1}(S^1)\oplus \dots \oplus \pi_{1}(S^1)\cong \mathbb{Z}\oplus \dots \oplus \mathbb{Z}$$As this is commutative, we have the statement.
> 3. From [[Real Projective Space|Proposition 3]].
> 4. The fundamental group is a free non-abelian group on $n$ letters and by Hurewicz we have that the 1-homology is the free abelian group on $n$ letters.

^b81476

---
