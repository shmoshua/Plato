#Definition #AlgebraicTopology 

> [!definition]
> Let $X$ be a [[topological space]] and $R$ a [[ring]].
> 1. the ***cup product*** is an operation: $$\cup:H^p(X;R)\otimes  H^q(X;R)\to H^{p+q}(X;R),\quad \alpha \otimes  \beta\mapsto d^{*}(\alpha \times\beta)$$where $d:X\to X\times X,x\mapsto (x,x)$ is the diagonal map and $\alpha \times\beta$ is the [[cross product]].
> 2. the ***cup product*** on cochain level is given as: $$\cup:S^p(X;R)\otimes  S^q(X;R)\to S^{p+q}(X;R),\quad \varphi \otimes  \psi\mapsto d^c(\varphi \times \psi)$$In other words, $\braket{ \varphi \cup \psi , c }=\braket{ \varphi \times \psi , d_{c}(c) }=\braket{ \varphi \otimes \psi , (\Theta \circ d_{c})(c) }$ for $S_{p+q}(X)$.

^7bacb8

- **Remark**: $\alpha \cup \beta$ is independent of the choice of $\Theta$ from [[Singular Homology|EZ theorem]] as $\alpha \times\beta$ is. ^3d12a2

---
##### Properties
> [!lemma] Proposition 1 (Properties of Cup Product)
> For $\alpha\in H^p(X;R)$, $\beta\in H^q(X;R)$ and $\gamma\in H^r(X;R)$:
> 1. **graded commutativity**: $\alpha \cup \beta=(-1)^{pq}(\beta \cup \alpha)$.
> 2. **associativity**: $(\alpha \cup\beta)\cup\gamma=\alpha \cup(\beta \cup\gamma)$.
> 3. **unity**: $\alpha \cup 1=1\cup \alpha=\alpha$.

^bd6af5

> [!proof]-
> From [[Cross Product|Proposition 2]]:
> 1. Notice that: $$\beta \cup \alpha=d^{*}(\beta \times\alpha)=(-1)^{pq}d^{*}T^{*}(\alpha \times\beta)=(-1)^{pq}(\underbrace{ T \circ  d }_{ =d })^{*}(\alpha \times\beta)=(-1)^{pq}(\alpha \cup \beta)$$
> 2. We have: $$\begin{aligned}(\alpha \cup\beta)\cup\gamma&=d^{*}((\alpha \cup \beta)\times\gamma)=d^{*}(d^{*}(\alpha \times\beta)\times\gamma)=d^{*}\circ (d\times \text{id})^{*}(\alpha \times\beta \times\gamma)\\&=((d\times \text{id})\circ  d)^{*}(\alpha \times\beta \times\gamma)\\&=((\text{id}\times d)\circ  d)^{*}(\alpha \times\beta \times\gamma)\\&=d^{*}\circ (\text{id}\times d)^{*}(\alpha \times\beta \times\gamma)\\&=d^{*}(\alpha \times d^{*}(\beta \times\gamma))\\&=\alpha \cup(\beta \cup\gamma)\end{aligned}$$
> 3. We have from [[Singular Cohomology|Unity properties]]: $$\alpha \cup 1=d^{*}(\alpha \times 1)=d^{*}(\pi_{1}^{*}(\alpha))=(\pi_{1}\circ  d)^{*}(\alpha)=\text{id}^{*}(\alpha)=\alpha$$Similarly, $$1\cup \alpha=d^{*}(1\times\alpha)=d^{*}(\pi_{2}^{*}(\alpha))=(\pi_{2}\circ d)^{*}(\alpha)=\text{id}^{*}(\alpha)=\alpha$$

^044e3b

