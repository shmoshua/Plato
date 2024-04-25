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

> [!proof]+
> We have that $$\begin{array}{cccc} {}&{C_{00}(G)}&\to&{C_{00}(G)}\\&{f} &\mapsto & {f\circ \alpha ^{-1}} \end{array}{}$$is linear and preserves positivity. If $\Lambda$ is a left Haar functional, define: $$\Lambda_{\alpha}(f):=\Lambda(f\circ \alpha ^{-1})$$Then, $\Lambda_{\alpha}$ is a positive functional on $C_{00}(G)$ and as:
> $$(\rho(g)f)(\alpha(x))=f(g^{-1}\cdot \alpha ^{-1}(x))=f(\alpha ^{-1}(\alpha(g^{-1})\cdot x))=\lambda(\alpha(g))(f\circ \alpha ^{-1})(x)$$we have:  $$\Lambda_{\alpha}(\rho(g)f)=\Lambda(\rho(\alpha(g))(f\circ \alpha ^{-1}))=\Lambda(f\circ \alpha ^{-1})=\Lambda_{\alpha}(f)$$By uniqueness in Theorem 1, there exists $c_{\Lambda}(\alpha)>0$ s.t. $\Lambda_{\alpha}=c_{\Lambda}(\alpha)\Lambda$.
> 
> Let $\Lambda_{1},\Lambda_{2}$ be two left Haar functionals. Then, by the existence $\Lambda_{2}=k\Lambda_{1}$ for some $k>0$. Then, $$c_{\Lambda_{2}}(\alpha)\Lambda(f)=\Lambda_{2,\alpha}(f)=\Lambda_{2}(f\circ \alpha ^{-1})=k\Lambda_{1}(f\circ \alpha ^{-1})=k\Lambda_{1,\alpha}(f)=kc_{\Lambda_{1}}(\alpha)\Lambda(f)$$
---
##### Examples
> [!h] Example 1
> We have that:
> 1. The [[Lebesgue Measure|Lebesgue measure]] $\mathcal{L}$ is the Haar measure of $(\mathbb{R}^n,+)$.
> 2. On $(\mathbb{R}^\times,\cdot)$, the Haar measure is given as $d\mu=d\mathcal{L} (x) / \left| x \right|$
> 3. For a discrete $G$, the Haar measure is the counting measure.
> 4. For a connected Lie group $G$, a non-zero $\omega_{e}:\land^n \text{T}_{e}G\to \mathbb{R}$ gives an orientation on $\text{T}_{e}G$. This defines an orientation/[[volume form]] $$\omega_{g}:=(d_{g}(L_{g^{-1}}))^{*}(\omega_{e})$$

