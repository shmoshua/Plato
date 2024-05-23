#Definition #FunctionalAnalysis 

> [!definition]
> Let $G$ be a [[Locally Compact Topological Group|locally compact Hausdorff group]]. The ***left/right Haar measure*** $\mu$ is the unique (up to scalars) non-zero left-invariant measure that is finite on compact sets, i.e. $$\mu(gA)=\mu(A),\quad \forall g\in G,A\subseteq G$$
> 
> If $G$ is [[Abelian Group|abelian]] on compact, this measure is also right invariant, known as the ***Haar measure***.

- **Related definition**: The ***left Haar functional*** $\Lambda$ is a function $\Lambda:C_{00}(G)\to \mathbb{C}$ s.t. $\Lambda(\lambda(g)f)=\Lambda(f)$ for all $f\in C_{00}(G)$ and $g\in G$.
- **Related definition**: The ***modular function*** of $G$ is a group homomorphism $\Delta_{G}:G\to \mathbb{R}^\times_{>0}$ s.t. for any left Haar functional $\Lambda$, $$\int_{G}^{} f(xg^{-1}) \, d\mu(x)=\Delta_{G}(g)\int_{G}^{} f \, d\mu, \quad \forall f\in C_{00}(G), g\in G$$
- **Remark**: For $f\in C_{b}(G)$, we have $\|f\|_{b}=\|f\|_{\infty}$, as for all $\Omega \subseteq G$ non-zero open, $\mu(\Omega)>0$.
---
##### Properties

> [!lemma] Theorem 1 (Existence and Uniqueness of Haar Measure, Haar 1933)
> Let $G$ be a [[Locally Compact Topological Group|locally compact Hausdorff group]]. Then, let $\lambda:G\to \text{GL}(C_{00}(G))$ be the [[Representation|left-regular representation]], i.e. for $f\in C_{00}(G)$, $$\lambda(g)f(x)=f(g^{-1}x)$$
> 1. there exists a unique (up to scaling) positive linear functional $\Lambda :C_{00}(G)\to \mathbb{C}$ that is invariant under left translation, i.e.$$\Lambda(\lambda(g)f)=\Lambda(f), \quad \forall f\in C_{00}(G),g\in G$$We call $\Lambda$ the ***left Haar functional***.
> 2. there exists a unique (up to scaling) non-zero positive regular Borel measure $\mu$ on $G$ s.t. for every $A\in \Sigma_{\mu}$, $\mu(gA)=\mu(A)$ for all $g\in G$, called the ***left Haar measure***. It also holds that: $$\Lambda(f)=\int_{G}^{} f \, d\mu $$

> [!proof]-
> We will only prove the uniqueness.
> 
> Let $\mu$ be a left Haar measure and $\nu$ a right Haar measure. Then for $f,g\in C_{0}(G)$ with $\int_{G}^{} f \, d\mu\neq 0$,  $$\begin{align}\left( \int_{G}^{} f \, d\mu  \right)\left( \int_{G}^{} g \, d\nu \right) &=\int_{G}^{} f(t)\left( \int_{G}^{} g(yt) \, d\nu(y)  \right)  \, d\mu(t)\\&=\int_{G}^{} \left( \int_{G}^{} f(t)g(yt) \, d\mu(t)  \right)  \, d\nu(y) \\&=\int_{G}^{} \left( \int_{G}^{} f(y^{-1}x)g(x) \, d\mu(x)  \right)  \, d\nu(y) \\&=\int_{G}^{} \left( \int_{G}^{} f(y^{-1}x)g(x) \, d\nu(y)  \right)  \, d\mu(x)  \end{align}$$ where we can apply Fubini as $f,g\in C_{00}(G)$. Define: $$w_{f}(x)=\frac{1}{\int_{G}^{} f \, d\mu }\int_{G}^{} f(y^{-1}x)\, d\nu(y) $$Then, $$\int_{G}^{} g \, d\nu=\int_{G}^{} w_{f}(x)g(x) \, d\mu(x) $$As the LHS is independent of $f$, using Lemma 2, as $w_{f_{1}}-w_{f_{2}}$ are continuous, we have that $w_{f_{1}}-w_{f_{2}}=0$ for all $f_{1},f_{2}\in C_{00}(G)$. Therefore, there exists $C\in \mathbb{R}^\times$ s.t. $$C\int_{G}^{} f \, d\mu=\int_{G}^{} f(y^{-1}) \, d\nu(y) =\int_{G}^{} f^\vee \, d\nu  $$Now, for $\nu$, there exists a left Haar measure $\mu'$ s.t. $$\int_{G}^{} f^\vee \, d\nu=\int_{G}^{} f \, d\mu'  $$Therefore, $C\mu=\mu'$.
---

