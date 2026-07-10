#Definition #Algebra 

> [!definition]
> Let $R$ be a commutative [[ring]]. We have that the ***spectrum*** $\text{Spec}(R)$ is defined as the set of all [[Prime Ideal|prime ideals]] of $R$ equipped with the [[Zariski topology]], i.e. the basis is given by $\{ X_{f} \}_{f\in R}$ where: $$X_{f}:=\text{Spec}(R) \backslash \{  P : f\in P \}$$
- **Remark**: Let $V(E):=\{ P: E\subseteq P \}$. 
---
##### Properties
> [!lemma] Proposition 1
> Let $f,g\in R$.
> 1. $X_{f}$ form the basis of the Zariski topology.
> 2. $X_{f}\cap X_{g}=X_{fg}$
> 3. $X_{f}=\varnothing$ if and only if $f$ is nilpotent.
> 4. $X_{f}=\text{Spec}(R)$ if and only if $f$ is a unit.
> 5. $X_{f}=X_g$ if and only if $\sqrt{ (f) }=\sqrt{ (g) }$.
> 6. $X$ is quasi-compact.

> [!proof]-
> We have that:
> 1. Obvious.
> 2. This is equivalent to $V(f)\cup V(g)=V(fg)$. Let $P\in V(f)\cup V(g)$. Then, $f\in P$ or $g\in P$. Hence, $fg\in P$ and $P\in V(fg)$. Conversely, if $fg\in P$, as $P$ is prime $f\in P$ or $g\in P$. This proves the statement.
> 3. $\sqrt{ (0) }=\bigcap_{P}^{}P$. Hence, $f\in\sqrt{ (0) }$ if and only if $V(f)=\text{Spec}(R)$.
> 4. $f$ is a unit if and only if it is not contained in any prime ideal.
> 5. By [[Radical (Ring)|Lemma 2]], we have that $\sqrt{ (f) }=\bigcap_{(f)\subseteq P}^{}P$. Hence, if $X_{f}=X_{g}$, then $V(f)=V(g)$ and: $$\sqrt{ (f) }=\bigcap_{P\in V(f)}^{}P=\bigcap_{P\in V(g)}^{}P=\sqrt{ (g) }$$Conversely, if $\sqrt{ (f) }=\sqrt{ (g) }$, then let $P\in V(f)$, i.e. $f\in P$ and as we have that $g^n = af$ for some $a\in R$, $g^n\in P$. Hence, $g\in P$. By symmetry we have our statement.
> 6. Let $X = \bigcup_{f\in I}^{}X_{f}$. Hence, $\varnothing = \bigcap_{f\in I}^{}V(f)=V(I)$. Hence, $(I)=R$. Therefore, $1=r_{1}f_{1}+\dots+r_{n}f_{n}$ for some $f_{1},\dots,f_{n}\in I$. We have that $V(I)=V(f_{1},\dots,f_{n})$. Hence, $X=\bigcup_{i}^{}X_{f_{i}}$. 

---
> [!lemma] Proposition 2
> Let $P\in \text{Spec}(X)$.
> 1. $\overline{\{ P \}}=V(P)$.
> 2. $\{ P \}$ is closed if and only if $P$ is maximal.
> 3. $\text{Spec}(R)$ is $T_{0}$.

> [!proof]-
> We have that:
> 1. As $V(P)$ is closed by definition and $\{ P \}\subseteq V(P)$, we have that $\overline{\{ P \}}\subseteq V(P)$. Conversely, for any closed set $V(I)$ containing $P$, because $P\in V(I)$, we have $I\subseteq P$. Now for $Q\in V(P)$, we have that $P\subseteq Q$ and $I\subseteq Q$. Hence, $Q\in V(I)$. This shows the statement.
> 2. If $\{ P \}$ is closed, then $\{ P \}=V(P)$. Hence, $P$ is the only prime ideal containing $P$. Hence it is maximal. The reverse is analogous.

