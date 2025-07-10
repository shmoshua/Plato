#Definition #AlgebraicTopology 

> [!definition]


---
##### Properties
> [!lemma] Proposition 1
> Let $\mathcal{C}$ be a [[chain complex]] of free abelian groups. 
> 1. We have that: $$0\to \mathcal{Z}\overset{ j }{ \to } \mathcal{C}\overset{ \partial }{ \to } \mathcal{B}_{-1}\to 0$$ s a SES of chain complexes where $\mathcal{Z}:=(Z_{i}(\mathcal{C}),0)_{i}$ and $\mathcal{B}_{-1}:=(B_{i-1}(\mathcal{C}),0)_{i}$.
> 2. This SES induces the following SES of cochain complexes: $$0 \to \mathcal{B}_{-1}^{*}\overset{ \delta }{ \to } \mathcal{C}^{*}\overset{ j^{*} }{ \to }\mathcal{Z}^{*}\to 0$$In particular, we have the following LES:$\tau$: $$\cdots\to Z_{n-1}^{*}\overset{ i_{n-1}^{*} }{ \to } B_{n-1}^{*}\overset{ \delta }{ \to  }H^n(C;G)\overset{ j^{*} }{ \to } Z_{n}^{*}\overset{ i_{n}^{*} }{ \to } B_{n}^{*}\to O\cdots$$where $i_{n}:B_{n}\hookrightarrow Z_{n}$ is the inclusion.
> 3. We hence have many SES's: $$0 \to \text{coker}(i^{*}_{n-1}) \overset{ \delta }{ \to } H^n(C;G)\overset{ \tilde{j} }{ \to  }\text{ker }i^{*}_{n}\to 0$$where $\text{ker }i^{*}_{n}\cong\text{Hom}(H_{n}(\mathcal{C}),G)$ and $h:H^n(C;G)\to \text{Hom}(H_{n}(\mathcal{C}),G)$ from [[Cochain Complex|Theorem 4]] can be identified as $$h:H^n(C;G)\overset{ \tilde{j} }{ \to } \text{ker } i^{*}_{n}\overset{ \cong }{ \to } \text{Hom}(H_{n}(\mathcal{C}),G)$$
> 4. We have the SES's: $$0 \to \text{coker}(i^{*}_{n-1}) \overset{ \delta }{ \to } H^n(C;G)\overset{ h}{ \to  }\text{Hom}(H_{n}(\mathcal{C}),G)\to 0$$