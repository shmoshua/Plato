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
> 4. 

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
> 2. **Leibniz rule**: $\delta(\varphi \cup \psi)=\delta\varphi \cup \psi+(-1)^p\varphi \cup \delta \psi$

^71b2b0

> [!proof]-
> We have:
> 1. Firstly,
> $$\begin{aligned}f^c(\varphi \cup \psi)&=f^cd^c_{Y}(\varphi \times \psi)=(d_{Y}\circ  f)^c(\varphi \times \psi)=((f\times f)\circ d_{X})^c(\varphi \times \psi)\\&=d_{X}^c((f\times f)^c(\varphi \times \psi))=d^c_{X}(f^c(\varphi)\times f^c(\psi))=f^c(\varphi)\cup f^c(\psi)\end{aligned}$$
> 2. Now, $$\begin{aligned}\delta(\varphi \cup \psi)&=\delta(d^c(\varphi \times \psi))=d^c(\delta_{X\times X}(\varphi \times \psi))\\&=d^c(\delta_{X}\varphi \times \psi+(-1)^p\varphi \times\delta_{X}\psi)\\&=\delta_{X}\varphi \cup \psi+(-1)^p\varphi \cup \delta_{X}\psi\end{aligned}$$

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
> [!lemma] Proposition 6 (Cup Product with Connecting Homomorphisms)
> Let $X$ and $A\subseteq X$ be topological spaces. Consider the LES: $$\dots\to H^{k-1}(A;R)\overset{ \delta ^{*} }{ \to } H^k(X,A;R)\overset{ j^{*} }{ \to } H^k(X;R)\overset{ i^{*} }{ \to } H^k(A;R)\overset{ \delta ^{*} }{ \to } H^{k+1}(X,A;R)\to \cdots$$Then, for all $\alpha\in H^{*}(A;R)$ and $\beta\in H^{*}(X;R)$ and $\gamma,\gamma'\in H^{*}(X,A;R)$:
> 1. $\delta ^{*}(\alpha \cup i^{*}\beta)=\delta ^{*}\alpha \cup\beta$.
> 2. $\delta ^{*}(i^{*}\beta \cup \alpha)=(-1)^\left| \beta \right|\beta \cup \delta ^{*}\alpha$
> 3. $j^{*}(\gamma \cup\gamma')=j^{*}\gamma \cup j^{*}\gamma'$.
> 4. $j^{*}(\beta \cup \gamma)=\beta \cup j^{*}\gamma$.

^2f5cfa

> [!proof]-
> We have: 
> 1. Let $\varphi\in S^p(A;R)$ and $\psi\in S^q(X;R)$ s.t. $p+q=n$ be cocycles. Then, let $\overline{\varphi}\in S^p(X;R)$ be an extension of $\varphi$. We have that: $$[\varphi]\cup i^{*}[\psi]=[i^c\overline{\varphi} \cup i^c\psi]=[i^c(\overline{\varphi}\cup \psi)]$$Then, we have that for any $c\in S_{n+1}(A)$, as $\varphi,\psi$ are both cocycles, for any $c\in S_{n+1}(A)$$$\delta(\overline{\varphi} \cup \psi)(c)=\delta(\varphi \cup i^c(\psi))(c)=(\underbrace{ \delta\varphi }_{ =0 } \cup i^c(\psi)+(-1)^p \varphi \cup \underbrace{ \delta(i^c(\psi)) }_{ =i^c(\delta(\psi))=0 })(c)=0$$ Therefore, $\delta(\overline{\varphi}\cup \psi)\in S_{n+1}(X,A;R)$ and $$\begin{aligned}\delta ^{*}([\varphi]\cup i^{*}[\psi])&=[\delta(\overline{\varphi}\cup \psi)]\\&=[\delta\overline{\varphi}\cup \psi+(-1)^p\overline{\varphi}\cup \underbrace{ \delta \psi }_{ =0 }]=[\delta\overline{\varphi}\cup \psi]=\delta ^{*}([\varphi])\cup[\psi]\end{aligned}$$
> 2. From 1, $$\begin{aligned}\delta ^{*}(i^{*}\beta \cup \alpha)&=(-1)^{\left| \alpha \right| \left| \beta \right| }\delta ^{*}(\alpha \cup i^{*}\beta)=(-1)^{\left| \alpha \right| \left| \beta \right| }\delta ^{*}\alpha \cup \beta=(-1)^{\left| \alpha \right| \left| \beta \right|+(\left| \alpha \right|+1)\left| \beta \right|   }\beta \cup \delta ^{*}\alpha\\&=(-1)^{\left| \beta \right| }\beta \cup \delta ^{*}\alpha\end{aligned}$$
> 3. Let $\varphi,\psi\in S^n(X;R)$ s.t. $\varphi|_{S_{n}(A)}=\psi|_{S_{n}(A)}=0$. Then, $$j^{*}([\varphi \cup \psi])=[j^c(\varphi)\cup j^c(\psi)]=j^{*}[\varphi]\cup j^{*}[\psi]$$
> 4. Obvious.

^b4b09c

---
> [!lemma] Theorem 7 (CW-Complexes)
> Let $X$ be a finite [[CW-complex]]. We view the attaching cells as $\Delta^k$ instead of $B^k$. Assume further that:
> - the inclusion $i:\mathcal{C}^\text{cw}(X)\to \mathcal{S}_{*}(X)$ is a [[Chain Complex|chain map]] and a quasi-isomorphism.
> - for all $0\leq k\leq \text{dim }X$ with $p+q=k$, and $\sigma:\Delta^k\to X$, $\sigma\rfloor_{p}$ and $_{q}\lfloor \sigma$ are also cells of $X$.
> 
> Let $\Delta:\mathcal{S}_{*}(X)\to \mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(X)$ be a [[diagonal approximation]]. Then, 
> 
> 1. If there exists $\Delta^\text{cw}:\mathcal{C}^{\text{cw}}(X)\to \mathcal{C}^{\text{cw}}(X)\otimes \mathcal{C}^{\text{cw}}(X)$ s.t. the diagram commutes:$$\begin{CD} \mathcal{C}^{\text{cw}}(X) @>\Delta^\text{cw}>>\mathcal{C}^{\text{cw}}(X)\otimes  \mathcal{C}^{\text{cw}}(X)\\ @ViVV @Vi\otimes  iVV \\\mathcal{S}_{*}(X) @>>\Delta> \mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(X)\end{CD}$$then $\Delta^\text{cw}$ is a chain map.
> 2. $i^{*}:H^{*}(X;R)\to H^{*}_{\text{cw}}(X;R)$ is an isomorphism of rings.
> 3. For $\Delta:=\Delta^\text{AW}$ the [[Diagonal Approximation|Alexander-Whitney diagonal approximation]], the following diagonal approximation commutes: $$\Delta^\text{cw}:\mathcal{C}^{\text{cw}}(X)\to \mathcal{C}^{\text{cw}}(X)\otimes \mathcal{C}^{\text{cw}}(X),\quad \sigma\mapsto \sum_{p+q=n}^{}\sigma\rfloor_{p}\otimes  {_{q}\lfloor \sigma} $$

^0e0941

> [!proof]-
> We have that: 
> 1. Notice that $i$ and $i\otimes i$ are injective maps. Hence, $$\Delta^\text{cw}\partial^\text{cw}+\partial^\text{cw}_{\otimes } \Delta^\text{cw} = 0 \iff (i\otimes  i)\circ (\Delta^\text{cw}\partial^\text{cw}+\partial^\text{cw}_{\otimes } \Delta^\text{cw}) = 0$$Now, $$\begin{aligned}(i\otimes  i)\circ (\Delta^\text{cw}\partial^\text{cw}+\partial^\text{cw}_{\otimes } \Delta^\text{cw})&=\Delta \circ  i\circ  \partial^\text{cw}+\partial_{\otimes }(i \otimes  i\circ  \Delta^\text{cw})\\&=\Delta \circ  i\circ  \partial^\text{cw}+\partial_{\otimes } \circ \Delta \circ  i\\&=\underbrace{ (\Delta \circ  \partial+\partial_{\otimes } \circ \Delta ) }_{ =0 }\circ  i=0\end{aligned}$$
> 2. Follows from 1. 
> 3. Obvious.

^fa317c

- **Remark**: The assumption 1) is not trivial: Consider $X:=S^{2}$ with one $0$-cell, no $1$-cell and one $2$-cell. Then, $\partial ^\text{cw}\equiv 0$. However, we have that $$\partial(\text{2-cell})=c-c+c=c$$where $c$ is a constant map. ^7576e6

