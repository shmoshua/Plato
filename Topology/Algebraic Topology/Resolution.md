#Definition #AlgebraicTopology 

> [!definition]
> Let $H$ be an [[abelian group]]. A ***resolution*** of $H$ is a [[chain complex]] $\mathcal{F}:=\{ F_{i} ,f_{i}\}_{i\in\mathbb{Z}}$ and a map $\varepsilon:F_{0}\to H$ s.t. 
> 1. $F_{i}=0$ for $i<0$ and
> 2. the sequence $\cdots\to F_{2}\overset{ f_{2} }{ \to }F_{1}\overset{ f_{1} }{ \to }F_{0}\overset{ \varepsilon }{ \to }H\to 0$ is [[Exact Sequence|exact]].
> 
> We denote this by $\mathcal{F}\overset{ \varepsilon }{ \to }H$.

^57fffb

- **Related definition**: A resolution $\mathcal{F}$ of $H$ is ***free*** if $F_{i}$ is free for all $i$. ^b055f9
---
##### Properties

> [!lemma] Proposition 1 (Equivalent Definitions)
> Let $H$ be an abelian group. TFAE:
> 1. $\mathcal{F}\overset{ \varepsilon }{ \to }H$ is a free resolution of $H$.
> 2. $\varepsilon$ extends to a [[Chain Complex|quasi-isomorphism]] $\varepsilon:\mathcal{F}\to \mathcal{H}$ where: $$\begin{CD}\mathcal{F}:\ \cdots @>>> F_{2}@>f_{2}>> F_{1}@>f_{1}>> F_{0} @>>> 0@>>>\cdots\\ &@V{0}VV&@V{0}VV&@V\varepsilon VV&@VVV\\ \mathcal{H}:\ \cdots @>>> 0@>>> 0@>>>H @>>> 0@>>>\cdots\end{CD}$$

^f592d6

> [!proof]-
> We have that:
> 1. (1=>2): Let $\mathcal{F}$ be a free resolution of $H$. We first show that $\varepsilon:\mathcal{F}\to \mathcal{H}$ is a valid chain map. It suffices to show that $\varepsilon \circ f_{1}= 0$, which is given by the fact that $\text{im }f_{1}=\text{ker }\varepsilon$ by exactness. 
>    
>    Now for $i\geq 1$, we have: $H_{i}(\mathcal{F})=\text{ker }f_{i} / \text{im } f_{i+1}=0=H_{i}(\mathcal{H})$ and $\varepsilon_{*}$ is the zero map at $i$. For $i=0$, $H_{0}(\mathcal{F})=F_{0} / \text{im }f_{1}$ and $H_{0}(\mathcal{H})=H$. However we have that $\text{im } f_{1}=\text{ker }\varepsilon$ and $$\varepsilon_{*}:F_{0} / \text{ker } \varepsilon\to H$$ is an isomorphism as $\varepsilon$ is surjective. 
> 2. (2=>1): For all $i\geq 1$, we have that $\text{ker }f_{i} / \text{im }f_{i+1}= 0$, i.e. $\text{ker }f_{i} = \text{im }f_{i+1}$. Further, for $i=0$, $\varepsilon_{*}:F_{0} / \text{im }f_{1}\to H$ is an isomorphism. Therefore, $\varepsilon$ is surjective. Lastly, as $H\cong F_{0} / \text{ker }\varepsilon$, we have that $\text{ker }\varepsilon = \text{im }f_{1}$. 

^f9084a

---
