#Definition #Algebra-I 

> [!definition]
> For a group $G$, the ***center*** $Z(G)$ of $G$ is defined as:
> $$Z(G):=\{ x\in G: \forall a\in G.(xa=ax) \}$$
> i.e., $Z(G)=\bigcap_{a\in G}^{}Z_{G}(a)$.
---
##### Properties

> [!lemma] Lemma 1
> For a group $G$ and its center $Z(G)$, it holds that:
> 1. $Z(G)=G$ if and only if $G$ is abelian.
> 2. $Z(G)\leq G$.
> 3. $Z(G)\unlhd G$.
> 4. $Z(G)$ is abelian.
> 5. If $H \leq Z(G)$, then $H\unlhd G$.

> [!proof]-
> For a group $G$ and its center $Z(G)$,
> 1. If $G$ is abelian, of course every element commutes with each other. In the other direction, we have $\forall x,a\in G:ax=xa$. Therefore, $G$ is abelian.
> 2. Because the center is an intersection of subgroups.
> 3. For $x\in Z(G)$ and $a\in G$, it holds that: $$ ax a^{-1}=aa^{-1}x=x\in Z(G)$$ Therefore, from Proposition 1, $Z(G) \unlhd G$.
> 4. For $x,y\in Z(G)$, we have $xy=yx$. Therefore, $Z(G)$ is abelian.
> 5. For $x\in H\le Z(G)$ and $a\in G$, it holds that $$ax a^{-1}=xaa^{-1}=x\in H$$Using the same proposition as 3, $H\unlhd G$.
---
> [!lemma] Lemma 2
> Let $N\unlhd Z(G)\unlhd G$ hold and $G / N$ be [[Cyclic Groups|cyclic]]. Then, $G$ is abelian. 

> [!proof]-
> Let $aN$ be the generator of $G / N$. Then, for every $x\in G$, the coset $x N=a^iN$ for some $i$ and as $e\in N$, $x=a^iz$ for some $z\in N$. It follows that for any two elements $x,y\in G$:$$xy = a^iza^jz'=a^{i+j}zz' =a^{i+j}z'z =a^jz'a^iz=yx$$as $z,z'\in Z(G)$ and commute with every group element. Therefore, $xy=yx$ for any $x,y\in G$ and the group is abelian. 
---
> [!lemma] Lemma 3
> For a [[simple group]] $G$ with $\left| G \right|>2$, $Z(\text{Aut}(G))=\{ \iota \}$ if and only if $G$ is non-abelian.

> [!proof]-
> If $Z(\text{Aut}(G))=\{ \iota \}$, then for $\varphi(x)= x ^{-1}$ and $\psi\in \text{Aut}(G)$, we have that: $$(\psi \varphi)(x)=\psi(x)=\psi(x)^{-1}=(\varphi \psi)(x)$$So either $\varphi=\iota$ or $\varphi\notin \text{Aut}(G)$. If $\varphi=\iota$, then we get an abelian group but this is a contradiction as $G$ is simple. Therefore, $\varphi\notin \text{Aut}(G)$ and $G$ is non-abelian. 
> 
> If $G$ is non-abelian, $Z(G)$ is trivial and for $\sigma\in Z(\text{Aut}(G))$, $\text{Inn}(G)\cong G / Z(G)\cong G$. Therefore, 
---
##### Examples
- The center of a [[Quaternion Group|quaternion group]], $Z(Q_{8})=\{ e,\bar{e} \}$.