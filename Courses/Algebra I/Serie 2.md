#Series #Algebra-I 
##### Problem 13

1. From last week, we know that:
    
    $$ \text{ord}(x)=\text{ord}(g^{120})=\frac{\text{lcm}(120,12\cdot 21)}{120}=\frac{12\cdot 210}{120}=21=n $$

    
2. We have:
    
    - $z:=g^{10}$. Then, $\text{ord}(z)=126$ and therefore, $\braket{ z  }\neq C_{mn}$. But, $z^m=g^{120}=x$
    - $y:=g^{31}$. Then, $\text{ord}(y)=252$ and therefore, $\braket{ y  }= C_{mn}$. But, $y^m=g^{372}=x$

---

##### Problem 14

1. We will show as follows:
    
    - Reflexivity: For all $g\in G$, $g^{-1}g=e\in H$. Therefore, $g\sim g$.
    - Symmetry: For all $g,h\in G$ s.t. $g\sim h$, then $h^{-1}g\in H$ and therefore $g^{-1}h=(h^{-1}g)^{-1}\in H$. Therefore, $h\sim g$.
    - Transitivity: For all $g,h,p\in G$ s.t. $g\sim h$ and $h\sim p$, we have $h^{-1}g\in H$ and $p^{-1}h\in H$. As $H$ is a group, we have $p^{-1}g=p^{-1}hh^{-1}g\in H$. Therefore, $g\sim p$.
    
2. Using lemma 3.6, we have:
    
    $$ [x] =\{g\in G:g^{-1}x\in H\}=\{g\in G:x\sim g\}=\{g\in G:gH=xH\}=xH $$
    
    Therefore, the equivalence classes are exactly the left cosets of $H$.
    
3. For all $x\in G$ and $h\in H$, we have that $h\in [e]$ as $e^{-1}h\in H$. Therefore, $hx^{-1}\in[x^{-1}]$ and consequently, $$(x^{-1})^{-1}hx^{-1}=xhx^{-1}\in H$$ This proves that. $H\unlhd G$.

---

##### Problem 15

1. For any element $a^k\in \braket{ a  }$, we have that $a^ka=aa^k$, therefore, $a^k\in Z_{G}(a)$. As $\braket{ a  }$ is a group, $\braket{ a  } \leq Z_{G}(a)$.
2. Let $H\leq G$. For $h\in Z_{H}(a)$, we have that $ah=ha$ and $h\in H$. Therefore, $h\in Z_{G}(a)\cap H$. Similarly, for any $h\in Z_{G}(a)\cap H$, we have $h\in H$ and $ah=ha$, therefore, $h\in Z_{H}(a)$.

-----

##### Problem 16
1. We will show the following:
	- (i) => (ii): Assume that $U\leq G$. For any element $uu'\in UU$ for $u,u'\in U$, as $U$ is a group, $uu'\in U$. Secondly, for any $u^{-1}\in U^{-1}$, we have that $u\in U$ and therefore, $u^{-1}=eu^{-1}\in U$. Therefore, $U^{-1}\subseteq U$.
	- (ii) => (iii): Assume that $UU\subseteq U$ and $U^{-1}\subseteq U$. For any element $v\in UU^{-1}$, we have $v=u_{1}u_{2}^{-1}$ for some $u_{1}\in U$ and $u_{2}\in U^{-1}$. Then, we also have that $u_{2}\in U$. Therefore, $v\in UU$ and subsequently in $U$. Therefore, $UU^{-1}\subseteq U$.
	- (iii) => (i): Assume that $UU^{-1}\subseteq U$. Then, for any $u_{1},u_{2}\in U$, we have that $u_{1}u_{2}^{-1}\in UU^{-1}$ and consequently, in $U$. This proves that $U\leq G$.
