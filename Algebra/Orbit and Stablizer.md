#Definition #Algebra

> [!definition]
> Let $G \curvearrowright M$ be a [[Group Action|group action]] and $x\in M$. Then: 
> 1. $[x]=Gx:=\{ a\circ x:a\in G \}\subseteq M$ is called the ***orbit*** of $x$.
> 2. $\text{St}_{G}(x):=\{ a\in G:a\circ x =x \}$ is the ***stabilizer group*** of $x$ in $G$.
> 3. $M / G:= \{  Gx : x\in M \}$ is a set of orbits in $M$.

- **Related Definition**: For $a\in G$: $$^aM=\{ x\in M:a\circ x=x \}$$ i.e. the elements that are conserved by $a$.
---
> [!lemma] Theorem 1
> It holds that:
> 1. for all $x\in M$: $\text{St}_{G}(x)\leq G$
> 2. $M=\bigcup_{N\in M / G}^{}N$ is a disjoint union.
> 3. for all $x\in M$ and $a\in G$, $\text{St}_{G}(a\circ x)=a \text{St}_{G}(x)a^{-1}$.
> 4. for all $x\in M$, $[G:\text{St}_{G}(x)]=|Gx|$

> [!proof]-
> Let's prove them!
> 1. Let $a,b\in \text{St}_{G}(x)$, i.e. $a\circ x = x = b \circ x$. Then, $$(ab^{-1})\circ x = (a  b^{-1})\circ (b \circ  x) = a \circ  x = x$$ Therefore, $ab^{-1}\in \text{St}_{G}(x)$.
> 2. Let $Gx,Gx'\in M/G$ and $y\in Gx \cap Gx'$. Then, there exists $a,a'\in G$ s.t. $a\circ x=y = a'\circ x'$. Then, $x=(a^{-1}a')\circ x'\in Gx'$ and $x'=(a'^{-1}a)\circ x\in Gx$. Therefore, $Gx=Gx'$.
> 3. If $b\in \text{St}_{G}(x)$, then $(aba^{-1})\circ (a\circ x)=(ab)\circ x=a\circ(b\circ x) = a\circ x$. Therefore, $a \text{St}_{G}(x)a^{-1}\leq \text{St}_{G}(a\circ x)$. Conversely, let $c\in \text{St}_{G}(a\circ x)$. Then, $c\circ(a\circ x)=a\circ x$ and $$(a^{-1}ca)\circ x=(a^{-1}a)\circ  x=x$$and $a^{-1}ca\in \text{St}_{G}(x)$, i.e. $c \in a \text{St}_{G}(x)a^{-1}$ and as $c$ was arbitrary, $\text{St}_{G}(a\circ x)\leq a \text{St}_{G}(x)a^{-1}$.
> 4. Let $x\in M$ and $a\circ x,b \circ x\in Gx$. Then, $a\circ x = b\circ x$ if and only if $( b^{-1}a)\circ x=x$, which is equivalent to $b^{-1}a\in \text{St}_{G}(x)$ then $a \text{St}_{G}(x)=b \text{St}_{G}(x)$. Then, $a\circ x \neq b\circ x$ if and only if $a \text{St}_{G}(x)\neq b \text{St}_{G}(x)$. Therefore, $[G: \text{St}_{G}(x)]=|Gx|$.
---

> [!lemma] Lemma 2 (Burnside)
> Let $G \curvearrowright M$ be a group action. Then, $$\left| M / G \right|=\frac{1}{\left| G \right| }\sum_{a\in G}^{}\left| ^a{M} \right|  $$

> [!proof]-
> It holds that: $$\sum_{a\in G}^{}\left| ^aM \right| =\sum_{a\in G}^{}\left| \{ x\in M:a\circ x=x \} \right| =\sum_{x\in M}^{}\left| \{ a\in G: a\circ x=x\} \right| =\sum_{x\in M}^{}\left| \text{St}_{G}(x) \right|$$Further, if $Y\in M / G$ and for any $y\in Y$ then:$$\left| Y \right| =\left| G y \right| =[G:\text{St}_{G}(y)]= \frac{|G|}{|\text{St}_{G}(y)|}$$ Therefore, 
> $$\sum_{x\in M}^{}\left| \text{St}_{G}(x) \right|=\sum_{Y\in M/ G}^{}\sum_{y\in Y}^{}\left| \text{St}_{G}(y) \right| =\sum_{Y\in M / G}^{}\left| Y \right| \cdot \left| \text{St}_{G}(y) \right| =\sum_{Y \in M / G}^{}|G|=\left| M / G \right| \cdot \left|  G \right| $$
---
##### Example
> [!example]
 How many essentially different 3-colorings of a cube are there? (i.e. that the colorings are different w.r.t. rotation)
> 
> We will consider a group action $G \curvearrowright M$ where $G=C$ and $M$ is the set of colorings of a cube. Then, we have:
> 1. Type A rotation: axis through midpoints of opposing surfaces
> 2. Type B rotation: axis through midpoints of opposing edges
> 3. Type C rotation: axis through two opposing vertices
>    
> Then, 
> $$\begin{array}{c|c|c|c}\text{axis}&\text{rotation} & \text{number}  & |^aM|\\ \hline e&-&1&3^6\\A&\pm \frac{\pi}{2}&6&3^3\\A&\pi & 3 & 3^4\\B&\pi&6&3^3\\C& \pm \frac{2\pi}{3}&8&3^2\end{array}$$
> Therefore, as $|G|=24$. It follows that from Proposition Orbit.2:
> $$\left| M / G \right| = \frac{1}{24}(3^6+6\cdot 3^3+3\cdot 3^4+6\cdot 3^3+8\cdot 3^2)=57$$

---
