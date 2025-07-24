#Definition #DifferentialGeometry 

> [!definition]
> Let $M^n$ be a [[Topological Manifold|manifold]]. 
> 1. the ***orientable double cover*** is given by: $$\text{O}M:=\{ (x,\mu_{x}): x\in M,\mu_{x}\in H_{n}(M|x) \}$$where $\mu_{x}$ is a [[Local Homology|local orientation]]. The covering map is given by $p:\text{O}M\to M,(x,\mu_{x})\mapsto x$.
> 2. the ***orientable double cover over $R$*** for a [[ring]] $R$ is given by: $$\tilde{M}_{R}:=\{ (x,\alpha_{x}):x\in M, \alpha_{x}\in H_{n}(M|x;R) \}$$with a covering map $p:\tilde{M}_{R}\to M$

^9fc8dd

- **Related Definition**: The orientable double cover is endowed with the following topology: For a chart $\varphi:\mathbb{R}^n\to U\subseteq M$, let $B:=\varphi(B_{<r}(0))\subseteq U$ be a ball chart. As $H_{n}(M|B)\cong H_{n}(M|y)\cong \mathbb{Z}$ for any $y\in B$ per [[Local Homology|Proposition 2]], we can choose a generator $\mu_{B}\in H_{n}(M|B)$ and define:$$\mathcal{W}(\mu_{B}):=\{ (x,L_{x}(\mu_{B})) \}_{x\in B}\subseteq \text{O}M$$Then, the base of the topology is defined as $\{ \mathcal{W}(\mu_{B}) \}_{B,\mu_{B}}$ ^6460ba
- **Related definition**: An ***$R$-orientation*** on $M$ is a [[section]] $\mu:M\to \tilde{M}_{R}$ s.t. for all $x\in M$, $\mu(x)\in H_{n}(M|x;R)$ is a generator. 
- **Related definition**: As $H_{n}(M|x;R)\cong H_{n}(M|x)\otimes_{\mathbb{Z}}R$ from [[Tor|UCT]] as $H_{n-1}(M|x)=0$, we have: $$\tilde{M}_{r}:=\{ (x,\pm \mu_{x}\otimes  r) \}_{x\in M}\subseteq \tilde{M}_{R}$$
	Notice that if $2r=0$ then $\tilde{M}_{r}=M$ and if $2r\neq 0$ then $\tilde{M}_{r}\cong \tilde{M}$.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. the topology is well-defined.
> 2. $p:\text{O}M\to M$ sends $\mathcal{W}(\mu_{B})$ homeomorphically to $B$.
> 3. $\text{O}M$ is [[Orientation|orientable]].

^abbee2

