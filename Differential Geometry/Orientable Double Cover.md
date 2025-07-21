#Definition #DifferentialGeometry 

> [!definition]
> Let $M^n$ be a [[Topological Manifold|manifold]]. 
> 1. the ***orientable double cover*** is given by: $$\text{O}M:=\{ (x,\mu_{x}): x\in M,\mu_{x}\in H_{n}(M|x) \}$$where $\mu_{x}$ is a [[Local Homology|local orientation]]. The covering map is given by $p:\text{O}M\to M,(x,\mu_{x})\mapsto x$.

^9fc8dd

- **Related Definition**: The orientable double cover is endowed with the following topology: For a chart $\varphi:\mathbb{R}^n\to U\subseteq M$, let $B:=\varphi(B_{<r}(0))\subseteq U$ be a ball chart. As $H_{n}(M|B)\cong H_{n}(M|y)\cong \mathbb{Z}$ for any $y\in B$ per [[Local Homology|Proposition 2]], we can choose a generator $\mu_{B}\in H_{n}(M|B)$ and define:$$\mathcal{W}(\mu_{B}):=\{ (x,L_{x}(\mu_{B})) \}_{x\in B}\subseteq \text{O}M$$Then, the base of the topology is defined as $\{ \mathcal{W}(\mu_{B}) \}_{B,\mu_{B}}$ ^6460ba
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. the topology is well-defined.
> 2. $p:\text{O}M\to M$ sends $\mathcal{W}(\mu_{B})$ homeomorphically to $B$.
> 3. $\text{O}M$ is [[Orientation|orientable]].

