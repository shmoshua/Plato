#Definition #FunctionalAnalysis 

> [!definition]
> A [[topological group]] $G$ is ***LCA/locally compact abelian*** if:
> 1. $G$ is abelian
> 2. $G$ is [[Locally Compact Hausdorff Space|locally compact Hausdorff]].
---
##### Properties
> [!lemma] Theorem 1 (Properties of LCA groups)
> Let $G$ be LCA. Then, 
> 1. for $f\in L^1(G)$ and $g\in L^\infty(G)$, $f*g$ is bounded and uniformly continuous.
> 2. for $f,g\in C_{00}(G)$, $f*g\in C_{00}(G)$ and $\text{supp}(f*g)\subseteq \text{supp}(f)\cdot \text{supp}(g)$.
> 3. for $1<p<\infty$ and $f\in L^p(G)$ and $g\in L^q(G)$, $f*g\in C_{0}(G)$.

> [!proof]-
> We have that:
> 1. Firstly, $$\left| f*g(x) \right|\leq \int_{G}^{} \left| f(xy)g(y^{-1}) \right|  \, d\mu(y)= \left\| f \right\|_{1}\left\| g \right\| _{\infty}  $$Secondly, $$\begin{align}\left| (f*g)(x) -(f*g)(z)\right|&\leq \int_{G}^{} \left| f(xy)-f(zy) \right| \left| g(y^{-1}) \right|  \, d\mu(y)\\&\leq \left\| \lambda(x ^{-1}) f-\lambda(z ^{-1})y \right\| \left\| g \right\| _{\infty} \end{align} $$where $\lambda$ is the [[Haar Measure|left-regular representation]]. Therefore, by [[Haar Measure|Lemma 5]], there exists $U\ni e$ s.t. if $z^{-1}x$ then $\left\| \lambda(x)f-\lambda(z)f \right\|<\varepsilon / \left\| g \right\|_{\infty}$. By taking $U^{-1}$ we have our statement.
> 2. $f*g$ is continuous by 1. Now, if $(f*g)(x)\neq 0$, then there exists $y\in G$ s.t. $f(xy)\neq 0$ and $g(y^{-1})\neq 0$ where $x=xyy^{-1}$. Hence, $x\in \text{supp}(f)\text{supp}(g)$.
> 3. If $f\in L^p(G)$ and $g\in L^q(G)$, since $G$ is abelian, $y\mapsto g(y^{-1})$ is in $L^q(G)$ too. Therefore, by Hölder, $y\mapsto f(xy)g(y^{-1})$ is in $L^1(G)$ and $f*g$ is well-defined. 
>    
>    Now let $(f_{n})_{n}\subseteq C_{00}(G)$ and $(g_{n})_{n}\subseteq C_{00}(G)$ s.t. $f_{n}\to f$ in $L^p$ and $g_{n}\to g$ in $L^q$. Then, $$\begin{align}\left| f*g(x)-f_{n}*g_{n}(x) \right|&\leq \left| (f-f_{n})*g(x) \right|+\left| f_{n}*(g_{n}-g)(x) \right|\\&\leq \left\| f-f_{n} \right\| _{p}\left\| g \right\| _{q}+\left\| f_{n} \right\| _{p}\left\| g_{n}-g \right\| _{q}  \end{align} $$Therefore, $\left\| f*g-f_{n}*g_{n} \right\|_{b}$ converges to $0$. As $f_{n}*g_{n}\in C_{00}(G)$, $f*g\in C_{0}(G)$. 
---
> [!lemma] Theorem 1 (Bochner)
> Let $G$ be a LCA group and $\Phi:G\to \mathbb{C}$ continuous positive definite. Then, there exists a unique positive bounded measure $\mu$ on $\widehat{G}$ s.t. $$\Phi(x)=\int_{\widehat{G}}^{} (x,\chi) \, d\mu(\chi),\quad \forall x\in G $$

^074e1a

