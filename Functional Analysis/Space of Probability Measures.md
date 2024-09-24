#Definition #FunctionalAnalysis 

> [!definition]
> Let $X$ be a compact Hausdorff space and $M(X,\mathbb{R})$ the space of all signed [[Borel Measure|Borel-regular measures]] on $X$. Then, the space of all probability measures on $X$ is denoted as: $$M^1(X):=\{ \mu\in M(X,\mathbb{R}):\mu \text{ is non-negative}, \mu(X)=1 \}$$
---
##### Properties
> [!lemma] Lemma 1
> $M^1(X)$ is closed and compact in $\sigma(C(X,\mathbb{R})^{*},C(X,\mathbb{R}))$-topology. Equivalently, this is the initial topology on $M(X,\mathbb{R})$ given by $\mathcal{F}=\{ (J_{f},\mathbb{R}) \}_{f\in C(X,\mathbb{R})}$ where: $$\begin{array}{cccc} {J_{f}:}&{M(X,\mathbb{R})}&\to&{\mathbb{R}}\\&{\mu} &\mapsto & {\int_{X}^{} f \, d\mu } \end{array}{}$$

> [!proof]-
> See [[Borel Measure|Lemma 3]].
---
> [!lemma] Corollary 2
> Let $G$ be an abelian group and $X$ a compact Hausdorff space. Let $G\curvearrowright X$ represented using the homeomorphisms $$\begin{array}{cccc} {\psi_{g}:}&{X}&\to&{X}\\&{x} &\mapsto & {g\circ x} \end{array}{}$$where $g\in G$. Then, there exists a $G$-invariant probability measure $\mu$ on $X$, i.e. there exists $\mu\in M^1(X)$ s.t. $$(\psi_{g})_{*}(\mu)=\mu\quad \forall g\in G$$where $(\psi_{g})_{*}(\mu)$ denotes the [[Pushforward Measure|pushforward measure]] of $\mu$. 

> [!proof]-
> We will apply Markov-Kakutani on $E=M(X)$ with weak\*-topology and $\pi :G\to \text{Aut}(E)$ by: $$\begin{array}{cccccc} {\pi:}&{G}&\to&{\text{Homeo}(X)}&\to&\text{Aut}(M(X))\\&{g} &\mapsto & {\Psi_{g}}&\mapsto&\lambda ^{*}(\Psi_{g}) \end{array}{}$$given by [[Pushforward Measure|Proposition 2]]. Further, $M^1(X)$ is closed, compact, convex and non-empty. Further, we know that from [[Pushforward Measure|Proposition 2]]: $$\lambda ^{*}(\Psi_{g})[M^1(X)]=M^1(X)$$Therefore, by [[Topological Vector Space with Seminorms|Markov-Kakutani]], there exists $\mu\in M^1(X)$ s.t. for all $g\in G$: $$\lambda ^{*}(\Psi_{g})(\mu)=\mu$$
---
> [!lemma] Corollary 3
> Let $X$ be a compact Hausdorff space and $\psi\in \text{Homeo}(X)$. Then, there exists $\mu\in M^1(X)$ s.t. $$\psi_{*}(\mu)=\mu$$

> [!proof]-
> We can use $G=\mathbb{Z}$ and $$\begin{array}{cccc} {}&{\mathbb{Z}\times X }&\to&{X}\\&{(m,x)} &\mapsto & {\psi^m(x)} \end{array}{}$$Then, we can use Corollary 2. 
---
> [!lemma] Theorem 4 (Unique Ergodicity)
> Let $X$ be a compact [[Hausdorff Space]] and $\psi\in \text{Homeo}(X)$. If there exists a unique $\psi$-invariant probability measure $\mu\in M^1(X)$, then for all $f\in C(X)$ s.t. $$ \frac{1}{n}\sum_{k=0}^{n-1}f(\psi^k(x))\xrightarrow{n\to \infty}\int_{X}^{} f \, d\mu $$converges uniformly, i.e. to a constant. In other words, the time average converges to the space average.

