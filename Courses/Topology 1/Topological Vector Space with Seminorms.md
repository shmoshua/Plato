#Definition #FunctionalAnalysis 

> [!definition]
> A ***topologcal vector space with seminorms***  is a [[Topological Vector Space]], i.e. a $\mathbb{K}$-vector space with a family of [[Seminorm]] $\{ \|\cdot\|_{a} \}_{a\in A}$. We then define the topology as follows: 
> 
> For all $v\in V$, $F\subseteq A$ finite, $r>0$, $$N(v,F,r)=\{ w\in V:\|w-v\|_{a}<r,\forall a\in F \}$$Then, a set $\Omega \subseteq V$ is ***open*** if for all $v\in \Omega$,  there exists finite $F\subseteq A$ and $r>0$ s.t. $$N(v,F,r)\subseteq\Omega$$

- **Related Definition**: $\{ p_{a} \}_{a\in A}$ is ***sufficient***, if for all $v\in V$ s.t. $v\neq 0$, there exists $a\in A$ s.t. $\|v\|_{a}\neq 0$. 
- **Necessity of $F$ being finite**. Example: consider $C(\mathbb{R})$ and look at $N(f,F,\varepsilon)$ where $F=\{ \|\cdot\|_{K}:K\text{ is compact} \}$ with $\|f\|_{K}=\sup_{x\in K}\left|f(x)  \right|$. Then, $$N(0,F,\varepsilon)=\{ f\in C(\mathbb{R}):\left\| f \right\| _{K}<\varepsilon,\forall K\subseteq \mathbb{R} \}=\{ f\in C(\mathbb{R}):\left\| f \right\| _{b}<\varepsilon \}$$Then, let $h\in C(\mathbb{R})$ be unbounded. Then, $0\cdot h\in N(0,F,\varepsilon)$ but for any $t\neq 0$, $t\cdot h\notin N(0,F,\varepsilon)$. This proves that scalar multiplication is not continuous, i.e. $C(\mathbb{R})$ is not a topological vector space.
---
> [!lemma] Proposition 1
> It holds that:
> 1. $\varnothing$ and $V$ are open.
> 2. Any arbitrary union of open sets is open.
> 3. Any intersection of two open sets is open.
>    
> Therefore, this introduces a [[Topological Space|topology]].

> [!proof]-
> We have that:
> 1. Obvious from the definition.
> 2. Obvious from the definition.
> 3. We will show that $\Omega:=N(v_{1},\{ \|\cdot\|_{1} \},r_{1})\cap N(v_{2},\{ \|\cdot\|_{2} \},r_{2})$ is open. Let $v_{3}\in \Omega$. Then, we have that: 
>       1. $\|v_{3}-v_{1}\|_{1}<r_{1}$
>       2. $\|v_{3}-v_{2}\|_{2}<r_{2}$
>      
>      and $\varepsilon:=\min\{ r_{1}-\|v_{3}-v_{1}\|_{1} ,r_{2}-\|v_{3}-v_{2}\|_{2}\}$. Then, for any $w\in N(v_{3},\{ \|\cdot\|_{1},\|\cdot\|_{2} \},\varepsilon)$, we have: 
>      1. $\|w-v_{1}\|_{1}\leq \|w-v_{3}\|_{1}+\|v_{3}-v_{1}\|_{1}<\varepsilon+\|v_{3}-v_{1}\|_{1}\leq r_{1}$ and $w\in N(v_{1},\{ \|\cdot\|_{1} \},r_{1})$
>      2. $\|w-v_{2}\|_{2}\leq \|w-v_{2}\|_{2}+\|v_{3}-v_{2}\|_{2}<\varepsilon+\|v_{3}-v_{2}\|_{2}\leq r_{2}$ and $w\in N(v_{2},\{ \|\cdot\|_{2} \},r_{2})$
>  
>     Therefore, $w\in \Omega$ and $N(v_{3},\{ p_{1},p_{2} \},\varepsilon)\subseteq\Omega$. This shows that $\Omega$ is open. 
>     
>     Hence, we have that if $\Omega_{1},\Omega_{2}\subseteq V$ are open, for every $v\in\Omega_{1}\cap\Omega_{2}$, there exists $F_{1},F_{2}$ and $r_{1},r_{2}$ s.t. 
>     1. $N(v,F_{1},r_{1})\subseteq\Omega_{1}$ and 
>     2. $N(v,F_{2},r_{2})\subseteq \Omega_{2}$.
>     
>     Therefore, there exists $\varepsilon>0$ s.t. $N(v,F_{1}\cup F_{2},\varepsilon)\subseteq N(v,F_{1},r_{1})\cap N(v,F_{2},r_{2})\subseteq\Omega_{1}\cap\Omega_{2}$.
---
> [!lemma] Lemma 2
> The topology on $V$ generated by $\{ p_{a} \}_{a\in A}$ endows $V$ with a structure of a [[Topological Vector Space]].

