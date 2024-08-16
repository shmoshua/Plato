#Definition  #FunctionalAnalysis 

> [!definition]
> Let $G$ be an [[LCA group]]. 
> 1. The ***Pontryagin dual*** $\widehat{G}$ of $G$ is defined as the space of all continuous [[Character|characters]] $\chi:G\to \mathbb{T}$.
- **Notation**: For $x\in G$ and $\gamma\in \widehat{G}$, we define $(x,\gamma):=\gamma(x)$. 
---
##### Properties

> [!lemma] Lemma 1
> $\widehat{G}$ can be equipped with a abelian group structure. More precisely,
> 1. for two characters $\chi_{1},\chi_{2}\in \widehat{G}$, $\chi_{1}\chi_{2}(x):=\chi_{1}(x)\chi_{2}(x)$ defines a mutiplication. 
> 2. $\widehat{e}\in \widehat{G}$, defined as $\widehat{e}\equiv 1$ defines a neutral element.
> 3. $(\gamma ^{-1})(x):=\gamma(x)^{-1}$ defines the inverse of $\gamma$.
---
> [!lemma] Lemma 2
> We have that:
> 1. $(x_{1}x_{2},\gamma)=(x_{1},\gamma)(x_{2},\gamma)$
> 2. $(x,\gamma_{1}\gamma_{2})=(x,\gamma_{1})(x,\gamma_{2})$
> 3. $(e,\gamma)=1$ and $(x,\widehat{e})=1$.

> [!proof]-
> We have:
> 1. $(x_{1}x_{2},\gamma)=\gamma(x_{1}x_{2})=\gamma(x_{1})\gamma(x_{2})=(x_{1},\gamma)(x_{2},\gamma)$
> 2. $(x,\gamma_{1}\gamma_{2})=\gamma_{1}\gamma_{2}(x)=\gamma_{1}(x)\gamma_{2}(x)=(x,\gamma_{1})(x,\gamma_{2})$
> 3. $(e,\gamma)=\gamma(e)=1$ as $\gamma(e)\gamma(g)=\gamma(g)$. Further, $(x,\widehat{e})=\widehat{e}(x)=1$.
---
> [!lemma] Theorem 3
> For a LCA group $G$, 
> 1. there is a bijection $\widehat{G}\to \widehat{L^1(G)},\chi\mapsto (f\mapsto \widehat{f}(\chi))$ where $\widehat{f}$ is the [[Fourier transform]].