> [!lemma] Lemma 2
> Let $G$ be a [[Locally Compact Topological Group|LCH group]] and $\mu$ the left Haar measure. Then, 
> 1. $\text{supp}(\mu)=G$, i.e for all non-empty open $U\subseteq G$, $\mu(U)>0$.
> 3. Any $h\in C(G)$ for which: $$\int_{G}^{} h\cdot \varphi \, d\mu=0,\quad \forall\varphi\in C_{00}(G) $$it holds that $h=0$.
> 4. For $X$ Hausdorff, if $f_{1},f_{2}:G\to X$ are continuous, if $f_{1}(g)=f_{2}(g)$ for $\mu$-a.e. $g\in G$ then $f_{1}\equiv f_{2}$.
> 5. if $0\neq f\in C_{00}(G)$ with $f\geq 0$, then $\int_{G}^{} f \, d\mu>0$.

> [!proof]-
> We have:
> 1. As $\Lambda$ is positive, we know that there exists $f\in C_{00}(G)$ with $f\geq 0$ and $$\Lambda (f)=\int_{G}^{} f \, d\mu >0$$Modulo rescaling, we may assume that $0\leq f\leq 1$. Then, $$\text{supp}(f)\subseteq \bigcup_{g\in G}^{}gU=G$$As the support is compact, there exists $g_{1},..,g_{n}\in G$ s.t. $\text{supp}(f)\subseteq \bigcup_{i=1}^{n}g_{i}U$ and it holds that: $$f\leq \sum_{i=1}^{n}\chi_{g_{i}U}$$Therefore, $$0<\int_{G}^{} f \, d\mu \leq \int_{G}\sum_{i=1}^{n}\chi_{g_{i}U}  \, d\mu=\sum_{i=1}^{n}\mu(g_{i}U)=n\cdot \mu(U)$$
> 2. We will show that $h(e)=0$ and the proof for $h(g)$ for any other $g\in G$ is analogous. Let $\varepsilon>0$. As $h$ is open, there exists an open neighborhood $V\ni e$ s.t. $V\subseteq h^{-1}(B_{<\varepsilon}(h(e)))$. Then, by [[Locally Compact Hausdorff Space|Urysohn's lemma]], there exists $\varphi\in C_{00}(G)$ s.t. $\varphi(e)=1$ and $\varphi\geq 0$ s.t. $\text{supp }\varphi \subseteq V$. Therefore, $$\left| h(e) \right| \left| \int_{G}\varphi(g) \, d\mu(g)  \right|=\left| \int_{G}^{} h(e)\varphi(g) \, d\mu(g)  \right| \leq \int_{G}^{} \left| h(e)-h(g) \right| \left| \varphi(g) \right|  \, d\mu(g)<\varepsilon \int_{G}^{} \varphi(g) \, d\mu(g)   $$and $\left| h(e) \right|<\varepsilon$ for any $\varepsilon>0$. Therefore, $h(e)=0$.
> 3. if $f_{1}\not\equiv f_{2}$, then $U:=\{ x\in G :f_{1}(x)\neq f_{2}(x)\}$ is a non-empty open subset, therefore, $\mu(U)>0$.
> 4. there exists open set $U\subseteq G$ s.t. $f(x)>\varepsilon>0$ on $x\in U$. Then, $$\int_{G}^{} f \, d\mu\geq \int_{U}f\, d\mu>\varepsilon \mu(U)>0  $$ 
---
> [!lemma] Corollary 3
> Let $G$ be a [[Locally Compact Topological Group|LCH group]] and $\text{Aut}(G)$ the group of topological group automorphisms of $G$. Then, 
> 1. there exists a group homomorphism $\text{mod}_{G}:\text{Aut}(G)\to \mathbb{R}^\times_{>0}$ s.t. $$\Lambda(f\circ \alpha ^{-1})=\text{mod}_{G}(\alpha)\Lambda(f),\quad \forall f\in C_{00}(G), \alpha\in \text{Aut}(G)$$
> 2. it holds that the modular function $\Delta_{G}:G\to \mathbb{R}^\times_{>0}, g\mapsto \text{mod}_{G}(\alpha_{g^{-1}})$,  where $\alpha_{g^{-1}}\in \text{Inn}(G)\subseteq \text{Aut}(G)$ is the [[inner automorphism]] $x\mapsto g^{-1}xg$.
> 3. $\Delta$
> 4. $G$ is unimodular, i.e. $\Delta_{G}\equiv 1$, if $G$ is abelian (or compact).

> [!proof]+
> We have:
> 1. For any $\alpha\in \text{Aut}(G)$,  $$\begin{array}{cccc} {}&{C_{00}(G)}&\to&{C_{00}(G)}\\&{f} &\mapsto & {f\circ \alpha ^{-1}} \end{array}{}$$is linear and preserves positivity. If $\Lambda$ is a left Haar functional, define: $$\Lambda_{\alpha}(f):=\Lambda(f\circ \alpha ^{-1})$$Then, $\Lambda_{\alpha}$ is a positive functional on $C_{00}(G)$ and as:$$(\lambda(g)f)(\alpha(x))=f(g^{-1}\cdot \alpha ^{-1}(x))=f(\alpha ^{-1}(\alpha(g^{-1})\cdot x))=\lambda(\alpha(g))(f\circ \alpha ^{-1})(x)$$
>    we have:  $$\Lambda_{\alpha}(\lambda(g)f)=\Lambda(\lambda(\alpha(g))(f\circ \alpha ^{-1}))=\Lambda(f\circ \alpha ^{-1})=\Lambda_{\alpha}(f)$$By uniqueness in Theorem 1, there exists $c_{\Lambda}(\alpha)>0$ s.t. $\Lambda_{\alpha}=c_{\Lambda}(\alpha)\Lambda$.
>    
>    
>    We now show that $c_{\Lambda}(\alpha)$ is independent of the choice of the left Haar functional. Let $\Lambda_{1},\Lambda_{2}$ be two left Haar functionals. Then, by the uniqueness $\Lambda_{2}=k\Lambda_{1}$ for some $k>0$. Then, $$c_{\Lambda_{2}}(\alpha)\Lambda_{2}(f)=\Lambda_{2,\alpha}(f)=\Lambda_{2}(f\circ \alpha ^{-1})=k\Lambda_{1}(f\circ \alpha ^{-1})=k\Lambda_{1,\alpha}(f)=kc_{\Lambda_{1}}(\alpha)\Lambda_{1}(f)=c_{\Lambda_{1}}(\alpha)\Lambda_{2}(f)$$
>    
>    So $c_{\Lambda_{2}}(\alpha)=c_{\Lambda_{1}}(\alpha)=:c(\alpha)$. Further,
> 	- $\Lambda(f\circ(\alpha\beta))=c(\alpha\beta)\Lambda(f)$
> 	- $\Lambda((f\circ\alpha)\circ\beta)=c(\beta)\Lambda(f\circ\alpha)=c(\beta)c(\alpha)\Lambda(f)$
> 
> 	Hence, if $\mu$ is a left Haar measure, then: $$\mu(\alpha(E))=\int_{G}^{} \chi_{\alpha(E)} \, d\mu=\Lambda(\chi_{\alpha(E)})=\Lambda(\chi_{E}\circ \alpha ^{-1})=c(\alpha)\Lambda(\chi_{E})=c(\alpha)\mu(E)$$So define $\text{mod}_{G}(\alpha):=c(\alpha)$.
> 2. Let $\alpha_{g}\in \text{Inn}(G)$. Then, $$\int_{G}^{} f(xg) \, d\mu(x)=\int_{G}^{} f(g^{-1}xg) \, d\mu(x)=\text{mod}_{G}(\alpha_{g})\int_{G}f  \, d\mu  $$Therefore, $\Delta_{G}(g):=\text{mod}_{G}(\alpha_{g^{-1}})$ is the modular function of $G$.
> 3. If $G$ is abelian, $$\int_{G}^{} f(xg^{-1}) \, d\mu(x)=\int_{G}^{} f(g^{-1}x) \, d\mu(x)=\int_{G}^{} f \, d\mu   $$and $\Delta_{G}(g)=1$ for all $g\in G$. 
---
> [!lemma] Proposition 4
> Let $G$ be a [[Locally Compact Topological Group|locally compact Hausdorff group]] and $\mu$ a left Haar measure. If $G$ is abelian, $$\int_{G}^{} f(x ^{-1}) \, d\mu(x)=\int_{G}^{} f(x) \, d\mu(x)  $$

> [!proof]-
> Verify that $f\mapsto \int_{G}^{} f(x ^{-1})d\mu(x)$ is a positive linear functional and: $$\int_{G}^{} f(x ^{-1}) \, d\mu(x)=c\int_{G}^{} f(x) \, d\mu(x)=c^{2} \int_{G}^{}  f(x ^{-1}) \, d\mu(x)   $$Therefore, $c=1$. 
---
##### Right Haar Functional
> [!lemma] Lemma 5
> For $f\in C(G)$, we define $f^\vee(x):=f(x ^{-1})$. Then, for a left Haar functional $\Lambda$, $$\Lambda'(f):=\Lambda(f^\vee)$$defines a right Haar functional.

> [!proof]-
> Let $\mu$ be the left Haar measure representing $\Lambda$. Then, for $f\in C_{00}(G)$, $g\in G$ and right regular represnetation $\rho$, $$\begin{align}\Lambda'(\rho (g)f)&=\Lambda((\rho(g)f)^{\vee})\\&=\int_{G}^{} (\rho(g)f)^{\vee}(x) \, d\mu(x)\\&= \int_{G}^{} \rho(g)f(x ^{-1}) \, d\mu(x)\\&=\int_{G}f(x ^{-1}g) \, d\mu(x)\\&=\int_{G}^{} f^\vee(g^{-1}x) \, d\mu(x)\\&=\int_{G}^{} f^\vee(x) \, d\mu(x)\\&=\Lambda(f^\vee)\\&=\Lambda'(f)    \end{align}$$where the linearly is easily seen.
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
> We have that: 
> 1. For $(\mathbb{R}^n,+)$, $\text{Aut}(\mathbb{R}^n)=\text{GL}(n,\mathbb{R})$ and $\text{mod}_{G}(\alpha)=\left| \det\alpha \right|$ as $\mathcal{L}(\alpha([0,1]^n))=\left| \det\alpha \right|\mathcal{L}([0,1]^n)$.
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