> [!proof]-
> As $\Phi$ is positive definite, from [[Positive Definite Function on a Group|Lemma 1]], we know that $\Phi(e)\in \mathbb{R}$. If $\Phi(e)\leq 0$, then $\Phi \equiv 0$ by the same Lemma and we may take the zero measure. Therefore, we may assume that $\Phi(e)>0$. Modulo rescaling, we may assume that $\Phi(e)=1$. 
> 
> Now let: $$T_{\Phi}(f):=\int_{G}^{} f(x)\Phi(x) \, d\lambda(x),\quad \forall f\in L^1(G) $$where $\lambda$ is a fixed Haar measure on $G$. As $\Phi\in L^\infty(G)$ with $\|\Phi\|_{\infty}=\Phi(e)=1$, this is a continuous linear functional with $\|T_{\Phi}\|\leq\|\Phi\|_{\infty}=1$. Indeed,$$\left| T_{\Phi}(f) \right| \leq \int_{G}^{} \left| f(x) \right| \left| \Phi(x) \right|  \, d\lambda(x)\leq\|f\|_{1}\|\Phi\|_{\infty} $$Let us define a Hermitian form on $L^1(G)$, $[f,g]:=T_{\Phi}(f*g^{*})$. Then, 
> 1. **Claim 1: $[f,f]\geq 0$ for all $f\in L^1(G)$**.
>    We have: $$\begin{align}[f,f]&=T_{\Phi}(f*f^{*})=\int_{G}^{} \int_{G}^{} f(xy)\overline{f(y)} \, d\lambda(y)  \Phi(x)\, d\lambda(x)\\&=\int_{G}^{} \left( \int_{G}^{} f(xy)\Phi(x) \, d\lambda(x) \right)\overline{f(y)}  \, d\lambda(y)  =\int_{G}^{} \left( \int_{G}^{} f(x)\Phi(y^{-1}x) \, d\lambda(x) \right)\overline{f(y)}  \, d\lambda(y)  \end{align}$$If $f\in C_{00}(G)$, then from [[Uniformly Continuous Function|uniform continuity]] of $(x,y)\mapsto f(x)\overline{f(y)}\Phi(y^{-1}x)$ on $K\times K$ for $K:=\text{supp }f$, we can partition $K=\bigsqcup_{i=1}^{n}E_{i}$ where $E_{i}$ are bounded sets s.t. $$\sum_{i,j=1}^{n}f(x_{i})\overline{f(x_{j})}\Phi(x_{j}^{-1}x_{i})\lambda(E_{i})\lambda(E_{j}),\quad x_{i}\in E_{i}$$approximates the integral. From the positive definiteness, therefore, $[f,f]\geq 0$. By density of $C_{00}(G)$ in $L^1(G)$ and the continuity of $f\mapsto T_{\Phi}(f*f^{*})$, we prove the claim.
> 2. **Claim 2: $\left| [f,g] \right|^{2}\leq[f,f][g,g]$ for all $f,g\in L^1(G)$**:
>    This is a consequence of $[f,f]\geq 0$ for all $f\in L^1(G)$.
>  3. **Claim 3: $\left| T_{\Phi}(f) \right|^{2}\leq[f,f]=T_{\Phi}(f*f^{*})$ for all $f\in L^1(G)$**.
>     We have: $$\begin{align}[f,g]=\int_{G}^{} \int_{G}^{} f(x)\overline{g(y)}\Phi(y^{-1}x) \, d\lambda(x)  \, d\lambda(y) \end{align}$$Take now $g=\chi_{V} / \lambda(V)$ where $V=V^{-1}\ni e$ open, with $\overline{V}$ compact. Then, $$\begin{align}[f,g]-T_{\Phi}(f)&=\int_{G}^{} f(x)\left( \int_{G}^{} \overline{g(y)}\Phi(y^{-1}x) \, d\lambda(y) -\Phi(x) \right) \, d\lambda(x)\\&=\frac{1}{\lambda(V)}\int_{G}^{} \int_{V}^{} f(x)(\Phi(y^{-1}x) -\Phi(x) )\, d\lambda(y)  \, d\lambda(x)\end{align} $$and $$[g,g]-1=\frac{1}{\lambda(V)^{2}}\int_{V}^{}\int_{V}^{} (\Phi(y^{-1}x) -\Phi(e))\, d\lambda(x)  \, d\lambda(y) $$since $\Phi(e)=1$. From uniform continuity of $\Phi$, both expressions can be made arbitrarily small and $\left| T_{\Phi}(f) \right|^{2}=\left| [f,g] \right|^{2}\leq \left| f,f \right|[g,g]=[f,f]$.
>  4. **Defining $\mu$**:
>     Let $h:=f*f^{*}$ for $f\in L^1(G)$. Then $h^{*}=h$ and set: $$h^n:=h^{n-1}*h$$ Then, we obtain from the claims that: $$\left| T_{\Phi}(h) \right| ^{2}\leq T_{\Phi}(h*h)=T_{\Phi}(h^{2}),\quad \left| T_{\Phi}(h^{2}) \right| ^{2}\leq T_{\Phi}(h^{2}*h^{2})=T_{\Phi}(h^4)$$Hence, $\left| T_{\Phi}(f) \right|^{2}\leq \left| T_{\Phi}(h) \right|\leq \left| T_{\Phi}(h^2) \right|^{1 /2}\leq \left| T_{\Phi}(h^4) \right|^{1/4}$ and $\left| T_{\Phi}(f) \right|^{2}\leq \left| T_{\Phi}(h^{2^n}) \right|^{1 / 2^n}\leq\|h^{2^n}\|_{1}^{1 / 2^n}$Therefore, $\left| T_{\Phi}(f) \right|^{2}\leq\|h\|_{\text{sp}}=\left\| \widehat{h} \right\|_{\infty}=\left\| \widehat{f} \right\|^2_{\infty}$ and $\left| T_{\Phi}(f) \right|\leq\|\widehat{f}\|_{\infty}$. Then, $$\begin{array}{cccc} {\Psi:}&{A(\widehat{G})}&\to&{L^1(G)}&\to&\mathbb{C}\\&{\widehat{f}} &\mapsto & {f} &\mapsto&T_{\Phi}(f)\end{array}{}$$is a bounded linear functional and can be extended to $\tilde{\Psi}:C_{0}(\widehat{G})\to \mathbb{C}$ from the density. Therefore, by [[Measure Theory/Complex Measure|Riesz representation theorem]], there exists a unique complex regular measure $\mu$ s.t. for $f\in L^1(G)$, $$T_{\Phi}(f)=\Psi(\widehat{f})=\int_{\widehat{G}}^{} \widehat{f}(\chi) \, d\mu(\chi) =\int_{\widehat{G}}^{} \int_{G}f(x)\overline{(x,\chi)} \, d\lambda(x)  \, d\mu(\chi) =\int_{G}^{} f(x)\left( \int_{\widehat{G}}^{} \overline{(x,\chi)} \, d\mu(\chi)  \right)  \, d\lambda(x) $$Therefore, $\Phi(x)=\int_{\widehat{G}}(x,\chi)  \, d\mu(\chi)$.
>   5. **$\mu$ is positive**: 
>      We have that: $$0\leq T_{\Phi}(f*f^{*})=\int_{\widehat{G}}\left| \widehat{f}(\chi) \right|^{2}   \, d\mu(\chi) $$As $C_{0}(\widehat{G})\to C_{0}(\widehat{G}),\varphi\mapsto \left| \varphi \right|^{2}$ is continuous with image $\{ \varphi\in C_{0}(\widehat{G}):\varphi\geq 0 \}$ and $A(\widehat{G})$ is dense in $C_{0}(\widehat{G})$, $$\int_{\widehat{G}}^{} \varphi \, d\mu \geq 0$$for any $\varphi\in C_{0}(\widehat{G})$ with $\varphi\geq 0$.
---
> [!lemma] Proposition 2
> For $G_{1},G_{2}$ LCA groups, let $\varphi :G_{1}\to G_{2}$ be a continuous homomorphism. Then, the following are equivalent:
> 1. $\varphi$ is a topological group isomorphism.
> 2. $\varphi ^{*}:\widehat{G}_{2}\to \widehat{G}_{1},\chi\mapsto \chi \circ\varphi$ is a topological group isomorphism.