> [!proof]-
> We have:
> 1. We need to show that $\{ \mathcal{W}(\mu_{B}) \}_{B,\mu_{B}}$ forms a base. Firstly, for any $(x,\mu_{x})\in \text{O}M$, let $B$ be a ball chart containing $x$. Then, by choosing $\mu_{B}:=L^{-1}_{x}(\mu_{x})$, we have that $(x,\mu_{x})\in\mathcal{W}(\mu_{B})$. 
>    
>    Let $(x,\mu_{x})\in \mathcal{W}(\mu_{B})\cap \mathcal{W}(\mu_{B'})$. Then, we have that $\mu_{x}=L_{x}(\mu_{B})=L_{x}'(\mu_{B'})$. As ball charts form a basis of $M$, we have a ball chart $x\in B''\subseteq B\cap B'$. Then, let $\mu_{B''}:=(L''_{x})^{-1}(\mu_{x})$. Then, we have that $(x,\mu_{B''})\in \mathcal{W}(\mu_{B''})$.
> 2. We have that $p$ is bijective: For $x=x'$, then $(x,L_{x}(\mu_{B}))=(x',L_{x'}(\mu_{B}))\in \mathcal{W}(\mu_{B})$. Conversely it is surjective by definition. 
>    
>    Now, to show continuity, for any ball chart $B'\subseteq B$, we have that $(p|_{\mathcal{W}(\mu_{B})}) ^{-1}(B')=\mathcal{W}(\mu_{B'})$ is open for $\mu_{B'}:=(L'_{x})^{-1}L_{x}(\mu_{B})$. Also the inverse is continuous as for every $\mathcal{W}(\mu_{B'})\subseteq \mathcal{W}(\mu_{B})$, we have that $B'$ is open.
> 3. We define an orientation as follows: $$(x,\mu_{x})\mapsto \tilde{\mu}\in H_{n}(\text{O}M|(x,\mu_{x}))\cong H_{n}(\mathcal{W}(\mu_{B})|(x,\mu_{x}))\overset{ p_{*} }{ \cong  } H_{n}(B|x)\cong H_{n}(M|x)$$where $\tilde{\mu}$ is the unique element corresponding to $\mu_{x}\in H_{n}(M|x)$ under the sequence of isomorphisms. Then, $\tilde{\mu}$ is indeed a generator and $\mathcal{W}(\mu_{B})$ is a ball chart of $(x,\mu_{x})$ via $(p|_{\mathcal{W}(\mu_{B})})^{-1}\circ\varphi$. We now define $$\mathcal{L}_{x}:H_{n}(\text{O}M | \mathcal{W}(\mu_{B}))\to H_{n}(\text{O}M|(x,\mu_{x}))$$Let $B=\varphi(B_{<r}(0))$. Then, we can define $B':=\varphi(B_{<2r}(0))$ and $B\subseteq B'$. Then, let $\mu_{B'}$ s.t. $$L'_{x}(\mu_{B'})=L_{x}(\mu_{B})=\mu_{x},\quad \forall x\in B$$We then have that:$$ H_{n}(\text{O}M| \mathcal{W}(\mu_{B}))\cong H_{n}(\mathcal{W}(\mu_{B'})|\mathcal{W}(\mu_{B}))\cong H_{n}(B'|B)\cong H_{n}(M|B)$$and $\tilde{\mu}_{B}\in H_{n}(\text{OM}|\mathcal{W}(\mu_{B}))$ that is identified with $\mu_{B}$ from the isomorphism. Then, we have that: $$\begin{CD} H_{n}(\text{O}M|\mathcal{W}(\mu_{B})) @>\cong>> H_{n}(\mathcal{W}(\mu_{B'})|\mathcal{W}(\mu_{B})) @>\cong>> H_{n}(B'|B) @>\cong>> H_{n}(M|B)\\ @V\mathcal{L}_{(x,\mu_{x})}VV&&&&@VVL_{x}V\\ H_{n}(\text{O}M|(x,\mu_{x}))@>\cong>> H_{n}(\mathcal{W}(\mu_{B'})|(x,\mu_{x})) @>\cong>> H_{n}(B'|x) @>\cong>> H_{n}(M|x)\end{CD}$$and $\mathcal{L}_{(x,\mu_{x})}(\tilde{\mu}_{B})\leftrightarrow L_{x}(\mu_{B})=\mu_{x}$ and $\mathcal{L}_{(x,\mu_{x})}(\tilde{\mu}_{B})=\tilde{\mu}_{x}$. This shows that we have an orientation.

^8434b4

- **Corollary**: $p:\text{O}M\to M$ is a $2:1$-covering and by [[Topological Manifold|Example 2]], $\text{O}M$ is a orientable $n$-dimensional manifold. ^1adb57

---
> [!lemma] Theorem 2
> Let $M^n$ be a path-connected manifold.
> 1. $\text{O}M$ has at most $2$ path-connected components.
> 2. $M$ is orientable if and only if $\text{O}M$ has $2$ path-connected components.
> 3. if $\pi_{1}(M)$ has no subgroups of index $2$, $M$ is orientable.

^8d5bea

> [!proof]-
> We have that:
> 1. From [[Covering Space|Lemma 5]].
> 2. Assume $M$ is orientable with orientation $o:x\mapsto \mu_{x}$. Then, we can define two continuous maps $j,j':M\to \text{O}M$: $$j(x):=(x,\mu_{x}),\quad j'(x):=(x,-\mu_{x})$$Indeed, for any $(x,\mu_{x})\in\mathcal{W}(\mu_{B})$ we have that $j(B)\subseteq \mathcal{W}(\mu_{B})$ as for any $y\in B$, $$\mu_{y}=L_{y}(L_{x}^{-1}(\mu_{x}))=L_{y}(L^{-1}_{x}(L_{x}(\mu_{B})))=L_{y}(\mu_{B})$$Similarly, $j'$ is continuous.
>    
>    Clearly, $j(M)\cap j'(M)=\varnothing$ and $j(M)\cup j'(M)=\text{O}M$ where $j(M),j'(M)$ are path connected.
>    
>    Conversely, if $\text{O}M$ is disconnected, i.e. $\text{O}M:=C_{1}\sqcup C_{2}$ with $C_{1},C_{2}$ path-connected. Then, $p|_{C_{j}}:C_{j}\to M$ is a homeomorphism by [[Covering Space|Lemma 5]]. Then, we can clearly endow $M$ an orientation by $o:=\pi_{2} \circ (p|_{C_{1}})^{-1}$ where for all $x\in M$ and a ball chart $B$ with $y\in B$ we have: $$o(y)=L_{y}(\mu_{B})=L_{y}(L_{x}^{-1}(o(x)))$$
> 3. If $\pi_{1}(M)$ has no subgroups of index $2$, then every $2:1$ covering $X\to M$ must be disconnected by [[Covering Space|Theorem 3]]. The rest follows from 2.

^9476bf

---
> [!lemma] Proposition 3
> Let $M^n$ be a manifold.
> 1. if $M$ is orientable, then it is $R$-orientable for all ring $R$.
> 2. $M$ is $R$-orientable if $2=0$ in $R$ even if $M$ is non-orientable. In particular, $M$ is $\mathbb{Z} / 2\mathbb{Z}$-orientable.

^acf957

> [!proof]-
> We have that:
> 1. We can take $o:x\mapsto \mu_{x}\otimes 1$.
> 2. If $2=0$, then $\tilde{M}_{r}=M$ for all $r\in R$. 

^0eb9f7

---
> [!lemma] Lemma 3
> Let $M^n$ be a manifold and $A\subseteq M$ compact.
> 1. if $\alpha:M\to \tilde{M}_{R}$ is a section of $\tilde{M}_{R}\to M$, then there exists a unique $\alpha_{A}\in H_{n}(M|A;R)$ s.t. for $$L_{A,x}:H_{n}(M|A;R)\to H_{n}(M|x;R)$$given by $\text{inc}:(M,M \backslash A)\to (M, M \backslash x)$ we have $L_{A,x}(\alpha_{A})=\alpha_{x}$ for all $x\in A$.
> 2. $H_{i}(M|A;R)=0$ for all $i>n$.

^fee136

> [!proof]-
> From [[Singular Homology|Mayer-Vietoris 2]], we have the LES: $$\dots\to H_{k}(M|A\cup B;R)\to H_{k}(M|A;R)\oplus H_{k}(M|B;R)\to H_{k}(M|A\cap B;R)\to H_{k-1}(M|A\cup B;R)\to \cdots$$For $T\subseteq S\subseteq X$, let $L_{S,T}:H_{k}(X|S;R)\to H_{k}(X|T;R)$ given by $\text{inc}:X|S\to X|T$.
> 1. **Claim 1**: **If Lemma holds for $A,B\subseteq M$ and $A\cap B\subseteq M$, then it holds for $A\cup B\subseteq M$.** 
>    Firstly, we show 2. If $k>n$, then $H_{k}(M|A;R)=H_{k}(M|B;R)=0$ and $H_{k+1}(M|A\cap B;R)=0$. Hence, by the sequence above, $H_{k}(M|A\cup B;R)=0$.
>    
>    For 1, let $k=n$. we have the following sequence: $$0\to H_{n}(M|A\cup B;R)\xrightarrow{\Phi:=(L_{A\cup B,A},-L_{A\cup B,B})}H_{n}(M|A;R)\oplus H_{n}(M|B;R)\xrightarrow{\Psi:=L_{A,A\cap B}+L_{B,A\cap B}}BH_{n}(M|A\cap B;R)\to \cdots$$If $\alpha$ is a section of $\tilde{M}_{R}\to M$, then there exists $\alpha_{A}\in H_{n}(M|A;R)$ and $\alpha_{B}\in H_{n}(M|B;R)$ s.t. $$L_{A,x}(\alpha_{A})=\alpha_{x},\quad \forall x\in A,\quad L_{B,x}(\alpha_{B})=\alpha_{x},\quad \forall x\in B$$Consider $\alpha'_{A\cap B}:=L_{A,A\cap B}(\alpha_{A})$ and $\alpha''_{A\cap B}:=L_{B,A\cap B}(\alpha_{B})$. Then, $L_{A\cap B,x}(\alpha'_{A\cap B})=L_{A\cap B,x}(\alpha''_{A\cap B})=\alpha_{x}$ for all $x\in A\cap B$. However, as the lemma holds for $A\cap B$, we have that $\alpha_{A\cap B}$ is unique and $\alpha_{A\cap B}:=\alpha'_{A\cap B}=\alpha''_{A\cap B}$. 
>    
>    We have that: $$\Psi(\alpha_{A},-\alpha _{B})=\alpha_{A\cap B}-\alpha_{A\cap B}=0$$Therefore, there exists $\alpha_{A\cup B}\in H_{n}(M|A\cup B;R)$ s.t. $L_{A\cup B,A}(\alpha_{A\cup B})=\alpha_{A}$ and $L_{A\cup B,B}(\alpha_{A\cup B})=\alpha_{B}$ and for all $x\in A\cup B$, $$L_{A\cup B,x}(\alpha_{A\cup B})=\alpha_{x}$$Now, to prove the uniqueness, as $L_{A\cup B,x}$ is a homomorphism, it suffices to show that if $L_{A\cup B,x}(\alpha)=0$ for all $x\in A\cup B$, we have that $\alpha=0$. Indeed, if $L_{A\cup B,x}(\alpha)=0$ for all $x\in A\cup B$, we can define $\alpha_{A}:=L_{A\cup B,A}(\alpha)$ and $\alpha_{B}:=L_{A\cup B,B}(\alpha)$ and clearly, $$L_{A,x}(\alpha_{A})=0,\quad \forall x\in A,\quad L_{B,x}(\alpha_{B})=0,\quad \forall x\in B$$Therefore, by uniqueness, $\alpha_{A}=0,\alpha_{B}=0$. Hence, $$\Phi(\alpha)=(\alpha_{A},-\alpha_{B})=0$$We conclude by the injectivity of $\Phi$.
> 2. **Claim 2: If Lemma holds for compact $A\subseteq \mathbb{R}^n$ then it holds for any compact $A\subseteq B\subseteq M$ where $B$ is a ball chart.**
>    Let $B$ be a ball chart. Then, we have that $A\subseteq B^\circ\subseteq U\subseteq M$ where $B^\circ\cong B_{<r}(0)$ and $U\cong \mathbb{R}^n$. Hence, by excision: $$H_{n}(M|A;R)\cong H_{n}(B^\circ |A;R)\cong H_{n}(U|A;R)\cong H_{n}(\mathbb{R}^n|A;R)$$where the isomorphism commutes with $L$ maps as they are all induced by inclusion. 
> 3. **Claim 3: If Lemma holds for $A\subseteq B\subseteq M$ for a ball chart $B$, then it holds for sets $A:=A_{1}\cup\dots \cup A_{m}$ with $A_{i}$ compact, contained in a ball chart.**
>    By induction, it holds when $m=1$. Otherwise, it holds with Claim 1. 
> 4. **Claim 4: the Lemma holds for compact $A\subseteq \mathbb{R}^n$ with $A=A_{1}\cup\dots \cup A_{m}$ for convex $A_{i}$** 
> 	First, take $m=1$, i.e. $A$ is a compact convex set. Then, the inclusion $(\mathbb{R}^n|A)\to(\mathbb{R}^n|x)$ is a homotopy equivalence from the convexity (similar to the $S^n$ case) and $L_{A,x}:H_{n}(\mathbb{R}^n|A;R)\cong H_{n}(\mathbb{R}^n|x;R)$. Further, for $x,y\in A$ we have that: $L_{A,x}$ and $L_{A,y}$ commute via a canonical isomorphism. This shows that for any section $\alpha$, we have an element in $H_{n}(\mathbb{R}^n|A;R)$ s.t. the Lemma holds.
> 	
> 	For $m\geq 2$, we can use Claim 1 and induction.
> 5. **Claim 5: the Lemma holds for compact $A\subseteq \mathbb{R}^n$**. 
>    Let $\alpha\in H_{i}(M|A;R)$. Let $z\in S_{i}(M|A;R)$ be a cycle s.t. $[z]=\alpha$. We can view $z$ as a chain in $S_{i}(M)$ with $C:=\text{im }\partial z\subseteq M \backslash A$. Note that $C$ is compact as a finite union of images of compact sets. Since $A,C$ are disjoint and both compact, there exists $0<\delta:=\text{dist}(A,C)$. 
>    
>    We can cover $A$ now with a $\delta /2$-net, i.e. $K:=B_{1}\cup\dots \cup B_{m}$ where $B_{i}$ is a closed ball of radius $<\delta / 2$ centered at a point in $A$. Then, clearly $C \subseteq M \backslash K$ and $z$ is also a cycle in $S_{i}(M|K;R)$. We can now define $\alpha_{K}:=[z]\in H_{i}(M|K;R)$ and we have that from Claim 4, $H_{i}(M|K;R)=0$ for all $i> n$. Therefore, $\alpha=L_{K,A}(\alpha_{K})=0$ and $H_{i}(M|A;R)=0$. 
>    
>    Now let $x\mapsto \alpha_{x}$ be a section of $\tilde{\mathbb{R}^n}_{R}$. We first show the uniqueness of $\alpha\in H_{n}(M|A;R)$. Let $L_{A,x}(\alpha)=\alpha_{x}=0$ for all $x\in A$. We first show that $\alpha_{x}=0$ for all $x\in K$. For any $x\in K$, we have from above that $L_{B_{i},x}:H_{n}(\mathbb{R}^n|B_{i};R)\to H_{n}(\mathbb{R}^n|x;R)$ is an isomorphism for all $x\in B_{i}$. Hence, $\alpha_{x}=0$ for all $x\in B_{i}$ and $\alpha_{x}=0$ for all $x\in K$.
>    
>    By Claim 4, we have that by uniqueness $\alpha_{K}=0$ and $\alpha=L_{K,A}(\alpha_{K})=0$.
>    
>    Lastly, to show the existence: Pick a huge ball $B:=B_{\leq r}(0)\subseteq \mathbb{R}^n$ s.t. $A\subseteq B^\circ$. Then, by Claim 4, there exists $\alpha_{B}\in H_{n}(\mathbb{R}^n|B;R)$ s.t. $L_{B,x}(\alpha_{B})=\alpha_{x}$ for all $x\in B$. If we define $\alpha_{A}:=L_{B,A}(\alpha_{B})$, then $L_{A,x}(\alpha_{A})=\alpha_{x}$ for all $x\in A$.
>    
>    