> [!proof]-
> We have:
> 1. We need to show that $\{ \mathcal{W}(\mu_{B}) \}_{B,\mu_{B}}$ forms a base. Firstly, for any $(x,\mu_{x})\in \text{O}M$, let $B$ be a ball chart containing $x$. Then, by choosing $\mu_{B}:=L^{-1}_{x}(\mu_{x})$, we have that $(x,\mu_{x})\in\mathcal{W}(\mu_{B})$. 
>    
>    Let $(x,\mu_{x})\in \mathcal{W}(\mu_{B})\cap \mathcal{W}(\mu_{B'})$. Then, we have that $\mu_{x}=L_{x}(\mu_{B})=L_{x}'(\mu_{B'})$. As ball charts form a basis of $M$, we have a ball chart $x\in B''\subseteq B\cap B'$. Then, let $\mu_{B''}:=(L''_{x})^{-1}(\mu_{x})$. Then, we have that $(x,\mu_{B''})\in \mathcal{W}(\mu_{B''})$.
> 2. We have that $p$ is bijective: For $x=x'$, then $(x,L_{x}(\mu_{B}))=(x',L_{x'}(\mu_{B}))\in \mathcal{W}(\mu_{B})$. Conversely it is surjective by definition. 
>    
>    Now, to show continuity, for any ball chart $B'\subseteq B$, we have that $(p|_{\mathcal{W}(\mu_{B})}) ^{-1}(B')=\mathcal{W}(\mu_{B'})$ is open for $\mu_{B'}:=(L'_{x})^{-1}L_{x}(\mu_{B})$. Also the inverse is continuous as for every $\mathcal{W}(\mu_{B'})\subseteq \mathcal{W}(\mu_{B})$, we have that $B'$ is open.
> 3. We define an orientation as follows: $$(x,\mu_{x})\mapsto \tilde{\mu}\in H_{n}(\text{O}M|(x,\mu_{x}))\cong H_{n}(\mathcal{W}(\mu_{B})|(x,\mu_{x}))\overset{ p_{*} }{ \cong  } H_{n}(B|x)\cong H_{n}(M|x)$$where $\tilde{\mu}$ is the unique element corresponding to $\mu_{x}\in H_{n}(M|x)$ under the sequence of isomorphisms. Then, $\tilde{\mu}$ is indeed a generator and $\mathcal{W}(\mu_{B})$ is a ball chart of $(x,\mu_{x})$ via $(p|_{\mathcal{W}(\mu_{B})})^{-1}\circ\varphi$. We now define $$\mathcal{L}_{x}:H_{n}(\text{O}M | \mathcal{W}(\mu_{B}))\to H_{n}(\text{O}M|(x,\mu_{x}))$$Let $B=\varphi(B_{<r}(0))$. Then, we can define $B':=\varphi(B_{<2r}(0))$ and $B\subseteq B'$. Then, let $\mu_{B'}$ s.t. $$L'_{x}(\mu_{B'})=L_{x}(\mu_{B})=\mu_{x},\quad \forall x\in B$$We then have that:$$ H_{n}(\text{O}M| \mathcal{W}(\mu_{B}))\cong H_{n}(\mathcal{W}(\mu_{B'})|\mathcal{W}(\mu_{B}))\cong H_{n}(B'|B)\cong H_{n}(M|B)$$and $\tilde{\mu}_{B}\in H_{n}(\text{OM}|\mathcal{W}(\mu_{B}))$ that is identified with $\mu_{B}$ from the isomorphism. Then, we have that: $$\begin{CD} H_{n}(\text{O}M|\mathcal{W}(\mu_{B})) @>\cong>> H_{n}(\mathcal{W}(\mu_{B'})|\mathcal{W}(\mu_{B})) @>\cong>> H_{n}(B'|B) @>\cong>> H_{n}(M|B)\\ @V\mathcal{L}_{(x,\mu_{x})}VV&&&&@VVL_{x}V\\ H_{n}(\text{O}M|(x,\mu_{x}))@>\cong>> H_{n}(\mathcal{W}(\mu_{B'})|(x,\mu_{x})) @>\cong>> H_{n}(B'|x) @>\cong>> H_{n}(M|x)\end{CD}$$and $\mathcal{L}_{(x,\mu_{x})}(\tilde{\mu}_{B})\leftrightarrow L_{x}(\mu_{B})=\mu_{x}$ and $\mathcal{L}_{(x,\mu_{x})}(\tilde{\mu}_{B})=\tilde{\mu}_{x}$. This shows that we have an orientation.

- **Corollary**: $p:\text{O}M\to M$ is a $2:1$-covering and by [[Topological Manifold|Example 2]], $\text{O}M$ is a orientable $n$-dimensional manifold.

---
> [!lemma] Theorem 2
> Let $M^n$ be a path-connected manifold.
> 1. $\text{O}M$ has at most $2$ path-connected components.
> 2. $M$ is orientable if and only if $\text{O}M$ has $2$ path-connected components.
> 3. if $\pi_{1}(M)$ has no subgroups of index $2$, $M$ is orientable.

> [!proof]+
> We have that:
> 1. Trivial.
> 2. Assume $M$ is orientable with orientation $o:x\mapsto \mu_{x}$. Then, we can define two continuous maps $j,j':M\to \text{O}M$: $$j(x):=(x,\mu_{x}),\quad j'(x):=(x,-\mu_{x})$$Indeed, for any $(x,\mu_{x})\in\mathcal{W}(\mu_{B})$ we have that $j(B)\subseteq \mathcal{W}(\mu_{B})$ as for any $y\in B$, $$\mu_{y}=L_{y}(L_{x}^{-1}(\mu_{x}))=L_{y}(L^{-1}_{x}(L_{x}(\mu_{B})))=L_{y}(\mu_{B})$$Similarly, $j'$ is continuous.
>    
>    Clearly, $j(M)\cap j'(M)=\varnothing$ and $j(M)\cup j'(M)=\text{O}M$ where $j(M),j'(M)$ are path connected.
>    
>    Conversely, if $\text{O}M$ is disconnected, i.e. $\text{O}M:=C_{1}\sqcup C_{2}$ with $C_{1},C_{2}$ path-connected. Then, $p|_{C_{j}}:C_{j}\to M$ is a homeomorphism.
> 3. 