> [!proof]-
> We have: 
> 1. **Showing $M_{\lambda}$ is continuous**:
> We will show that $M_{\lambda}:v\mapsto \lambda v$ is continuous for all $\lambda\neq 0$. Let $\Omega \subseteq V$ open. Then, for $v\in M_{\lambda}^{-1}[\Omega]$, there exists  finite $F\subseteq A$ and $r>0$ s.t. $$\lambda N(v,F,r / \left| \lambda \right| )=N(\lambda v,F,r)\subseteq\Omega$$Therefore, $N(v,F,r / \left| \lambda \right|)\subseteq M^{-1}_{\lambda}[\Omega]$. 
> 2. **Showing addition is continuous**:
> Similarly, for $(v,w)\mapsto v+w$, let $\Omega \subseteq V$ open. Then, for $(v,w)$ s.t. $v+w\in \Omega$, there exists $F$ and $r>0$ s.t. $$N(v+w,F,r)\subseteq\Omega$$Then, we have an open set $N(v,F,r/2)\times N(w,F,r/2)$ s.t. for $(a,b)$: $$\|a+b-v-w\|\leq \|a-v\|+\|b-w\|< \frac{r}{2}+\frac{r}{2}=r$$Therefore, $a+b\in \Omega$. This shows that addition is continuous.
---
> [!lemma] Lemma 3
> If $\{ \|\cdot\|_{a}\}_{a\in A}$ is sufficient, the topology generated by $\{ \|\cdot\|_{a}\}_{a\in A}$ is a [[Hausdorff Space]].

> [!proof]-
> By using translations (homeomorphisms), we are reduced to separating $0$ from $v\neq 0$. As $\{ \|\cdot\|_{a} \}_{a\in A}$ is sufficient, let $a\in A$ s.t. $\|v\|_{a}=\varepsilon>0$. Then, we will show that: $$N\left( 0,\|\cdot \|_{a}, \frac{\varepsilon}{3} \right)\cap N\left( v,\|\cdot \|_{a}, \frac{\varepsilon}{3} \right)=\varnothing$$
> If otherwise, there exists $w$ s.t. $$\varepsilon =\|v\|_{a}\leq \|w\|_{a}+\|v-w\|_{a}< \frac{2\varepsilon}{3}$$which is a contradiction. Therefore, we have a Hausdorff space.
---
> [!lemma] Proposition 4
> If $\{\|\cdot\|_{n} \}_{n\geq 1}$ is a countable sufficient family of semi-norms, then the associated topological vector space is metrizable.