> [!proof]-
> We have:
> 1. **Showing that the map is well-defined**:
>    For $\chi\in \widehat{G}$, since $\left| (x,\chi) \right|=1$ for all $x\in G$, we have that $$\left| \widehat{f}(\chi) \right| \leq \int_{G}^{} \left| f \right|  \, d\mu = \left\| f \right\| _{1}$$ and $f\to \widehat{f}(\chi)$ is in $L^1(G)^{*}$ with norm $\leq 1$.
>        
>    Let $f_{1},f_{2}\in L^1(G)$. Then, $$\begin{align}\widehat{(f_{1}*f_{2})}(\chi)&=\int_{G}^{} (f_{1}*f_{2})(x)\overline{(x,\chi)} \, d\mu(x)\\&=\int_{G}^{} \int_{G} f_{1}(xy)f_{2}(y^{-1}) \, d\mu(y)\overline{(x,\chi)}d\mu(x)\\&=\int_{G}^{} f_{2}(y ^{-1}) \int_{G}f_{1}(xy) \overline{(x,\chi)} \, d\mu(x) \, d\mu(y) \\&=\int_{G}^{} f_{2}(y ^{-1}) \int_{G}f_{1}(x) \overline{(xy^{-1},\chi)} \, d\mu(x) \, d\mu(y)  \\&=\int_{G}^{} f_{2}(y ^{-1}) \overline{(y^{-1},\chi)}\, d\mu(y) \cdot \int_{G}f_{1}(x) \overline{(x,\chi)} \, d\mu(x)\\&=\widehat{f}_{1}(\chi)\cdot \widehat{f}_{2}(\chi)  \end{align}$$Therefore, $f\mapsto \widehat{f}(\chi)$ is an algebra homomorphism for all $\chi\in \widehat{G}$. Furthermore, if $\widehat{f}(\chi)=0$ for all $f\in L^1(G)$, then, $$\int_{G}^{} f(x)\overline{\chi(x)} \, d\mu(x)=0,\quad \forall f\in L^1(G) $$Therefore, $\chi(x)=0$ for almost every $x\in G$, which is a contradiction.
> 2. **Showing that the map is injective**:
>    Assume $\chi_{1},\chi_{2}\in \widehat{G}$ s.t. $\widehat{f}(\chi_{1})=\widehat{f}(\chi_{2})$ for all $f\in L^1(G)$. Then, $$\int_{G}^{} f(x)\overline{(\chi_{1}(x)-\chi_{2}(x))} \, d\mu(x)=0,\quad \forall f\in L^1(G) $$Therefore, $\chi_{1}(x)=\chi_{2}(x)$ for $\mu$-a.e. $x\in G$. Since $\{ x\in G:\chi_{1}(x)\neq \chi_{2}(x) \}$ is open and of $\mu$-measure zero, it is empty, i.e. $\chi_{1}=\chi_{2}$.
> 3. **Showing that the map is surjective**.
>    Let $\varphi\in \widehat{L^1(G)}$. Then, $\varphi\in L^1(G)^{*}\cong L^\infty(G)$. Therefore, there exists a unique $\Phi\in L^\infty(G)$ s.t. $$\varphi(f)=\int_{G}^{} f(x)\Phi(x) \, d\mu(x),\quad \forall f\in L^1(G) $$We have that: $\varphi(f_{1}*f_{2})=\varphi(f_{1})\varphi(f_{2})$ for all $f_{1},f_{2}\in L^1(G)$, where: $$\begin{align}\varphi(f_{1}*f_{2})&=\int_{G}^{} (f_{1}*f_{2})\Phi \, d\mu\\&=\int_{G}^{} \int_{G} f_{1}(xy)f_{2}(y^{-1})\Phi(x) \, d\mu(x)d\mu(y) \\&=\int_{G}^{} \int_{G}f_{1}(xy^{-1})f_{2}(y)\Phi(x) \, d\mu(x)d\mu(y)  \\&=\int_{G}^{} \varphi(\lambda(y)f_{1})f_{2}(y)\, d\mu(y)  \end{align}$$and $$\varphi(f_{1})\varphi(f_{2})=\int_{G}^{}  \varphi(f_{1})f_{2}(y)\Phi(y)\, d\mu(y) $$Therefore, for all $f_{1} \in L^1(G)$ and $\mu$-a.e. $y\in G$, $$\varphi(f_{1})\Phi(y)=\varphi(\lambda(y)f_{1})$$By [[Haar Measure|Lemma 5]], $G\to L^1(G),y\mapsto \lambda(y)f_{1}$ is continuous and therefore, $y\mapsto \varphi(\lambda(y)f_{1})$ is continuous. Pick any $f_{0}\in L^1(G)$ s.t.. $\varphi(f_{0})\neq 0$. Then, $$\Phi(y)=\frac{\varphi(\lambda(y)f_{0})}{\varphi(f_{0})},\quad \mu \text{-a.e. }y\in G$$Replacing $\Phi$ by the RHS, we assume that $\Phi$ is continuous. Therefore, we have that: $$\Phi(y)\varphi(f_{1})=\varphi(\lambda(y)f_{1}),\quad \forall f_{1}\in L^1(G), y\in G$$Then, $$\Phi(y_{1}y_{2})\varphi(f_{1})=\varphi(\lambda(y_{1}y_{2})f_{1})=\varphi(\lambda(y_{1})\lambda(y_{2})f_{1})=\Phi(y_{1})\varphi(\lambda(y_{2})f_{1})=\Phi(y_{1})\Phi(y_{2})\varphi(f_{2})$$and $\Phi(y_{1}y_{2})=\Phi(y_{1})\Phi(y_{2})$. Then, $\Phi:G\to \mathbb{C}$ is continuous bounded and $\Phi(y_{1}y_{2})=\Phi(y_{1})\Phi(y_{2})$ for all $y_{1},y_{2}\in G$. Therefore, we have: $\Phi(G)\subseteq \mathbb{C}^\times$. Otherwise, if $\Phi(x)=0$, then $$\Phi(xy)=\Phi(x)\Phi(y)=0$$for all $y\in G$ and $\Phi \equiv 0$, which is a contradiction.
>    
>    If there exists $y\in G$ with $\left| \Phi(y) \right|\neq 1$, then as $\Phi(e)=1$, $$\Phi(y)\Phi(y^{-1})=1$$and wlog $\left| \Phi(y) \right|>1$ and $\left| \Phi(y^n) \right|\to +\infty$, which is a contradiction. Therefore, $\Phi\in \widehat{G}$.
- **Remark**: Therefore, we can endow $\widehat{G}$ with the topology given by the basis of open sets: $$\mathcal{U}(\chi_{0};f_{1},\dots,f_{n};\varepsilon):=\left\{ \chi\in \widehat{G}:\left| \widehat{f}_{i}(\chi)-\widehat{f_{i}}(\chi_{0}) \right| <\varepsilon,\quad i\in[n] \right\}$$where $f_{1},\dots,f_{n}\in L^1(G)$ and $\varepsilon>0$.
- **Remark**: This endows $\widehat{G}$ with two different structures: 1) that of an abelian group from Lemma 1, 2) a locally compact Hausdorff group inherited from $\widehat{L^1(G)}$.
---
> [!lemma] Proposition 4
> We have:
> 1. if $G$ is discrete, then $\widehat{G}$ is compact.
> 2. if $G$ is compact, then $\widehat{G}$ is discrete.

