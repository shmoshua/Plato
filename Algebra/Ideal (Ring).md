#Definition #Algebra

> [!definition]
> Let $R$ be a [[Ring|ring]]. Then, an additive [[subgroup]] $I\subseteq A$ is:
> 1. a ***left ideal*** if $aI\subseteq I$ for all $a\in R$.
> 2. a ***right ideal*** if $Ia\subseteq I$ for all $a\in R$.
> 3. an ***ideal*** if it's both left and right ideal.

^bbcb4f

- **Related Definition**: For ideals $I,J\unlhd R$:  ^451b55
	1. the ***sum*** $I+J:=\{ a+b:a\in I,b\in J \}\unlhd R$.
	2. the ***intersection***: $I\cap J\unlhd R$.
	3. the ***product***: $I\cdot J:=(\{ ab:a\in I,b\in J \})$
	4. the ***quotient*** $I:J:=\{ a\in R:aJ\subseteq I \}$.
- $$\begin{align}I+J&=\{a+b:a\in I,b\in J\}\\I\cdot J&=(\{ ab:a\in I,b\in J \})=\left\{  \sum_{i=1}^{n}a_{i}b_{i}:n\in \mathbb{N}, a_{i}\in I,b_{i}\in J \right\}\end{align}$$ ^8b2b1e
- **Remark**: Left-ideals are subrepresentations of the [[Representation|regular representation]] $A$.
---
##### Properties
> [!lemma] Fact 1
> $\mathfrak{a}\subseteq R$ is an ideal in $R$ if and only if it holds that
> 1. $\mathfrak{a} \neq \varnothing$ and
> 2. $a,b\in \mathfrak{a} \implies a+b\in \mathfrak{a}$ and
> 3. for $r\in R$ and $a\in \mathfrak{a}$, $ra,ar\in \mathfrak{a}$

> [!proof]-
> - =>: is clear.
> - <=: To show that $\mathfrak{a}$ is an additive subgroup: from 3, we have for $b\in \mathfrak{a}$, $(-1)b=-b\in \mathfrak{a}$. If $a,b\in \mathfrak{a}$, then, $a,-b\in \mathfrak{a}$ and $a-b\in \mathfrak{a}$.
---
> [!lemma] Proposition 2
> $R / \mathfrak{a}$ forms a [[Ring|ring]] w.r.t the multiplication:
> $$(a+\mathfrak{a})(b+\mathfrak{a})=ab+\mathfrak{a}$$
> This ring is called the [[quotient ring]] of $R$ w.r.t. $\mathfrak{a}$.

