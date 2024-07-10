#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. The ***tangent bundle*** $\text{T}M$ of $M$ is defined as: $$\text{T}M:=\bigsqcup_{p\in M}^{}\text{T}_{p}M$$
- **Remark**: $\text{T}M$ has a natural projection $\pi:\text{T}M\to M$ where $\pi(v)=p$ if $v\in \text{T}_{p}M$.
- **Notation**: If $\pi(v)=p$, we sometimes denote $v$ as $(p,v)\in \text{T}M$.
- **Related definition**: For every $U\subseteq M$, $\text{T}U:=\pi ^{-1}(U)$.
- **Remark**: For any chart $(U,\varphi)$, the function: $$\begin{array}{cccc} {d\varphi:}&{\text{T}U}&\to&{\varphi(U)\times \mathbb{R}^m}\subseteq \mathbb{R}^{2m}\\&{(p,v)} &\mapsto & {(\varphi(p),d_{p}\varphi(v))} \end{array}{}$$is a bijection to an open image as [[Differential|differential of homeomorphism is a bijection]]. 
---
##### Properties
> [!lemma] Lemma 1
> $\text{T}M$ is equipped with the following topology: $E\subseteq \text{T}M$ is open if and only if for every chart $(U,\varphi)$, $d\varphi(E\cap \text{T}U)\subseteq \mathbb{R}^{2m}$ is open. Then, 
> 1. The above topology is well-defined.
> 2. For a chart $(U,\varphi)$, $d\varphi$ is a [[diffeomorphism]].
> 3. $\text{T}M$ is a second countable [[Hausdorff space]].
> 5. $\pi:\text{T}M\to M$ is continuous and open.
> 6. For the [[atlas|smooth atlas]] $\mathcal{A}$ on $M$, $\{ (\text{T}U_{\alpha},d\varphi_{\alpha}):(U_{\alpha},\varphi_{\alpha})\in \mathcal{A} \}$ is a smooth atlas on $\text{T}M$.

> [!proof]-
> We have that:
> 1. We trivially have that $\varnothing$ is open. For a chart $(U,\varphi)$, $d\varphi(\text{T}U)=\varphi(U)\times \mathbb{R}^m$ which is open. Therefore, $\text{T}M$ is open. Further, for $E_{1},E_{2}$ open and $(U,\varphi)$ chart, $$(E_{1}\cap E_{2})\cap \text{T}U=(E_{1}\cap \text{T}U)\cup(E_{2}\cap \text{T}U)$$$E_{1}\cap E_{2}$ is open. Similarly, for $(E_{\alpha})_{\alpha\in A}$ open in $\text{T}M$, $$\bigcup_{\alpha\in A}^{}E_{\alpha}\cap \text{T}U=\bigcup_{\alpha\in A}^{}(E_{\alpha}\cap \text{T}U)$$ and $\bigcup_{\alpha\in A}^{}E_{\alpha}$ is open.
> 2. By definition.
> 3. Let $(p_{1},v_{1})\neq(p_{2},v_{2})$. If $p_{1}\neq p_{2}$, then choose charts $(U_{1},\varphi_{1}),(U_{2},\varphi_{2})$ at $p_{1},p_{2}$ respectively s.t. $U_{1}\cap U_{2}=\varnothing$. Therefore, $\text{T}U_{1}$ and $\text{T}U_{2}$ are open sets that are disjoint. 
>    
>    If $p_{1}=p_{2}$, then $v_{1}\neq v_{2}$. Let $(U,\varphi)$ be a chart at $p:=p_{1}=p_{2}$. Then, $(p,v_{1}),(p,v_{2})\in \text{T}U\cong \varphi(U)\times \mathbb{R}^m$. Therefore, the Hausdorff property follows from that of $\mathbb{R}^m$.
>    
>    Finally, let $\{ U_{n} \}_{n}$ be the countable basis of $M$. Then, $\{ \text{T}U_{m} \}$ is a countable basis. 
> 4. It suffices to show that $\pi|_{U_{\alpha}}:\text{T}U_{\alpha}\to U_{\alpha}$ is continuous and open for all $\alpha\in A$. We have: $$\begin{CD}\text{T}U_{\alpha} @>\pi|_{U_{\alpha}}>>U_{\alpha}\\@V d\varphi_{\alpha} VV&@VV\varphi_{\alpha}V\\\varphi_{\alpha}(U_{\alpha})\times \mathbb{R}^m @>\text{pr}_{1}>>\varphi_{\alpha}(U_{\alpha})\end{CD}$$where $\text{pr}_{1}$ is continuous and open and $d\varphi_{\alpha}$ and $\varphi_{\alpha}$ are homeomorphisms.
> 5. As $d\varphi$ are diffeomorphisms, we see that it is an atlas. To see that it is smooth, let $\alpha,\beta\in A$. Then, $$d\psi \circ d\varphi ^{-1}|_{\varphi(U\cap V)\times \mathbb{R}^m}$$
>$\text{T}U_{\alpha}\cap \text{T}U_{\beta}=\text{T}(U_{\alpha}\cap U_{\beta})$ and: $$\theta_{\beta\alpha}=(\varphi_{\beta}\circ \varphi_{\alpha}^{-1},d(\varphi_{\beta}\circ \varphi_{\alpha}^{-1}))$$which are smooth.
- **Corollary**: $\text{T}M$ is a smooth manifold of dimension $2m$.
---
> [!lemma] Proposition 2
> The map $\pi:\text{T}M\to M$ is a [[Immersion|submersion]].

^d01715

> [!proof]-
> For any $(p,v)\in \text{T}M$ let $(\text{T}U,d\varphi)$ be a chart containing $(p,v)$. Then, let the coordinate functions be $(x^1,\dots,x^m,dx^1,\dots,dx^m)$. For $i,j\leq m$, $$\frac{ \partial x^i\circ \pi }{ \partial x^j }=\frac{ \partial x^i }{ \partial x^j }=\delta^i_{j} $$
> 
> Therefore, the Jacobian of $d\pi$ is given by: $$d\pi=\begin{bmatrix}I_{m}&*\end{bmatrix}\in \text{Mat}_{2m\times m}(\mathbb{R})$$which shows that $d\pi$ is a surjecrtive and $\pi$ is a submersion. 

^04ed06

---