> [!proof]-
> We have: 
> 1. if $G$ is discrete, the Haar measure $\mu$ is the counting measure and $\delta_{e}$ is an identity for $\ell^1(G)$. Therefore, $\widehat{\ell^1(G)}$ is compact and so is $\widehat{G}$.
> 2. Assume $G$ is compact and let $\mu$ be the Haar measure on $G$. Modulo rescaling, $\mu(G)=1$. Let $\widehat{e}\in \widehat{G}$. We claim that: $$\int_{G}^{} \gamma(x) \, d\mu(x)=\delta_{\widehat{e}}(\gamma),\quad \forall \gamma\in \widehat{G} $$Clearly, $$\int_{G}\widehat{e}(x)d\mu(x)=\int_{G}1 \, d\mu=\mu(G)=1 $$and $$\int_{G}^{} \gamma \, d\mu=\int_{G}^{} \gamma(yx) \, d\mu(x)=\gamma(y)\int_{G}^{} \gamma \, d\mu   $$Therefore, if $\gamma\neq \widehat{e}$, choose $y\in G$ s.t. $\gamma(y)\neq 1$. Then, $\int_{G}^{} \gamma \, d\mu= 0$.
>    
>    Let $\gamma\in \widehat{G}\subseteq L^1(G)$. Then, $$\widehat{\gamma}(\chi)=\int_{G}\gamma(x)\overline{(x,\chi)}  \, d\mu(x)=\int_{G}\gamma \cdot \chi ^{-1}  \, d\mu=\delta_{\widehat{e}}(\gamma \chi ^{-1})=\delta_{\gamma}(\chi)  $$Therefore, $\delta_{\gamma}$ is continuous and $\{ \gamma \}\subseteq \widehat{G}$ is open and $\widehat{G}$ is discrete.
---

> [!lemma] Proposition 5
> Let $G$ be an abelian [[Locally Compact Group|locally compact Hausdorff group]]. Then, 
> 1. the function: $$\begin{array}{cccc} {}&{G\times \widehat{G}}&\to&{\mathbb{T}}\\&{(x,\chi)} &\mapsto & {\chi(x)} \end{array}{}$$ is continuous. 
> 2. let $K\subseteq G$ compact and $C\subseteq \widehat{G}$ compact. For $\varepsilon>0$ and $$N(K,\varepsilon):=\{ \chi\in \widehat{G}:\left| (x,\chi)-1 \right| <\varepsilon, x\in K \},\quad N(C,\varepsilon):=\{ x\in G:\left| (x,\chi)-1 \right| <\varepsilon ,\chi\in C\}$$are open subsets of $\widehat{G}$ and $G$ respectively. 
> 3. the family of subsets $N(K,\varepsilon)\subseteq \widehat{G}$ and their translates form a basis of open sets for the Guelfand topology on $\widehat{G}$.
> 4. $\widehat{G}$ is a (locally compact) topological group.

