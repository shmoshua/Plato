#Definition #AlgebraicTopology 

> [!definition]
> Let $H$ be an [[abelian group]]. Then, 
> 1. $\text{Ext}(H,G):=H^1(\mathcal{F};G)$ where $\mathcal{F}\overset{ \varepsilon }{ \to } H$ is a [[Resolution|free resolution]] of $H$.

- **Remark**: By [[Resolution|Example 1]], there always exists a free resolution. By [[Resolution|Theorem 3]], $\text{Ext}(H,G)$ is well-defined, i.e. doesn't depend on the choice of $\mathcal{F}$.
---
##### Properties
> [!lemma] Proposition 1
> Let $\mathcal{C}$ be a [[chain complex]] of free abelian groups. 
> 1. We have that: $$0\to \mathcal{Z}\overset{ j }{ \to } \mathcal{C}\overset{ \partial }{ \to } \mathcal{B}_{-1}\to 0$$ is a SES of chain complexes where $\mathcal{Z}:=(Z_{i}(\mathcal{C}),0)_{i}$, $\mathcal{B}_{-1}:=(B_{i-1}(\mathcal{C}),0)_{i}$, and $j$ is the inclusion.
> 2. This SES induces the following SES of cochain complexes: $$0 \to \mathcal{B}_{-1}^{*}\overset{ \delta }{ \to } \mathcal{C}^{*}\overset{ j^{*} }{ \to }\mathcal{Z}^{*}\to 0$$In particular, we have the following LES:$$\cdots\to Z_{n-1}^{*}\overset{ i_{n-1}^{*} }{ \to } B_{n-1}^{*}\overset{ \delta ^{*} }{ \to  }H^n(C;G)\overset{ j^{*} }{ \to } Z_{n}^{*}\overset{ i_{n}^{*} }{ \to } B_{n}^{*}\to \cdots$$where $i_{n}:B_{n}\hookrightarrow Z_{n}$ is the inclusion.
> 3. We hence have many SES's: $$0 \to \text{coker}(i^{*}_{n-1}) \overset{ \delta ^{*} }{ \to } H^n(C;G)\overset{ \tilde{j} }{ \to  }\text{ker }i^{*}_{n}\to 0$$where $\text{ker }i^{*}_{n}\cong\text{Hom}(H_{n}(\mathcal{C}),G)$ and $h:H^n(C;G)\to \text{Hom}(H_{n}(\mathcal{C}),G)$ from [[Cochain Complex|Theorem 4]] can be identified as $$h:H^n(C;G)\overset{ \tilde{j} }{ \to } \text{ker } i^{*}_{n}\overset{ \cong }{ \to } \text{Hom}(H_{n}(\mathcal{C}),G)$$
> 4. We have the SES's: $$0 \to \text{coker}(i^{*}_{n-1}) \overset{ \delta }{ \to } H^n(C;G)\overset{ h}{ \to  }\text{Hom}(H_{n}(\mathcal{C}),G)\to 0$$

^327278

