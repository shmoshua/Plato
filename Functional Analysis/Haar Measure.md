#Definition #FunctionalAnalysis 

> [!definition]
> Let $G$ be a [[Locally Compact Group|LCH group]]. 
> 1. The ***left Haar measure*** $\mu$ is the (up to scalars) unique non-zero left-invariant measure that is finite on compact sets, i.e. $$\mu(gA)=\mu(A),\quad \forall g\in G,A\subseteq G$$
> 2. if a left Haar measure $\mu$ is also right-invariant, it is known as the ***Haar measure***, e.g. when $G$ is abelian or compact.

- **Related definition**: $\lambda:G\to \text{GL}(C_{00}(G))$ is a ***left-regular representation*** given by: $$\lambda(g)f(x)=f(g^{-1}x),\quad \forall f\in C_{00}(G),g,x\in G$$
- **Related definition**: The ***left Haar functional*** $\Lambda$ is a function $\Lambda:C_{00}(G)\to \mathbb{C}$ s.t. $\Lambda(\lambda(g)f)=\Lambda(f)$ for all $f\in C_{00}(G)$ and $g\in G$ where $\lambda$ is the left-regular representation.
- **Related definition**: The ***modular function*** of $G$ is a map $\Delta_{G}:G\to \mathbb{R}^\times_{>0}$ s.t. for any left Haar measure $\mu$, $$\int_{G}^{} f(xg^{-1}) \, d\mu(x)=\Delta_{G}(g)\int_{G}^{} f \, d\mu, \quad \forall f\in C_{00}(G), g\in G$$
- **Remark**: For $f\in C_{b}(G)$, we have $\|f\|_{b}=\|f\|_{\infty}$, as for all $\Omega \subseteq G$ non-zero open, $\mu(\Omega)>0$.
---
##### Properties

> [!lemma] Theorem 1 (Existence and Uniqueness of Haar Measure, Haar 1933)
> Let $G$ be a [[Locally Compact Group|locally compact Hausdorff group]]. Then, let $\lambda:G\to \text{GL}(C_{00}(G))$ be the [[Representation|left-regular representation]], i.e. for $f\in C_{00}(G)$, $$\lambda(g)f(x)=f(g^{-1}x)$$
> 1. there exists a unique (up to scaling) positive linear functional $\Lambda :C_{00}(G)\to \mathbb{C}$ that is invariant under left translation, i.e.$$\Lambda(\lambda(g)f)=\Lambda(f), \quad \forall f\in C_{00}(G),g\in G$$We call $\Lambda$ the ***left Haar functional***.
> 2. there exists a unique (up to scaling) non-zero positive regular Borel measure $\mu$ on $G$ s.t. for every $A\in \Sigma_{\mu}$, $\mu(gA)=\mu(A)$ for all $g\in G$, called the ***left Haar measure***. It also holds that: $$\Lambda(f)=\int_{G}^{} f \, d\mu $$

> [!proof]-
> We have:
> 1. We will only prove the uniqueness.
>    
>    Let $\mu$ be a left Haar measure and $\nu$ a right Haar measure. Then for $f,g\in C_{0}(G)$ with $\int_{G}^{} f \, d\mu\neq 0$,  $$\begin{align}\left( \int_{G}^{} f \, d\mu  \right)\left( \int_{G}^{} g \, d\nu \right) &=\int_{G}^{} f(t)\left( \int_{G}^{} g(yt) \, d\nu(y)  \right)  \, d\mu(t)\\&=\int_{G}^{} \left( \int_{G}^{} f(t)g(yt) \, d\mu(t)  \right)  \, d\nu(y) \\&=\int_{G}^{} \left( \int_{G}^{} f(y^{-1}x)g(x) \, d\mu(x)  \right)  \, d\nu(y) \\&=\int_{G}^{} \left( \int_{G}^{} f(y^{-1}x)g(x) \, d\nu(y)  \right)  \, d\mu(x)  \end{align}$$ where we can apply Fubini as $f,g\in C_{00}(G)$. Define: $$w_{f}(x)=\frac{1}{\int_{G}^{} f \, d\mu }\int_{G}^{} f(y^{-1}x)\, d\nu(y) $$Then, $$\int_{G}^{} g \, d\nu=\int_{G}^{} w_{f}(x)g(x) \, d\mu(x) $$As the LHS is independent of $f$, using Lemma 2, as $w_{f_{1}}-w_{f_{2}}$ are continuous, we have that $w_{f_{1}}-w_{f_{2}}=0$ for all $f_{1},f_{2}\in C_{00}(G)$. Therefore, there exists $C\in \mathbb{R}^\times$ s.t. $$C\int_{G}^{} f \, d\mu=\int_{G}^{} f(y^{-1}) \, d\nu(y) =\int_{G}^{} f^\vee \, d\nu  $$Now, for $\nu$, there exists a left Haar measure $\mu'$ s.t. $$\int_{G}^{} f^\vee \, d\nu=\int_{G}^{} f \, d\mu'  $$Therefore, $C\mu=\mu'$.
---