> [!proof]-
> We have:
> 1. for $f\in L^1(G)$, $$(\widehat{\lambda(x ^{-1})f})(\chi)=\int_{G}^{} f(xy)\overline{\chi(y)} \, d\mu(y)=\int_{G}^{} f(y)\overline{\chi(x ^{-1}y)} \, d\mu(y)= \chi(x)\widehat{f}(\chi) $$As $\widehat{f}:\widehat{G}\to \mathbb{C}$ is continuous, if we show that $G\times \widehat{G}\to \mathbb{C},(x,\chi)\mapsto (\widehat{\lambda(x ^{-1})f})(\chi)$  is continuous, then the function $(x,\chi)\mapsto \chi(x)$ is continuous on the open set $G\times \{ \chi\in \widehat{G}:\widehat{f}(\chi)\neq 0 \}$. But since, $A(\widehat{G})=\{ \widehat{f}:f\in L^1(G) \}$ is dense in $C_{0}(\widehat{G})$, $$\bigcup_{f\in L^1(G)}^{}\{ \chi\in \widehat{G}:\widehat{f}(\chi)\neq 0 \}=\widehat{G}$$
>    To show the continuity of $(x,\chi)\mapsto (\widehat{\lambda(x ^{-1})f})(\chi)$, let $(x_{0},\chi_{0})\in G\times \widehat{G}$. Let $$V:=\{ x\in G :\left\| \lambda(x ^{-1})f-\lambda(x_{0}^{-1})f \right\|_{1} <\varepsilon\}\subseteq G$$ is open by [[Uniformly Continuous Function|Lemma 1]]. Similarly,  $$W:=\left\{ \chi \in \widehat{G}:\left| (\widehat{\lambda(x_{0}^{-1})f)(\chi)}-(\widehat{\lambda(x_{0}^{-1})f)(\chi_{0})} \right| <\varepsilon \right\}=\mathcal{U}(\chi_{0}),\lambda(x ^{-1}_{0})f,\varepsilon)$$ is an open neighborhood of $\chi_{0}$. 
>    
>    Therefore, for every $(x,\chi)\in V\times W$, $$\begin{align}&\left| (\widehat{\lambda(x^{-1})f)(\chi)}-(\widehat{\lambda(x_{0}^{-1})f)(\chi_{0})} \right| \\&\leq\left| (\widehat{\lambda(x^{-1})f)(\chi)}-(\widehat{\lambda(x_{0}^{-1})f)(\chi)} \right| +\left| (\widehat{\lambda(x_{0}^{-1})f)(\chi)}-(\widehat{\lambda(x_{0}^{-1})f)(\chi_{0})} \right| \\&<\left| (\widehat{\lambda(x^{-1})f-\lambda(x_{0}^{-1})f)}(\chi) \right| +\varepsilon \\&\leq\left\|_{1} (\lambda(x^{-1})f-\lambda(x_{0}^{-1})f)\right\|+\varepsilon \\&<2\varepsilon\end{align}$$This shows the continuity of the function and proves the claim.
> 2. Let $\chi_{0}\in N(K,\varepsilon)$ and $x\in K$ Then, $\left| \chi_{0}(x)-1 \right|<\varepsilon$. By 1, there exists $x\in U_{x}\subseteq G$ open and $\chi_{0}\in W_{x}\subseteq \widehat{G}$ open s.t. $$\left| \chi(y)-1 \right| <\varepsilon,\quad \forall \chi\in W_{x},y\in U_{x}$$As $K$ is compact, let $K\subseteq \bigcup_{i=1}^{n}U_{x_{i}}$ and define $W:=\bigcap_{i=1}^{n}W_{x_{i}}$. Then, $$\left| \chi(y)-1 \right| <\varepsilon,\quad \forall y\in K\subseteq \bigcup_{i=1}^{n}U_{x_{i}}, \chi \in W$$Therefore, $W\subseteq N(K,\varepsilon)$ and $N(K,\varepsilon)$ is open. The statement for $N(C,\varepsilon)$ holds by symmetry.
> 3. First, we show that $\{ N(K,r):r>0,K\subseteq G\text{ compact} \}$ forms a fundamental system of neighborhoods of $\widehat{e}$. We have to show that given $\varepsilon>0$ and $f_{1},\dots,f_{n}\in L^1(G)$, there are $K\subseteq G$ compact and $r>0$ s.t. $$N(K,r)\subseteq \mathcal{U}(\widehat{e};f_{1},\dots,f_{n};\varepsilon)=\left\{ \chi\in \widehat{G}:\left| \widehat{f}_{i}(\chi)-\widehat{f}_{i}(\widehat{e}) \right| <\varepsilon,1\leq i\leq n \right\}$$Let $g_{1},\dots,g_{n}\in C_{00}(G)$ s.t. $\|f_{i}-g_{i}\|_{1}< \varepsilon /3$ (as $C_{00}(G)\subseteq L^1(G)$ is dense). Then,  for $\chi\in \widehat{G}$, $$\left| \widehat{f}_{i}(\chi)-\widehat{f}_{i}(\widehat{e}) \right|\leq $$Let $K=\bigcup_{i=1}^{n}\text{supp } g_{i}$ and $r:= \frac{\varepsilon}{3 \max_{1\leq i\leq n}\|g_{i}\|_{1}}$. Then, indeed assume $\left| \chi(x)-1 \right|<r$ for all $x\in K$. Then, $$\begin{align}\left| \widehat{g}_{i}(\chi)-\widehat{g}_{i}(\widehat{e}) \right|&=\left| \int_{G}^{} g_{i}(x)(\overline{\chi(x)}-1) \, d\mu(x)  \right|\\&\leq \int_{G}^{} \left| g_{i}(x) \right| \left| \chi(x)-1 \right|  \, d\mu(x)\\&\leq \text{sup}_{x\in K}\left| \chi(x)-1 \right|  \cdot \|g_{i}\|_{1}\\&< r\|g_{i}\|_{1}\\&\leq \varepsilon /3 \end{align} $$Then, for $\gamma_{0}N(K,r)\subseteq \gamma_{0}\mathcal{U}(\widehat{e};f_{1}\cdot \gamma_{0}^{-1},\dots,f_{n}\cdot\gamma_{0}^{-1},\varepsilon)$
> 4. For $\eta_{1},\eta_{2}\in \widehat{G}$, $$\left| \eta_{1}(x)\eta_{2}(x)-1 \right| =\left| (\eta_{1}(x)-1)\eta_{2}(x)+\eta_{2}(x)-1 \right|\leq \left| \eta_{1}(x)-1 \right| +\left| \eta_{2} (x)-1\right|  $$Therefore, for all $K\subseteq G$ compact and $\varepsilon >0$, $$N(K. \varepsilon /2)N(K, \varepsilon / 2)\subseteq N(K,\varepsilon)$$This shows the continuity of multiplication at $(\widehat{e},\widehat{e})$. Furthermore, $$\gamma_{1}N(K, \varepsilon / 2)\gamma_{2} N(K, \varepsilon / 2)\subseteq\gamma_{1}\gamma_{2}N(K, \varepsilon)$$
- **Corollary**: on $\widehat{G}=\text{Hom}_{\text{cont}}(G, \mathbb{T})$, the [[compact-open topology]] and the Guelfand topology coincide.
---
> [!lemma] Lemma 6
> We have:
> 1. $N(C,\varepsilon)$ defined as above forms a basis of neighborhood of $e\in G$. 
> 2. $\{ gN(C,r):g\in G ,C\subseteq \widehat{G}\text{ compact},r>0\}$ defines a basis of the topology of $G$.
> 3. For $0<r<1$ and $x_{1}\neq x_{2}\in G$, there exists $\chi\in \widehat{G}$ with $\left| \chi(x_{1})-\chi(x_{2}) \right|\geq r$

