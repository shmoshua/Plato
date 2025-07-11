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

> [!proof]-
> We have that:
> 1. We will extend $\alpha$ inductively. Let $\alpha_{-1}:= \alpha$, $f_{0}:=\varepsilon$ and $f_{0}':=\varepsilon'$. Let $\{ x_{s} \}_{s\in \mathcal{S}}$ be a basis of $F_{0}$. Choose $\alpha_{0}(x_{s})\in F'_{0}$ s.t. $f_{0}'(\alpha_{0}(x_{s}))=\alpha_{-1}(f_{0}(x_{s}))$. This exists as $f'_{0}$ is surjective. Since $F_{0}$ is free abelian, this defines $\alpha_{0}:F_{0}\to F'_{0}$ s.t. it commutes. 
>    
>    Now, let $i\geq 0$. Consider the setting: $$\begin{CD}\cdots @>>> F_{i+1}@>f_{i+1}>> F_{i}@>f_{i}>> F_{i-1} @>>>\cdots \\ &&&@V\alpha_{i}VV&@V\alpha_{i-1} VV&\\ \ \cdots @>>>F_{i+1}'@>>f_{i+1}'> F_{i}'@>>f_{i}'>F'_{i-1} @>>> \cdots\end{CD}$$where we have $\alpha_{0},\dots,\alpha_{i}$ all satisfying the desired properties. To define $\alpha_{i+1}$, let $\{ x_{s} \}_{s\in \mathcal{S}}$ be a basis of $F_{i+1}$. Then, we claim that $\alpha_{i}(f_{i+1}(x_{s}))\in \text{im}f'_{i+1}$. Indeed, we have: $$f'_{i}(\alpha_{i}(f_{i+1}(x_{s})))=\alpha_{i-1}(\underbrace{ f_{i}(f_{i+1} }_{ =0 }(x_{s})))=0$$Hence, $\alpha_{i}(f_{i+1}(x_{s}))\in \text{ker }f'_{i}=\text{im }f'_{i+1}$. Therefore, we can choose $\alpha_{i+1}(x_{s})$ s.t. $f'_{i+1}(\alpha_{i+1}(x_{s}))=\alpha_{i}(f_{i+1}(x_{s}))$. Therefore, the existence is given by induction. 
>    
>    To show the uniqueness up to homotopy, let $\{ \alpha_{i} \}$ and $\{ \alpha_{i}' \}$ be two extensions. Let $\beta_{i}:=\alpha_{i}-\alpha_{i}'$. Therefore, it suffices to show that any extension of $0$ is chain homotopic to $\{ \beta_{i} \}$. We show this via induction by defining a chain homotopy $h_{i}:F_{i}\to F_{i+1}'$. 
> 	1. For $i=-1$, we take that $h_{-1}:= 0$. Then, we need that $f'_{1} \circ h_{0}=\beta_{0}$. We define $h_{0}$ as follows: For a basis $\{ x_{s} \}_{s\in \mathcal{S}}$ of $F_{0}$, we have that $f'_{0}(\beta_{0}(x_{s}))=0$ from the following diagram. $$\begin{CD}\cdots@>>> F_{2}@>f_{2}>> F_{1}@>f_{1}>> F_{0} @>f_{0} >> H@>>>0\\ &@V\beta_{2}VV&@V\beta_{1}VV&@V\beta_{0} VV&@V 0 VV\\\cdots @>>>F_{2}'@>>f_{2}'> F_{1}'@>>f_{1}'>F'_{0} @>>f_{0} '> H'@>>>0\end{CD}$$Therefore, $\beta_{0}(x_{s})\in \text{ker }f'_{0}=\text{im }f'_{1}$ and we can choose $h_{0}(x_{s})\in F'_{1}$ s.t. $f'_{1}(h_{0}(x_{s}))=\beta_{0}(x_{s})$.
> 	2. For $i\geq 0$, assume that we have $h_{-1},\dots,h_{i-1}$ meeting the desired properties. Then:$$\begin{CD}\cdots @>>> F_{i+1}@>f_{i+1}>> F_{i}@>f_{i}>> F_{i-1} @>>>\cdots \\ &&@V\beta_{i+1}VV&@V\beta_{i}VV&@V\beta_{i-1} VV&\\ \ \cdots @>>>F_{i+1}'@>>f_{i+1}'> F_{i}'@>>f_{i}'>F'_{i-1} @>>> \cdots\end{CD}$$To define $h_{i}$, let $\{ x_{s} \}_{s\in \mathcal{S}}$ be a basis of $F_{i}$. Let $y_{s}:=\beta_{i}(x_{s})-h_{i-1}(f_{i}(x_{s}))$. We claim that $y_{s}\in \text{ker }f'_{i}$. Indeed, $$\begin{aligned}f'_{i}(y_{s})&=f'_{i}\circ \beta_{i}(x_{s})-f'_{i} \circ  h_{i-1} \circ  f_{i}(x_{s})\\&=\beta_{i-1} \circ  f_{i}(x_{s})-(\beta_{i-1}-h_{i-2} \circ  f_{i-1})  \circ  f_{i}(x_{s})=0\end{aligned}$$Therefore, $y_{s}\in \text{im } f'_{i+1}$ and we can similarly choose $h_{i}(x_{s})\in F'_{i+1}$ s.t. $f'_{i+1}(h_{i}(x_{s}))=y_{s}$. 
> 
> 	 Hence, by induction we have the desired statement.
>  2. By Part 1, we have a chain map $\alpha: \mathcal{F}\to \mathcal{F'}$ that extends $\text{id}_{H}$. Similarly, we have a chain map $\beta:\mathcal{F}'\to \mathcal{F}$ that extends $\text{id}_{H}$. Therefore, $\beta \circ \alpha:\mathcal{F}\to \mathcal{F}$ is a chain map that extends $\text{id}_{H}$. However, as $\text{id}_{\mathcal{F}}$ is also such a chain map, by uniqueness modulo chain homotopy, $\beta \circ \alpha\sim \text{id}_{\mathcal{F}}$. Therefore, by dualizing, $\alpha ^{*}\circ \beta ^{*}\sim \text{id}_{\mathcal{F}^{*}}$ and we have that $\alpha ^{*} \circ \beta ^{*}=\text{id}_{H^n(\mathcal{F};G)}$. Analogously, we can show that $\beta ^{*} \circ \alpha ^{*}=\text{id}_{H^n(\mathcal{F}'; G)}$. 
>     
>     Lastly, as these maps are invariant under chain homotopy, they induce the same isomorphism for the cohomology.

^a01a4f

- **Corollary**: From Example 1, we have that $H^n(\mathcal{F};G)=0$ for all $n\geq 2$.  ^a90f58
---
##### Examples
> [!h] Example 1
> Let $H$ be an abelian group. 
> 1. Let $\mathcal{S}$ be a set of generators of $H$. Then, $$0\to \text{ker }\varepsilon \to\bigoplus_{s\in \mathcal{S}}\mathbb{Z}x_{s}\overset{ \varepsilon }{ \to }H\to 0$$ is exact and this gives rise to a free resolution of $H$.

^910349

