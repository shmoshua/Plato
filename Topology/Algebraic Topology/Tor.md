> [!definition]
> Let $H$ be an [[abelian group]]. Then, 
> 1. $\text{Tor}(H,G):=H_{1}(\mathcal{F};G)$ where $\mathcal{F}\overset{ \varepsilon }{ \to } H$ is a [[Resolution|free resolution]] of $H$.

^629334

---
##### Properties
> [!lemma] Proposition 1
>  Let $\mathcal{C}$ be a [[chain complex]] of free abelian groups and $G$ an abelian group.
> 1. We have that: $$0\to \mathcal{Z}\overset{ j }{ \to } \mathcal{C}\overset{ \partial }{ \to } \mathcal{B}_{-1}\to 0$$ is a SES of chain complexes where $\mathcal{Z}:=(Z_{i}(\mathcal{C}),0)_{i}$, $\mathcal{B}_{-1}:=(B_{i-1}(\mathcal{C}),0)_{i}$, and $j$ is the inclusion.
> 2. This SES induces the following SES of cochain complexes: $$0 \to \mathcal{Z}\otimes  G\overset{ j\otimes  \text{id} }{ \to } \mathcal{C}\otimes  G\overset{ d:= \partial \otimes \text{id} }{ \to }\mathcal{B}_{-1}\otimes G\to 0$$In particular, we have the following LES:$$\cdots\to B_{n}\otimes  G\overset{ i_{n}\otimes \text{id} }{ \to  }Z_{n}\otimes  G \to H_{n}(\mathcal{C};G)\to B_{n-1}\otimes  G \overset{ i_{n-1}\otimes \text{id} }{ \to } Z_{n-1}\otimes G\to \cdots$$where $i_{n}:B_{n}\hookrightarrow Z_{n}$ is the inclusion.

^6e33f6

> [!proof]-
> We have that:
> 1. Obvious.
> 2. As $\mathcal{C}$ is free, so is $\mathcal{B}_{-1}$ and hence the SES in 1 is split in each level. Hence, by [[Tensor Product|Proposition 3.3.1]], we get the desired SES. To see that we get the given connecting homomorphism is easy.


^3ae30a

