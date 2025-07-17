#Definition #AlgebraicTopology 

> [!definition]
> Let $X$ be a [[topological space]] and $R$ a [[ring]]. 
> 1. The ***cap product*** is a map:$$\cap:S^p(X;R)\otimes_{R}  S_{n}(X)\to S_{n-p}(X;R),\quad  \varphi \otimes  c\mapsto ((\pi_{n-p}\otimes  \varphi)\circ  \Delta )c$$where $\Delta:\mathcal{S}_{*}(X)\to \mathcal{S}_{*}(X)\otimes_{R}\mathcal{S}_{*}(X)$ is a [[diagonal approximation]] over $R$ and the projection $\pi_{q}:\bigoplus_{j\in \mathbb{Z}}S_{j}(X)\to S_{q}(X)$.
> 2. The ***cap product on homology*** is given by: $$\cap :H^p(X;R)\otimes  H_{n}(X)\to H_{n-p}(X;R)$$
- **Remark**: We write $\varphi \cap c=(\text{id}\otimes \varphi)\circ \Delta c$ instead as well to make it more intuitive.
- **Remark**: $\cap$ on homology is independent of $\Delta$ by [[Diagonal Approximation|Theorem 1]].
---
> [!lemma] Proposition 1 (Properties of Cap Product)
> We have that:
> 1. $\cap$ is natural w.r.t. maps $f:X\to Y$, i.e. $$f_{c}(f^c\varphi \cap c)=\varphi \cap f_{c}c,\quad \forall \varphi\in S^p(Y;R),c\in S_{n}(X)$$
> 2. $\cap$ is a chain map in the sense that: $$\partial(\varphi \cap c)=\delta\varphi \cap c+(-1)^p\varphi \cap \partial c,\quad \forall \varphi\in S^p(X;R),c\in S_{n}(X)$$

> [!proof]-
> We have that:
> 1. See that: $$\begin{aligned}\varphi \cap f_{c}c&=(\pi_{n-p}\otimes  \varphi)\circ \Delta f_{c}c\\&=(\pi_{n-p}\otimes  \varphi)\circ (f_{c}\otimes  f_{c})\Delta c\\&=(\pi_{n-p}\circ  f_{c})\otimes  (\varphi \circ  f_{c})\Delta c\\&=f_{c}((\pi_{n-p}\otimes  f^c(\varphi))\Delta c)\\&=f_{c}(f^c\varphi \cap c)\end{aligned}$$
> 2. We have that: $$\begin{aligned}\partial(\varphi \cap c)&=\partial((\text{id}\otimes  \varphi)\circ \Delta c)=(\partial \otimes \text{id}_{R})(\text{id}\otimes  \varphi)\circ  \Delta c\\&=(-1)^p(\text{id}\otimes  \varphi)(\partial \otimes  \text{id})\Delta c\\&=(-1)^p(\text{id}\otimes  \varphi)(\partial_{\otimes }-\text{id}\otimes  \partial)\Delta c\\&=(-1)^p(\text{id}\otimes  \varphi)\Delta \partial c+(-1)^{p+1}(\text{id}\otimes  \varphi \circ \partial)\Delta c\\&=(-1)^p(\text{id}\otimes  \varphi)\Delta \partial c+(\text{id}\otimes  \delta\varphi )\Delta c\\&=\delta \varphi \cap c+(-1)^p\varphi \cap \partial c\end{aligned}$$
---
> [!lemma] Proposition 2 (Properties of Homological Cap Product)
> For $\alpha,\beta\in H^{*}(X)$ and $a\in H_{*}(X)$, 
> 1. $1\cap a=a$
> 2. $\varepsilon_{*}(\alpha \cap a)=\braket{ \alpha , a }$ where $\braket{ \cdot , \cdot }$ is the [[Kronecker pairing]].
> 3. $(\alpha \cup \beta)\cap a=\alpha \cap(\beta \cap a)$
> 4. $f_{*}(f^{*}\alpha \cap a)=\alpha \cap f_{*}a$