> [!proof]-
> Let $e\in V \subseteq G$ be an open neighborhood of the identity. By continuity, there exists an open neighborhood $W\subseteq G$ s.t. $WW^{-1}\subseteq V$. 
> 
> By [[Locally Compact Hausdorff Space|Lemma 1]], wlog we may assume that $\overline{W}$ is compact. Let $\psi:=\chi_{W}*\chi_{W}^{*}$. Then, $\psi\in L^1(G)\cap P(G)$. Through Fourier inversion, we have that $\psi ^{-1}\in L^1(\widehat{G})$. Therefore, by the regularity of the Haar measure, there exists a compact $C\subseteq \widehat{G}$ s.t. $$\int_{\widehat{G} \backslash C} \left| \widehat{\psi}(\chi) \right|   \, d\omega(\chi)<\varepsilon $$Then, for all $x\in N(C,\varepsilon)$, it holds that: $$\left| \psi(x)-\psi(e) \right| \leq \int_{\widehat{G}}^{} \left| \widehat{\psi}(\chi) \right| \left| (x,\chi)-1 \right|  \, d\omega(\chi)\leq \int_{C}^{} +\int_{\widehat{G} \backslash C}\leq \varepsilon\|\widehat{\psi}\|_{1}+2\varepsilon=:\varepsilon'  $$
> 
> Therefore, $$\psi(e)=\int_{G}^{} \left| \chi_{W}(x) \right| ^{2}\, d\lambda(x)=\lambda(W)>0 $$Therefore, $$N(C,r)\subseteq \text{supp }\psi \subseteq WW^{-1}\subseteq V$$
> 
> For 3, as $x_{1}x_{2}^{-1}\neq e$, there exists $C\subseteq \widehat{G}$ compact with $x_{1}x_{2}^{-1}\notin N(C,r)$. Therefore, there exists $\chi\in C$ s.t. $$\left| \chi(x_{1})-\chi(x_{2}) \right| =\left| \chi(x_{2})\right|\left|\chi(x_{1}x_{2}^{-1})-1 \right|\geq r $$
---
> [!lemma] Theorem 7 (Pontryagin Duality Theorem)
> Let $G$ be an LCA group. Then, $$\alpha:G\to \widehat{\widehat{G}},\quad x\mapsto (\gamma\mapsto\gamma(x))$$is a topological group isomorphism.

