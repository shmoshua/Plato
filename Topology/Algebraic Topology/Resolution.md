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
> [!lemma] Proposition 2
> Let $\mathcal{F}\overset{ \varepsilon }{ \to }H$ be a free resolution. Then, 
> 1. We can dualize the exact sequence into: $$0\to H^{*} \overset{ \varepsilon ^{*} }{ \to } F^{*}_{0}\overset{ f_{1}^{*} }{ \to } F^{*}_{1}\overset{ f_{2}^{*} }{ \to } F^{*}_{2}\overset{ f_{3}^{*} }{ \to } F^{*}_{3}\to \cdots$$where up to $F^{*}_{1}$ the sequence is exact.
> 2. $H^0(\mathcal{F};G)\cong H^{*}=\text{Hom}(H,G)$.

^db3384

> [!proof]-
> We have that:
> 1. By [[Module|left exactness of homomorphism]].
> 2. We have that: $$H^0(\mathcal{F};G)=\text{ker }f^{*}_{1}=\text{im }\varepsilon ^{*}$$However, as $\varepsilon ^{*}$ is injective, we have that $\varepsilon ^{*}:H^{*}\to H^0(\mathcal{F};G)$ is an isomorphism. 

^7844ed

---
> [!lemma] Theorem 3 (Uniqueness of Resolution)
> Let $H$ be an abelian group and $\mathcal{F}\overset{ \varepsilon }{ \to }H$ a free resolution.
> 1. Let $\mathcal{F}'\overset{ \varepsilon' }{ \to }H'$ be a resolution of an abelian group $H'$. For any homomorphism $\alpha:H\to H'$, we can extend it to a chain map as follows: $$\begin{CD}\mathcal{F}:\ \cdots @>>> F_{2}@>f_{2}>> F_{1}@>f_{1}>> F_{0} @>\varepsilon >> H@>>>0\\ &@V\alpha_{2}VV&@V\alpha_{1}VV&@V\alpha_{0} VV&@V\alpha VV\\ \mathcal{F}':\ \cdots @>>>F_{2}'@>>f_{2}'> F_{1}'@>>f_{1}'>F'_{0} @>>\varepsilon '> H'@>>>0\end{CD}$$
> 	Moreover, any two such extensions are [[Chain Homotopy|chain homotopic]].
> 2. Let $\mathcal{F}'\overset{ \varepsilon' }{ \to }H$ be a free resolution. Then, there exists a canonical isomorphism $H^{n}(\mathcal{F};G)\cong H^{n}(\mathcal{F}';G)$ for all $n\geq 0$. In other words, $H^n(\mathcal{F};G)$ only depends on $H$ and $G$.

^c44c09

> [!proof]+
> We have that:
> 1. We will extend $\alpha$ inductively. Let $\alpha_{-1}:= \alpha$, $f_{0}:=\varepsilon$ and $f_{0}':=\varepsilon'$. Let $\{ x_{s} \}_{s\in \mathcal{S}}$ be a basis of $F_{0}$. Choose $\alpha_{0}(x_{s})\in F'_{0}$ s.t. $f_{0}'(\alpha_{0}(x_{s}))=\alpha_{-1}(f_{0}(x_{s}))$. This exists as $f'_{0}$ is surjective. Since $F_{0}$ is free abelian, this defines $\alpha_{0}:F_{0}\to F'_{0}$ s.t. it commutes. 
>    
>    Now, let $i\geq 0$. Consider the setting: $$\begin{CD}\cdots @>>> F_{i+1}@>f_{i+1}>> F_{i}@>f_{i}>> F_{i-1} @>>>\cdots \\ &&&@V\alpha_{i}VV&@V\alpha_{i-1} VV&\\ \ \cdots @>>>F_{i+1}'@>>f_{i+1}'> F_{i}'@>>f_{i}'>F'_{i-1} @>>> \cdots\end{CD}$$where we have $\alpha_{0},\dots,\alpha_{i}$ all satisfying the desired properties. To define $\alpha_{i+1}$, let $\{ x_{s} \}_{s\in \mathcal{S}}$ be a basis of $F_{i+1}$. Then, we claim that $\alpha_{i}(f_{i+1}(x_{s}))\in \text{im}f'_{i+1}$. Indeed, we have: $$f'_{i}(\alpha_{i}(f_{i+1}(x_{s})))=\alpha_{i-1}(\underbrace{ f_{i}(f_{i+1} }_{ =0 }(x_{s})))=0$$Hence, $\alpha_{i}(f_{i+1}(x_{s}))\in \text{ker }f'_{i}=\text{im }f'_{i+1}$. Therefore, we can choose $\alpha_{i+1}(x_{s})$ s.t. $f'_{i+1}(\alpha_{i+1}(x_{s}))=\alpha_{i}(f_{i+1}(x_{s}))$. Therefore, the existence is given by induction. 
>    
>    To show the uniqueness up to homotopy, let $\{ \alpha_{i} \}$ and $\{ \alpha_{i}' \}$ be two extensions. 

- **Corollary**: From Example 1, we have that $H^n(\mathcal{F};G)=0$ for all $n\geq 2$.  ^a90f58
---
##### Examples
> [!h] Example 1
> Let $H$ be an abelian group. 
> 1. Let $\mathcal{S}$ be a set of generators of $H$. Then, $$0\to \text{ker }\varepsilon \to\bigoplus_{s\in \mathcal{S}}\mathbb{Z}x_{s}\overset{ \varepsilon }{ \to }H\to 0$$ is exact and this gives rise to a free resolution of $H$.

^910349