> [!proof]-
> We define the following metric: $$d(v,w)= \sum_{n=1}^{\infty}\left( \frac{\|v-w\|_{n}}{1+\|v-w\|_{n}} \right) \frac{1}{2^n}$$
> 1. **Showing non-degeneracy**:
>    If $d(v,w)=0$, then $\|v-w\|_{n}=0$ for all $n\geq 1$. As $\{ \|\cdot\|_{n}\}_{n\geq 1}$ is sufficient, we have $v=w$.
> 2. **Showing symmetry**:
>    Follows from the definition of a seminorm.
> 3. **Showing triangular inequality**:
>    Firstly, for $0\leq a,b,c$ s.t. $a\leq b+c$, we have that: $$\frac{a}{1+a}\leq \frac{b+c}{1+b+c}=\frac{b}{1+b+c}+\frac{c}{1+b+c}\leq \frac{b}{1+b}+ \frac{c}{1+c}$$
> 	Therefore, for all $x,y,z\in V$ and $n\geq 1$, $\|x-z\|_{n}\leq\|x-y\|_{n}+\|y-z\|_{n}$ and $$\begin{align}d(x,z)&=\sum_{n=1}^{\infty}\left( \frac{\|x-z\|_{n}}{1+\|x-z\|_{n}} \right) \frac{1}{2^n}\\&\leq\sum_{n=1}^{\infty}\left( \frac{\|x-y\|_{n}}{1+\|x-y\|_{n}}+\frac{\|y-z\|_{n}}{1+\|y-z\|_{n}} \right) \frac{1}{2^n}\\&=d(x,y)+d(y,z)\end{align}$$
> 4. **Showing an open set by metric is open by seminorm**:
>    Observe that for all $n\geq 1$ and $\ell\geq 1$: $$\frac{1}{2^n}\left( \frac{\|v-w\|_{n}}{1+\|v-w\|_{n}} \right) \leq d(v,w)\leq \sum_{k=1}^{\ell}\left( \frac{\|v-w\|_{k}}{1+\|v-w\|_{k}} \right) \frac{1}{2^k}+\frac{1}{2^\ell} $$Hence, for any open set $\Omega$ according to the metric $d$ and $v\in \Omega$, there exists $r>0$ s.t. $B_{<r}(v)\subseteq\Omega$. Then, for $\ell$ s.t. $2^{-\ell}<r/2$: $$N\left( v,\{ \|\cdot \|_{k} \}_{k\in[\ell]}, \frac{r}{2} \right)\subseteq B_{<r}(v)\subseteq\Omega$$as $$\begin{align}d(v,w)&\leq \sum_{k=1}^{\ell}\left( \frac{\|v-w\|_{k}}{1+\|v-w\|_{k}} \right) \frac{1}{2^k}+\frac{1}{2^\ell}\\&< \frac{r}{2}+ \frac{r}{2}=r\end{align} $$
> Therefore, $\Omega$ is open with semi-norms. 
> 5. **Showing an open set by seminorm is open by metric**:
> Assume $\Omega \subseteq V$ is open with semi-norms. Then, for $v\in \Omega$, there exists $F$ and $r>0$ s.t. $$N(v,\{ \|\cdot \|_{n_{1}},..,\|\cdot \|_{n_{k}} \},r)\subseteq\Omega$$Then, we choose $n$ s.t. $n_{k}\leq n$ and $\varepsilon=\min\{1,r\}$. Hence, if $d(v,w)< \frac{\varepsilon}{2^{n+1}}$, then for all $n_{k}$:$$\frac{1}{2^{n_{k}}}\left( \frac{\|v-w\|_{n_{k}}}{1+\|v-w\|_{n_{k}}} \right) \leq d(v,w)< \frac{\varepsilon}{2^{n_{k}+1}}$$and $2\|v-w\|_{n_{k}}<\varepsilon(1+\|v-w\|_{n_{k}})$ and $\|v-w\|_{n_{k}}\leq(2-\varepsilon)\|v-w\|_{n_{k}}< \varepsilon\leq r$. Therefore, $$B_{< \varepsilon / 2^{n+1}}(v)\subseteq N(v,\{ p_{n_{1}},..,p_{n_{k}} \},r)\subseteq\Omega$$This proves the statement. 
---
> [!lemma] Proposition 5
> Let $V$ and $W$ be topological vector spaces from $\{ \|\cdot\|_{a}^V \}_{a\in A}$ and $\{ \|\cdot\|_{b}^W \}_{b\in B}$. Then, for a linear map $T:V\to W$, the following are equivalent: 
> 1. $T$ is continuous
> 2. $T$ is continuous at $0$.
> 3. For all finite $F\subseteq B$, there exists finite $G\subseteq A$ s.t. for all $b\in F$: $$\sup\{\left\| T(x) \right\|_{b}^W :\max_{a\in G}\|x\|^V_{a}\leq 1\}<+\infty$$