> [!proof]-
> We have that:
> 1. Notice that: $$\begin{CD}0 @>>> Z_{n+1}@>j>> C_{n+1}@>\partial>> B_{n} @>>> 0\\ &@V{0}VV&@V{\partial}VV&@V{0} VV\\  0 @>>> Z_{n}@>>j> C_{n}@>>\partial>B_{n-1} @>>> 0\end{CD}$$commute as $\partial \circ j = 0$ from $\partial|_{Z_{n+1}}=0$ and $\partial^{2}=0$.
> 2. As $\mathcal{C}$ is free abelian, $\mathcal{B}_{1}$ is free abelian as well. Hence, from [[Split Exact Sequence|Proposition 2]], $0 \to Z_{n} \to C_{n }\to B_{n-1}\to 0$ is split for all $n$. Therefore, by [[Split Exact Sequence|Proposition 3]], $$0\to B_{n-1}^{*}\overset{ \delta }{ \to } C_{n}^{*}\overset{ j^{*} }{ \to } Z_{n}^{*}\to 0$$is a split SES. To show that $i^{*}_{n}:Z^{*}_{n}\to B^{*}_{n}$ is the connecting homomorphism, let $\psi\in Z^{*}_{n}$. Let $\tau$ be the connecting homomorphism. Then, we have that $\delta(\tau(\psi))=\delta(\varphi)$ where $\varphi|_{Z_{n}}=\psi$ for some $\varphi\in C_{n}^{*}$. This is given if $\tau(\psi)=\psi|_{B_{n}}=\psi \circ i_{n}=i^{*}_{n}(\psi)$. 
> 3. To show that $\text{ker }i^{*}_{n}\cong \text{Hom}(H_{n}(\mathcal{C}),G)$, let $\varphi\in \text{ker }i^{*}_{n}$. Then, $\varphi:Z_{n}\to G$ and $\varphi|_{B_{n}}=0$. Hence, $\varphi$ induces $\bar{\varphi}:H_{n}(\mathcal{C})\to G$. Let $\Theta(\varphi):=\overline{\varphi}$. Then, $\Theta:\text{ker }i^{*}_{n}\to \text{Hom}(H_{n}(\mathcal{C}),G)$ is a homomorphism. Conversely, for $\psi:H_{n}(\mathcal{C})\to G$, define $\phi:=\psi \circ p$ where $p:Z_{n}\to Z_{n} / B_n$ is the standard projection. Then, $\phi\in \text{ker }i^{*}_{n}$ and $\overline{\phi}=\psi$. Therefore, $\Theta$ is surjective. Lastly, if $\Theta(\varphi)=\overline{\varphi}=0$, then obviously $\varphi=0$. 
>    
>    Moreover, recall that: $$h:H^n(C;G)\to \text{Hom}(H_{n}(C),G),\quad [\varphi]\mapsto \overline{\varphi|_{Z_{n}}}$$Then, $\tilde{j}([\varphi])=j^{*}(\varphi)=\varphi|_{Z_{n}}$. This proves the statement.
> 4. Obvious.

^a2ab91

- **Corollary**: $\text{ker } h\cong \text{coker}(i^{*}_{n-1})$.  ^4565bf

---
> [!lemma] Proposition 2
> Let $\mathcal{C}$ be a chain complex of free abelian groups. 
> 1. For every $n$, the followings are exact sequences: $$0\to B_{n-1}\overset{ i_{n-1} }{ \to } Z_{n-1} \overset{ q }{ \to } H_{n-1}(\mathcal{C}) \to 0$$$$0\to \text{Hom}(H_{n-1}(\mathcal{C}),G)\to Z_{n-1}^{*}\to B^{*}_{n-1}\to \text{coker}(i^{*}_{n-1})\to 0$$
> 2. $\mathcal{F}\overset{ q}{ \to }H_{n-1}(\mathcal{C})$ is a [[Resolution|free resolution]] of $H_{n-1}(\mathcal{C})$ where $F_{0}:= Z_{n-1}$, $F_{1}:=B_{n-1}$ and $F_{i}=0$ for $i\geq 2$. 
> 3. $H^1(\mathcal{F};G)\cong \text{coker}(i^{*}_{n-1})\cong \text{ker }h$.

^eac318

> [!proof]-
> We have that:
> 1. Obvious. 
> 2. By definition and from 1.
> 3. Obvious.

^9b9273

---
> [!lemma] Theorem 3 (Universal Coefficient Theorem)
> Let $\mathcal{C}$ be a chain complex of free abelian groups. For an abelian group $G$,
> 1. there exists a split SES: $$0\to \text{Ext}(H_{n-1}(\mathcal{C}),G)\to H^n(\mathcal{C};G)\to \text{Hom}(H_{n}(\mathcal{C}),G)\to 0$$

^87b1dc

> [!proof]-
> Follows from [[Resolution|Theorem 3]] and Proposition 1,2.

^817d2e

- **Remark**: In general, there is no canonical splitting. ^c22a3c

---
> [!lemma] Lemma 4 (Computation with Ext)
> We have that:
> 1. $\text{Ext}(H\oplus H',G)\cong \text{Ext}(H,G)\oplus \text{Ext}(H',G)$ canonically.
> 2. if $H$ is free abelian, $\text{Ext}(H,G)=0$.
> 3. $\text{Ext}(\mathbb{Z} / n\mathbb{Z},G)\cong G / nG$

^3976b6