---
> [!lemma] Proposition 3
> Let $R$ be a commutative ring. TFAE:
> 1. $\text{Spec}(R)$ is irreducible.
> 2. the [[nilradical]] $N(R)$ is prime.

> [!proof]-
> We have that:
> 1. (1=>2): Let $f,g\in R$ s.t. $fg\in N(R)$. Then, $X_{f}\cap X_{g}=X_{fg}=\varnothing$. However, as $X_{f}$ and $X_{g}$ are both open, irreducibility implies that $X_{f}=\varnothing$ or $X_{g}=\varnothing$, in which case $f$ or $g$ is nilpotent. 
> 2. (2=>1): For $f,g$, if $X_{f},X_{g}$ are non-empty then $X_{f}\cap X_{g}=X_{fg}$. Assume that $X_{fg}=\varnothing$. Then, $fg\in N(R)$ and $f\in N(R)$ or $g\in N(R)$. However, this is a contradiction.

---
> [!lemma] Proposition 4
> Let $\varphi:A\to B$ be a ring homomorphism. Then, it induces a map 
> $$\varphi ^{*}:\text{Spec}(B)\to \text{Spec}(A),\quad Q\mapsto \varphi ^{-1}(Q)$$
> 1. For $f\in A$, $(\varphi ^{*})^{-1}(X_{f})=Y_{\varphi(f)}$. More concretely, $\varphi ^{*}$ is continuous.
> 2. For $I\unlhd A$, $(\varphi ^{*})^{-1}(V(I))=V(I^e)$
> 3. For $J\unlhd B$, $\overline{\varphi ^{*}(V(J))}=V(\varphi ^{-1}(J))$.
> 4. If $\varphi$ is surjective, $\varphi ^{*}$ is a homeomorphism $\text{Spec}(B)\cong V(\text{ker }\varphi)$. In particular, $\text{Spec}(A)\cong \text{Spec}(A / N(A))$.
> 5. If $\varphi$ is injective, $\varphi ^{*}(\text{Spec}(B))$ is dense in $\text{Spec}(A)$. More precisely, $\varphi ^{*}(\text{Spec}(B))$ is dense in $\text{Spec}(A)$ if and only if $\text{ker }\varphi \subseteq N(A)$.

> [!proof]-
> We have that:
> 1. By definition: $$\begin{aligned}(\varphi ^{*})^{-1}(X_{f})&=\{ P\in \text{Spec}(B):f\notin\varphi ^{-1} (P)\}\\&=\{ P\in \text{Spec}(B):\varphi(f)\notin  P\}=Y_{\varphi(f)}\end{aligned}$$
> 2. Let $I\unlhd A$. Then, $$\begin{aligned}(\varphi ^{*})^{-1}(V(I))&=\{ P\in \text{Spec}(B):I \subseteq\varphi ^{-1} (P)\}\\&=\{ P\in \text{Spec}(B) : I^e \subseteq P\}=V(I^e)\end{aligned}$$
> 3. Similar.
> 4. Let $I\cong \text{ker } \varphi$. Then, by the first isomorphism theorem $A / I\cong B$ where is a one-to-one correspondence between $A / I$ and ideals of $A$ that contain $I$. Hence, $\varphi ^{*}$ is a bijection between $\text{Spec}(B)$ and $V(\text{ker }\varphi)$. Lastly, we have that $\varphi ^{*}(V(J))=V(\varphi ^{-1}(J))$ and we have a homeomorphism. 
>    
>    In particular for $\pi:A \to A / N(A)$, we have that $\text{Spec}(A / N(A))\cong V(N(A))=\text{Spec}(A)$.
> 1. From 3) we have that $\overline{\varphi ^{*}(\text{Spec}(B))}=\overline{\varphi ^{*}(V(0))}=V(\varphi ^{-1}(0))=V(\text{ker }\varphi)$. Hence, $\overline{\varphi ^{*}(\text{Spec}(B))}=\text{Spec}(A)$ if and only if $V(\text{ker }\varphi)=\text{Spec}(A)$.