---
> [!lemma] Proposition 2 (Induced Maps between Tor)
> Let $G,G',H,H'$ be abelian groups. 
> 1. For a homomorphism $\alpha:H\to H'$ and free resolutions $\mathcal{F}\to H$ and $\mathcal{F'}\to H'$, the extension of $\alpha$ given by [[Resolution|Theorem 3]] induces a map in cohomology:
>    $$\alpha_{\text{tor}}:\text{Tor}(H,G)\to \text{Tor}(H',G)$$In particular, $\alpha_{\text{tor}}$ is well-defined and canonical.
> 2. A homomorphism $\varphi:G \to G'$ induces a map for any abelian group $M$. $$\text{id}\otimes \varphi: M\otimes  G\to M\otimes  G'$$ Therefore, $(\text{id} \otimes \varphi)_{*}:\text{Tor}(H,G)\to \text{Tor}(H,G')$ is well-defined. 

^a9ce8b

> [!proof]-
> We have that:
> 1. Analogous to [[Ext]]
> 2. Obvious.

^cd1aec

---
> [!lemma] Theorem 3 (Universal Coefficient Theorem for Tensor Products)
> Let $\mathcal{C}$ be a chain complex of free abelian groups. For an abelian group $G$, 
> 1. there exists a split SES: $$0\to H_{n}(\mathcal{C})\otimes G\overset{ \tau }{ \to } H_{n}(\mathcal{C};G)\to \text{Tor}(H_{n-1}(\mathcal{C}),G)\to 0$$where $\tau([c],g)=[c\otimes g]$.
> 2. the SES is natural w.r.t. chain maps, i.e. for any chain map $\alpha:\mathcal{C}\to \mathcal{C}'$, $$\begin{CD}0& @>>> H_{n}(\mathcal{C})\otimes  G@>>> H_{n}(\mathcal{C};G)@>>> \text{Tor}(H_{n-1}(\mathcal{C}),G) @>>> 0\\&@V\alpha_{*}\otimes  \text{id}VV&@V(\alpha\otimes  \text{id})_{*}VV&@V\alpha_{\text{tor}}VV\\0& @>>> H_{n}(\mathcal{C}') \otimes  G@>>> H_{n}(\mathcal{C}';G)@>>> \text{Tor}(H_{n-1}(\mathcal{C}'),G) @>>> 0\end{CD}$$
> 3. the SES is natural w.r.t. homomorphisms between $G,G'$ i.e. for any homomorphism $\varphi:G \to G'$, $$\begin{CD}0& @>>> H_{n}(\mathcal{C})\otimes  G@>>> H_{n}(\mathcal{C};G)@>>> \text{Tor}(H_{n-1}(\mathcal{C}),G) @>>> 0\\&@V\text{id}\otimes  \varphi VV&@V(\text{id}\otimes  \varphi)_{*}VV&@V(\text{id}\otimes  \varphi)_{*}VV\\0& @>>> H_{n}(\mathcal{C}) \otimes  G'@>>> H_{n}(\mathcal{C};G')@>>> \text{Tor}(H_{n-1}(\mathcal{C}),G') @>>> 0\end{CD}$$

^fe86d5

> [!proof]-
> We have that: 
> 1.  From 2, we get the following SES's: $$0\to \text{coker}(i_{n}\otimes  \text{id})\to H_{n}(\mathcal{C};G)\to \text{ker}(i_{n-1}\otimes \text{id})\to 0$$However, by [[Tensor Product|Proposition 4]], $\text{coker}(i_{n}\otimes \text{id})\cong \text{coker}(i_{n})\otimes G=H_{n}(\mathcal{C})\otimes G$.
>    
> 	   Consider the bilinear map $$\overline{\tau}:H_{n}(\mathcal{C})\times G\to H_{n}(\mathcal{C};G),\quad ([c],g)\mapsto [c\otimes  g]$$
> 	   1. $\overline{\tau}$ is well defined: If $c'-c\in B_{n}$, then: $$(\partial \otimes \text{id})(c' \otimes  g-c\otimes  g)=(\partial \otimes \text{id})((c'-c)\otimes  g)=0\otimes  g=0$$
> 	   
> 	   Therefore, there exists a unique homomorphism $\tau:H_{n}(\mathcal{C})\otimes G\to H_{n}(\mathcal{C};G)$. Further, $$\begin{CD}H_{n}(\mathcal{C})\otimes  G @>\tau>> H_{n}(\mathcal{C};G)\\@V\cong VV@VV\text{id}V\\\text{coker}(i_{n}\otimes \text{id}) @>>(j\otimes \text{id})_{*}> H_{n}(\mathcal{C};G)\end{CD}$$commutes. 
> 	   
> 	   Now, to show that $\text{ker}(i_{n-1}\otimes \text{id})\cong \text{Tor}(H_{n-1}(\mathcal{C}),G)$ consider the free resolution: $$0\to B_{n-1}\otimes  G\overset{ i_{n-1}\otimes  \text{id} }{ \to }Z_{n-1}\otimes  G \to H_{n-1}(\mathcal{C}) \otimes  G \to 0$$Hence, $\text{ker}(i_{n-1}\otimes \text{id})\cong \text{Tor}(H_{n-1}(\mathcal{C}),G)$. 
> 	   
> 	   Finally, it's left to show that this sequence splits. Consider $0\to Z_{n}\overset{ j_{n} }{ \to }C_{n}\overset{ \partial }{ \to } B_{n-1}\to 0$which splits as $B_{n-1}$ is free. Therefore, there exists a left inverse $p:C_{n}\to Z_{n}$ s.t. $p|_{Z_{n}}=\text{id}$. by composing $p$ with $Z_{n}\to H_{n}(\mathcal{C})$, we have $\overline{p}:C_{n}\to H_{n}(\mathcal{C})$ s.t. $\bar{p}(z)=[z]$ for all $z\in Z_{n}$.
> 	   
> 	   Now, we claim that $\overline{p}$ gives a chain map $\overline{p}:\mathcal{C}\to \mathcal{H}_{*}(\mathcal{C})$ where $\mathcal{H}_{*}(\mathcal{C})$ is the chain complex of $H_{n}(\mathcal{C})$ with zero differential. Indeed, $$\overline{p}(\partial c)=[\partial c]=0$$Hence, we can consider $\overline{p} \otimes \text{id}: \mathcal{C}\otimes G\to \mathcal{H}_{*}(\mathcal{C})\otimes G$ as a chain map. We claim that $$(\overline{p}\otimes  \text{id})_{*}:H_{n}(\mathcal{C};G)\to H_{n}(\mathcal{C})\otimes  G$$ is a left inverse of $\tau$. For any $c\in Z_{n}$ and $g\in G$, we have that: $$(\overline{p}\otimes  \text{id})_{*} \circ  \tau([c]\otimes  g)=(\overline{p}\otimes \text{id})_{*}([c\otimes  g])=\overline{p}(c)\otimes   g=[c]\otimes  g$$This proves the statement.
> 	   
> 2. Analogous to Ext
> 3. Analogous to Ext

^a5f237

---
> [!lemma] Lemma 5 (Computation with Tor)
> Let $A,B$ be abelian groups. 
> 1. if $A$ or $B$ is free, $\text{Tor}(A,B)=0$.
> 2. $\text{Tor}(A,B)\cong \text{Tor}(B,A)$
> 3. $\text{Tor}(\bigoplus_{i\in \mathcal{I}}A_{i},B)\cong \bigoplus_{i\in \mathcal{I}}\text{Tor}(A_{i},B)$
> 4. if $A$ is finitely generated, $\text{Tor}(A,B)\cong \text{Tor}(A_{\text{tors}}, B)$
> 5. $\text{Tor}(\mathbb{Z} / m\mathbb{Z}, A)\cong \text{ker}(A \overset{ \times m }{ \to } A)$
> 6. $\text{Tor}(\mathbb{Z} / m\mathbb{Z}, \mathbb{Z} / n \mathbb{Z})\cong \mathbb{Z} / \text{gcd}(m,n)\mathbb{Z}$.
> 7. if $A,B$ are finitely generated $\text{Tor}(A,B)\cong A_{\text{tors}}\otimes B_{\text{tors}}$

^1b5eed


> [!proof]-
> We have:
> 1. If $A$ is free, then $0 \to A \to A \to 0$ is exact and $0\to A\overset{ \text{id} }{ \to }A$ is a free resolution. Hence, $\text{Tor}(A,B)=0$. 
>    
>    If $B$ is free, then consider the SES from [[Resolution|Example 1]] which is a free resolution for $A$. Then, as $B$ is free, tensoring with $B$ keeps the exactness. Therefore, $\text{Tor}(A,B)=0$.
> 2. To be added
> 3. Let $\mathcal{F}_{i}\to A_{i}$ be a free resolution. Then, $\bigoplus_{i\in \mathcal{I}}\mathcal{F}_{i}\to \bigoplus_{i\in \mathcal{I}}A_{i}$ is also a free resolution. Hence, $$\text{Tor}\left( \bigoplus_{i\in \mathcal{I}} A_{i},B \right) =H_{1}\left( \bigoplus_{i\in \mathcal{I}} \mathcal{F}_{i} ;B\right) \cong \bigoplus_{i\in \mathcal{I}} H_{1}(\mathcal{F}_{i};B)=\bigoplus _{i\in \mathcal{I}}\text{Tor}(A_{i},B)$$
> 4. We have that: $$\text{Tor}(A,B)\cong \text{Tor}(A_{\text{tors}},B)\oplus \underbrace{ \text{Tor}(A_{\text{free}},B) }_{ =0 }=\text{Tor}(A_{\text{tors}},B)$$
> 5. Consider the free resolution: $0\to \mathbb{Z} \overset{ \times m }{ \to } \mathbb{Z} \to \mathbb{Z} / m\mathbb{Z} \to 0$. Hence, we get: $$\to 0\to \mathbb{Z} \otimes  A \overset{ (\times m )\otimes  \text{id} }{ \to } \mathbb{Z} \otimes  A $$As $\mathbb{Z}\otimes A\cong A$, we have that $\text{Tor}(\mathbb{Z} / m\mathbb{Z}, A)\cong \text{ker }(A \overset{ \times m }{ \to } A)$.
> 6. We have that: $$\text{Tor}(\mathbb{Z} / m\mathbb{Z} , \mathbb{Z} / n\mathbb{Z})\cong \text{ker }(\mathbb{Z} / n\mathbb{Z}\overset{ \times m }{ \to }\mathbb{Z} / n\mathbb{Z})\cong \mathbb{Z} / \text{gcd}(m,n)\mathbb{Z}$$
> 7. Let $A_{\text{tors}}=\bigoplus_{i=1}^r \mathbb{Z} / m_{i} \mathbb{Z}$ and $B_{\text{tors}}=\bigoplus_{j=1}^\ell \mathbb{Z} / n_{j}\mathbb{Z}$. Then, $$\text{Tor}(A,B)\cong \text{Tor}(A_{\text{tors}},B)\cong \text{Tor}(B,A_{\text{tors}})\cong \text{Tor}(B_{\text{tors}}, A_{\text{tors}})\cong \text{Tor}(A_{\text{tors}}, B_{\text{tors}})$$where: $$\begin{aligned}\text{Tor}(A_{\text{tors}}, B_{\text{tors}})&\cong \bigoplus _{i=1}^r\bigoplus _{j=1}^{\ell}\text{Tor}(\mathbb{Z} / m_{i}\mathbb{Z}, \mathbb{Z} / n_{j}\mathbb{Z})\cong \bigoplus _{i=1}^r\bigoplus _{j=1}^{\ell} \mathbb{Z} / {\text{gcd}(m_{i},n_{j})\mathbb{Z}}\\&\cong \bigoplus _{i=1}^r\bigoplus _{j=1}^{\ell} (\mathbb{Z} / m_{i} \mathbb{Z} \otimes  \mathbb{Z}  / n_{j}\mathbb{Z})\cong A_{\text{tors}}\otimes  B_{\text{tors}}\end{aligned}$$

^fdb79b

---
> [!lemma] Theorem 4 (Künneth Formula)
> Let $\mathcal{K},\mathcal{L}$ be two chain complexes of free abelian groups. 
> 1. there exists a split SES: $$0\to \bigoplus _{p+q=n}H_{p}(\mathcal{K})\otimes H_{q}(\mathcal{L})\overset{ h }{ \to }H_{n}(\mathcal{K}\otimes  \mathcal{L})\to \bigoplus _{p+q=n-1}\text{Tor}(H_{p}(\mathcal{K}),H_{q}(\mathcal{L}))\to 0$$where $h([k]\otimes[\ell])=[k\otimes \ell]$. 
> 2. the SES is natural w.r.t. chain maps $f:\mathcal{K}\to \mathcal{K}'$ and $g:\mathcal{L}\to \mathcal{L}'$.

> [!proof]+
> From Proposition 1, we have the SES: $$0\to \mathcal{Z}\overset{ j }{ \to }\mathcal{K}\overset{ \partial }{ \to }\mathcal{B}[-1]\to 0$$We have that the following is an SES:$$0\to \mathcal{Z}\otimes  \mathcal{L}\overset{ j\otimes  \text{id} }{ \to } \mathcal{K}\otimes  \mathcal{L}\overset{ \partial \otimes  \text{id} }{ \to } \mathcal{B}[-1]\otimes  \mathcal{L}\to 0$$where $\partial_{\mathcal{Z}\otimes \mathcal{L}}=\text{id}\otimes \partial_{L}$ and $\partial_{\mathcal{B}[-1]\otimes \mathcal{L}}=\text{id}\otimes \partial_{L}$.
> 
> Indeed, we have that: $$0\to \bigoplus _{p+q=n}Z_{p}\otimes  L_{q}\to \bigoplus _{p+q=n}K_{p}\otimes  L_{q}\to \bigoplus _{p+q=n-1}B_{p}\otimes  L_{q}\to 0$$which splits as $\bigoplus_{p+q=n-1}B_{p}\otimes L_{q}$ is free. Now, as $\mathcal{Z}\otimes \mathcal{L}=\bigoplus_{p\in \mathbb{Z}}Z_{p}\otimes \mathcal{L}$, we have that: $$H_{n}(\mathcal{Z}\otimes  \mathcal{L})\cong\bigoplus _{p\in \mathbb{Z}}H_{n}(Z_{p}\otimes  \mathcal{L})\cong \bigoplus _{p\in \mathbb{Z}}Z_{p}\otimes  H_{n-p}(\mathcal{L})=\bigoplus _{p+q=n}Z_{p}\otimes  H_{q}(\mathcal{L})$$Similarly, $H_{n}(\mathcal{B}[-1]\otimes \mathcal{L})\cong\bigoplus_{p+q=n}B_{p-1}\otimes H_{q}(\mathcal{L})=\bigoplus_{p+q=n-1}B_{p}\otimes H_{q}(\mathcal{L})$
> 
> 
> We hence get the LES: $$\dots\to \bigoplus _{p+q=n}Z_{p}\otimes  H_{q}(\mathcal{L})\to H_{n}(\mathcal{K}\otimes  \mathcal{L})\to \bigoplus_{p+q=n-1}B_{p}\otimes H_{q}(\mathcal{L})\overset{i_{n-1} }{ \to } \bigoplus _{p+q=n-1}Z_{p}\otimes  H_{q}(\mathcal{L})\to\cdots$$Therefore, we have the SES: $$0\to \text{coker}(i_{n})\to H_{n}(\mathcal{K}\otimes  \mathcal{L})\to \text{ker } i_{n-1}\to 0$$where: $$\text{coker}(i_{n})=\left( \bigoplus _{p+q=n}Z_{p}\otimes  H_{q}(\mathcal{L}) \right) / \left( \bigoplus _{p+q=n}B_{p}\otimes  H_{q}(\mathcal{L}) \right) \cong \bigoplus _{p+q=n}H_{p}(\mathcal{K})\otimes  H_{q}(\mathcal{L}) $$as $0\to B_{p}\overset{ i }{ \to } Z_{p}\overset{ q }{ \to } H_{p}(\mathcal{K})\to 0$ is exact and by [[Tensor Product|right exactness of tensor products]], $$B_{p}\otimes  H_{q}(\mathcal{L})\to Z_{p}\otimes  H_{q}(\mathcal{L})\to H_{p}(\mathcal{K})\otimes  H_{q}(\mathcal{L})\to 0$$is exact. Therefore, by surjectivity, $$H_{p}(\mathcal{K})\otimes  H_{q}(\mathcal{L})\cong \frac{Z_{p }\otimes  H_{q}(\mathcal{L})}{B_{p}\otimes  H_{q}(\mathcal{L})}$$Now, as $0\to B_{p}\to Z_{p}\to H_{p}(\mathcal{K})\to 0$ is a free resolution, $$\text{ker }i_{n-1}\cong \bigoplus _{p+q=n-1}\text{Tor}(H_{p}(\mathcal{K}),H_{q}(\mathcal{L}))$$This gives us the statement.
> 
> To show that the SES splits, from $0\to Z_{i}\to K_{i}\to B_{i-1}\to 0$ which splits, we have a left inverse $p:K_{i}\to Z_{i}$ s.t. $p|_{Z_{i}}=\text{id}$. By composing with $Z_{i}\to H_{i}(\mathcal{K})$, we have $\overline{p}:K_{i}\to H_{i}(\mathcal{K})$ s.t. $\overline{p}(z)=[z]$ for all $z\in Z_{i}$. Similarly $\overline{q}:L_{j}\to H_{j}(\mathcal{L})$ which are chain maps considering $H_{i}(\mathcal{K})$ and $H_{j}(\mathcal{L})$ as chain complexes with zero differential. Hence, $$\overline{p}\otimes  \overline{q}:\mathcal{K}\otimes  \mathcal{L}\to $$