> [!proof]-
> from 1=>2 is elementary. 
> 
> For the converse, we observe that the diagram: $$\begin{CD} \widehat{\widehat{G_{1}}}@>\varphi ^{**}>> \widehat{\widehat{G_{2}}}\\@A\alpha_{1}AA&@AA\alpha_{2}A\\G_{1} @>\varphi >>G_{2}\end{CD}$$ commutes, where $\alpha_{i}$ is the [[Pontryagin Dual|Pontryagin duality isomorphism]]. Now apply 1=>2.
---
##### Duals of Subgroups and Lattices


> [!lemma] Theorem 1
> Let $G$ be an LCA group and $H\leq G$ a closed subgroup. Then, 
> 1. $G / H$ is also an LCA group with canonical projection $p:G\to G / H$. 
> 2. for $q:\widehat{G}\to \widehat{H},\chi\mapsto \chi|_{H}$, let $H^{{\bot}}:=\text{ker }q=\{ \chi\in \widehat{G}:\chi|_{H}=1 \}$. Then, $H^{\bot}\leq \widehat{G}$ and closed.
> 3. $p^{*}:\widehat{G / H}\to H^{\bot}$ is a LCA group isomorphism.
> 4. $\overline{q}:\widehat{G} / H^{\bot}\to \widehat{H}$ is a LCA group isomorphism.
> 5. every continuous character on $H$ extends to a continuous character on $G$.