> [!lemma] Lemma 2
> Let $G$ be a [[Locally Compact Group|LCH group]] and $\mu$ the left Haar measure. Then, 
> 1. $\text{supp}(\mu)=G$, i.e for all non-empty open $U\subseteq G$, $\mu(U)>0$.
> 2. if $0\neq f\in C_{00}(G)$ with $f\geq 0$, then $\int_{G}^{} f \, d\mu>0$.
> 3. Any $h\in C(G)$ for which: $$\int_{G}^{} h\cdot \varphi \, d\mu=0,\quad \forall\varphi\in C_{00}(G) $$it holds that $h=0$.
> 4. For $X$ Hausdorff, if $f_{1},f_{2}:G\to X$ are continuous, if $f_{1}(g)=f_{2}(g)$ for $\mu$-a.e. $g\in G$ then $f_{1}\equiv f_{2}$.


> [!proof]-
> We have:
> 1. As $\Lambda$ is positive, we know that there exists $f\in C_{00}(G)$ with $f\geq 0$ and $$\Lambda (f)=\int_{G}^{} f \, d\mu >0$$Modulo rescaling, we may assume that $0\leq f\leq 1$. Then, $$\text{supp}(f)\subseteq \bigcup_{g\in G}^{}gU=G$$As the support is compact, there exists $g_{1},..,g_{n}\in G$ s.t. $\text{supp}(f)\subseteq \bigcup_{i=1}^{n}g_{i}U$ and it holds that: $$f\leq \sum_{i=1}^{n}\chi_{g_{i}U}$$Therefore, $$0<\int_{G}^{} f \, d\mu \leq \int_{G}\sum_{i=1}^{n}\chi_{g_{i}U}  \, d\mu=\sum_{i=1}^{n}\mu(g_{i}U)=n\cdot \mu(U)$$
> 2. there exists open set $U\subseteq G$ s.t. $f(x)>\varepsilon>0$ on $x\in U$. Then, $$\int_{G}^{} f \, d\mu\geq \int_{U}f\, d\mu>\varepsilon \mu(U)>0  $$ 
> 3. We will show that $h(e)=0$ and the proof for $h(g)$ for any other $g\in G$ is analogous. Let $\varepsilon>0$. As $h$ is continuous, there exists an open neighborhood $V\ni e$ s.t. $V\subseteq h^{-1}(B_{<\varepsilon}(h(e)))$. Then, by [[Locally Compact Hausdorff Space|Urysohn's lemma]], there exists $\varphi\in C_{00}(G)$ s.t. $\varphi(e)=1$ and $\varphi\geq 0$ s.t. $\text{supp }\varphi \subseteq V$. Therefore, $$\left| h(e) \right| \left| \int_{G}\varphi(g) \, d\mu(g)  \right|=\left| \int_{G}^{} h(e)\varphi(g) \, d\mu(g)  \right| \leq \int_{G}^{} \left| h(e)-h(g) \right| \left| \varphi(g) \right|  \, d\mu(g)<\varepsilon \int_{G}^{} \varphi(g) \, d\mu(g)   $$and $\left| h(e) \right|<\varepsilon$ for any $\varepsilon>0$. Therefore, $h(e)=0$.
> 4. if $f_{1}\not\equiv f_{2}$, then $U:=\{ x\in G :f_{1}(x)\neq f_{2}(x)\}$ is a non-empty open subset, therefore, $\mu(U)>0$.
---
> [!lemma] Proposition 3 (Existence of a Modular Function)
> Let $G$ be a [[Locally Compact Group|LCH group]] and $\text{Aut}(G)$ the group of topological group automorphisms of $G$. Then, for any left Haar functional $\Lambda$, 
> 1. there exists a group homomorphism $\text{mod}_{G}:\text{Aut}(G)\to \mathbb{R}^\times_{>0}$ s.t. $$\Lambda(f\circ \alpha ^{-1})=\text{mod}_{G}(\alpha)\Lambda(f),\quad \forall f\in C_{00}(G), \alpha\in \text{Aut}(G)$$
> 2. the modular function is given by $$\Delta_{G}:G\to \mathbb{R}^\times_{>0}, \quad g\mapsto \text{mod}_{G}(\alpha_{g^{-1}})$$where $\alpha_{g}\in \text{Inn}(G)\subseteq \text{Aut}(G)$ is the [[inner automorphism]] $x\mapsto gxg^{-1}$.
> 3. $\Delta_{G}$ is continuous.
> 4. for any $f\in C_{00}(G)$, $$\int_{G}^{} f(x ^{-1} )\Delta_{G}(x ^{-1}) \, d\mu(x)=\int_{G}^{} f(x ) \, d\mu(x)  $$
> 5. $G$ is unimodular, i.e. $\Delta_{G}\equiv 1$, if $G$ is abelian (or compact).

> [!proof]-
> We have:
> 1. For any $\alpha\in \text{Aut}(G)$, the map, $C_{00}(G)\to C_{00}(G),f\mapsto f\circ\alpha ^{-1}$ is linear and preserves positivity. If $\Lambda$ is a left Haar functional, define: $\Lambda_{\alpha}(f):=\Lambda(f\circ \alpha ^{-1})$. Then, $\Lambda_{\alpha}$ is a positive functional on $C_{00}(G)$ and as: $$(\lambda(g)f)(\alpha ^{-1}(x))=f(g^{-1}\alpha ^{-1}(x))=f(\alpha ^{-1}(\alpha(g^{-1})x))=\lambda(\alpha(g))(f\circ \alpha ^{-1})(x)$$ and$$\Lambda_{\alpha}(\lambda(g)f)=\Lambda(\lambda(\alpha(g))(f\circ \alpha ^{-1}))=\Lambda(f\circ \alpha ^{-1})=\Lambda_{\alpha}(f)$$By uniqueness of left Haar functionals, there exists $c_{\Lambda}(\alpha)>0$ s.t. $\Lambda_{\alpha}=c_{\Lambda}(\alpha)\Lambda$.
>        
>    We now show that $c_{\Lambda}(\alpha)$ is independent of the choice of the left Haar functional. Let $\Lambda_{1},\Lambda_{2}$ be two left Haar functionals. Then, by the uniqueness $\Lambda_{2}=k\Lambda_{1}$ for some $k>0$. Then, for $\alpha\in \text{Aut}(G)$, $$\begin{align}c_{\Lambda_{2}}(\alpha)\Lambda_{2}(f)&=\Lambda_{2,\alpha}(f)=\Lambda_{2}(f\circ \alpha ^{-1})\\&=k\Lambda_{1}(f\circ \alpha ^{-1})=k\Lambda_{1,\alpha}(f)=kc_{\Lambda_{1}}(\alpha)\Lambda_{1}(f)=c_{\Lambda_{1}}(\alpha)\Lambda_{2}(f)\end{align}$$
>    
>    So $c_{\Lambda_{2}}(\alpha)=c_{\Lambda_{1}}(\alpha)=:c(\alpha)$. Further,
> 	1. $\Lambda(f\circ(\beta ^{-1}\circ\alpha ^{-1}))=c(\alpha\beta)\Lambda(f)$
> 	2. $\Lambda((f\circ\beta ^{-1})\circ\alpha ^{-1})=c(\alpha)\Lambda(f\circ\beta ^{-1})=c(\alpha)c(\beta)\Lambda(f)$
>   
>     So define $\text{mod}_{G}(\alpha):=c(\alpha)$ and $\text{mod}_{G}$ is a homomorphism. 
> 2. We have that: $$\int_{G}^{} f(xg^{-1}) \, d\mu(x)=\int_{G}^{} f(gxg^{-1}) \, d\mu(x)=\int_{G}^{} (f\circ \alpha_{g^{-1}}^{-1})\, d\mu  =\text{mod}_{G}(\alpha_{g^{-1}})\int_{G}^{} f \, d\mu  $$Hence, $\Delta_{G}(g):=\text{mod}_{G}(\alpha_{g^{-1}})$ is the modular function of $G$. 
> 2. It suffices to show that $\Delta_{G}$ is continuous at $e$. Let $f\in C_{00}(G)$ with $f\geq 0$. Then, $\int_{G}^{} f \, d\mu>0$ from Lemma 2 and we may assume that $\int_{G}^{} f \, d\mu=1$. 
>    
>    Then, $$\left| \Delta_{G}(g)-1 \right| =\left|\text{mod}_{G}(\alpha_{g^{-1}}) \int_{G}^{} f \, d\mu-\int_{G}^{} f \, d\mu \right|=\left| \int_{G}^{} f(xg^{-1})-f(x) \, d\mu(x)  \right|  $$Assume $g\in U=U^{-1}$ open neighborhood of $e$ s.t. $\overline{U}$ is compact. Let $K:=\text{supp }f\cdot \overline{U}$.  Then, if $x\notin K$, $f(x)=f(xg^{-1})=0$. Therefore, $$\left| \Delta_{G}(g)-1 \right| \geq\left| \int_{K}^{}f(xg^{-1})-f(x)  \, d\mu(x)  \right| =\|\rho(g)f-f\|_{\infty}\mu(K)$$However, as $g\mapsto \rho(g)f$ is continuous by [[Uniformly Continuous Function|Lemma 1]], $\Delta_{G}$ is continuous at $1$.
> 4. We have that $f\cdot\Delta_{G}\in C_{00}(G)$. We define: $$I(f):=\int_{G}^{} f(x ^{-1} )\Delta_{G}(x ^{-1}) \, d\mu(x) $$Then, 
> 	- **Claim: $I$ is a left Haar functional**:
> 	  We have: $$\begin{align}I(\lambda(g)f)&=\int_{G}^{} f(g^{-1}x ^{-1})\Delta_{G}(x ^{-1}) \, d\mu(x)\\&=\int_{G}^{} f((xg)^{-1})\Delta_{G}((xg)^{-1}) \, d\mu(x)\Delta_{G}(g)\\&= \int_{G}^{} f(x^{-1} )\Delta_{G}(x ^{-1}) \, d\mu(x)\Delta_{G}(g)\Delta_{G}(g^{-1})\\&= \int_{G}^{} f(x^{-1} )\Delta_{G}(x ^{-1}) \, d\mu(x)\\&=I(f)\end{align} $$
> 	  
> 	 Therefore, there exists $c\in \mathbb{R}_{>0}$ s.t. $\int_{G}^{} f(x ^{-1})\Delta_{G}(x ^{-1}) \, d\mu(x)=c\int_{G}^{} f(y) \, d\mu(y)$. We claim that $c=1$. Consider $g(x):=f(x ^{-1})\Delta_{G}(x ^{-1} )$. Then, $$\begin{align}\int_{G}^{} f(x) \, d\mu(x)&=\int_{G}^{} f(x)\Delta_{G}(x)\Delta_{G}(x ^{-1})\, d\mu(x)\\&=\int_{G}^{} g(x ^{-1})\Delta_{G}(x ^{-1})\, d\mu(x)\\&=c\int_{G}^{} f(x ^{-1})\Delta_{G}(x ^{-1}) \, dx\\&=c^{2}\int_{G}^{} f(x) \, d\mu(x)  \end{align} $$Therefore, $c^{2}=1$ and $c=1$.
> 5. We have that for any $g\in G$, $$\Delta_{G}(g)\int_{G}^{} f \, d\mu=\int_{G}^{} f(xg^{-1}) \, d\mu(x)=\int_{G}^{} f(g^{-1}x) \, d\mu(x)=\int_{G}^{} f \, d\mu    $$and $\Delta_{G}(g)=1$.
---
> [!lemma] Proposition 4
> For an LCH group $G$, the following are equivalent:
> 1. $G$ is compact.
> 2. $G$ has a finite left/right Haar measure.

> [!proof]-
> We have: 
> 1. If $G$ is compact, then for any left Haar measure $\mu$, due to the inner regularity of $\mu$, we have: $$\mu(G)<+\infty$$
> 2. Conversely, if $\mu(G)<+\infty$, by inner regularity, there exists $K$ compact s.t. $$\mu(K)> \frac{1}{2}\mu(G)$$Then, for any $g\in G$, $gK\cap K\neq \varnothing$. Indeed, otherwise, $$\mu(gK \cup K)=\mu(gK)+\mu(K)=2\mu(K)>\mu(G)$$which is a contradiction. Therefore, $g\in KK ^{-1}$ and $G=KK ^{-1}$. Therefore, $G$ is compact.
---
> [!lemma] Lemma 5 (Left-regular representation and uniform continuity)
> Let $G$ be a LCH group and $\lambda:G\to C_{00}(G)$  left-regular representation, i.e. $\lambda(g)f(x)=f(g^{-1}x)$.
> 1. $G\to C_{00}(G),x\mapsto \lambda(x)f$ is [[Uniformly Continuous Function|left uniformly continuous]] w.r.t. $\|\cdot\|_{b}$ for all $f\in C_{00}(G)$.
> 2. $G\to L^p(G),x\mapsto \lambda(x)f$ is left uniformly continuous w.r.t. $\|\cdot\|_{p}$ for all $f\in L^p(G)$ where $1\leq p<+\infty$.

^9177e0

> [!proof]+
> We have: 
> 1. For $x,y\in G$, from translation invariance, we have $\|\lambda(x)f-\lambda(y)f\|_{b}=\|\lambda(y^{-1}x)f-f\|_{b}$. Therefore, we are reduced to show that for every $\varepsilon>0$, there exists $W\ni e$ open s.t. $$\left| f(zg)-f(g) \right| <\varepsilon,\quad \forall g\in G,z\in W$$Let $K:=\text{supp}(f)$ and there exists $V_{0}\ni e$ open s.t. $V_{0}=V_{0}^{-1}$ and $\overline{V_{0}}$ compact. Fix $\varepsilon>0$. Then, for all $x\in G$, we can find $V_{x}\ni e$ open, with $V_{x}\subseteq V_{0}$ s.t. $$\left| f(zx)-f(x) \right| <\varepsilon /2,\quad \forall z\in V_{x}$$Let $U_{x}\ni e$ open with $U_{x}^{2}\subseteq V_{x}$. Then, we have: $$\overline{V_{0}}\cdot K \subseteq \bigcup_{x\in G}^{}U_{x}\cdot x=G$$Since $\overline{V_{0}}\cdot K$ is compact, there exists $x_{1},\dots,x_{n}\in G$ s.t. $$\overline{V_{0}}\cdot K\subseteq \bigcup_{i=1}^{n}U_{x_{i}}\cdot x_{i}$$Let $W:=\bigcap_{i=1}^{n}U_{x_{i}}$ and $z\in W$ and $g\in G$: 
> 	1. if $g\notin \overline{V_{0}}\cdot K$, then since $\text{supp}(f)\subseteq \overline{V_{0}}\cdot K$, $f(g)=0$. Further, if $f(zg)\neq 0$, then $zg\in \text{supp}(f)$ and $g\in z^{-1}\text{supp}(f)\subseteq W^{-1}\text{supp}(f)$. However, $W\subseteq V_{0}$ and $W^{-1}\subseteq V_{0}^{-1}=V_{0}$. This is a contradiction and $f(zg)=0$. Therefore, $\left| f(zg)-f(g) \right|=0$.
> 	2. if $g\in \overline{V_{0}}\cdot K\subseteq \bigcup_{x=1}^{n}U_{x_{i}}x_{i}$, then $g\in U_{x_{i}}x_{i}$ for some $i\in[n]$. Then, as $U_{x_{i}}\subseteq U_{x_{i}}^{2}\subseteq V_{x_{i}}$, $$\left| f(g)-f(x_{i}) \right|=\left| f(zx_{i})-f(x_{i}) \right| <\varepsilon /2  $$If $z\in W\subseteq U_{x_{i}}$, then $zg\in U_{x_{i}}^{2} x_{i}\subseteq V_{x_{i}}\cdot x_{i}$ Therefore, $$\left| f(zg)-f(x_{i}) \right| <\varepsilon /2$$This shows that $\left| f(zg)-f(g) \right|<\varepsilon$.
> 2. Let $1\leq p<+\infty$. We will use that $C_{00}(G)$ is dense in $L^p(G)$. For $f\in L^p$ and $\varepsilon>0$, pick $g\in C_{00}(G)$ s.t. $\|f-g\|_{p}<\varepsilon$. Then, $$\begin{align}\left\| \lambda(x)f-\lambda(y)f \right\| _{p}&=\left\| \lambda(x)(f-g)+\lambda(x)g-\lambda(y)g+\lambda(y)(g-f) \right\|\\&\leq 2\|f-g\|_{p}+\|\lambda(x)g-\lambda(y)g\|_{p}\\&<2\varepsilon+\|\lambda(x)g-\lambda(y)g\|_{p}\end{align} $$Then, $$\|\lambda(x)g-\lambda(y)g\|_{p}^p=\|\lambda(y^{-1}x)g-g\|^p_{p}=\int_{G}^{} \left| g(x ^{-1}yt)-g(t) \right|^p  \, d\mu(t) $$Fix $V_{0}=V_{0}^{-1}\ni e$ open with $\overline{V_{0}}$ compact and restrict $y^{-1}x\in \overline{V_{0}}$. Let $C:=\overline{V_{0}}\cdot \text{supp}(g)$. 
> 		1. if $t\notin C$, then $g(x ^{-1}yt)=0$ and $g(t)=0$. 
> 		   
> 		Therefore, $$\|\lambda(x)g-\lambda(y)g\|_{p}^p=\int_{C}\left| \lambda(y^{-1}x)g(t)-g(t) \right| ^p  \, d\mu(t)\leq \|\lambda(y^{-1}x)g-g\|_{\infty}\cdot \mu(C) $$Now we are done because there exists $W\ni e$ open s.t.  $$\|\lambda(y^{-1}x)g-g\|_{\infty}< \varepsilon /\mu(C),\quad \forall y^{-1}x\in W$$
---

##### Right Haar Functional
> [!lemma] Lemma 5
> For $f\in C(G)$, we define $f^\vee(x):=f(x ^{-1})$. Then, for a left Haar functional $\Lambda$, $$\Lambda'(f):=\Lambda(f^\vee)$$defines a right Haar functional.

> [!proof]-
> Let $\mu$ be the left Haar measure representing $\Lambda$. Then, for $f\in C_{00}(G)$, $g\in G$ and right regular represnetation $\rho$, $$\begin{align}\Lambda'(\rho (g)f)&=\Lambda((\rho(g)f)^{\vee})\\&=\int_{G}^{} (\rho(g)f)^{\vee}(x) \, d\mu(x)\\&= \int_{G}^{} \rho(g)f(x ^{-1}) \, d\mu(x)\\&=\int_{G}f(x ^{-1}g) \, d\mu(x)\\&=\int_{G}^{} f^\vee(g^{-1}x) \, d\mu(x)\\&=\int_{G}^{} f^\vee(x) \, d\mu(x)\\&=\Lambda(f^\vee)\\&=\Lambda'(f)    \end{align}$$where the linearity is easily seen.
---
> [!lemma] Proposition 6
> If there exists a left Haar measure $\mu$ that is also right Haar measure, $G$ is unimodular, i.e. $\Delta_{G}\equiv 1$.

> [!proof]-
> We have that: $$\Delta_{G}(g)\int_{G}^{} f \, d\mu=\text{mod}_{G}(\alpha_{g ^{-1}})\int_{G}^{} f \, d\mu =\int_{G}^{} f (gxg ^{-1}) \, d\mu =\int_{G}^{}\rho(g^{-1})f\, d\mu =\int_{G}^{} f \, d\mu  $$Therefore, $\Delta_{G}\equiv 1$.
---

##### Examples
> [!h] Example 1 (Simple Haar Measures)
> We have that:
> 1. The [[Lebesgue Measure|Lebesgue measure]] $\mathcal{L}$ is the Haar measure of $(\mathbb{R}^n,+)$.
> 2. On $(\mathbb{R}^\times,\cdot)$, the Haar measure is given as $d\mu=d\mathcal{L} (x) / \left| x \right|$
> 3. For a discrete $G$, the Haar measure is the counting measure.
> 4. For a connected Lie group $G$, a non-zero $\omega_{e}:\land^n \text{T}_{e}G\to \mathbb{R}$ gives an orientation on $\text{T}_{e}G$. This defines an orientation/[[volume form]] $$\omega_{g}:=(d_{g}(L_{g^{-1}}))^{*}(\omega_{e})$$

---
> [!h] Example 2 (Modular Function for Rn)
> For $(\mathbb{R}^n,+)$
> 1. $\text{Aut}(\mathbb{R}^n)\cong\text{GL}(n,\mathbb{R})$ from [[General Linear Group|Proposition 2]] and
> 2. $\text{mod}_{G}(\alpha)=\left| \det\alpha \right|$.
> 3. There exists a discontinuous bijective homomorphism from $(\mathbb{R},+)$ to itself.

> [!proof]-
> As the Lebesgue measure is the Haar measure, for any $A\in \text{GL}(n,\mathbb{R})$ and $f\in C_{00}(\mathbb{R}^n)$, $$\int_{\mathbb{R}^n}^{} f(A^{-1}x) \, dx=\left| \det(A) \right| \int_{\mathbb{R}^n}^{} f(A^{-1}x)\left| \det(A^{-1}) \right|  \, dx =\left| \det(A) \right| \int_{\mathbb{R}^n}^{} f(x) \, dx  $$
> 
---
> [!h] Example 3
> Let $K$ be a field with a locally compact Hausdorff topology for which the field operations are continuous, e.g. $\mathbb{R},\mathbb{C},\mathbb{Q}_{p}$ Then, 
> 1. Every $y\in K^\times$ gives rise to: $$\begin{array}{cccc} {m_{y}:}&{K}&\to&{K}\\&{x} &\mapsto & {yx} \end{array}{}$$with $m_{y}\in \text{Aut}(K,+)$. 
> 2. There exists a homomorphism: $$\begin{array}{cccc} {}&{K^\times}&\to&{\mathbb{R}^\times_{>0}}\\&{y} &\mapsto & {\left| y \right| } \end{array}{}$$s.t. $\left| y \right|:=\text{mod}_{K}(m_{y})$.
> 3. If $K$ is not discrete, by extending the homomorphism with $\left| 0 \right|=0$, one obtains $K\to \mathbb{R}_{\geq 0}$ which is continuous.
---
> [!h] Example 4
> In $K=\mathbb{Q}_{p}$, for every $y\in \mathbb{Q}_{p}^\times$, $$\left| y \right| =p^{-n}$$

> [!proof]-
> We have that $y$ can be uniquely written as $y=p^n\cdot u$ for $n\in \mathbb{Z}$ and $u$ invertible in $\mathbb{Z}_{p}$. 
> 
> Assume $n<0$. Then, $\left| y \right|^{-1}=\left| y ^{-1}\right|$ and we have that $y^{-1}=p^{-n}u^{-1}\in \mathbb{Z}_{p}$. Therefore, we may assume wlog that $n\geq 0$, i.e. $y\in \mathbb{Z}_{p}$. 
> 
> As $\mathbb{Z}_{p}$ is compact, $\mu(\mathbb{Z}_{p})<+\infty$, where $\mu$ is the left Haar measure on $\mathbb{Q}_{p}$. We have $$\mathbb{Z}_{p}=\{ x\in \mathbb{Q}_{p}:\|x\|_{p}<e \}$$which is open. Hence, $0<\mu(\mathbb{Z}_{p})<+\infty$.
> 
> As we know that for $y\in \mathbb{Z}_{p}$: $$\mu(y\cdot \mathbb{Z}_{p})=\mu(m_{y}(\mathbb{Z}_{p}))=\text{mod}_{\mathbb{Q}_{p}}(m_{y})\mu(\mathbb{Z}_{p})=\left| y \right| \mu(\mathbb{Z}_{p})$$However, as $\text{ker }\varepsilon_{n}=p^n\mathbb{Z}_{p}=p^n\cdot u\mathbb{Z}_{p}=y\cdot \mathbb{Z}_{p}$, let $R\subseteq \mathbb{Z}_{p}$ be a complete set of representatives of $\mathbb{Z}_{p} / p^n \mathbb{Z}_{p}$. Then, $$\mathbb{Z}_{p}=\bigsqcup_{r\in R}^{}(r+p^n \mathbb{Z}_{p})$$and $$\mu(\mathbb{Z}_{p})=\sum_{r\in R}^{}\mu(r+p^n \mathbb{Z}_{p})=\left| R \right| \mu(p^n\mathbb{Z}_{p})=p^n\cdot  \mu(p^n\mathbb{Z}_{p})$$Therefore, $$p^{-n}\mu(\mathbb{Z}_{p})=\mu(p^n \mathbb{Z}_{p})=\mu(y\mathbb{Z}_{p})=\left| y \right| \cdot \mu(\mathbb{Z}_{p})$$We can conclude that $\left| y \right|=p^{-n}$.
---
> [!h] Example 5 (Heisenberg Group)
> Consider the three-dimensional ***Heisenberg group*** $H:=\mathbb{R} \rtimes_{\eta}\mathbb{R}^{2}$ where $\eta:\mathbb{R}\to \text{Aut}(\mathbb{R}^{2})$ is given as: $$\eta(x)\begin{bmatrix}y\\z\end{bmatrix}=\begin{bmatrix}y\\z+xy\end{bmatrix}$$Then, the group operation is defined as:$$(x_{1},y_{1},z_{1})*(x_{2},y_{2},z_{2})=(x_{1}+x_{2},y_{1}+y_{2},z_{1}+z_{2}+x_{1}y_{2})$$Therefore, it can be identified with: $$H\cong\left\{ \begin{bmatrix}1&x&z\\0&1&y\\0&0&1\end{bmatrix}:x,y,z\in \mathbb{R} \right\}$$Then, we have:
> 1. Lebesgue measure is the Haar measure of $H$.
> 2. $H$ is unimodular.

> [!proof]-
> Let $f\in C_{00}(H)$ and $h=(x_{1},y_{1},z_{1})\in H$. Then, $$\begin{align}\int_{H}^{} \lambda(h^{-1})(f) \, d\mu&= \int_{\mathbb{R}}^{} \int_{\mathbb{R}} \int_{\mathbb{R}}  f(h(x_{2},y_{2},z_{2})) \, dx_{2} dy_{2}dz_{2}\\&=\int_{\mathbb{R}}^{} \int_{\mathbb{R}}^{} \int_{\mathbb{R}}^{} f(x_{1}+x_{2},y_{1}+y_{2},z_{1}+z_{2}+x_{1}y_{2}) \, dx_{2}  \, dy_{2}  \, dz_{2}\\&=\int_{\mathbb{R}}^{} \int_{\mathbb{R}}^{} \int_{\mathbb{R}}^{} f(x_{1}+x_{2},y_{1}+y_{2},z_{2}) \, dx_{2}  \, dy_{2}  \, dz_{2}\\&=\int_{\mathbb{R}}^{} \int_{\mathbb{R}}^{} \int_{\mathbb{R}}^{} f(x_{1}+x_{2},y_{2},z_{2}) \, dx_{2}  \, dy_{2}  \, dz_{2}\\&=\int_{\mathbb{R}}^{} \int_{\mathbb{R}}^{} \int_{\mathbb{R}}^{} f(x_{2},y_{2},z_{2}) \, dx_{2}  \, dy_{2}  \, dz_{2}\\&=\int_{H}^{} f \, d\mu  \end{align} $$Similarly, one can show the right invariance and therefore it is unimodular.
---
> [!h] Example 6
> Consider: $$P:=\left\{ \begin{bmatrix}a&b\\0&a^{-1}\end{bmatrix}: a,b\in \mathbb{R} , a\neq 0\right\}$$Then, 
> 1. $\frac{da}{a^{2}}db$ is the left Haar measure.
> 2. $dadb$ is the right Haar measure.

> [!proof]-
> Let $h=(a,b)$ and $f\in C_{00}(P)$. Then, $$\begin{align}\int_{P}^{} \lambda(h ^{-1})(f) \, d\mu&=\int_{\mathbb{R}}^{} \int_{\mathbb{R} \backslash \{ 0 \}}\frac{f(ax,ay+bx ^{-1})}{x^2} \, dxdy\\&=\int_{\mathbb{R}}^{} \int_{\mathbb{R} \backslash \{ 0 \}}\frac{f(u,v+abu ^{-1})}{u^2}\, dudv\\&=\int_{\mathbb{R}}^{} \int_{\mathbb{R} \backslash \{ 0 \}}\frac{f(u,v)}{u^2}\, dudv\\&=\int_{P}^{} f \, d\mu \end{align} $$and $$\begin{align}\int_{P}^{} \rho(h^{-1})(f) \, d\mu&=\int \int f(ax,bx+ay^{-1})\, dx  \, dy\\&=\int \int f(u,ba^{-1}x+v)\, du  \, dv\\&=\int \int f(u,v)\, du  \, dv \end{align}$$
---
> [!h] Example 7
>  Let $\lambda_{n^{2}}$ be the Lebesgue measure for $\mathbb{R}^{n^{2}}$. Then, 
>  1. For $G:=\text{GL}(n,\mathbb{R})$, $\left| \det x \right|^{-n}d\lambda_{n^{2}}(x)$ is the left and right Haar measure.
>  2. For $G:=\text{SL}(n,\mathbb{R})$, $\mu(B):=\lambda_{n^{2}}([0,1]\cdot B)$ is the left and right Haar measure.

> [!proof]-
> We have 
> 1. for $h\in \text{GL}(n,\mathbb{R})$ and $f\in C_{00}(\text{GL}(n,\mathbb{R}))$ $$\begin{align}\int_G \lambda(h^{-1})f(x) \left| \det x \right| ^{-n} \, d\lambda_{n^{2}}(x)&=\int_{G}^{}f(hx) \left| \det x \right| ^{-n} \, d\lambda_{n^2}(x) \\&=\int_{G}^{}f(hx) \left| \det h \right| ^n\left| \det hx \right| ^{-n} \, d\lambda_{n^2}(x) \\&=\int_{G}^{} f(x)\left| \det x \right| ^{-n} d\lambda_{n^{2}}(x)\end{align} $$
> and
> $$\begin{align}\int_{G}^{} \rho(h^{-1})f(x)\left| \det x^{-n} \right|  \, d\lambda_{n^{2}}(x)&=\int_{G}^{} f(xh)\left| \det x \right|^{-n}  \, d\lambda_{n^{2}}(x)\\&=\int_{G}^{} f((h^\top x^\top)^\top)\left| \det h^\top \right| ^n\left| \det h^\top x^\top \right| ^{-n} \, d\lambda_{n^{2}}(x) \\&=\int_{G}^{} f(( x^\top)^\top)\left| \det  x^\top \right| ^{-n} \, d\lambda_{n^{2}}(x) \\&=\int_{G}^{} f(x)\left| \det x \right| ^{-n} \, d\lambda_{n^{2}}(x) \end{align} $$
> 2. for $h\in \text{SL}(n,\mathbb{R})$ and $f\in C_{00}(\text{SL}(n,\mathbb{R}))$, $$\begin{align}\int_{G}\lambda(h^{-1})f \, d\mu&=\int_{G}^{} f(hx) \, d\mu(x) \end{align} $$
---
> [!h] Example 8
> Let $$G:=\left\{ \begin{bmatrix}a&b\\0&1\end{bmatrix}:a\in \mathbb{R}^\times,b\in \mathbb{R}\right \}$$Then, we can represent this group as $(\alpha,\beta):=\left( a, \frac{b}{a} \right)$ and $d\mu(\alpha,\beta)= \frac{1}{\left| \alpha \right|}d\alpha d\beta$ defines a left Haar measure.

> [!proof]-
> We have for $h=(\alpha,\beta)$ and $f\in C_{00}(G)$, $$\begin{align}\int_{G}^{} \lambda(h^{-1})f(x,y) \, d\mu(x,y)&=\int_{G}^{} \frac{f(\alpha x,y+x ^{-1}\beta)}{\left| x \right| }\, dxdy\\&=\int_G \frac{f(\alpha x,y+x ^{-1}\beta)}{\left| \alpha x \right| }\left| \alpha \right|  \, dxdy\\&=\int_G \frac{f(x,y+x ^{-1}\alpha\beta)}{\left| x\right| } \, dxdy \\&=\int_G \frac{f(x,y)}{\left| x\right| } \, dydx   \end{align}$$To find the modular function, $h^{-1}=\left( \frac{1}{\alpha},-\alpha\beta \right)$. Then, $$\begin{align}\int_{G}^{} \frac{f\left( \frac{x}{\alpha}, -\alpha\beta +\alpha y\right)}{\left| x \right| } \, dxdy&=\int_{G}^{} \frac{f(x,-\alpha\beta+y)}{\left| \alpha x \right| } \, dxdy=\frac{1}{\left| \alpha \right|}\int_{G}^{} \frac{f(x,y)}{\left| x \right| } \, dx dy \end{align} $$Therefore, $\Delta_{G}(\alpha,\beta)=\frac{1}{\left| \alpha \right|}$.