2. Assume that $UV\leq G$. Then, for any $uv\in UV$, we have that $v^{-1}u^{-1}\in UV$, i.e. there exists $\hat{u}\in U$ and $\hat{v}\in V$ s.t. $v^{-1}u^{-1}=\hat{u}\hat{v}$. Then, $uv=(v^{-1}u^{-1})^{-1}=(\hat{u}\hat{v})^{-1}=\hat{v}^{-1}\hat{u}^{-1}\in VU$. On the other hand, for any $vu\in VU$, as $v\in UV$ and $u\in UV$, we have that $vu\in UV$. Therefore, $UV=VU$.
	Conversely, now assume that $UV=VU$. Then, for any $uv,\hat{u}\hat{v}\in UV$, $(uv)(\hat{u}\hat{v})^{-1}=uv\hat{v}^{-1}\hat{u}^{-1}$. As $v\hat{v}^{-1}\hat{u}^{-1}\in VU=UV$, $v\hat{v}^{-1}\hat{u}^{-1}=u^*v^*$ for $u^*\in U$ and $v^*\in V$. Then, 
	$$(uv)(\hat{u}\hat{v})^{-1}=uv\hat{v}^{-1}\hat{u}^{-1}=\underbrace{ uu^*}_{\in U  }v^*\in UV$$ 
	This proves that $UV$ is a subgroup.
3. Assume that $U$ is finite and $UU\subseteq U$. Then, for any $x\in U$, the map $\varphi:U\to U, u\mapsto ux$ is injective due to cancellativity, and surjective as well as $U$ is finite. Therefore, as $x\in U$, we also have $e\in U$ where $e=\varphi^{-1}(x)$. Then, we also have that $x^{-1}=\varphi^{-1}(e)\in U$. It follows that for any $x,y\in U$, $y^{-1}\in U$ and $x y^{-1}\in UU \subseteq U$.
---
##### Problem 17
1. As $(\mathbb{C}^*,\cdot)$ is abelian, we just need to show that $\mathbb U \leq \mathbb{C}^*$. For any $z,z'\in \mathbb U$, we have: $$|z'z^{-1}|=|z'| | z^{-1}|=\frac{|z'|}{|z|}=1$$
	Therefore, $\mathbb U \leq \mathbb{C}^*$ and $\mathbb U \unlhd \mathbb{C}^*$.
2. Let's consider the quotient set $\mathbb{C}^* / \mathbb U=\{z \mathbb U : z\in \mathbb{C}^* \}$. For any $z\in \mathbb{C}^*$, $z\mathbb U$ is the circle with radius $|z|$.  Therefore, 
	$$ \mathbb{C}^* / \mathbb U=\{z \mathbb U : z\in \mathbb{C}^* \}=\{x\mathbb U : x\in \mathbb{R}^+ \}\cong \mathbb{R}^+$$
---
##### Problem 18
We can define $D_{4}$ as follows:
$$D_{4}:=\braket{ \rho , \sigma |\rho^4=e,\sigma^{2}=e,\sigma\rho=\rho^{3}\sigma}=\{ e,\rho,\rho^{2},\rho^{3},\sigma,\sigma\rho,\sigma\rho^{2},\sigma\rho^{3} \} $$
where $\rho$ is a rotation by $\frac{\pi}{2}$  and $\sigma$ is a reflection. As $|D_{4}|=8$, the possible orders of the subgroups are: $\{ 1,2,4,8 \}$.
- Subgroups of order 1: $\{ e \}$.
- Subgroups of order 2: $\{ e,\rho^{2} \},\{ e,\sigma \},\{ e,\sigma \rho \},\{ e,\sigma \rho^{2} \},\{ e,\sigma \rho^{3} \}$
- Subgroups isomorphic to $C_{2}\times C_{2}$: $\{ e,\rho^{2},\sigma,\sigma\rho^{2} \}, \{ e,\rho^{2},\sigma\rho,\sigma\rho^{3} \}$
- Subgroups isomorphic to $C_{4}$: $\{ e,\rho,\rho^{2},\rho^{3} \}$
- Subgroup of order 8: $D_{4}$.