> [!proof]+
> Let $\alpha=[\varphi]$ and $\beta=[\psi]$ and $a=[c]$. Then, 
> 1. $1\cap a=[\varepsilon]\cap[c]=[\varepsilon \cap c]=[c]=a$.
> 2. $\varepsilon_*(\alpha \cap a)=\varepsilon_{*}([\varphi]\cap[c])=\varepsilon_{*}([\varphi \cap c])=\varepsilon(\varphi \cap c)=\varphi(c)=\braket{ \alpha , a }$.
> 3. 
---
##### Examples
> [!h] Example 1 (AW Diagonal Approximation)
> Let $\Delta:=\Delta^\text{AW}$ be the [[Diagonal Approximation|Alexander-Whitney diagonal approximation]]. Let $\varepsilon:S_{0}(X)\to R$ also be the augmentation. Then, we have:
> 1. $\varphi \cap \sigma=(-1)^{pq}\braket{ \varphi , {_{p}\lfloor\sigma} }\cdot\sigma\rfloor_{q}$ for $\varphi\in S^p(X)$ and $\sigma\in S_{n}(X)$
> 2.  $\varepsilon \cap c = c$.
> 3. $\varepsilon(\varphi \cap c)=\varphi(c)$ for $\varphi\in S^p(X)$ and $c\in S_{p}(X)$
> 4. $(\varphi \cup \psi)\cap \sigma=\varphi \cap(\psi \cap \sigma)$

> [!proof]-
> We have that:
> 1. Compute that: $$\varphi \cap \sigma=(\pi_{q}\otimes  \varphi)\circ  \Delta\sigma=(\pi_{q}\otimes  \varphi)\sum_{s+t=n}\sigma\rfloor_{s}\otimes {_{t}\lfloor\sigma}=(-1)^{pq}\sigma\rfloor_{q}\cdot \braket{ \varphi , {_{p}\lfloor\sigma} } $$
> 2. We have that: $$\varepsilon \cap c=\underbrace{ \braket{ \varepsilon , {_{0}\lfloor c} } }_{ =1 } \cdot c=c$$
> 3. We have that: $$\varepsilon(\varphi \cap c)=\varepsilon(\braket{ \varphi , c } \cdot c\rfloor_{0} )=\braket{ \varphi , c } =\varphi(c)$$
> 4. Let $\varphi\in S^p(X;R)$ and $\psi\in S^q(X;R)$ with $\sigma: \Delta^n\to R$ with $r:= n-p-q$. Then, $$\begin{aligned}(\varphi \cup \psi)\cap c&=(-1)^{(p+q)r}\braket{ \varphi \cup \psi , {_{p+q}\lfloor  \sigma}} \cdot \sigma\rfloor_{r}\\&=(-1)^{pq+pr+qr} \varphi(({_{p+q}\lfloor \sigma})\rfloor_{p} )\cdot \psi({_{q}\lfloor({_{p+q}\lfloor \sigma})})\cdot  \sigma\rfloor_{r} \end{aligned}$$and $$\begin{aligned}\varphi \cap(\psi \cap\sigma)&=(-1)^{q(p+r)}\cdot \psi({_{q}\lfloor \sigma} )\cdot (\varphi \cap \sigma\rfloor_{p+r})\\&=(-1)^{pq+pr+qr}\varphi(_{p}\lfloor(\sigma\rfloor_{p+r}) )\cdot \psi({_{q}\lfloor \sigma} ) \cdot (\sigma\rfloor_{p+r})\rfloor_{r}  \end{aligned}$$It is easy to see that $(\sigma\rfloor_{p+r})\rfloor_{r}  =\sigma\rfloor_{r}$ and ${_{q}\lfloor({_{p+q}\lfloor \sigma})}={_{q}\lfloor \sigma}$. Further,$$\begin{aligned}({_{p+q}\lfloor \sigma})\rfloor_{p}[v_{0}:\dots:v_{p}]&={_{p+q}\lfloor \sigma}[v_{0}:\dots:v_{p}:0:\dots:0]\\&=\sigma [0:\dots:0:v_{0}:\dots:v_{p}:0:\dots:0]\\&=\sigma\rfloor_{p+r}[0:\dots:0:v_{0}:\dots:v_{p}]\\&={_{p}\lfloor }(\sigma\rfloor_{p+r})[v_{0}:\dots:v_{p}]\end{aligned}$$