> [!proof]-
> - (2=>3): Let $F\subseteq B$. Then, $N_{W}(0,F,r)$ is an open neighborhood of $0\in W$. Therefore, there exists $N_{V}(0,G,\varepsilon_{r})\subseteq T^{-1}(N_{W}(0,F,r))$. Then, for any $x\in V$ s.t. $\max_{a\in G}\|x\|_{a}< \varepsilon_{r}$, $\|T(x)\|_{b}^W<r$ for every $b\in F$. Then, with the same $G$, we have: $$\sup\{ \left\| Tx \right\| _{b}^W:\max_{a\in G}\|x\|_{a}^V\leq1 \}\leq \frac{r}{\varepsilon_{r}}<+\infty$$
> - (3=>1): Let $N(0,F,r)$ be an open neighborhood of $0\in W$. Then, there exists $G\subseteq A$ s.t. for all $b\in F$, $\sup\{\left\| T(x) \right\|_{b}^W :\max_{a\in G}\|x\|^V_{a}\leq 1\}<+\infty$. Let $m$ be the maximum over all $b\in F$. In other words, $$\begin{align}N(0,G,r/m)&=\{ x\in V:\|x\|_{a}<r /m,\forall a\in G \}\\&=\{ x\in V:\|mx / r\|_{a}<1,\forall a\in G \}\\&=r /m \cdot N(0,G,1)\\&\subseteq r/m\cdot T^{-1}(N(0,F,m))\\&=T^{-1}(N(0,F,r))\end{align}$$
- **Corollary**: A linear form $f:V \to \mathbb{K}$ is continuous if and only if there exists finite $G\subseteq A$ s.t. $$\sup\{ \left| f(x) \right| : \max_{a\in G}\|x\|^V_{a}\leq 1\}<+\infty$$by choosing $\{ \left| \cdot \right| \}$ as the seminorm for $\mathbb{K}$.
---
> [!lemma] Theorem 6 (Hahn-Banach)
> Let $V$ be a topological vector space defined by a sufficient family of semi-norms $\{ \|\cdot\|_{a} \}_{a\in A}$. Then, for all $v\neq 0$, there exists $F\in V^{*}$ s.t. $$F(v)\neq 0$$

> [!proof]-
> Let $v\neq 0$ and $a\in A$ s.t. $\|v\|_{a}\neq 0$. Let $M:=\mathbb{K}\cdot v$. Finally, we define the linear form $$\begin{array}{cccc} {f:}&{M}&\to&{\mathbb{K}}\\&{\lambda v} &\mapsto & {\lambda\|v\|_{a}} \end{array}{}$$Then, we have that for $\lambda v\in M$: $$\left| f(\lambda v) \right| =\left| \lambda \|v\|_{a} \right|=\|\lambda v\|_{a} $$Therefore, from [[Seminorm|Hahn-Banach]], there exists a linear extension $F:V\to \mathbb{K}$ s.t. $|F(w)|\leq \|w\|_{a}$ for all $w\in V$. It follows that from Corollary of Proposition 5, $F$ is continuous, i.e. $F\in V^{*}$ and: $$F(v)=f(v)=\|v\|_{a}\neq 0$$
---
> [!lemma] Proposition 7
> Let $V$ be a topological vector space defined by a family of semi-norms $\{ \|\cdot\|_{a} \}_{a\in A}$. Then, $$\overline{\{ 0 \}}=\{ v\in V:\|v\|_{a}=0\quad \forall a\in A \}$$

