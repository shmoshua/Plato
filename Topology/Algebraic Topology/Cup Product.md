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

^71b2b0

> [!proof]-
> We have:
> $$\begin{aligned}f^c(\varphi \cup \psi)&=f^cd^c_{Y}(\varphi \times \psi)=(d_{Y}\circ  f)^c(\varphi \times \psi)=((f\times f)\circ d_{X})^c(\varphi \times \psi)\\&=d_{X}^c((f\times f)^c(\varphi \times \psi))=d^c_{X}(f^c(\varphi)\times f^c(\psi))=f^c(\varphi)\cup f^c(\psi)\end{aligned}$$

^4924af

- **Corollary**: $f^{*}:H^{*}(Y;R)\to H^{*}(X;R)$ is a homomorphism of rings by [[Singular Cohomology|Unity properties]]. ^d99359

---
> [!lemma] Proposition 4 (Relative Cup Product)
> For a topological space $X$, $A\subseteq X$, and $R$ a ring, 
> 1. the ***relative cup product*** is a cochain level map: $$\begin{aligned}\cup:S^p(X,A;R)\otimes  S^q(X;R)\to S^{p+q}(X,A;R)\\\cup:S^p(X;R)\otimes  S^q(X,A;R)\to S^{p+q}(X,A;R)\end{aligned}$$
> 2. On cohomology level, we get:$$\begin{aligned}\cup:H^{*}(X,A;R)\otimes_{R}  H^{*}(X;R)\to H^{*}(X,A;R)\\\cup:H^{*}(X;R)\otimes_{R}  H^{*}(X,A;R)\to H^{*}(X,A;R)\end{aligned}$$
> 3. $H^{*}(X,A;R)$ is a $H^{*}(X;R)$-[[bimodule]].

^dfd342

> [!proof]-
> We have that:
> 1. Let $\varphi\in S^p(X,A;R)\cong \text{ker}(\Phi\mapsto \Phi|_{S_{p}(A)})$, i.e. $\varphi\in S^p(X;R)$ with $\varphi|_{S_{p}(A)}=0$. Then, for $i:A\to X$ the inclusion, $$i^c(\varphi \cup \psi)=i^c(\varphi)\cup i^c(\psi)=0\cup i^c(\psi)=0$$Hence, $(\varphi \cup \psi)|_{S_{p+q}(A)}=0$. Similarly, if $\psi\in S^q(X,A;R)$, then $(\varphi \cup \psi)|_{S_{p+q}(A)}=0$. This proves the statement.
> 2. Obvious. 
> 3. We have that for $\psi\in H^{*}(X,A;R)$:
> 	1. $\varphi \cup(\psi+\psi')=\varphi \cup \psi+\varphi \cup \psi'$ by definition.
> 	2. $(\varphi +\varphi')\cup \psi=\varphi \cup \psi+\varphi'\cup \psi$ also by definition.
> 	3. $(\varphi \cup \phi)\cup \psi=\varphi \cup (\phi \cup \psi)$ by associativity.
> 	4. $1\cup \psi=\psi$
> 	
> 	By symmetry, it is also a right module. It is left to show that: $$(\varphi \cup \psi)\cup \phi=\varphi \cup(\psi \cup \phi)$$which holds by associativity.

^bd811f

---
> [!lemma] Proposition 5 (Double Relative Cup Product)
> For a topological space $X$, $A,B\subseteq X$ open, 
> 1. The cup product extends to: $$\cup:H^{p}(X,A;R)\otimes H^q(X,B;R)\to H^{p+q}(X,A\cup B;R)$$

^ef3896

> [!proof]-
> Let $\varphi\in S^p(X,A;R)$ and $\psi\in S^q(X,B;R)$. We can view them as:
> 1. $\varphi:S_{p}(X)\to R$ with $\varphi|_{S_{p}(A)}=0$ and 
> 2. $\psi:S_{q}(X)\to R$ with $\varphi|_{S_{p}(B)=0}$.
> 
> Then, from Proposition 4, $\varphi \cup \psi$ is zero on $S_{p+q}(A)$ and $S_{p+q}(B)$, i.e. on $S_{p+q}^{A,B}\subseteq S_{p+q}(A\cup B)$, where $S^{A,B}_{p+q}$ is the subcomplex generated by $\mathcal{S}_{*}(A)$ and $\mathcal{S}_{*}(B)$.  We now know by [[Singular Homology|Theorem 4]] that $i:\mathcal{S}_{*}^{A,B}\to \mathcal{S}_{*}(A\cup B)$ is a quasi-isomorphism.
> 
> Now, the cup product gives us a map: $$\cup:S^p(X,A;R)\otimes  S^q(X,B;R)\to \text{Hom}(S_{p+q}(X) / S_{p+q}^{A,B},R)$$Consider the SES of chain complexes: $$\begin{CD}0 @>>> \mathcal{S}_{*}^{A,B}@>>> \mathcal{S}_{*}(X)@>>> \mathcal{S}_{*}(X) / \mathcal{S}_{*}^{A,B} @>>>  0\\ & @ViVV @V\text{id}VV & @VVV\\ 0 @>>> \mathcal{S}_{*}(A\cup B)@>>> \mathcal{S}_{*}(X)@>>> \mathcal{S}_{*}(X) / \mathcal{S}_{*}(A\cup B) @>>>  0\end{CD}$$where the vertical maps are chain maps. By dualizing we get: $$\begin{CD}0 @>>> (\mathcal{S}_{*}(X) / \mathcal{S}_{*}^{A,B} )^{*}@>>> \mathcal{S}^{*}(X;R)@>>> (\mathcal{S}_{*}^{A,B})^{*} @>>>  0\\ & @Ai^{*}A A @A\text{id}AA & @AAA\\ 0 @>>> \mathcal{S}^{*}(X,A\cup B;R)@>>> \mathcal{S}^{*}(X;R)@>>> \mathcal{S}^{*}(A\cup B;R)@>>>  0\end{CD}$$all the groups are free abelian. Therefore, in cohomology, by the 5-lemma, we get that: $$H^{*}((\mathcal{S}_{*}(X) / \mathcal{S}^{A,B}_{*})^{*})\cong H^{*}(X,A\cup B)$$This proves the statement.

^2d4dce

---
> [!lemma] Theorem 6 (CW-Complexes)
> Let $X$ be a finite [[CW-complex]]. We view the attaching cells as $\Delta^k$ instead of $B^k$. Assume further that:
> 1. the inclusion $i:\mathcal{C}^\text{cw}(X)\to \mathcal{S}_{*}(X)$ is a [[Chain Complex|chain map]] and a quasi-isomorphism.
> 2. ]

- **Remark**: The assumption 1) is not trivial: Consider $X:=S^{2}$ with one $0$-cell, no $1$-cell and one $2$-cell. Then, $\partial ^\text{cw}\equiv 0$. However, we have that $$\partial(\text{2-cell})=c-c+c=c$$where $c$ is a constant map.