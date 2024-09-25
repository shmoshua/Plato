#Definition #Algebra

> [!definition]
> Let $R$ and $S$ be [[Ring|rings]]. A map $\varphi:R \to S$ is a ***ring homomorphism*** if 
> 1. $\varphi(a+b)=\varphi(a)+\varphi(b)$
> 2. $\varphi(ab)=\varphi(a)\varphi(b)$
> 3. $\varphi(1_{R})=1_{S}$ for $S\neq \{ 0 \}$

^4740fd

- **Remark**: $\varphi[R]$ is a subring of $S$.
- **Related definition**: For $I\unlhd S$, $\varphi ^{-1}(I)$ is called the ***contraction*** of $I$ by $\varphi$, denoted with $I^c$.  ^dcea70
- **Related definition**: For $I\unlhd R$, $(\varphi(I))$ is called the ***extension*** of $I$ by $\varphi$, denoted with $\varphi(I)S$ or $I^e$. If $\varphi$ is surjective, $I^e=\varphi(I)$. ^c7184a
---
##### Properties
> [!lemma] Lemma 1
> Let $\varphi:R \to S$ be a ring homomorphism and $\mathfrak{a}\subseteq R$ an [[Ideal (Ring)]] s.t. $\mathfrak{a}\subseteq \text{ker}(\varphi)$.  Then, there exists a unique ring homomorphism $\overline{\varphi}: R / \mathfrak{a}\to S$ s.t.  
>
> ```tikz 
> \usepackage{tikz-cd} \usepackage{amsfonts} 
> \usepackage{amssymb} 
> \begin{document} 
> \begin{tikzcd}
> R \arrow[r, "\varphi"] \arrow[d,swap, "\pi"]& S\\R /\mathfrak{a} \arrow[ru, swap,"\overline{\varphi}"]
> \end{tikzcd}
> \end{document}
> ```
> 
> commutes and especially, $$\varphi[R]=\overline{\varphi}[R / \mathfrak{a}]$$and $\text{ker}(\overline{\varphi})= \text{ker}(\varphi) / \mathfrak{a}$.

^ae05b2

> [!proof]-
> We define $\overline{\varphi}(x+\mathfrak{a}):=\varphi(x)$.  Then, we show:
> - $\overline{\varphi}$ is well-defined. We have that: $$\begin{align}\overline{x}&=\overline{y}\iff x-y\in\mathfrak{a}\subseteq \text{ker}(\varphi)\iff\varphi(x-y)=0_{S}\iff\varphi(x)=\varphi(y)\end{align}$$
> - $\overline{\varphi}$ is a ring homomorphism, which follows from the definition of $\overline{\varphi}$ and that $\varphi$ is a ring homomorphism. 
> - $\overline{\varphi}$ is unique and $\overline{\varphi}[R / \mathfrak{a}]=\varphi[R]$: follows from proof of [[Group Homomorphism|Isomorphism theorem]]
> - $\text{ker}(\overline{\varphi})=\text{ker}(\varphi) / \mathfrak{a}$: $$\text{ker}(\overline{\varphi})=\{ x+\mathfrak{a}\in R / \mathfrak{a}:\varphi(x)=0 \}=\{ x+\mathfrak{a}\in R / \mathfrak{a}: x \in\text{ker}(\varphi)\}=\text{ker}(\varphi) / \mathfrak{a}$$
- **Corollary**: By letting $\mathfrak{a}=\text{ker}(\varphi)$, we have the first isomorphism theorem: $$R / \text{ker}(\varphi)\cong \text{Im }\varphi$$

---
> [!lemma] Theorem 2 (First isomorphism theorem)
> For rings $R,S$ and a surjective homomorphism $\varphi:R\to S$, let $I\unlhd R$ with $\text{ker}(\varphi) \subseteq I$. Then, $$R / I\cong S / \varphi(I)$$

^d4ff10

