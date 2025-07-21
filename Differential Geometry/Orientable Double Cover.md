#Definition #DifferentialGeometry 

> [!definition]
> Let $M^n$ be a [[Topological Manifold|manifold]]. 
> 1. the ***orientable double cover*** is given by: $$\text{O}M:=\{ (x,\mu_{x}): x\in M,\mu_{x}\in H_{n}(M|x) \}$$where $\mu_{x}$ is a [[Local Homology|local orientation]]. The covering map is given by $p:\text{O}M\to M,(x,\mu_{x})\mapsto x$.
> 2. the ***orientable double cover over $R$*** for a [[ring]] $R$ is given by: $$\tilde{M}_{R}:=\{ (x,\alpha_{x}):x\in M, \alpha_{x}\in H_{n}(M|x;R) \}$$with a covering map $p:\tilde{M}_{R}\to M$

^9fc8dd

- **Related Definition**: The orientable double cover is endowed with the following topology: For a chart $\varphi:\mathbb{R}^n\to U\subseteq M$, let $B:=\varphi(B_{<r}(0))\subseteq U$ be a ball chart. As $H_{n}(M|B)\cong H_{n}(M|y)\cong \mathbb{Z}$ for any $y\in B$ per [[Local Homology|Proposition 2]], we can choose a generator $\mu_{B}\in H_{n}(M|B)$ and define:$$\mathcal{W}(\mu_{B}):=\{ (x,L_{x}(\mu_{B})) \}_{x\in B}\subseteq \text{O}M$$Then, the base of the topology is defined as $\{ \mathcal{W}(\mu_{B}) \}_{B,\mu_{B}}$ ^6460ba
- **Related definition**: An ***$R$-orientation*** on $M$ is a [[section]] $\mu:M\to \tilde{M}_{R}$ s.t. for all $x\in M$, $\mu(x)\in H_{n}(M|x;R)$ is a generator. 
- **Related definition**: As $H_{n}(M|x;R)\cong H_{n}(M|x)\otimes_{\mathbb{Z}}R$ from [[Tor|UCT]] as $H_{n-1}(M|x)=0$, we have: $$\tilde{M}_{r}:=\{ (x,\pm \mu_{x}\otimes  r) \}_{x\in M}\subseteq \tilde{M}_{R}$$
	Notice that $\tilde{M}_{r}=M$ if and only if $2r=0$.
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

> [!proof]+
> We have that:
> 1. We can take $o:x\mapsto \mu_{x}\otimes 1$.
> 2. If $2=0$, then $\tilde{M}_{r}=M$ for all $r\in R$. 