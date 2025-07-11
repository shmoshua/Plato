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
> 2. Analogous to Ext
> 3. Analogous to Ext

^a5f237

---
> [!lemma] Lemma 5 (Computation with Tor)
> Let $A,B$ be abelian groups. 
> 1. $\text{Tor}(A,B)\cong \text{Tor}(B,A)$
> 2. if $A$ or $B$ is free, $\text{Tor}(A,B)=0$.
> 3. $\text{Tor}(\bigoplus_{i\in \mathcal{I}}A_{i},B)\cong \bigoplus_{i\in \mathcal{I}}\text{Tor}(A_{i},B)$
> 4. if $A$ is finitely generated, $\text{Tor}(A,B)\cong \text{Tor}(A_{\text{tors}}, B)$
> 5. $\text{Tor}(\mathbb{Z} / m\mathbb{Z}, A)\cong \text{ker}(A \overset{ \times m }{ \to } A)$
> 6. $\text{Tor}(\mathbb{Z} / m\mathbb{Z}, \mathbb{Z} / n \mathbb{Z})\cong \mathbb{Z} / \text{gcd}(m,n)\mathbb{Z}$.


> [!proof]+
> We have:
> 7. Let $\mathcal{F}\overset{ \varepsilon }{ \to }H$ and $\mathcal{F}'\overset{ \varepsilon' }{ \to }H'$ be free resolutions of $H$ and $H'$ respectively. Then, $$ \to F_{2}\oplus F_{2}'\overset{ f_{2}\oplus f_{2}' }{ \to }F_{1}\oplus F_{1}'\overset{ f_{1}\oplus f_{1}' }{ \to }F_{0}\oplus F_{0}'\overset{ \varepsilon \oplus \varepsilon' }{ \to } H\oplus H' \to 0$$ is an exact sequence and $\mathcal{F}\oplus \mathcal{F'}$ is a free resolution of $H\oplus H'$. Therefore, $$\text{Ext}(H\oplus H',G)=H^1(\mathcal{F}\oplus \mathcal{F'};G)\cong H^1(\mathcal{F};G)\oplus H^1(\mathcal{F}';G)=\text{Ext}(H,G)\oplus \text{Ext}(H',G)$$
> 8. If $H$ is free abelian, $$0\to H\overset{ \text{id} }{ \to }H\to 0$$is exact and $F_{0}:= H$ and $F_{n}:= 0$ for $n\neq0$ is a free resolution of $H$. Therefore, $$\text{Ext}(H,G)=H^1(F;G)= 0$$
> 9. We have that: $$0\to \mathbb{Z} \overset{ \times n }{ \to } \mathbb{Z} \to\mathbb{Z} /n \mathbb{Z} \to 0$$is an exact sequence. Hence, $F_{0}:= \mathbb{Z}$ and $F_{1}:= \mathbb{Z}$ is a free resolution of $\mathbb{Z} / n\mathbb{Z}$. Then, $$0 \to \text{Hom}(\mathbb{Z} , G) \overset{ (\times n)^{*} }{ \to } \text{Hom}(\mathbb{Z} , G) \to 0$$where the map is given as $f\mapsto (x\mapsto f(nx)=nf(x))$. In other words, $f\mapsto nf$. Therefore, the map is also $\times n$ and as $\text{Hom}(\mathbb{Z},G)\cong G$, we have that $$\text{Ext}(\mathbb{Z} / n\mathbb{Z}, G)\cong  G / nG$$