> [!proof]-
> We show that:
> 1. $\varphi[\mathfrak{a}]\subseteq S$ is an ideal. For $a,b\in \varphi[\mathfrak{a}]$, there exists $c,d\in \mathfrak{a}$ s.t. $$\varphi(c+d)=\varphi(c)+\varphi(d)=a+b\in \varphi[\mathfrak{a}]$$Further, for any $s\in S$, $s\varphi(a)=\varphi(b)\varphi(a)=\varphi(ba)\in \varphi[\mathfrak{a}]$.
>    
> We now define the following homomorphism: $$\begin{array}{cccc} {\phi:}&{R}&\to&{S / \varphi[\mathfrak{a}]}\\&{x} &\mapsto & {\varphi(x)+\varphi[\mathfrak{a}]} \end{array}{}$$
> 1. $\phi$ is a homomorphism:
>     $$\phi(x+y)=\varphi(x+y)+\varphi[\mathfrak{a}]=\varphi(x)+\varphi[\mathfrak{a}]+\varphi(x)+\varphi[\mathfrak{a}]=\phi(x)+\phi(y)$$
>     $$\phi(xy)=\varphi(xy)+\varphi[a]=(\varphi(x)+\varphi[\mathfrak{a}])(\varphi(y)+\varphi[\mathfrak{a}])=\phi(x)\phi(y)$$
>     $$\phi(1_{R})=\varphi(1_{R})+\varphi[\mathfrak{a}]=1_{S}+\varphi[\mathfrak{a}]$$
> 2. $\phi$ is surjective as $\phi=\pi \circ\varphi$ where both functions are surjective. 
> 3. We have: $$\text{ker }\phi=\{ x\in R:\varphi(x)\in \varphi[\mathfrak{a}] \}$$
> 	Therefore, $\mathfrak{a}\subseteq\text{ker }\phi$. Similarly, for $y\in \text{ker }\phi$, there exists $x\in \mathfrak{a}$ s.t. $\varphi(y)=\varphi(x)$. Then, $\varphi(y-x)=0$ and $y-x\in \text{ker }\varphi \subseteq \mathfrak{a}$. Therefore, $y=(y-x)+x\in \mathfrak{a}$. This shows that $\text{ker }\phi=\mathfrak{a}$. $$R / \mathfrak{a}\cong S / \varphi[\mathfrak{a}]$$ 

^76eff0

---
> [!lemma] Theorem 3 (Second isomorphism theorem)
 > Let $R$ be a ring, $S\subseteq R$ a subring and $\mathfrak{a}\subseteq R$ an [[Ideal (Ring)]]. Then, $$S+\mathfrak{a}:=\{ x+a:x\in S,a\in\mathfrak{a} \}$$is a subring of $R$ that contains $\mathfrak{a}$ as ideal and it holds that: $$S / S \cap \mathfrak{a}\cong (S+\mathfrak{a}) / \mathfrak{a}$$

^035149

> [!proof]-
> We show that: 
> 1. $S+\mathfrak{a}$ is a subring of $R$: $$(x+a)(y+b)=xy+xb+ay+ab\in S+\mathfrak{a}$$
> 2. $\mathfrak{a}\subseteq S+\mathfrak{a}$ is an ideal is trivial.
> 3. Then, we define:
$$\begin{array}{cccccc}\varphi:&S&\xhookrightarrow{}&S+\mathfrak{a}&\xrightarrow{\pi}&(S+\mathfrak{a})/\mathfrak{a} \\&x&\mapsto &x+0&\mapsto&(x+0)+\mathfrak{a}\end{array}$$
> We will show that $\varphi$ is a ring homomorphism: $$\varphi(x+y)=((x+y)+0)+\mathfrak{a}=(x+0)+\mathfrak{a}+(y+0)+\mathfrak{a}=\varphi(x)+\varphi(y)$$
> $$\varphi(xy)=(xy+0)+\mathfrak{a}=((x+0)+\mathfrak{a})((y+0)+\mathfrak{a})=\varphi(x)\varphi(y)$$
> $$\varphi(1)=(1+0)+\mathfrak{a}=1_{(S + \mathfrak{a})/\mathfrak{a}}$$
> 4. Then,
>    $$\text{ker}(\varphi)=\{ x\in S: x+0 \in \mathfrak{a} \}=\{ x\in S: x\in \mathfrak{a} \}=S\cap \mathfrak{a}$$
> 5. Further, $$\varphi[S]=\{ (x+0)+\mathfrak{a}: x\in S \}=\{ (x+a)+\mathfrak{a}: x\in S,a\in \mathfrak{a} \}=(S+\mathfrak{a}) / \mathfrak{a}$$
> 
> Therefore, $$S / (S \cap \mathfrak{a})\cong (S+\mathfrak{a}) / \mathfrak{a}$$