The inclusion relations are as follows:
- For every $H \leq D _{4}$,$\{ e \} \subseteq H$  and $H\subseteq D_{4}$
- $\{ e,\rho^{2} \},\{ e,\sigma \},\{ e,\sigma\rho^{2} \}\subseteq \{ e,\rho^{2},\sigma,\sigma\rho^{2} \}$
- $\{ e,\rho^{2} \},\{ e,\sigma\rho \},\{ e,\sigma\rho^{3} \}\subseteq \{ e,\rho^{2},\sigma\rho,\sigma\rho^{3} \}$
- $\{ e,\rho^{2} \}\subseteq \{ e,\rho,\rho^{2},\rho^{3}\}$

For normal divisors, we have:
- Trivial normal divisors: $\{ e \},D_{4}$
- Subgroups of order $4$: because $|G:H|=2$.
- $\{ e,\rho^{2} \}$ as the intersection of two normal divisors is a normal divisor.

For $k\in\{ 0,1,2,3 \}$, $\{ e, \sigma\rho^k\}$ is not a normal divisor, as:
$$\rho\sigma\rho^k\rho^{-1}=\rho\sigma\rho^k\rho^3=\sigma\rho^{k+2}\notin\{ e,\sigma\rho^k \}$$
Therefore, these are all the normal divisors.

---
##### Problem 19
Let $T$ be the regular tetrahedron symmetry group (without reflections).
1. For a regular tetrahedron, we have $4$ possible top point, and once we have fixed the top, we have 3 rotations of the bottom triangle. Therefore, $|T|=12$. 
2. We will look at two rotations where we fix one point and rotate the base triangle of that doesn't contain the points by $\frac{2\pi}{3}$. Let $\sigma_{1}$ be the rotation where the top point (A in the diagram) is fixed and let $\sigma_{2}$ be the one where the front point (C) is fixed. Then, $\sigma_{2} \circ \sigma_{1}$ moves A to the where D is, but $\sigma_{1} \circ \sigma_{2}$ moves A to where C is.
    ![[ARVST.jpeg|150]]
	Therefore, $T$ is not abelian.
3. As $|T|=12$, the possible order of the subgroups are: $\{ 1,2,3,4,6,12 \}$. 
	- Subgroups of order 1: $\{ e \}$.
	- Subgroups of order 2: as they are isomorphic to $C_{2}$, the only possibilities are subgroups that are each generated by a rotation around a line through the midpoints of each pair of opposing edges by $\pi$. For example, in the diagram above, AC and BD are opposing and DA and BC are opposing. (The two edges aren't adjacent to a common point.) As there are three pairs of such opposing edges, there are three subgroups of this kind.
	- Subgroups of order 3: as they are isomorphic to $C_{3}$, these are subgroups generated by the rotation of any triangle (similar to the rotations in part 2.). As there are 4 triangles with each 2 rotations, there are 8 different subgroups.
	- Subgroups of order 4: as all elements in $T$ has order $\leq 3$, we can't have a subgroup isomorphic to $C_{4}$. Consider $C_{2} \times C_{2}$. Notice that the subgroup generated by any two of the rotations by $\pi$ is the subgroup that contains all rotations by $\pi$. Therefore, we have 1 subgroup of order 4.
	- Subgroup of order 6: with the same reasoning as above, we can only have $S_{3}$ as the subgroup. As $S_{3}$ has three elements of order 2, the subgroup must have them too. However, we know that then the subgroup of order 4 we've found would be a subgroup of this subgroup of order 6. As this is not possible, there is no subgroup of order 6.
	- Subgroup of order 12: $T$.
4. The subgroups of order 2 cannot be normal divisors, as for any order-3 rotations $xn x^{-1}\notin N$. Same goes for subgroups of order 3, as there is an element $x\in T$ that will change the one point that is fixed for that subgroup. The subgroup of order 4 is normal, as for $x\in T$, and an order-2 rotation $n$, $xnx^{-1}$ is another order-2 rotation: $$ xnx^{-1}xnx^{-1}=e$$Therefore, the subgroup of order 4 is a normal divisor.
----