---
> [!lemma] Theorem 8 
> Let $X$ be a topological space with $X=U\cup V$ where $U,V$ are open and [[Acyclic Space|acyclic]].
> 1. for all $\alpha,\beta\in H^{*}(X;R)$ with $\left| \alpha \right|,\left| \beta \right|>0$, $\alpha \cup \beta=0$.

^8b8bdf

> [!proof]-
> Let $\alpha\in H^p(X;R)$ and $\beta\in H^q(X;R)$ with $p,q\geq 1$. Consider the LES for $(X,U)$. We have: $$\dots\to H^p(X,U;R)\overset{ j^{*}_{U} }{ \to }H^p(X;R)\overset{ i^{*}_{U} }{ \to }H^p(U;R)\to H^{p+1}(X;R)\to \cdots$$Now, as $U$ is acyclic, by UCT $H^p(U;R)=0$. Hence, $\alpha\in \text{ker } i^{*}_{U}=\text{im }j^{*}_{U}$ and we have $\alpha'\in H^p(X,U;R)$ s.t. $j^{*}_{U}(\alpha')=\alpha$. 
> 
> Similarly, we have that there exists $\beta'\in H^q(X,V;R)$ s.t. $j^{*}_{V}(\beta')=\beta$. 
> We now claim that $j^{*}:H^{p+q}(X , U\cup V)\to H^{p+q}(X)$ sends $\alpha'\cup \beta'$ to $\alpha \cup \beta$. If $U,V$ are open, we have a commutative diagram: $$\begin{CD}H^p(X,U)\otimes  H^q(X,V) @>\cup>> H^{p+q}(X,U\cup V)\\@Vj^{*}_{U}\otimes  j^{*}_{V}VV @VVj^{*}V\\H^p(X)\otimes  H^q(X) @>>\cup>H^{p+q}(X)\end{CD}$$ Therefore, we have that: $$\alpha \cup \beta=j^{*}(\alpha'\cup \beta')=0$$ as $H^{p+q}(X,\underbrace{ U\cup V }_{ =X };R)=0$.

