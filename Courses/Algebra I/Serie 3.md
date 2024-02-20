#Series #Algebra

##### Problem 20
Let $aN$ be the generator of $G / N$. Then, for every $x\in G$, the coset $x N=a^iN$ for some $i$ and as $e\in N$, $x=a^iz$ for some $z\in N$. It follows that for any two elements $x,y\in G$:
$$xy = a^iza^jz'=a^{i+j}zz' =a^{i+j}z'z =a^jz'a^iz=yx$$
as $z,z'\in Z(G)$ and commute with every group element. Therefore, $xy=yx$ for any $x,y\in G$ and the group is abelian. 

---
##### Problem 21
1. We will show the two conditions. Firstly, for all $gH \in G / H$, $egH = gH$. Secondly, for all $a,b\in G$ and $gH\in G / H$, $$(ab)\circ  gH=(abg)H=a((bg)H)=a\circ (b\circ gH)$$
2. Let $g,a\in G$ s.t. $a\circ gH = agH \in GgH$. Then, $$agH=\underbrace{ ag\hat{g}^{-1} }_{ \in G }\hat{g}H\in G \hat{g}H$$for any $\hat{g}\in G$. Therefore, this operation has only one orbit.
3. For all $gH\in G / H$, we have that $[G:\text{St}_{G}(gH)]=|Gx|=|G|$. Therefore, from Lagrange, we have $|\text{St}_{G}(gH)|=1$, i.e. $\text{St}_{G}(gH)=\{ e \}$, for all $gH\in G/ H$.
---
##### Problem 22
For $(a,b)\in\mathbb{R}^2$, the orbit $\mathbb{R}^*(a,b):=\{ (ga,b/g):g\in \mathbb{R}^* \}=\{ (c,d)\in \mathbb{R}^2:cd=ab \}$. The stabilizer of $(a,b)$ is then $\text{St}_{G}(a,b)=\{ g\in \mathbb{R}^*: ga=a\land b / g=b\}=\{ 1 \}$.

---
##### Problem 23
Let $N=Gy$ for some $y\in M$ and $f(Gy)=:x$. Then, $x\in Gy$ and there exists $a\in G$ s.t. $x = a\circ y$. We will show that $Gx=Gy$. For $z=b \circ x\in Gx$, we have $z = b \circ (a \circ y)=(ba)\circ y\in Gy$. Similarly, for $z=b\circ y\in Gy$, we have $z=b \circ y = (ba^{-1}a)\circ y=(ba^{-1})\circ(a\circ y)=(ba^{-1})\circ x\in Gx$. Therefore, $Gf(N)=Gx=Gy=N$. Now, as $M$ is a disjoint union $\bigcup_{N\in M / G}^{}N$, we have that: $$|M|=\sum_{N\in M / G}^{}|N|=\sum_{N\in M / G}^{}|Gf(N)|=\sum_{N\in M / G}^{}[G:\text{St}_{G}(f(N))]$$

---
##### Problem 24
We will show that $*$ meets the two conditions. Firstly, for all $f\in \mathcal{ F}(M)$, $$(e * f)(x)=f(e^{-1}\circ x)=f(e\circ x)=f(x)$$ for all $x\in M$. Secondly, for all $a,b\in G$ and $f\in \mathcal{ F}(M)$, $$((ab)*f)(x)=f((b^{-1}a^{-1})\circ  x)=f(b^{-1}\circ (a^{-1}\circ x))=(b* f)(a^{-1}\circ x)=(a * (b * f))(x) $$for all $x\in M$. Therefore, $*$ is a group operation. 

For the fixed points, $f$ is a fixed point if for all $g\in G$, $g*f=f$, i.e. for all $x\in M$: $$f( g^{-1}\circ x)=f(x)$$This holds if $f$ is a constant function. Therefore, the fixed points are constant functions.

---