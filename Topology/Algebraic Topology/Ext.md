#Definition #AlgebraicTopology 

> [!definition]


---
##### Properties
> [!lemma] Proposition 1
> Let $\mathcal{C}$ be a [[chain complex]] of free abelian groups. 
> 1. We have that: $$0\to \mathcal{Z}\overset{ j }{ \to } \mathcal{C}\overset{ \partial }{ \to } \mathcal{B}_{-1}\to 0$$ is a SES of chain complexes where $\mathcal{Z}:=(Z_{i}(\mathcal{C}),0)_{i}$, $\mathcal{B}_{-1}:=(B_{i-1}(\mathcal{C}),0)_{i}$, and $j$ is the inclusion.
> 2. This SES induces the following SES of cochain complexes: $$0 \to \mathcal{B}_{-1}^{*}\overset{ \delta }{ \to } \mathcal{C}^{*}\overset{ j^{*} }{ \to }\mathcal{Z}^{*}\to 0$$In particular, we have the following LES:$$\cdots\to Z_{n-1}^{*}\overset{ i_{n-1}^{*} }{ \to } B_{n-1}^{*}\overset{ \delta }{ \to  }H^n(C;G)\overset{ j^{*} }{ \to } Z_{n}^{*}\overset{ i_{n}^{*} }{ \to } B_{n}^{*}\to O\cdots$$where $i_{n}:B_{n}\hookrightarrow Z_{n}$ is the inclusion.
> 3. We hence have many SES's: $$0 \to \text{coker}(i^{*}_{n-1}) \overset{ \delta }{ \to } H^n(C;G)\overset{ \tilde{j} }{ \to  }\text{ker }i^{*}_{n}\to 0$$where $\text{ker }i^{*}_{n}\cong\text{Hom}(H_{n}(\mathcal{C}),G)$ and $h:H^n(C;G)\to \text{Hom}(H_{n}(\mathcal{C}),G)$ from [[Cochain Complex|Theorem 4]] can be identified as $$h:H^n(C;G)\overset{ \tilde{j} }{ \to } \text{ker } i^{*}_{n}\overset{ \cong }{ \to } \text{Hom}(H_{n}(\mathcal{C}),G)$$
> 4. We have the SES's: $$0 \to \text{coker}(i^{*}_{n-1}) \overset{ \delta }{ \to } H^n(C;G)\overset{ h}{ \to  }\text{Hom}(H_{n}(\mathcal{C}),G)\to 0$$

> [!proof]+
> We have that:
> 1. Notice that: $$\begin{CD}0 @>>> Z_{n+1}@>j>> C_{n+1}@>\partial>> B_{n} @>>> 0\\ &@V{0}VV&@V{\partial}VV&@V{0} VV\\  0 @>>> Z_{n}@>>j> C_{n}@>>\partial>B_{n-1} @>>> 0\end{CD}$$commute as $\partial \circ j = 0$ from $\partial|_{Z_{n+1}}=0$ and $\partial^{2}=0$.
> 2. As $\mathcal{C}$ is free abelian, $\mathcal{B}_{1}$ is free abelian as well. Hence, from [[Split Exact Sequence|Proposition 2]], $0 \to Z_{n} \to C_{n }\to B_{n-1}\to 0$ is split for all $n$. Therefore, by [[Split Exact Sequence|Proposition 3]], $$0\to B_{n-1}^{*}\overset{ \delta }{ \to } C_{n}^{*}\overset{ j^{*} }{ \to } Z_{n}^{*}\to 0$$is a split SES. To show that $i^{*}_{n}:Z^{*}_{n}\to B^{*}_{n}$ is the connecting homomorphism, let $\psi\in Z^{*}_{n}$. Let $\tau$ be the connecting homomorphism. Then, we have that $\delta(\tau(\psi))=\delta(\varphi)$ where $\varphi|_{Z_{n}}=\psi$ for some $\varphi\in C_{n}^{*}$. This is given if 