^981230

---
> [!lemma] Theorem 4
> Let $M^n$ be a compact connected manifold. For $x\in M$, consider the map: $$L_{x}:H_{n}(M;R)\to H_{n}(M|x;R)\cong R$$given by inclusion $\text{inc}:(M,\varnothing)\to (M, M \backslash x)$.
> 1. if $M$ is $R$-orientable, then $L_{x}$ is an isomorphism.
> 2. if $M$ is not $R$-orientable, then $L_{x}$ is injective and $\text{im }L_{x}=\{ a\in R:2a = 0 \}$.
> 3. for all $i>n$, $H_{i}(M;R)=0$.

^6ed1a7

> [!proof]-
> We have that:
> 1. Let $\Gamma_{R}$ denote all sections of the covering $\tilde{M}_{R}\to M$. Then, $\Gamma_{R}$ is an $R$-module by adding sections using fiberwise additions in $H_{n}(M|x;R)$ and multiplication by a scalar $r\in R$. Indeed, these operations preserve the continuity of the sections. 
>    
>    We now have the following homomorphism of $R$-modules: $$\Theta:H_{n}(M;R)\to\Gamma_{R},\quad a\mapsto (x\mapsto L_{M,x}(a))$$By Lemma 3.1 with $A:=M$, we have that $\Theta$ is an isomorphism. Let $x_{0}\in M$. Then, we have the restriction map: $$\rho:\Gamma_{R}\to H_{n}(M|x_{0};R),\quad s\mapsto s_{x_{0}}$$
>    If $M$ is $R$-orientable, there exists an $R$-orientation $\mu\in \Gamma_{R}$ s.t. $\rho(\mu)$ is a generator and $\rho$ is surjective. However, as $M$ is path-connected we have that $\Gamma_{R}$ must be injective: Indeed, as $p:\tilde{M}_{R}\to M$ is a covering space and $\text{id}:M\to M$ is a continuous map, then as $M$ is a connected manifold, we have that any lift of $\text{id}$ is unique by [[Lift|Lemma 3]]. However, such lifts are exactly the sections. Hence, the sections are disjoint on $x_{0}$. 
>    
>    Now, we have that $L_{x_{0}}=\rho \circ\Theta$ which proves the statement.
>    
> 2. If $M$ is not $R$-orientable, we only have that $L_{x_{0}}$ is injective from 1. Further, if $M$ is not $R$-orientable, by Proposition 3 it is also not-orientable. Assume $r\in \text{im }\rho$ where $2r\neq 0$. Then, $\tilde{M}_{r}\cong \text{O}M$ and we have a section in $\tilde{M}_{r}\cong \text{O}M$. This contradicts that $M$ is not orientable.
>    
>    Conversely, if $r\in R$ with $2r=0$, then $\tilde{M}_{r}=M$ and we clearly have a section. Therefore, $r\in \text{im }\rho$. 
> 3. From Lemma 3, by taking $A:= M$.