---

> [!lemma] Theorem 4 (Third isomorphism theorem)
> Let $R$ be a ring and $\mathfrak{a,b}\subseteq R$ ideals s.t. $\mathfrak{b}\subseteq \mathfrak{a}$. Then, $$(R / \mathfrak{b}) / (\mathfrak{a}/\mathfrak{b})\cong R / \mathfrak{a}$$where $\mathfrak{a}/\mathfrak{b}:=\{ a+\mathfrak{b}:a\in \mathfrak{a} \}$

> [!proof]-
> We first show that $\mathfrak{a / b}$ is an ideal in $R / \mathfrak{b}$. We have that: 
> 1. for $a_{1}+\mathfrak{b},a_{2}+\mathfrak{b}\in \mathfrak{a} / \mathfrak{b}$, $a_{1}+a_{2}+\mathfrak{b}\in \mathfrak{a / b}$.
> 2. for $a+\mathfrak{b}\in \mathfrak{a / b}$ and $r+\mathfrak{b}\in R / \mathfrak{b}$, $ra+\mathfrak{b}\in\mathfrak{a / b}$.
> 
> Finally, we define the homomorphism: $$\begin{array}{cccc} {\varphi:}&{R / \mathfrak{b}}&\to&{R / \mathfrak{a}}\\&{x+\mathfrak{b}} &\mapsto & {x+\mathfrak{a}} \end{array}{}$$
> 1. $\varphi$ is well defined: let $x+\mathfrak{b}=y+\mathfrak{b}$, i.e. $x-y\in \mathfrak{b}$. Then, $x-y\in \mathfrak{a}$ and $x+\mathfrak{a}=y+\mathfrak{a}$.
> 2. $\varphi$ is surjective by definition.
> 3. $\text{ker }\varphi=\{ x+\mathfrak{b}\in R/\mathfrak{b}: x\in \mathfrak{a}\}=\mathfrak{a / \mathfrak{b}}$.
> 
> Therefore, by the isomorphism theorem: $$(R / \mathfrak{b}) / (\mathfrak{a / b})\cong R / \mathfrak{a}$$
---
> [!lemma] Lemma 5 (Contraction and Extension gives a bijection for Quotient)
> Let $I\unlhd R$. 
> 1. the ideals in $R / I$ and the ideals in $R$ containing $I$ form a bijection given by $J\to J^c$ and $J\to J^e$ given by the canonical projection $\varphi:R \to R / I$.

^5f80ff

> [!proof]-
> We have that:
> 1. We can check that the bijection is well-defined. Further, as $\varphi$ is surjective, $J^e=\varphi(J)$. Therefore, for $J\unlhd R / I$, $$(J^c)^e=\varphi(\varphi ^{-1}(J))=J$$Further, for $J\unlhd R$ with $I\subseteq J$:$$(J^e)^c=\varphi ^{-1}(\varphi(J))=\{ a\in R:\varphi(a)\in \varphi(J) \}=J+I=J$$

^747f92

---
##### Examples
- Let $R=\mathbb{Z}\times \mathbb{Z}$, $S= \mathbb{Z}\times \{ 0 \}$, $\mathfrak{a}=\{ 0 \}\times 3\mathbb{Z}$ and $\varphi(x,y)=(x,0)$. Then, 
	1. $\text{ker}(\varphi)=\{ 0 \}\times \mathbb{Z}$ and $\mathfrak{a}\subseteq \text{ker}(\varphi)$.
	2. $\text{ker}(\overline{\varphi})=(\{ 0 \}\times \mathbb{Z}) / (\{ 0 \}\times 3\mathbb{Z})\cong \mathbb{Z} / 3\mathbb{Z}$

---