> [!proof]-
> For $v\in V$, if $\|v\|_{a}=0$ for all $a\in A$,  then for every neighborhood $U$ containing $v$, there exists $N(v,F,\varepsilon)\subseteq U$ where $F\subseteq A$ is finite and $\varepsilon>0$. However, for all $a\in F$, $$\|v\|_{a}=0<\varepsilon$$Therefore, $\{ 0 \}\cap N(v,F,\varepsilon)\neq \varnothing$ for all $F,\varepsilon$. This proves that $v\in \overline{\{ 0 \}}$.
> 
> Conversely, let $v\in \overline{\{ 0 \}}$. Then, for any $F\subseteq A$ and $\varepsilon>0$, $0\in N(v,F,\varepsilon)$. In other words, $$\|v\|_{a}<\varepsilon$$for all $a\in F$. This proves that $\|v\|_{a}=0$ for all $a\in A$.
---
> [!lemma] Theorem 8 (Hahn-Banach, the 1st Geometric Form)
> Let $E$ be a $\mathbb{R}$-topological vector space of seminorms $\{ \|\cdot\|_{a} \}_{a\in B}$.  Further, let $A\subseteq E$ be an non-empty, open, [[Convex Set|convex]] set. Then, for any $v\notin A$, there exists $F\in E^{*}$ with $$F(a)<F(v)\quad\forall a\in A$$ 