> [!proof]-
> We have:
> 1. **Showing $\alpha$ is a homomorphism**.$$\alpha(x_{1}x_{2})(\gamma)=\gamma(x_{1}x_{2})=\gamma(x_{1})\gamma(x_{2})=\alpha(x_{1})(\gamma)\alpha(x_{2})(\gamma)$$
> 2. **Showing $\alpha$ is injective**:
>    let $x\neq y\in G$ and by Lemma 6.3 there exists a character $\chi\in \widehat{G}$ with $\chi(x)\neq \chi(y)$. Therefore, $\alpha(x)\neq\alpha(y)$. 
> 3. **Showing $\alpha:G\to\alpha(G)$ is a homeomorphism**:
>    For every compact $C\subseteq \widehat{G}$ and $r>0$, we have that: $$N_{G}(C,r)=\{ x\in G:\left| (x,\gamma)-1 \right|,\forall \gamma\in C  \}$$$$N_{\widehat{\widehat{G}}}(C,r)=\{ \chi\in \widehat{\widehat{G}}:\left| (\gamma,\chi)-1 \right| <r,\forall \gamma\in C \}$$form the basis of neighborhoods of $e$ in $G$ and $\alpha(e)$ in $\widehat{\widehat{G}}$ respectively. Then, $$\alpha(N_{G}(C,r))=N_{\widehat{\widehat{G}}}(C,r)\cap\alpha(G)$$
> 4. **Showing $\alpha$ is surjective:**
>    By [[Locally Compact Hausdorff Space|Lemma 4]], $\alpha(G)$ is an open subgroup of its losure $\overline{\alpha(G)}$ in $\widehat{\widehat{G}}$. Then by [[Topological Group|Proposition 2]], $\alpha(G)=\overline{\alpha(G)}$. 
>    
>    Assume $\alpha(G)\subsetneq \widehat{\widehat{G}}$. Then, by [[Fourier Transform|Proposition 6]], there exists $F\in A(\widehat{\widehat{G}})$ with $F|_{\alpha(G)}=0$ and $F\neq 0$. However, $$F(\chi)=\int_{\widehat{G}}^{} f(\gamma)\overline{(\gamma,x)} \, d\omega(\gamma),\quad \forall f\in L^1(G) $$Then, for all $x\in G$, $$0=F(\alpha(x))=\int_{\widehat{G}}^{} f(\gamma)\overline{(\gamma,\alpha(x))} \, d\omega(\gamma)=\int_{\widehat{G}}^{} f(\gamma)\overline{(x,\gamma)} \, d\omega(\gamma)  $$Then, for all $h\in L^1(G)$, $$0=\int_{G}^{} h(x)\int_{\widehat{G}}^{} f(\gamma)\overline{(x,\gamma)} \, d\omega(\gamma)  \, d\lambda(x)=\int_{\widehat{G}}^{} f(\gamma)\int_{G}^{} h(x)\overline{(x,\gamma)} \, d\lambda(x)  \, d\omega(\gamma)=\int_{\widehat{G}}^{} f(\gamma)\widehat{h}(\gamma) \, d\omega(\gamma)   $$Therefore, by taking $d\mu=f\cdot d\omega$, the complex measure vanishes on $A(\widehat{G})$ and hence on $C_{0}(\widehat{G})$. It follows that, $\mu=0$.
>    
>    Therefore, $f=0$ $\omega$-a.e.  and $F=0$ which is a contradiction.
---
##### Examples
> [!h] Example 1
> Let $G:=\mathbb{T}$, $f\in C(\mathbb{T})$ and $$I(f):=\int_{0}^{1} f(e^{2\pi i\theta}) \, d\mathcal{L}(\theta) $$ is a Haar functional on $C(\mathbb{T})$. Let $\mu$ be the corresponding Haar measure on $\mathbb{T}$. One shows that:
> 1. every $\chi\in \widehat{\mathbb{T}}$ is of the form $\chi_{n}(z):=z^n$ for $n\in \mathbb{Z}$.
> 2. there exists a group isomorphism $\mathbb{Z}\to \widehat{\mathbb{T}}$.
> 3. the Fourier transform of $f\in L^1(\mathbb{T})$ is: $$\widehat{f}(n)=\int_{\mathbb{T}} f(z)z^{-n}  \, d\mu(z)=\int_{0}^{1} f(e^{2\pi i\theta})e^{-2\pi in \theta} \, d\mathcal{L}(\theta)  $$
---
> [!h] Example 2
> Let $G:=\mathbb{R}$. Then, 
> 1. every $\chi\in \widehat{\mathbb{R}}$ is of the form $\chi_{\alpha}(t)=e^{2\pi i\alpha t}$ for $\alpha\in \mathbb{R}$.
> 2. there exists an isomorphism of locally compact abelian groups $\mathbb{R}\to \widehat{\mathbb{R}},\alpha\mapsto \chi_{\alpha}$.