- **Corollary**: For $H^{*}(X;R):=\bigoplus_{i\geq 0}H^i(X;R)$ we can extend the cup product into: $$\cup:H^{*}(X;R)\otimes _{R}H^{*}(X;R)\to H^{*}(X;R)$$This defines a graded commutative ring on $H^{*}(X;R)$.
- **Remark**: If $X$ is [[Path-Connected Space|path-connected]], by [[Singular Cohomology|Proposition 2]], $R$ sits inside $H^{*}(X;R)$ as $H^0(X;R)\cong R$.
---
> [!lemma] Proposition 2 (Cup Product and Cross Product)
> Let $X,Y$ be topological spaces.
> 1. Let  $\alpha_{1}\in H^p(X;R), \alpha_{2}\in H^q(X;R)$ and $\beta_{1}\in H^r(Y;R),$ and $\beta_{2}\in H^s(Y;R)$. Then, 
> $$(\alpha_{1}\times\beta_{1})\cup(\alpha_{2}\times\beta_{2})=(-1)^{\left| \beta_{1} \right| \left| \alpha_{2} \right| }(\alpha_{1}\cup\alpha_{2})\times(\beta_{1}\cup\beta_{2})$$
> 2. Let $\pi_{X}:X\times Y\to X$ and $\pi_{Y}:X\times Y\to Y$ be projections. For $\alpha\in H^p(X;R)$ and $\beta\in H^q(Y;R)$, $$(\pi_{X}^{*}\alpha)\cup(\pi ^{*}_{Y}\beta)=\alpha \times\beta$$

^8d1ccf

> [!proof]-
> We have that:
> 1. Let $d_{X}:X\to X\times X$, $d_{Y}:Y\to Y\times Y$ and $d_{X\times Y}:X\times Y\to X\times Y\times X\times Y$ be diagonal maps. Further, denote $$T':X\times X\times Y\times Y\to X\times Y\times X\times Y,\quad (x_{1},x_{2},y_{1},y_{1})\mapsto (x_{1},y_{1},x_{2},y_{2})$$Note that $d_{X\times Y}=T'(d_{X}\times d_{Y})$. Then, $$\begin{aligned}(\alpha_{1}\times\beta_{1})\cup(\alpha_{2}\times\beta_{2})&=d^{*}_{X\times Y}(\alpha_{1}\times\beta_{1}\times\alpha_{2}\times\beta_{2})\\&=(d_{X}\times d_{Y})^{*}(T')^{*}(\alpha_{1}\times\beta_{1}\times\alpha_{2}\times\beta_{2})\\&=(-1)^{\left| \alpha_{2} \right| \left| \beta_{1} \right| }(d_{X}\times d_{Y})^{*}(\alpha_{1}\times\alpha_{2}\times\beta_{1}\times\beta_{2})\end{aligned}$$By naturality of cross products, $$\begin{aligned}(\alpha_{1}\times\beta_{1})\cup(\alpha_{2}\times\beta_{2})&=(-1)^{\left| \alpha_{2} \right| \left| \beta_{1} \right| }d_{X}^{*}(\alpha_{1}\times\alpha_{2})\times d^{*}_{Y}(\beta_{1}\times\beta_{2})\\&=(-1)^{\left| \beta_{1} \right| \left| \alpha_{2} \right| }(\alpha_{1}\cup\alpha_{2})\times(\beta_{1}\cup\beta_{2})\end{aligned}$$
> 2. From [[Singular Cohomology|Unity properties]]:$$(\pi ^{*}_{X}\alpha)\cup (\pi ^{*}_{Y}\beta)=(\alpha \times 1_{Y})\cup(1_{X}\times\beta)=(\alpha\cup 1_{X})\times(1_{Y}\cup \beta)=\alpha \times\beta$$

^023205

---
> [!lemma] Proposition 3 (Naturality of Cup Product)
> For any continuous map $f:X\to Y$, $\varphi\in S^p(Y;R)$ and $\psi\in S^q(Y;R)$
> 1. $f^c(\varphi \cup \psi)=f^c(\varphi)\cup f^c(\psi)$

> [!proof]-
> We have:
> $$\begin{aligned}f^c(\varphi \cup \psi)&=f^cd^c_{Y}(\varphi \times \psi)=(d_{Y}\circ  f)^c(\varphi \times \psi)=((f\times f)\circ d_{X})^c(\varphi \times \psi)\\&=d_{X}^c((f\times f)^c(\varphi \times \psi))=d^c_{X}(f^c(\varphi)\times f^c(\psi))=f^c(\varphi)\cup f^c(\psi)\end{aligned}$$

- **Corollary**: $f^{*}:H^{*}(Y;R)\to H^{*}(X;R)$ is a homomorphism of rings by [[Singular Cohomology|Unity properties]].