^b15041

---
##### Examples
> [!h] Example 1 (2-Torus)
> Let $R$ be a ring and $X:=\mathbb{T}^{2}$ be a CW-complex defined as follows:
> ```tikz
> \usepackage{tikz}
> \usetikzlibrary{calc, arrows, decorations.markings}
> \begin{document}
> \begin{tikzpicture}[scale=1., line width=1pt,
> double_arrow/.style={postaction={decorate}, decoration={markings, mark=at position 0.53 with {\arrow{>>}}}}, 
> triple_arrow/.style={postaction={decorate}, decoration={markings, mark=at position 0.53 with {\arrow{>>>}}}}, 
> single_arrow/.style={postaction={decorate}, decoration={markings, mark=at position 0.53 with {\arrow{>}}}}]
> \tikzset{dot/.style = {shape=circle, fill,draw, inner sep=0pt, minimum size=3pt}}
> \draw[single_arrow] (0,-2) -- (0,0);
> \draw[single_arrow] (2,-2) -- (2,0);
> \draw[double_arrow] (0,0) -- (2,0);
> \draw[double_arrow] (0,-2) -- (2,-2);
> \draw[triple_arrow] (0,-2) -- (2,0);
> \node[dot] (da) at (0,0) {};
> \node[dot] (da) at (2,-2) {};
> \node[dot] (da) at (0,-2) {};
> \node[dot] (da) at (2,0) {};
> \node at (-0.25,0.2) {$x_{3}$};
> \node at (2.25,0.2) {$x_{2}$};
> \node at (-0.25,-2.2) {$x_{0}$};
> \node at (2.25,-2.2) {$x_{1}$};
> 
> \fill[pink!30, opacity=0.5] (0,-2) -- (2,0) -- (0,0) -- cycle;
> \fill[purple!30, opacity=0.2] (0,-2) -- (2,0) -- (2,-2) -- cycle;
> \node at (-0.3,-1) {$a$};
> \node at (2.3,-1) {$a$};
> \node at (1,0.3) {$b$};
> \node at (1,-2.3) {$b$};
> \node at (1.1,-1.3) {$c$};
> \node at (0.5,-0.5) {$U$};
> \node at (1.5,-1.5) {$L$};
> 
> \node at (5.98,-0.5) {$\textbf{0-cells}:x=x_{0}=x_{1}=x_{2}=x_{3}$};
> \node at (4.63,-1) {$\textbf{1-cells}:a,b,c$};
> \node at (6.7,-1.5) {$\textbf{2-cells}:U:=[x_{0},x_{3},x_{2}],L:=[x_{0},x_{1},x_{2}]$};
> \end{tikzpicture}
> \end{document}
>  ```
> 
>  Then, consider $x^{*},a^{*},b^{*},c^{*},U^{*},L^{*}$ as linear functionals forming a basis, i.e. $$\braket{ a^{*} , a } =1,\quad \braket{ a^{*} , b } =\braket{ a^{*} , c } =0$$We have that:
>  1. the differentials are given by: 
> 	 - $\partial x=0$ and $\partial^\text{cw}x=0$
> 	 - $\partial a=\partial b=\partial c=0$ and $\partial^\text{cw}a=\partial^\text{cw}b=\partial^\text{cw}c=0$
> 	 - $\partial U=b-c+a$ and $\partial^\text{cw}U=b-c+a$.
> 	 - $\partial L=a-c+b$ and $\partial^\text{cw}L=a-c+b$
> 2. $i:\mathcal{C}^\text{cw}(\mathbb{T}^{2})\to \mathcal{S}_{*}(\mathbb{T}^{2})$ is a chain map and a quasi-isomorphism.
> 3. $X$ meets all the assumptions of Theorem 6.
> 4. the cochain differentials are given by: 
> 	- $\delta^\text{cw}(x^{*})=x^{*} \circ \partial^\text{cw}=0$ as $\partial^\text{cw}=0$ for all $\sigma\in C_{1}^\text{cw}(\mathbb{T}^{2})$.
> 	- $\delta^\text{cw}(a^{*})=U^{*}+{L^{*}}$ as $\braket{ \delta^\text{cw}(a^{*}) ,U  }=\braket{ a^{*} , \partial^\text{cw}U }=1$ and $\braket{   \delta^\text{cw}(a^{*}) ,L  }=\braket{ a^{*} , \partial^\text{cw}L }=1$.
> 	- $\delta^\text{cw}(b^{*})=U^{*}+{L^{*}}$ as $\braket{ \delta^\text{cw}(b^{*}) ,U  }=\braket{ b^{*} , \partial^\text{cw}U }=1$ and $\braket{   \delta^\text{cw}(b^{*}) ,L  }=\braket{ b^{*} , \partial^\text{cw}L }=1$.
> 	- $\delta^\text{cw}(c^{*})=-U^{*}-{L^{*}}$ as $\braket{ \delta^\text{cw}(c^{*}) ,U  }=\braket{ c^{*} , \partial^\text{cw}U }=-1$, $\braket{   \delta^\text{cw}(c^{*}) ,L  }=\braket{ c^{*} , \partial^\text{cw}L }=-1$.
> 	- $\delta^\text{cw}(U^{*})=\delta^\text{cw}(L^{*})=0$ as we don't have any 3-cell.
> 5. Therfore, we have: 
> 	- $H^0_{\text{cw}}(\mathbb{T}^{2})\cong R\cdot[x^{*}]$
> 	- $H^1_{\text{cw}}(\mathbb{T}^{2})\cong R\cdot[a^{*}+c^{*}]\oplus R\cdot[b^{*}+c^{*}]$
> 	- $H^2_{\text{cw}}(\mathbb{T}^{2})\cong R\cdot[U^{*}]$ with $[U^{*}]=-[L^{*}]$.
> 6. If we define $1:=[x]$, $\alpha:=[a^{*}+c^{*}]$, $\beta:=[b^{*}+c^{*}]$, $\mu:=[U^{*}]=-[L^{*}]$, 
> 	- $\alpha \cup\beta=-\mu$.
> 	- $\varphi \cup \psi=-U^{*}$ and $\psi \cup \varphi=-L^{*}$ for $\varphi:=a^{*}+c^{*}$ and $\psi:=b^{*}+c^{*}$, hence there is no commutativity.
> 	- $\alpha \cup \alpha=0$ and $\beta \cup \beta=0$.
> 7. $H^{*}(\mathbb{T}^{2};R)\cong R[\alpha,\beta] / \{ \alpha^{2}=0, \beta^{2}=0, \alpha\beta=-\beta\alpha \}$

