#Definition #FunctionalAnalysis 

> [!definition]
> Let $G$ be a [[Locally Compact Topological Group|locally compact Hausdorff topological group]]. Then, we can define a left regular representation $\rho:G \to \text{GL}(C_{00}(G))$ as: $$\rho(g)f(x)=f(g^{-1}x)$$
---
##### Properties

> [!lemma] Theorem 1
> Let $G$ be a locally compact Hausdorff topological group. Then, there is up to scaling a unique positive linear functional $\Lambda :C_{00}(G)\to \mathbb{C}$ that is invariant under left translation: $$\Lambda(\rho(g)f)=\Lambda(f), \quad \forall f\in C_{00}(G),g\in G$$Then, $\Lambda$ is called the ***left Haar functional***.

> [!lemma] Corollary 2
> There exists up to a strictly positive scalar multiple, a unique, non-zero positive regular Borel measure $\mu$ on $G$ s.t. for every measurable set $E\subseteq G$ and $g\in G$: $$\mu(gE)=\mu(E)$$ s.t. $$\Lambda(f)=\int_{G}^{} f \, d\mu $$
---
> [!lemma] Lemma 3
> Let $G$ be a locally compact Hausdorff topological group and $\mu$ the left Haar measure. Then, for all non-empty open $U\subseteq G$, $\mu(U)>0$.

> [!proof]-
> We know that there exists $f\in C_{00}(G)$ with $f\geq 0$ and $$\Lambda f=\int_{G}^{} f \, d\mu >0$$Modulo rescaling, we may assume that $0\leq f\leq 1$. Then, $$\text{supp}(f)\subseteq \bigcup_{g\in G}^{}gU=G$$As the support is compact, there exists $g_{1},..,g_{n}\in G$ s.t. $\text{supp}(f)\subseteq \bigcup_{i=1}^{n}g_{i}U$ and it holds that: $$f\leq \sum_{i=1}^{n}\chi_{g_{i}U}$$Therefore, $$0<\int_{G}^{} f \, d\mu \leq \int_{G}\sum_{i=1}^{n}\chi_{g_{i}U}  \, d\mu=\sum_{i=1}^{n}\mu(g_{i}U)=n\cdot \mu(U) $$
---
> [!lemma] Corollary 4
> Let $G$ be a locally compact Hausdorff topological group and $\text{Aut}(G)$ the group of continuous group automorphisms of $G$. Then, there exists a well-defined group homomorphism: $$\text{mod}_{G}:\text{Aut}(G)\to \mathbb{R}_{>0}^\times$$s.t. for any left Haar functional $\Lambda$, $$\Lambda(f\circ \alpha ^{-1})=\text{mod}_{G}(\alpha)\Lambda(f),\quad \forall f\in C_{00}(G),\alpha\in \text{Aut}(G)$$

> [!proof]-
> We have that $$\begin{array}{cccc} {}&{C_{00}(G)}&\to&{C_{00}(G)}\\&{f} &\mapsto & {f\circ \alpha ^{-1}} \end{array}{}$$is linear and preserves positivity. If $\Lambda$ is a left Haar functional, define: $$\Lambda_{\alpha}(f):=\Lambda(f\circ \alpha ^{-1})$$Then, $\Lambda_{\alpha}$ is a positive functional on $C_{00}(G)$ and as:
> $$(\rho(g)f)(\alpha(x))=f(g^{-1}\cdot \alpha ^{-1}(x))=f(\alpha ^{-1}(\alpha(g^{-1})\cdot x))=\lambda(\alpha(g))(f\circ \alpha ^{-1})(x)$$we have:  $$\Lambda_{\alpha}(\rho(g)f)=\Lambda(\rho(\alpha(g))(f\circ \alpha ^{-1}))=\Lambda(f\circ \alpha ^{-1})=\Lambda_{\alpha}(f)$$By uniqueness in Theorem 1, there exists $c_{\Lambda}(\alpha)>0$ s.t. $\Lambda_{\alpha}=c_{\Lambda}(\alpha)\Lambda$.
> 
> Let $\Lambda_{1},\Lambda_{2}$ be two left Haar functionals. Then, by the existence $\Lambda_{2}=k\Lambda_{1}$ for some $k>0$. Then, $$c_{\Lambda_{2}}(\alpha)\Lambda(f)=\Lambda_{2,\alpha}(f)=\Lambda_{2}(f\circ \alpha ^{-1})=k\Lambda_{1}(f\circ \alpha ^{-1})=k\Lambda_{1,\alpha}(f)=kc_{\Lambda_{1}}(\alpha)\Lambda(f)$$
> So $\Lambda(f\circ\alpha)=c(\alpha)\Lambda(f)$ for all $\Lambda$, which is the left Haar measure and:
> - $\Lambda(f\circ(\alpha\beta))=c(\alpha\beta)\Lambda(f)$
> - $\Lambda((f\circ\alpha)\circ\beta)=c(\beta)\Lambda(f\circ\alpha)=c(\beta)c(\alpha)\Lambda(f)$
>   
> Hence, if $\mu$ is a left Haar measure, then: $$\mu(\alpha(E))=\text{mod}_{G}(\alpha)\mu(E)$$So define $\text{mod}_{G}(\alpha)=c(\alpha)$.
---
##### Examples
> [!h] Example 1
> We have that:
> 1. The [[Lebesgue Measure|Lebesgue measure]] $\mathcal{L}$ is the Haar measure of $(\mathbb{R}^n,+)$.
> 2. On $(\mathbb{R}^\times,\cdot)$, the Haar measure is given as $d\mu=d\mathcal{L} (x) / \left| x \right|$
> 3. For a discrete $G$, the Haar measure is the counting measure.
> 4. For a connected Lie group $G$, a non-zero $\omega_{e}:\land^n \text{T}_{e}G\to \mathbb{R}$ gives an orientation on $\text{T}_{e}G$. This defines an orientation/[[volume form]] $$\omega_{g}:=(d_{g}(L_{g^{-1}}))^{*}(\omega_{e})$$

