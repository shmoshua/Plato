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
>    $$\alpha^{\text{ext}}:\text{Ext}(H',G)\to \text{Ext}(H,G)$$In particular, $\alpha^{\text{ext}}$ is well-defined and canonical.
> 2. A homomorphism $\varphi:G \to G'$ induces a map for any abelian group $M$. $$\varphi: \text{Hom}(M,G)\to \text{Hom}(M,G')$$ Therefore, $\varphi ^{*}:\text{Ext}(H,G)\to \text{Ext}(H,G')$ is well-defined. 

> [!proof]-
> We have that:
> 1. Let $\mathcal{E}\to H$ and $\mathcal{E}'\to H'$ be another pair of free resolutions. It suffices to show that: $$\begin{CD}H^1(\mathcal{F}';G)@>\alpha_{1}^*>>H^1(\mathcal{F};G)\\@V\cong VV & @VV\cong V \\H^1(\mathcal{E}';G)@> >\alpha_{2}^*>H^1(\mathcal{E};G)\end{CD}$$where $\alpha_{1},\alpha_{2}$ are two respective extensions of $\alpha$. 
>    
>    Let $\beta$ be the extension of $\text{id}_{H}$ from $\mathcal{E}$ to $\mathcal{F}$. Similarly, let $\beta'$ be the extension of $\text{id}_{H'}$ from $\mathcal{E}'$ to $\mathcal{F}'$. Then, $\alpha_{1}\circ\beta$ and $\beta' \circ \alpha_{2}$ are extension of $\alpha$. Therefore, by [[Resolution|Theorem 3]], they are chain homotopic and in cohomology, they induce the same maps, i.e. $$\beta ^{*} \circ  \alpha_{1}^{*}=(\alpha_{1} \circ  \beta)^{*}=(\beta' \circ  \alpha_{2})^{*}=\alpha_{2}^{*} \circ  (\beta')^{*}$$
> 2. Obvious.

---
> [!lemma] Theorem 3 (Universal Coefficient Theorem for Tensor Products)
> Let $\mathcal{C}$ be a chain complex of free abelian groups. For an abelian group $G$, 
> 1. there exists a split SES: $$0\to H_{n}(\mathcal{C})\otimes G\overset{ \tau }{ \to } H_{n}(\mathcal{C};G)\to \text{Tor}(H_{n-1}(\mathcal{C}),G)\to 0$$where $\tau([c],g)=[c\otimes g]$.
> 2. the SES is natural w.r.t. chain maps, i.e. for any chain map $\alpha:\mathcal{C}\to \mathcal{C}'$, $$\begin{CD}0& @>>> \text{Ext}(H_{n-1}(\mathcal{C}),G)@>>> H^n(\mathcal{C};G)@>>> \text{Hom}(H_{n}(\mathcal{C}),G) @>>> 0\\&@A\alpha_{h}^{\text{ext}}AA&@A\alpha ^{*} AA&@A\alpha_{h}^{*}AA\\0& @>>> \text{Ext}(H_{n-1}(\mathcal{C}'),G)@>>> H^n(\mathcal{C}';G)@>>> \text{Hom}(H_{n}(\mathcal{C}'),G) @>>> 0\end{CD}$$where $\alpha_{h}:H_{*}(\mathcal{C})\to H_{*}(\mathcal{C}')$.
> 3. the SES is natural w.r.t. homomorphisms between $G,G'$ i.e. for any homomorphism $\varphi:G \to G'$, $$\begin{CD}0& @>>> \text{Ext}(H_{n-1}(\mathcal{C}),G)@>>> H^n(\mathcal{C};G)@>>> \text{Hom}(H_{n}(\mathcal{C}),G) @>>> 0\\&@V\varphi ^{*} VV&@V\varphi ^{*} VV&@V\varphi VV\\0& @>>> \text{Ext}(H_{n-1}(\mathcal{C}),G')@>>> H^n(\mathcal{C};G')@>>> \text{Hom}(H_{n}(\mathcal{C}),G') @>>> 0\end{CD}$$

> [!proof]+
> We have that: 
> 1.  From 2, we get the following SES's: $$0\to \text{coker}(i_{n}\otimes  \text{id})\to H_{n}(\mathcal{C};G)\to \text{ker}(i_{n-1}\otimes \text{id})\to 0$$However, by [[Tensor Product|Proposition 4]], $\text{coker}(i_{n}\otimes \text{id})\cong \text{coker}(i_{n})\otimes G=H_{n}(\mathcal{C})\otimes G$.
>    
> 	   Consider the bilinear map $$\overline{\tau}:H_{n}(\mathcal{C})\times G\to H_{n}(\mathcal{C};G),\quad ([c],g)\mapsto [c\otimes  g]$$
> 	   1. $\overline{\tau}$ is well defined: If $c'-c\in B_{n}$, then: $$(\partial \otimes \text{id})(c' \otimes  g-c\otimes  g)=(\partial \otimes \text{id})((c'-c)\otimes  g)=0\otimes  g=0$$
> 	   
> 	   Therefore, there exists a unique homomorphism $\tau:H_{n}(\mathcal{C})\otimes G\to H_{n}(\mathcal{C};G)$. Further, $$\begin{CD}H_{n}(\mathcal{C})\otimes  G @>\tau>> H_{n}(\mathcal{C};G)\\@V\cong VV@VV\text{id}V\\\text{coker}(i_{n}\otimes \text{id}) @>>(j\otimes \text{id})_{*}> H_{n}(\mathcal{C};G)\end{CD}$$commutes. 