> [!proof]- Proof
> Assume it is not, i.e. there exists $g\in C(X)$, $\varepsilon>0$ s.t. for all $N\in \mathbb{N}$, there exists $n\geq N$ and $x_{n}\in X$ s.t.: $$\left| \frac{1}{n}\sum_{k=0}^{n-1}g(\psi^k(x_{n}))-\int_{X}^{} g \, d\mu  \right| \geq \varepsilon$$
> 
> 1. **Constructing**:
>    Let $(n_{k})_{k\geq 1}\subseteq \mathbb{N}$ be a strictly increasing sequence and $(x_{k})_{k\geq 1}\subseteq X$ any sequence. Then, we define a set of probability measures $(\mu_{k})_{k}$: $$\mu_{k}:= \frac{1}{ n_{k}}\sum_{j=0}^{n_{k}-1}\delta_{\psi^j(x_{k})}$$Let $\nu\in M^1(X)$ be an accumulation point in the sequence, i.e. $$\nu\in \bigcap_{N\geq 1}^{}\overline{\{ \mu_{k}: k\geq N \}}^{w*}=\varnothing$$where the closure is taken in weak\*-topology. (Notice that the closures are a decreasing sequence of weak\*-compact sets) Further, from  [[Compact Space|compact metric space Proposition 1]], we have that intersection is non-empty.
> 2. **Showing that $\nu$ is $\psi$-invariant**:
> For every $f\in C(X)$: $$\mu_{k}(f\circ \psi)-\mu_{k}(f)=\frac{1}{n_{k}}\sum_{j=0}^{n_{k}-1}f(\psi^{j+1}(x_{k})))-f(\psi^{j}(x_{k})))=\frac{1}{n_{k}}\left( f(\psi^{n_{k}}(x_{k}))-f(x_{k}) \right) $$Therefore, $$\left| \mu_{k}(f\circ \psi)-\mu_{k}(f)\right| \leq \frac{2\|f\|_{b}}{n_{k}}$$and by sending $k\to \infty$, $\nu$ is $\psi$-invariant.
> 3. **Showing that $\mu\neq \nu$**:
>    As there is no uniform convergence, there exists $f\in C(X)$, $\varepsilon>0$ s.t. $$\limsup_{ n \to \infty } \sup_{x\in X}\left| \frac{1}{n}\sum_{k=0}^{n-1} f(\psi^k(x))-\int_{X}^{} f \, d\mu \right|>\varepsilon $$Then, there exists $(x_{k})_{k}\subseteq X$ and $(n_{k})$ strictly increasing s.t.$$\left| \frac{1}{n_{k}}\sum_{k=0}^{n_{k}-1}f(\psi^k(x_{k}))-\int_{X}^{} f \, d\mu  \right|>\varepsilon $$ This leads to a $\psi$-invariant sequence $\nu\in M^1(X)$ with: $$\left| \int_{X}^{} f \, d\nu-\int_{X}^{} f \, d\mu   \right| >\varepsilon$$which is a contradiction.
---
> [!lemma] Corollary 5
> Let $X=\mathbb{R} / \mathbb{Z}$ and $T_{\alpha}:\mathbb{R} / \mathbb{Z} \to \mathbb{R} / \mathbb{Z}$ be the translation $x\mapsto x+\alpha$, which is a homeomorphism. Then, we define $\lambda\in M^1(\mathbb{R} / \mathbb{Z})$, s.t. for all $f\in C(\mathbb{R} / \mathbb{Z})$$$\int_{\mathbb{R} / \mathbb{Z}}^{} f \, d\lambda:=\int_{0}^{1} (f\circ \pi)(x) \, d\lambda(x)  $$where $\pi:\mathbb{R} \to \mathbb{R} / \mathbb{Z}$ is the canonical projection. Notice that $\lambda$ is $T_{\alpha}$-invariant. Then, $\lambda$ is the unique $T_{\alpha}$-invariant probability measure if and only if $\alpha\notin \mathbb{Q} / \mathbb{Z}$, in which case for all $f\in C(\mathbb{R} / \mathbb{Z})$: $$\lim_{ n \to \infty } \frac{1}{n}\sum_{k=0}^{n-1}f(x+k\alpha)=\int_{\mathbb{R} / \mathbb{Z}}^{} f \, d\lambda $$converges uniformly.

> [!proof]-
> Let $\alpha\in \mathbb{Q} / \mathbb{Z}$ i.e. $\alpha= \frac{p}{q}+\mathbb{Z}$ where $p,q\in \mathbb{N}_{\geq 1}$ and coprime. Then, $$T_{\alpha}^q(x+\mathbb{Z})=x+p+\mathbb{Z}=x+\mathbb{Z},\quad T^q_{\alpha}=\text{id}_{\mathbb{R} / \mathbb{Z}}$$and for all $x\in \mathbb{R} / \mathbb{Z}$: $$\mu_{x}:= \frac{1}{ q}\sum_{k=0}^{q-1}\delta_{T_{\alpha}^k(x)}\in M^1(\mathbb{R} / \mathbb{Z})$$is a $T_{\alpha}$-invariant probability measure, which shows that $\lambda$ is not unique.
> 
> If $\alpha\notin \mathbb{Q} / \mathbb{Z}$, then $\lambda$ is the unique $T_{\alpha}$-invariant probability measure, as there exists no $q$ s.t. $T_{\alpha}^q(x+\mathbb{Z}) = x+\mathbb{Z}$ for any $x\in \mathbb{R}$. Therefore, from Theorem 4, our statement holds.
---