>[!proof]-
>We have that: 
>1. Well-definedness: for $a+\mathfrak{a}=a'+\mathfrak{a}$ and $b+\mathfrak{a}=b'+\mathfrak{a}$, we have that $a-a'\in \mathfrak{a}$ and $b-b'\in\mathfrak{a}$. Therefore, 
>	$$\begin{align}ab-a'b'=(a-a')b +a'(b-b')\in\mathfrak{a}\end{align}$$Therefore, $(a+\mathfrak{a})(b+\mathfrak{a})=ab+\mathfrak{a}=a'b'+\mathfrak{a}=(a'+\mathfrak{a})(b'+\mathfrak{a})$.
---
> [!lemma] Fact 3
> For a ring $R$ and $S\subseteq R$, 
> 1. $(S)$ is an ideal.
> 2. $(S)$ is the smallest ideal that contains $S$.
> 
> If $S$ is finite, we also write $(a_{1},\dots,a_{n})$ instead of $(\{ a_{1},\dots,a_{n} \})$.

> [!proof]-
> - $0\in (S)$, therefore, $(S)\neq \varnothing$.
> - For $a,b\in(S)$, $a+b\in (S)$.
> - For $a\in (S)$ and $r\in R$, $ar,ra \in (S)$.
---
> [!lemma] Lemma 4
> Let $\mathfrak{a,b}\subseteq R$ be ideals. Then, 
> 1. $\mathfrak{a+b}$ is an ideal in $R$.
> 2. $(\mathfrak{a\cup b})=\mathfrak{a+b}$
> 3. $\mathfrak{a\cdot b}\subseteq \mathfrak{a\cap b}$
> 4. $\mathfrak{a\cdot b}=\left\{  r\sum_{i=0}^{n}x_{i}y_{i}:n\in \mathbb{N},x_{i}\in \mathfrak{a},y_{i}\in \mathfrak{b},r\in R  \right\}$
> 5. $\cdot$ is associative.
> 6. the left and right distributivity hold for $+$ and $\cdot$.

> [!proof]-
> We have that: 
> 1. $(x_{1}+y_{1})+(x_{2}+y_{2})=(x_{1}+x_{2})+(y_{1}+y_{2})\in \mathfrak{a+b}$ and 
>    for all $r\in R$: $r(x+y)=rx+ry\in\mathfrak{a+b}$.
> 2. It holds that $\mathfrak{a,b \subseteq a+b}$. So $\mathfrak{a\cup b \subseteq a+b}$. Therefore, from 1, $$(\mathfrak{a\cup b})\subseteq \mathfrak{a+b}$$Let $\mathfrak{d}\subseteq R$ be an ideal s.t. $\mathfrak{a\cup b}\subseteq \mathfrak{d}$. Then, for $x\in \mathfrak{a}$ and $y\in \mathfrak{b}$, it holds that: $$x+y \in \mathfrak{d}$$and $\mathfrak{a+b \subseteq d}$. Therefore, $(\mathfrak{a\cup b})=\mathfrak{a+b}$.
> 3. We have that both $\mathfrak{a\cdot b}$ and $\mathfrak{a\cap b}$ are ideals. For $x\in \mathfrak{a}$ and $y\in \mathfrak{b}$, we have that: $$xy\in \mathfrak{a\cap b}$$so $\mathfrak{a\cdot b}\subseteq \mathfrak{a\cap b}$
>    
>  The rest follow from definition.
---
> [!lemma] Theorem 5 (Chinese Remainder Theorem)
> Let $R$ be a ring and $I_{1},\dots,I_{n}\unlhd R$. Let further: $$\varphi:R\to R/I_{1}\times \dots  \times R / I_{n},\quad x\mapsto(x+I_{1},\dots,x+I_{n})$$Then, 
> 1. $\varphi$ is injective if and only if $I_{1}\cap\dots \cap I_{n}=(0)$.
> 2. $\varphi$ is surjective if and only if $I_{1},\dots,I_{n}$ are pairwisely [[Coprime Ideal|coprime]].

^893375

> [!proof]-
> We have:
> 1. $\text{ker }\varphi=I_{1}\cap\dots \cap I_{n}$.
> 2. Assume that $\varphi$ is surjective. Then, as $(1+I_{1},I_{2},\dots,I_{n})\in\text{Im }\varphi$ and there exists $a\in R$ s.t. $a\equiv 1 \mod I_{1}$. Then, $1=(1-a)+a\in I_{1}+I_{2}$ and therefore, $I_{1}+I_{2}=R$. Similarly, we have $I_{i}+I_{j}=R$ for any $i,j$.
> 	
> 	Conversely, there exists $a_{i}\in I_{1}$ and $b_{i}\in I_{i}$ for all $i=2,\dots,n$ s.t. $a_{i}+b_{i}=1$. Then, $b_{i}=1-a_{i}=1 \mod I_{1}$ and $b_{i}=0\mod I_{i}$. Now define $b:=b_{2}\dots b_{n}$. Then, $b=1\mod I_{1}$ and $b=0\mod I_{i}$. Therefore, $$\varphi(b)=(1,0,\dots,0)$$Similarly, we can show that $(0,\dots,1,\dots,0)\in \varphi(R)$ and $\varphi$ is surjective.


^3258a2

> [!proof]- Old proof
>  We first show the claim:
> > [!claim] Claim
> > For all $k\in[n]$:
> > $$R=\mathfrak{a}_{k}+\bigcap_{j\neq k}^{}\mathfrak{a}_{j}$$
>
> > [!proof]-
> > We will show with induction over $n$ with the assumption that $n=2$. Now assume that: $$R=\mathfrak{a_{1}}+(\mathfrak{a}_{2}\cap\dots \cap \mathfrak{a}_{n-1})$$Then, $$\begin{align}R=R\cdot R&=[\mathfrak{a}_{1}+(\mathfrak{a}_{2}\cap\dots \cap \mathfrak{a}_{n-1})]\cdot [\mathfrak{a}_{1}+\mathfrak{a}_{n}]\\&=R\mathfrak{a}_{1}+\mathfrak{a}_{1}\cdot \mathfrak{a}_{n}+(\mathfrak{a}_{2}\cap\dots \cap \mathfrak{a}_{n-1})\mathfrak{a}_{n}\\&\subseteq\mathfrak{a}_{1}+\mathfrak{a}_{1}\cap \mathfrak{a}_{n}+\mathfrak{a}_{2}\cap\dots \cap \mathfrak{a}_{n}\\&= \mathfrak{a}_{1}+\mathfrak{a}_{2}\cap\dots \cap \mathfrak{a}_{n}\end{align}$$
> 
> Let $b_{1},\dots,b_{n}\in R$. Then, there exists for every $k\in [n]$, $a_{k}\subseteq \mathfrak{a}_{k}$ and $r_{k}\in \bigcap_{j\neq k}^{}\mathfrak{a}_{j}$ s.t. $$b_{k}=a_{k}+r_{k}$$Then, we define $b:= r_{1}+\dots+r_{n}$. Now, we show that $b$ meets all the properties. For $i\in[n]$: $$b-b_{i}=b-a_{i}-r_{i}=\sum_{k\neq i}^{}r_{k}-a_{i}$$As $r_{k}\in \bigcap_{j\neq k}^{}\mathfrak{a}_{j}$, for $k\neq i$, $r_{k}\in \mathfrak{a}_{i}$. Therefore, $b-b_{i}\in \mathfrak{a}_{i}$ and $b\equiv b_{i}\mod \mathfrak{a}_{i}$.
> 
> Let $b,c\in R$ s.t. $b\equiv b_{i}\mod \mathfrak{a}_{i}$ and $c \equiv b_{i}\mod \mathfrak{a_{i}}$. Then, for $i\in[n]$, $b-b_{i},c-b_{i}\in \mathfrak{a}_{i}$. Therefore, $$(b-b_{i})-(c-b_{i})=b-c\in \mathfrak{a}_{i}$$Therefore, $b\equiv_{\mathfrak{a}_{i}}c$ and $b=c\mod\mathfrak{a}_{1}\cap\dots \cap \mathfrak{a}_{n}$.
 
---
> [!lemma] Corollary 6
> For $R$ and $\mathfrak{a}_{1},\dots,\mathfrak{a}_{n}$ pairwise coprime, $$R / (\mathfrak{a}_{1}\cap\dots \cap \mathfrak{a}_{n})\cong R / \mathfrak{a}_{1}\oplus \dots \oplus  R / \mathfrak{a}_{n}$$

> [!proof]-
> Consider the following homomorphism: 
> $$\begin{array}{cccc} {\varphi:}&{R}&\to&{R / \mathfrak{a}_{1}\oplus \dots \oplus R / \mathfrak{a}_{n}}\\&{r} &\mapsto & {(r+\mathfrak{a}_{1},\dots,r+\mathfrak{a}_{n})} \end{array}{}$$
> then, $$\text{ker}(\varphi)=\{ r\in R:\forall i\in[n].r\in \mathfrak{a}_{i} \}=\mathfrak{a}_{1}\cap\dots \cap \mathfrak{a}_{n}$$and for $\overline{b}:=(b_{1}+\mathfrak{a}_{1},\dots,b_{n}+\mathfrak{a}_{n})$, then there exists from the CRT $b\in R$ s.t. $\varphi(b)=\overline{b}$. This shows that $\varphi$ is surjective and from the isomorphism theorem, $$R / (\mathfrak{a}_{1}\cap\dots \cap \mathfrak{a}_{n})\cong R / \mathfrak{a}_{1}\oplus \dots \oplus  R / \mathfrak{a}_{n}$$
---
##### Examples
> [!h] Example 1
> For any ring $R$, $(0)$ and $R$ are ideals of $R$.
---
> [!h] Example 2
> For any ring homomorphism $\varphi:R\to S$, $\text{ker }\varphi$ is an ideal in $R$.

^6da822

> [!proof]-
> if $a,b\in \text{ker}(\varphi)$, $r\in R$, then: 
> 1. $0_{R}\in \text{ker}(\varphi)$
> 2. $\varphi(a+b)=\varphi(a)+\varphi(b)=0_{S}$, therefore, $a+b \in \text{ker}(\varphi)$.
> 3. $\varphi(ra)=\varphi(r)\varphi(a)=\varphi(r)\cdot 0_{S}=0_{S}$, therefore, $ra\in \text{ker}(\varphi)$.
> 
> Therefore, from Fact 1, $\text{ker}(\varphi)$ is an ideal.

^25795b

---
- $m\mathbb{Z}$ is an ideal of $\mathbb{Z}$ for $m\in \mathbb{Z}$.
- Consider $\text{C}(\mathbb{R})$, i.e. the set of all functions $f:\mathbb{R}\to \mathbb{R}$. For $M \subseteq \mathbb{R}$, the following: $$\mathfrak{a}_{M}:=\{ f:f(M)=\{ 0 \} \}$$is an ideal in $\text{C}(\mathbb{R})$. 
  
---