^8c5e48

> [!proof]-
> We have that:
> $$\begin{aligned}\braket{ \varphi \cup \psi , U } &=- \varphi(U\rfloor_{1} )\psi(_{1}\lfloor U)=-\braket{ a^{*}+c^{*} ,  a}\braket{ b^{*}+c^{*} ,  b}=-1\\\braket{ \varphi \cup \psi , L } &=-\varphi(L\rfloor_{1} )\psi(_{1}\lfloor L)=-\braket{ a^{*}+c^{*} , b }\braket{ b^{*}+c^{*} ,  a} =0\end{aligned} $$Hence, $\varphi \cup \psi=-U^{*}$. Similarly, $$\begin{aligned}\braket{ \psi \cup \varphi , U } &=- \psi(U\rfloor_{1} )\varphi(_{1}\lfloor U)=-\braket{ b^{*}+c^{*} ,  a}\braket{ a^{*}+c^{*} ,  b}=0\\\braket{ \psi \cup \varphi , L } &=- \psi(L\rfloor_{1} )\varphi(_{1}\lfloor L)=-\braket{ b^{*}+c^{*} ,  b}\braket{ a^{*}+c^{*} ,  a}=-1\end{aligned} $$Hence, $\psi \cup \varphi=-L^{*}$. Therefore, it holds that $\alpha \cup \beta=-\mu=-\beta \cup \alpha$
> 
> Now, $$\begin{aligned}\braket{ \varphi \cup \varphi , U } &=-\varphi(U\rfloor_{1} )\varphi(_{1}\lfloor U)=-\braket{ a^{*}+c^{*} , a } \braket{ a^{*}+c^{*} , b }=0\\\braket{ \varphi \cup \varphi , L } &=-\varphi(L\rfloor_{1} )\varphi(_{1}\lfloor L)=-\braket{ a^{*}+c^{*} , b } \braket{ a^{*}+c^{*} , a }=0\end{aligned} $$Similarly $\psi \cup \psi=0$ and we have the statement.

^b1e89f

---
