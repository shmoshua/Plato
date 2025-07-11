> [!definition]
> Let $H$ be an [[abelian group]]. Then, 
> 1. $\text{Tor}(H,G):=H_{1}(\mathcal{F};G)$ where $\mathcal{F}\overset{ \varepsilon }{ \to } H$ is a [[Resolution|free resolution]] of $H$.

---
##### Properties
> [!lemma] Proposition 1
>  Let $\mathcal{C}$ be a [[chain complex]] of free abelian groups and $G$ an abelian group.
> 1. We have that: $$0\to \mathcal{Z}\overset{ j }{ \to } \mathcal{C}\overset{ \partial }{ \to } \mathcal{B}_{-1}\to 0$$ is a SES of chain complexes where $\mathcal{Z}:=(Z_{i}(\mathcal{C}),0)_{i}$, $\mathcal{B}_{-1}:=(B_{i-1}(\mathcal{C}),0)_{i}$, and $j$ is the inclusion.
> 2. This SES induces the following SES of cochain complexes: $$0 \to \mathcal{Z}\otimes  G\overset{ j\otimes  \text{id} }{ \to } \mathcal{C}\otimes  G\overset{ d:= \partial \otimes \text{id} }{ \to }\mathcal{B}_{-1}\otimes G\to 0$$In particular, we have the following LES:$$\cdots\to B_{n}\otimes  G\overset{ i_{n}\otimes \text{id} }{ \to  }Z_{n}\otimes  G \to H_{n}(\mathcal{C};G)\to B_{n-1}\otimes  G \overset{ i_{n-1}\otimes \text{id} }{ \to } Z_{n-1}\otimes G\to \cdots$$where $i_{n}:B_{n}\hookrightarrow Z_{n}$ is the inclusion.
> 3. We hence have many SES's: $$0 \to H_{n}(\mathcal{C})\otimes G \overset{ \tau }{ \to } H_n(\mathcal{C};G)\overset{  }{ \to  }\text{Tor}(H_{n-1}(\mathcal{C}),G)\to 0$$where $\tau([c],g)=[c\otimes g]$.

> [!proof]+
> We have that:
> 1. Obvious.
> 2. As $\mathcal{C}$ is free, so is $\mathcal{B}_{-1}$ and hence the SES in 1 is split in each level. Hence, by [[Tensor Product|Proposition 3.3.1]], we get the desired SES. To see that we get the given connecting homomorphism is easy.
> 3. From 2, we get the following SES's: $$0\to \text{coker}(i_{n}\otimes  \text{id})\to H_{n}(\mathcal{C};G)\to \text{ker}(i_{n-1}\otimes \text{id})\to 0$$However, by [[Tensor Product|Proposition 4]], $\text{coker}(i_{n}\otimes \text{id})\cong \text{coker}(i_{n})\otimes G=H_{n}(\mathcal{C})\otimes G$.
>    
>    Consider the map $$\overline{\tau}:H_{n}(\mathcal{C})\times G\to H_{n}(\mathcal{C};G),\quad ([c],g)\mapsto [c\otimes  g]$$
>    1. $\overline{\tau}$ is well defined: If $c'-c\in B_{n}$, then 