^64ddf6

- **Corollary**: We have that: $$H_{n}(M;\mathbb{Z})\cong \begin{cases}\mathbb{Z}&\text{if }M\text{ is orientable}\\0&\text{otherwise}\end{cases}$$ ^cf0227
---
> [!lemma] Corollary 5
> Let $M^n$ be a compact connected manifold.
> 1. if $M$ is orientable, then $H_{n-1}(M)_{\text{tors}}=0$.
> 2. if $M$ is not orientable, then $H_{n-1}(M)_{\text{tors}}\cong \mathbb{Z} / 2\mathbb{Z}$.

^b26bbc

> [!proof]-
> We use the well-known fact that if $M$ is compact, $H_{i}(M)$ is finitely generated. Recall the [[Tor|UCT]]: $$0\to H_{n}(M)\otimes  R\to H_{n}(M;R)\to \text{Tor}(H_{n-1}(M),R)\to 0$$Since $H_{n-1}(M)$ is finitely generated, we have $H_{n-1}(M)_{\text{tors}}\cong \bigoplus_{i\in[r]}\mathbb{Z} / \ell_{i}\mathbb{Z}$ for $\ell_{i}\geq 2$. 
> 1. Assume $M$ is orientable. Suppose by contradiction that $r\geq 1$. Pick $p$ prime s.t. $p|\ell_{1}$. Take $R:= \mathbb{Z} / p\mathbb{Z}$. Then, the UCT becomes: $$0\to \mathbb{Z} / p\mathbb{Z}\to \mathbb{Z} / p\mathbb{Z}\to \bigoplus _{i\in[r]}\mathbb{Z} / \text{gcd}(\ell_{i},p)\mathbb{Z}\to 0$$as $H_{n}(M)\otimes \mathbb{Z} / p\mathbb{Z}\cong \mathbb{Z}\otimes \mathbb{Z} / p\mathbb{Z}\cong \mathbb{Z}  / p\mathbb{Z}$ and as $M$ is orientable by Proposition 3 it is $\mathbb{Z} / p\mathbb{Z}$-orientable and $H_{n}(M;\mathbb{Z} / p\mathbb{Z})\cong \mathbb{Z} / p\mathbb{Z}$. For the last term, it follows from [[Tor|Lemma 5]]. 
>    
>    However, as $\mathbb{Z} / \text{gcd}(\ell_{1},p)\mathbb{Z}\neq 0$, we have that the UCT is not exact, which is a contradiction.
> 2. If $M$ is not orientable, then, we claim that for all $2\leq m\in \mathbb{Z}$, we have: $$H_{n}(M; \mathbb{Z} / m\mathbb{Z})\cong\begin{cases} 0&m\text{ odd}\\\mathbb{Z} / 2\mathbb{Z}&m \text{ even}\end{cases}$$
> 	Indeed, if $m$ is odd, there is no element $r\in \mathbb{Z} / m\mathbb{Z}$ s.t. $2r=0$. Hence, $\tilde{M}_{r}\cong \tilde{M}$ for all $0\neq r\in \mathbb{Z} / m\mathbb{Z}$ and $M$ is not $\mathbb{Z} / m\mathbb{Z}$-orientable. Hence, by Theorem 4, $H_{n}(M; \mathbb{Z} / m\mathbb{Z}) = 0$. 
> 	
> 	If $m$ is even, for $m> 2$ for the same reason $M$ is not $\mathbb{Z} / m\mathbb{Z}$-orientable. Hence, by Theorem 4, $H_{n}(M;\mathbb{Z} / m\mathbb{Z})\cong \mathbb{Z} / 2\mathbb{Z}$. If $m=2$, then $M$ is $\mathbb{Z} / 2\mathbb{Z}$-orientable and we have the statement.
> 	
> 	Now, we have that for all odd $m$, $0\to \bigoplus _{i\in [r]}\mathbb{Z} / \text{gcd}(\ell_{i},m)\mathbb{Z} \to 0$ from the UCT. Therefore, for all $i\in[r]$, $\ell_{i}$ is coprime with every odd number, i.e. $\ell_{i}=2^{s_{i}}$ for $s_{i}\geq 1$. Now, by taking even $m$, as $H_{n}(M;\mathbb{Z})= 0$, we have that the UCT becomes: $$0\to 0 \to \mathbb{Z} / 2\mathbb{Z} \to \text{Tor}(H_{n-1}(M),\mathbb{Z} / 2\mathbb{Z})\to 0$$i.e. $\text{Tor}(H_{n-1}(M),\mathbb{Z} / 2\mathbb{Z})\cong \mathbb{Z} / 2\mathbb{Z}$. In other words, $r=1$ and $\ell_{1}=2$. This shows that $H_{n-1}(M)_{\text{tors}}\cong \mathbb{Z} / 2\mathbb{Z}$.

^3eaaab

---