---
> [!h] Example 2
> We have that: 
> 1. For $(\mathbb{R}^n,+)$, $\text{Aut}(\mathbb{R}^n)=\text{GL}(n,\mathbb{R})$ and $\text{mod}_{G}(\alpha)=\left| \det\alpha \right|$ as $\mathcal{L}(\alpha([0,1]^n))=\left| \det\alpha \right|\mathcal{L}([0,1]^n)$.
---
> [!h] Example 3
> Let $K$ be a field with a locally compact Hausdorff topology for which the field operations are continuous, e.g. $\mathbb{R},\mathbb{C},\mathbb{Q}_{p}$ Then, 
> 1. Every $y\in K^\times$ gives rise to: $$\begin{array}{cccc} {m_{y}:}&{K}&\to&{K}\\&{x} &\mapsto & {yx} \end{array}{}$$Then, $m_{y}\in \text{Aut}(K,+)$. 
> 2. There exists a homomorphism: $$\begin{array}{cccc} {}&{K^\times}&\to&{\mathbb{R}^\times_{>0}}\\&{y} &\mapsto & {\left| y \right| } \end{array}{}$$s.t. $\left| y \right|:=\text{mod}_{K}(m_{y})$.
> 3. If $K$ is not discrete, by extending the homomorphism with $\left| 0 \right|=0$, one obtains $K\to \mathbb{R}_{\geq 0}$ which is continuous.
---
> [!h] Example 4
> For $K=\mathbb{Q}_{p}$, we will try to determine its "norm". Then, for every $y\in \mathbb{Q}_{p}^\times$, 
> 1. $y$ can be uniquely written as $y=p^n\cdot u$ where $n\in \mathbb{Z}$ and $u$ is invertible in $\mathbb{Z}_{p}$.
> 2. If $n\leq-1$, in which case $\left| y \right|^{-1}=\left| y^{-1} \right|$, we just need to determine $\left| y^{-1} \right|$ and $y^{-1}\in \mathbb{Z}_{p}$. Therefore, wlog we can assume that $y\in \mathbb{Z}_{p}$. 
>    
>    As $\mathbb{Z}_{p}$ is compact, $\mu(\mathbb{Z}_{p})<+\infty$, where $\mu$ is the left-Haar measure on $\mathbb{Q}_{p}$. Then, $$\mathbb{Z}_{p}=\{ x\in \mathbb{Q}_{p}:\|x\|_{p}<e \}$$Then, $\|\cdot\|_{p}\in \{ e^n:n\in \mathbb{Z} \}\cup \{ 0 \}$
>    
>    Recall $\|y\|_{p}=e^{-n}$ where $y=p^n\cdot u$. Hence, $0<\mu(\mathbb{Z}_{p})<+\infty$.
>    
>    As we know that for $y\in \mathbb{Z}_{p}$: $$\mu(y\cdot \mathbb{Z}_{p})=\left| y \right| \mu(\mathbb{Z}_{p})$$However, as $\text{ker }\varepsilon_{n}=p^n\mathbb{Z}_{p}=p^n\cdot u\mathbb{Z}_{p}=y\cdot \mathbb{Z}_{p}$, $$\mathbb{Z}_{p} / p^n \mathbb{Z}_{p}\cong \mathbb{Z} / p\mathbb{Z}$$ So let $R\subseteq \mathbb{Z}_{p}$ be a complete set of representatives of $\mathbb{Z}_{p} / p^n \mathbb{Z}_{p}$. Then, $$\mathbb{Z}_{p}=\bigsqcup_{r\in R}^{}(r+p^n \mathbb{Z}_{p})$$and $$\mu(\mathbb{Z}_{p})=\sum_{r\in R}^{}\mu(r+p^n \mathbb{Z}_{p})=\left| R \right| \mu(p^n\mathbb{Z}_{p})=p^n\cdot  \mu(p^n\mathbb{Z}_{p})$$Therefore, $$p^{-n}\mu(\mathbb{Z}_{p})=\mu(p^n \mathbb{Z}_{p})=\mu(y\mathbb{Z}_{p})=\left| y \right| \cdot \mu(\mathbb{Z}_{p})$$We can conclude that $\left| y \right|=p^{-n}$.
---