> [!proof]-
> We have:
> 1. **Constructing the subspace $M$**:
>    Pick $a_{0}\in A$ and consider $A'=A-a_{0}$ which is open, convex and absorbant, by [[Absorbant Set|Lemma 2]]. Now, define $M:=\mathbb{R}(v-a_{0})$ and $$\begin{array}{cccc} {f:}&{M}&\to&{\mathbb{R}}\\&{\lambda(v-a_{0})} &\mapsto & {\lambda} \end{array}{}$$
> 2. **Showing that $f\leq p_{A'}$ on $M$**:
>    Firstly, if $\lambda<0$, then it holds trivially as $p_{A'}\geq 0$. If $\lambda\geq 0$, then as $v-a_{0}\notin A-a_{0}=A'$, we have that $p_{A'}(v-a_{0})\geq 1$ from [[Gauge Function|Proposition 2]]. Therefore, $$f(\lambda(v-a_{0}))=\lambda\leq\lambda p_{A'}(v-a_{0})=p_{A'}(\lambda(v-a_{0}))$$
>  3. **Using Hahn-Banach**:
>     From the [[Gauge Function|Analytic form of Hahn-Banach]], there exists $F\in E^{*}$ s.t. 
> 	1. $F|_{M}=f$ and
> 	2. $F(w)\leq p_{A'}(w)$ for all $w\in E$.
> 
> 	Hence, for all $a\in A$: $F(a-a_{0})\leq p_{A'}(a-a_{0})<1$ from [[Gauge Function|Proposition 2]]. Further, $F(v-a_{0})=f(v-a_{0})=1$. Therefore, $$F(v)=1+F(a_{0})>F(a)$$for all $a\in A$.
---
> [!lemma] Corollary 9 (Hahn-Banach, the 2nd Geometric Form)
> Let $E$ be a $\mathbb{R}$-topological vector space of seminorms $\{ \|\cdot\|_{a} \}_{a\in B}$.  Further, let $A\subseteq E$ be an non-empty, closed, [[Convex Set|convex]] set. Then, for any $v\notin A$, there exists $F\in E^{*}$ and $\alpha\in \mathbb{R}$ s.t. $$F(a)<\alpha<F(v)\quad\forall a\in A$$ 

> [!proof]-
> We have: 
> 1. **Constructing a non-empty, open, convex set**:
>    Since $A$ is closed, there exists an open set $U$ with $0\in U$ and $(v+U)\cap A=\varnothing$. Let $G\subseteq B$ be finite and $\varepsilon>0$ s.t. $N(0,G,\varepsilon)\subseteq U$. Then, $$(v-N(0,G,\varepsilon))\cap A=(v+N(0,G,\varepsilon))\cap A=\varnothing$$and $v\notin A+N(0,G,\varepsilon)$. Further, 
> 	1. $A+N(0,G,\varepsilon)$ is convex as $A$ and $N(0,G,\varepsilon)$ are both convex.
> 	2. $A+N(0,G,\varepsilon)=\bigcup_{a\in A}^{}(a+N(0,G,\varepsilon))$ is open. 
> 2. **Using Hahn-Banach the 1st geometric form**:
> 	Therefore, from the first geometric from of Hahn-Banach, there exists $F\in E^{*}$ s.t. $$F(a+w)<F(v)\quad \forall a\in A,w\in N(0,F,\varepsilon)$$
> 
> 	Since $F\not\equiv 0$, there exists $v_{0}\in E$ s.t. $F(v_{0})>0$.  Further, as $N(0,F,\varepsilon)$ is absorbant, there exists $\lambda>0$ s.t. $\lambda v_{0}\in N(0,F,\varepsilon)$. Then, by letting $w_{0}:=\lambda v_{0}$, we have $F(w_{0})>0$ and $$F(a)<\underbrace{ F(a)+F(w_{0}) }_{ =:\alpha }<F(v)\quad\forall a\in A$$
---
> [!lemma] Lemma 10
> Let $E$ be a TVS with seminorms $\{ \|\cdot\|_{a} \}_{a\in A}$. Then, for a [[Convex Set|convex]] set $C\subseteq E$, the [[Interior and Closure|closure]] $\overline{C}$ is convex.

> [!proof]-
> Let $v_{1},v_{2}\in \overline{C}$. We want to show that $tv_{1}+(1-t)v_{2}\in \overline{C}$. Let $\varepsilon>0$ and $F\subseteq A$ finite.  Then, $$\begin{align}(v_{1}+N(0,F,\varepsilon))\cap C&\neq \varnothing\\(v_{2}+N(0,F,\varepsilon))\cap C&\neq \varnothing\end{align}$$Therefore, there exists $x_{1},x_{2}\in N(0,F,\varepsilon)$ s.t. $$v_{1}+x_{1}\in C,\quad v_{2}+x_{2}\in C$$
> Hence, $$t(v_{1}+x_{1})+(1-t)(v_{2}+x_{2})=tv_{1}+(1-t)v_{2}+\underbrace{ tx_{1}+(1-t)x_{2} }_{ \in N(0,F,\varepsilon) }\in C$$It follows that $tv_{1}+(1-t)v_{2}\in \overline{C}$.
---
> [!lemma] Theorem 11 (Markov-Kakutani)
> Let $E$ be a topological vector space with a sufficient family of seminorms $\{ \|\cdot\|_{a} \}_{a\in B}$, $G$ an [[Abelian Group|abelian group]] and $\pi:G \to \text{Aut}(E)$ a [[Group Representation|representation]]. For a compact, convex, non-empty set $A\subseteq E$, if $A$ is $G$-invariant, i.e. $$\pi(g)[A]\subseteq A\quad \forall g\in G$$then, there exists $x\in A$ s.t. $\pi(g)(x)=x$ for all $g\in G$.

> [!proof]-
> We have:
> 1. **Defining automorphisms $M_{g,n}$**:
> For every $g\in G$ and $n\geq 1$, we define: $$\begin{array}{cccc} {M_{g,n}:}&{E}&\to&{E}\\&{v} &\mapsto & {\frac{1}{n}\sum_{k=0}^{n-1}\pi(g^k)(v)} \end{array}{}$$which is a continuous linear map as a sum of continuous linear maps (automorphisms)
> 
>    Since, for all $v\in A,g\in G,k\in \mathbb{Z}$ we have that $\pi(g^k)(v)\in A$, we have: $$M_{g,n}[A]\subseteq A$$
> 2. **Defining the space of finite combinations of $M_{g,n}$**:
>    Now, we define the following set: $$G^{*}:=\{ M_{g_{1},n_{1}}\circ  \dots \circ  M_{g_{\ell},n_{\ell}}: \ell\geq 1, (g_{1},...,g_{\ell})\in G^\ell, (n_{1},\dots,n_{\ell})\in (\mathbb{N}_{\geq 1})^{\ell} \}$$
> Then, we have the property that for any $S,T\in G^{*}$:
>    1. $T\circ S\in G^{*}$ from the definition.
> 	2. $T(A)\subseteq A$ as $M_{g,n}[A]\subseteq A$ for any $g\in G,n\geq 1$.
> 	3. $T\circ S = S\circ T$
> 
>    For $3$, we have that for $M_{g,n}$ and $M_{h,m}$: $$\begin{align}(M_{g,n}\cdot M_{h,m})(v)&=\frac{1}{n}\sum_{k=0}^{n-1}\pi(g^k)\left( M_{h,m}(v) \right) \\&=\frac{1}{n}\sum_{k=0}^{n-1}\pi(g^k)\left( \frac{1}{m}\sum_{p=1}^{m-1}\pi(h^p)(v) \right)\\&=\frac{1}{nm}\sum_{k=0}^{n-1} \sum_{p=1}^{m-1}(\pi(g^k)\pi(h^p))(v) \\&=\frac{1}{nm}\sum_{k=0}^{n-1} \sum_{p=1}^{m-1}(\pi(g^kh^p))(v) \\&=\frac{1}{nm}\sum_{p=1}^{m-1}\sum_{k=0}^{n-1} (\pi(h^pg^k))(v) \\&=(M_{h,m}\cdot M_{g,n})(v) \end{align}$$
> Therefore, $T\circ S = S\circ T$. 
> 3. **Showing that $\bigcap_{T\in G^{*}}^{}T[A]\neq \varnothing$**:
> As $A$ is compact, $T[A]\subseteq A$ is compact. However, as $E$ is Hausdorff, $T[A]$ is closed. Then, for all $T_{1},\dots,T_{\ell}\in G^{*}$, notice that: $$(T_{1}\circ \dots \circ   T_{\ell})[A]=T_{i}\circ (T_{1}\circ  \dots \circ  T_{i-1}\circ  T_{i+1}\circ  \dots \circ   T_{\ell})[A]\subseteq T_{i}[A]$$Therefore, $$(T_{1}\circ \dots \circ   T_{\ell})[A]\subseteq\bigcap_{i=1}^{\ell}T_{i}[A]\ne \varnothing$$By [[Compact Space|Compact Metric Space Proposition 1]], we have that $\bigcap_{T\in G^{*}}^{}T[A]\neq \varnothing$.
> 4. **Finding the fixed point**:
> Therefore, there exists $y\in \bigcap_{T\in G^{*}}^{}T[A]$. In other words, for all $n\geq 1$, $g\in G$, there exists $x_{g,n}\in A$ s.t. $M_{g,n}(x_{g,n})=y$, i.e. $$y=\frac{1}{n}\sum_{k=0}^{n-1}\pi(g^k)(x_{g,n})$$Then, $$\pi(g)(y)-y=\frac{1}{n}\sum_{k=1}^{n}\pi(g^k)(x_{g,n})-\frac{1}{n}\sum_{k=0}^{n-1}\pi(g^k)(x_{g,n})=\frac{1}{n}\left( \pi(g^n)(x_{g,n})-x_{g,n} \right) $$Therefore, if we let $B_{a}:=\sup_{v\in A}\|v\|_{a}<+\infty$, $$\left\| \pi(g)(y)-y \right\| _{a}\leq \frac{1}{n}(\left\| \pi(g^n)(x_{g,n}) \right\|_{a} +\left\| x_{g,n} \right\|_{a} )\leq \frac{2B_{a}}{n}$$By $n\to0$, we get: $\|\pi(g)(y)-y\|_{a}=0$ for all $a\in A$. Since the seminorms are sufficient, $\pi(g)(y)=y$.
---