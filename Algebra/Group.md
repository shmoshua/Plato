#Definition #Algebra-I 

> [!Definition]
> 
> For a set $G$ and a binary operator $\circ$, the pair $(G,\circ)$ forms a ***group*** if the following three axioms hold:
> 1. **Associativity**: for any $a,b,c\in G$ we have: $$a\circ (b\circ c) = (a\circ b)\circ c$$
> 2. **Neutral element**: there exists an element $e\in G$ s.t. for all $a\in G$ we have: $$e\circ a = a \circ e = a$$
> 3. **Inverse element**: for all $a\in G$, there exists $\bar{a}\in G$ s.t. $$a\circ \bar{ a}=\bar{ a}\circ a=e$$
---
##### Propositions

> [!lemma] Proposition 1
> For any group $(G,\circ)$, there is exactly one neutral element and each element in $G$ has exactly one inverse.

> [!Proof]-
> Let $e,e'\in G$ be neutral elements of $G$. Then, we have: $$e = e \circ e' = e'$$ Therefore, there is exactly one neutral element.
> 
> Now, let $a\in G$ be arbitrary and let $x,y\in G$ s.t. $a\circ x=y\circ a=e$. Then, $$y = y \circ e = y \circ (a \circ x)= (y \circ a)\circ x=e \circ x=x$$
> Therefore, $a$ has exactly one inverse.

---
> [!lemma] Proposition 2
> $(G,\cdot)$ is a group if the following axioms hold:
> 1. $\cdot$ is associative.
> 2. **Left-neutral element**: there is an element $e\in G$ s.t. for all $a\in G$, $$ea = a$$
> 3. **Left inverse**: for all $a\in G$, there exist $a^{-1}\in G$ s.t. $$a^{-1}a=e$$

> [!proof]-
> Let $a\in G$ and $b$ be the left inverse of $a^{-1}$. Then, we have $$aa^{-1}=e(a a^{-1})=(ba^{-1})(aa^{-1})=b(a^{-1}a)a^{-1}=b a^{-1}=e$$
> Therefore, the left-inverse is also the right inverse.
>
> Furthermore, we have: $$ae=a( a^{-1}a)=(a a^{-1})a=ea=a$$
> This means that $e$ is also the right neutral element.

- **Remark**: If $(S,\cdot)$ has a left-neutral element and a right inverse for every element, $S$ is not necessarily a group. **Example**: $S=\{ 0,1 \}$ and for $x,y\in S$, define $x\cdot y=y$. Then $\cdot$ is associative and $0$ is a left-neutral element. Further, $0$ is the right inverse of both $0,1$. 
However, there is no $x\in S$ s.t. $x 1 = 0$, i.e. $1$ has no left-inverse. Therefore, $(S,\cdot)$ is not a group.
---

> [!lemma] Proposition 3
> If a set $G$ with an associative operation $\cdot$ has a *unique* left-neutral element and a right inverse for every element, then $G$ is a group.

> [!proof]-
> Let $e$ be the unique left neutral element. We then define: $$ E(G):=\{ a\in G:aa=a \}$$
> First, we show that $E(G)=\{  e \}$. For any $a\in E(G)$ and $b\in G$, we have: $$ab=a(eb)=a(aa^{-1})b=(aa)a^{-1}b=a a^{-1}b=eb=b$$
> Therefore, $a$ is the left neutral element of $b$ and as the left neutral element is unique, $a=e$.
> 
> Consider $Ge:=\{ ge : g\in G \}$. We can easily verify that $Ge$ is a group. Now we will show that each element in $g\in G$ has a left inverse. For any $g\in G$, let $x\in Ge$ s.t. $x(ge)=(ge)x=e$. Then, $$ (xg)(xg)=(xg)e(xg)=xeg=xg$$
>  Therefore, $xg\in E(G)$ and $xg=e$. This proves that every $g$ has a left-inverse and from Proposition 1.2, $G$ is a group.
---
> [!lemma] Proposition 4
> For a finite set $G$ with an associative operation $\cdot$, if $G$ is [[Cancellative operations|cancellative]], then $G$ is a group.

> [!proof]-
> Let $a\in G$ be arbitrary. Consider the set $aG:=\{  ax: x\in G \}$. Then, $|aG| \leq|G|$.  On the other hand, if $|aG|<|G|$, then there exists two different elements $x,y\in G$, s.t. $ax=ay$. Using cancellativity, we have $x=y$. This implies that $|aG|=|G|$ and $aG=G$.
> 
> Then, there exists an element $e\in G$ s.t $ae=a$. Further, we have $ae = (ae)e = a(e e)$. As $G$ is cancellative, $e=e  e$. For any $b\in G$, we have: $be = b(e  e) = (be) e$. Using cancellativity, we have that $b=be$. This implies that $e$ is the right neutral element of $G$. 
> 
> Now, as $aG=G$ for any $a\in G$, there should be $g\in G$ s.t. $ag =e$. This proves that $G$ also has a right inverse element. This proves that $G$ is a group.
---
> [!lemma] Proposition 5
> For a set $S$ with an associative operation $\cdot$,
> 1. even if $S$ is finite and $\cdot$ is right-[[Cancellative operations|cancellative]], $S$ is not necessarily a group.
> 2. even if $S$ is infinite and $\cdot$ is cancellative, $S$ is not necessarily a group.

> [!proof]-
> We have that:
> 1. for $S=\{ 0,1 \}$ and for all $x,y \in S$, $xy=x$. Then, $\cdot$ is right-cancellative but $S$ is definitely not a group.
> 2. For $(\mathbb{N},+)$, $+$ is cancellative, but $\mathbb{N}$ does not form a group.

---

#### Related Definitions
- [[Order of groups]]
- [[Cancellative operations]]
- [[Product of groups]]
- [[Subgroup]]
- [[Coset]]
- [[Inner Product of Groups]]
- [[Center of a group]]

---