> [!proof]-
> Let $\varphi\in C^\infty_{00}(\mathbb{R})$. Then, $\varphi*\chi\in C^\infty(\mathbb{R})$. Therefore, $\chi\in C^\infty$ and as $\chi(t+h)=\chi(t)\chi(h)$, $$\chi'(t)=\lim_{ h \to 0 }  \frac{\chi(t+h)-\chi(t)}{h}=\lim_{ h \to 0 }  \frac{\chi(t)\chi(h)-\chi(t)}{h}=\chi(t)\chi'(0)$$

> [!proof]- Proof (Using Pontryagin Duality)
> Let $\widehat{\mathbb{R}}$ is a LCA group. Then, for a continuous homomorphism $\chi:\mathbb{R}\to \mathbb{T}$, then $\alpha(x)(\chi)=\chi(ax)$. Therefore, $\widehat{\mathbb{R}}$ is a LCH $\mathbb{R}$-vector space, which is finite. Therefore, $\widehat{\mathbb{R}}\cong \mathbb{R}^n$. Then, $$\mathbb{R}\cong \widehat{\widehat{\mathbb{R}}}\cong \widehat{\mathbb{R}^n}\cong \widehat{\mathbb{R}}^n\cong \mathbb{R}^{n^{2}}$$Therefore, $\widehat{\mathbb{R}}\cong \mathbb{R}$.
---
> [!h] Example 3
> Let $G_{1},G_{2}$ be abelian locally compact Hausdorff groups. Then,
> 1. $\widehat{G_{1}\times G_{2}}\cong\widehat{G_{1}}\times \widehat{G_{2}}$ as for $\chi:G_{1}\times G_{2}\to \mathbb{T}$, we have $\chi|_{G_{1}}\in \widehat{G}_{1}$ and $\chi|_{G_{2}}\in \widehat{G}_{2}$.
> 2. Let $G=\mathbb{Z} / m\mathbb{Z}$ the cyclic group of order $m$. Then, $$\begin{array}{cccc} {}&{\mathbb{Z} / m\mathbb{Z}}&\to&{\widehat{\mathbb{Z} / m\mathbb{Z}}}\\&{a} &\mapsto & {x\mapsto e^{2\pi iax / m}} \end{array}{}$$is a group isomorphism.
> 3. If $F$ is finite abelian, then $\widehat{F}$ is isomorphic to $F$.
> 4. $\widehat{\mathbb{T}}\cong \mathbb{Z}$ and $\widehat{\mathbb{R}}\cong \mathbb{R}$.
> 5. $\widehat{\mathbb{Z}}\cong \mathbb{T}$
> 6. $\widehat{(\mathbb{R}^n\times \mathbb{T}^m\times \mathbb{Z}^\ell \times F)}\cong \mathbb{R}^n\times \mathbb{Z}^m\times \mathbb{T}^\ell \times F$
---
> [!h] Example 4
> We have $\widehat{\mathbb{Q}_{p}}\cong \mathbb{Q}_{p}$. We have that: $$\mathbb{Q}_{p}\xrightarrow{p}\mathbb{Q}_{p} / \mathbb{Z}_{p}\xrightarrow{\sim}\{ z\in \mathbb{T}: \exists n\geq 1, z^{p^n}=1 \}\subseteq \mathbb{T}$$This defines a continuous character $\chi:\mathbb{Q}_{p}\to \mathbb{T}$ with $\text{ker }\chi= \mathbb{Z}_{p}$. Then, $$\begin{array}{cccc} {}&{\mathbb{Q}_{p}}&\to&{\widehat{\mathbb{Q}_{p}}}\\&{a} &\mapsto & {\chi_{a}: x\mapsto \chi(ax)} \end{array}{}$$is an isomorphism. 
> 
> If $\gamma:\mathbb{Q}_{p}\to \mathbb{T}$ is a continuous homomorphism, then there exists $n\geq 1$ s.t. $\gamma(p^n \mathbb{Z}_{p})=1 \in \mathbb{T}$, where it is 1 as an image of a subgroup as a subgroup.
---
> [!h] Example 5
> Let $(F_{n})_{n}$ be a sequence of finite abelian group with discrete topology and $G:=\prod_{n\geq 1}^{}F_{n}$ with the product topology. Then, $G$ is compact and $\widehat{G}$ is discrete as: $$\widehat{G}\cong \bigoplus_{n\geq 1}\widehat{F_{n}} $$If $\chi_{n}\in \widehat{F_{n}}$ with $\chi_{n}=\widehat{e}_{F_{n}}$ for all but finitely many $n$, then: $$(\bigoplus \chi_{n})(x_{n}):=\prod_{n\geq 1}^{}\chi_{n}(x_{n})$$
---
> [!h] Example 6 (Restrictive Product)
> Let $(G_{j})_{j\in J}$ be a family of locally compact groups where for all $j\in J$, there exists a compact open subgroup $K_{j}\leq G_{j}$, e.g. $\text{SL}(2, \mathbb{Z}_{p})<\text{SL}(2,\mathbb{Q}_{p})$. Then, the ***restrictive product*** of $G_{j}$ w.r.t. $K_{j}$ is: $$\prod_{j\in J}^{}'G_{j}:=\left\{  (g_{j})_{j\in J}\in \prod_{j\in J}^{}G_{j}:g_{j}\in K_{j}\text{ for all but finitely many }j\in J  \right\}$$Then, the basis of topology is given by $\prod_{j\in J}^{}A_{j}$ where $A_{j} \subseteq G_{j}$ open and $A_{j}=K_{j}$ for all but finitely many $j\in J$. Then, $\prod_{j\in J}^{}'G_{j}$ is a locally compact group.
---
> [!h] Example 7 (Ring of Adeles)
> Apply the preceding construction to $(\mathbb{Q}_{p})_{p}$. Then, $$\mathbb{A}_{\mathbb{Q}}:=\mathbb{R}\times \prod_{p}^{}'\mathbb{Q}_{p}$$is the ring of Adeles of $\mathbb{Q}$. Then, the injection $\mathbb{Q}\hookrightarrow \mathbb{A}_{\mathbb{Q}}$ has a discrete image and $\mathbb{A}_{\mathbb{Q}} / \mathbb{Q}$ is compact, as it holds that $\widehat{\mathbb{A}_{\mathbb{Q}}}\cong \mathbb{A}_{\mathbb{Q}}$.