> [!proof]-
> We have:
> 1. Let $\mathcal{F}\overset{ \varepsilon }{ \to }H$ and $\mathcal{F}'\overset{ \varepsilon' }{ \to }H'$ be free resolutions of $H$ and $H'$ respectively. Then, $$ \to F_{2}\oplus F_{2}'\overset{ f_{2}\oplus f_{2}' }{ \to }F_{1}\oplus F_{1}'\overset{ f_{1}\oplus f_{1}' }{ \to }F_{0}\oplus F_{0}'\overset{ \varepsilon \oplus \varepsilon' }{ \to } H\oplus H' \to 0$$ is an exact sequence and $\mathcal{F}\oplus \mathcal{F'}$ is a free resolution of $H\oplus H'$. Therefore, $$\text{Ext}(H\oplus H',G)=H^1(\mathcal{F}\oplus \mathcal{F'};G)\cong H^1(\mathcal{F};G)\oplus H^1(\mathcal{F}';G)=\text{Ext}(H,G)\oplus \text{Ext}(H',G)$$
> 2. If $H$ is free abelian, $$0\to H\overset{ \text{id} }{ \to }H\to 0$$is exact and $F_{0}:= H$ and $F_{n}:= 0$ for $n\neq0$ is a free resolution of $H$. Therefore, $$\text{Ext}(H,G)=H^1(F;G)= 0$$
> 3. We have that: $$0\to \mathbb{Z} \overset{ \times n }{ \to } \mathbb{Z} \to\mathbb{Z} /n \mathbb{Z} \to 0$$is an exact sequence. Hence, $F_{0}:= \mathbb{Z}$ and $F_{1}:= \mathbb{Z}$ is a free resolution of $\mathbb{Z} / n\mathbb{Z}$. Then, $$0 \to \text{Hom}(\mathbb{Z} , G) \overset{ (\times n)^{*} }{ \to } \text{Hom}(\mathbb{Z} , G) \to 0$$where the map is given as $f\mapsto (x\mapsto f(nx)=nf(x))$. In other words, $f\mapsto nf$. Therefore, the map is also $\times n$ and as $\text{Hom}(\mathbb{Z},G)\cong G$, we have that $$\text{Ext}(\mathbb{Z} / n\mathbb{Z}, G)\cong  G / nG$$

^b9aa9b

- **Remark**: This gives us a way to compute the Ext for every finitely generated abelian group $H$. ^43f119
---
> [!lemma] Proposition 5 (Induced Maps between Ext)
> Let $G,G',H,H'$ be abelian groups. 
> 1. For a homomorphism $\alpha:H\to H'$ and free resolutions $\mathcal{F}\to H$ and $\mathcal{F'}\to H'$, the extension of $\alpha$ given by [[Resolution|Theorem 3]] induces a map in cohomology:
>    $$\alpha^{\text{ext}}:\text{Ext}(H',G)\to \text{Ext}(H,G)$$In particular, $\alpha^{\text{ext}}$ is well-defined and canonical.
> 2. A homomorphism $\varphi:G \to G'$ induces a map for any abelian group $M$. $$\Phi: \text{Hom}(M,G)\to \text{Hom}(M,G')$$ 

> [!proof]+
> We have that:
> 3. Let $\mathcal{E}\to H$ and $\mathcal{E}'\to H'$ be another pair of free resolutions. It suffices to show that: $$\begin{CD}H^1(\mathcal{F}';G)@>\alpha_{1}^*>>H^1(\mathcal{F};G)\\@V\cong VV & @VV\cong V \\H^1(\mathcal{E}';G)@> >\alpha_{2}^*>H^1(\mathcal{E};G)\end{CD}$$where $\alpha_{1},\alpha_{2}$ are two respective extensions of $\alpha$. 
>    
>    Let $\beta$ be the extension of $\text{id}_{H}$ from $\mathcal{E}$ to $\mathcal{F}$. Similarly, let $\beta'$ be the extension of $\text{id}_{H'}$ from $\mathcal{E}'$ to $\mathcal{F}'$. Then, $\alpha_{1}\circ\beta$ and $\beta' \circ \alpha_{2}$ are extension of $\alpha$. Therefore, by [[Resolution|Theorem 3]], they are chain homotopic and in cohomology, they induce the same maps, i.e. $$\beta ^{*} \circ  \alpha_{1}^{*}=(\alpha_{1} \circ  \beta)^{*}=(\beta' \circ  \alpha_{2})^{*}=\alpha_{2}^{*} \circ  (\beta')^{*}$$