> [!proof]-
> We have that:
> 1. from [[Quotient Topology|Quotient Lemma]].
> 2. from the fact that $H^{\bot}$ is a kernel.
> 3. Let $\chi\in \widehat{G / H}$. Then, for $h\in H$, $\chi(p(h))=\chi(H)=1$ and $\chi\in H^{\bot}$. Further, $p^{*}$ is continuous. Lastly, $$p^{*}(\chi_{1}\chi_{2})=\chi_{1}\chi_{2}\circ \varphi=p^{*}(\chi_{1})p^{*}(\chi_{2})$$
> 4. We show that: $$\overline{q}^{*}:H\to (H^{\bot})^{\bot}=\{ x\in G:\chi(x)=1,\forall \chi\in H^{\bot} \}$$We claim that $(H^{\bot})^{\bot}=H$. Assume $x\in (H^{\bot})^{\bot}$ but not in $H$. Then, $p(x)\neq e$ in $G / H$. However, there exists $\chi\in \widehat{G / H}$ with $\chi(p(x))\neq 1$ by [[Pontryagin Dual|Lemma 6]]. But $\chi \circ p\in H^{\bot}$, which is a contradiction.
>    
>    Conversely, assume $x\in H$. Then, $\chi(x)=1$ for all $\chi\in H^{\bot}$ and $x\in (H^{\bot})^{\bot}$. Therefore, by Proposition 2, $\overline{q}$ is an isomorphism.
>  5. Let $\phi\in \widehat{H}$. By 4, we may view it as an element of $\widehat{G} / H^{\bot}$. Hence, there exists $\chi\in \widehat{G}$ s.t. $q(\chi)=\phi$. Therefore, $\chi|_{H}=\phi$.
---

 > [!lemma] Corollary 2
 > Let $G$ be a LCA group and $\Gamma\leq G$ be a discrete subgroup s.t. $G / \Gamma$ is compact. Then, 
 > 1. $\Gamma ^{\bot}\leq \widehat{G}$ is a discrete subgroup with $\widehat{G} / \Gamma ^{\bot}$ compact.

> [!proof]-
> As $\Gamma ^{\bot}$ is the dual of $G / \Gamma$, since $G / \Gamma$ is compact, by [[Pontryagin Dual|Proposition 4]], $\Gamma ^{\bot}$ is discrete. Since $\widehat{\Gamma}$ is isomorphic to $\widehat{G} / \Gamma ^{\bot}$, $\Gamma$ is discrete and $\widehat{\Gamma}$ is compact and $\widehat{G} / \Gamma ^{\bot}$ is compact.

- **Example**: $\mathbb{Z}^n\leq \mathbb{R}^n$. Then, $(\mathbb{Z}^n)^{\bot}\cong \mathbb{Z}^n$.

- **Example**: $\mathbb{Q}^{\bot}=\mathbb{Q}$ in $\mathbb{A}_{\mathbb{Q}}$ and $\widehat{\mathbb{Q}}\cong \mathbb{A}_{\mathbb{Q}} / \mathbb{Q}$, which is compact.

---
Let $f\in C(G)$. We call $f$ uniformly summable over $\Gamma$ if $$\sum_{\gamma\in \Gamma}^{}\left| f(g\gamma) \right| $$converges uniformly for $g$ on compact sets of $G$. Then, let $$T_{\Gamma}f(g\Gamma):=\sum_{\gamma\in \Gamma}^{}f(g\gamma)$$
Then, it holds that $T_{\Gamma}f\in C(G / \Gamma)$ and:

> [!lemma] Theorem (Weil's Formula)
> Given a Haar measure $\alpha$ on $G / \Gamma$, there exists a unique Haar measure $\lambda$ on $G$ s.t. for all $f\in C(G) \cap L^1(G)$ uniformly summable over $\Gamma$, $$\int_{G}^{} f \, d\lambda=\int_{G / \Gamma}T_{\Gamma}f  \, d\alpha  $$
---
> [!lemma] Theorem (Poisson Formula)
> Let $\Gamma\leq G$ be discrete with $G / \Gamma$ compact. Let $\alpha$ be the Haar measure on $G/ \Gamma$ with $\alpha(G / \Gamma)=1$. Let $\lambda$ be the corresponding Haar measure on $G$. 
> 	
> Let $f\in C(G)\cap L^1(G)$ uniformly summable over $\Gamma$. Assume that $\widehat{f}|_{\Gamma ^{\bot}}\in \ell^1(\Gamma ^{\bot})$. Then, $$\sum_{\gamma\in \Gamma}^{}f(\gamma)=\sum_{\eta\in\Gamma ^{\bot}}^{}\widehat{f}(\eta)$$

> [!proof]+
> We use Fourier inversion for $G / \Gamma$ with $\alpha(G / \Gamma)=1$. Then, the dual measure on $\Gamma ^{\bot}$ would be the counting measure. (not any multiple).
> 
> Then, for $f\in C(G)\cap L^1(G)$ uniformly summable, for $\chi\in \widehat{G / \Gamma}$: $$\begin{align}\widehat{T_{\Gamma}f}(\chi)&=\int_{G / \Gamma}^{} T_{\Gamma}f(g\Gamma) \overline{(g\Gamma,\chi)}\, d\alpha(g\Gamma)\\&=\int_{G / \Gamma}^{} \sum_{x\in \Gamma}^{}f(gx)\overline{(gx,\chi \circ p)} \, d\alpha(g\Gamma)  \\&=\int_{G}^{} f(g)\overline{(g,\chi \circ p)} \, d\lambda(g)\\&=\widehat{f}(\chi \circ  p)\end{align}$$However, as $G / \Gamma$ is compact, $T_{\Gamma}f\in C(G / \Gamma)\subseteq L^1(G /\Gamma)$. Therefore, $\widehat{T_{\Gamma}f}=\widehat{f}|_{\Gamma ^{\bot}}\in \ell^1(\Gamma ^{\bot})$. Then, by Fourier inversion, $$\sum_{x\in \Gamma}^{}f(x)=T_{\Gamma}f(\Gamma)=\sum_{\eta\in \widehat{G / \Gamma}}^{}\widehat{T_{\Gamma}f}(\eta)=\sum_{\eta\in \widehat{G / \Gamma}}^{}\widehat{f}(\eta \circ p)=\sum_{\eta\in \Gamma ^{\bot}}^{}\widehat{f}(\eta)$$
---
