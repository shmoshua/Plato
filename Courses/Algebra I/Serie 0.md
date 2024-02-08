#Series #Algebra-I 
##### Problem 0
$$ \begin{aligned}(a\circ (b\circ c))\circ d&=((a\circ b)\circ c)\circ d=(a\circ b)\circ (c\circ d)\end{aligned} $$

---
##### Problem 1
We have that:
$$ x=a\star b\iff x|a\land x|b\land (\forall c\in A:c|a\land c|b\to c\le x) $$

1. **Commutativity**: let $x=a\star b$. Then, we also have:
    
    $$ x|b\land x|a\land (\forall c\in A:c|b\land c|a\to c\le x)\Longrightarrow x=b\star a $$
    
    Therefore, $a\star b=b\star a$.
    
2. **Associativity**: $a\star(b\star c)=(a\star b)\star c$
    
    - $a\star (b\star c)|(b\star c)$ and $(b\star c)|c$ → $a\star (b\star c)|c$
    - $a\star (b\star c)|a$ and $a\star (b\star c)|b$ → $a\star (b\star c)|(a\star b)$
    - Therefore, $a\star (b\star c)|((a\star b)\star c)$
    
3. $12$ is a neutral element: $\forall a\in A:12\star a = \gcd(a,12)=a$
4. For example, there is no element $a\in A$ s.t. $\gcd(1,a)=12$.

---

##### Problem 2

- Associativity: $(p\bullet q)\bullet r = (2pq)\bullet r=4pqr = p\bullet (2qr)=p\bullet (q\bullet r)$
- Identity element: $\forall q\in\mathbb Q^*$, $\frac{1}{2}\bullet q = 2\frac{1}{2}q=q$
- Inverse element $\forall q\in\mathbb Q^*$, let $q=\frac{n}{m}$ for $n,m\in\mathbb{N}^+$. Then, the inverse of $q$ is $\frac{m}{2n}$.
- Communtativity: $p\bullet q = 2pq=2qp=q\bullet p$

---

##### Problem 3

- Associativity:
    
    $$ \begin{aligned}((p_1,q_1)\bullet (p_2,q_2))\bullet (p_3,q_3) &=(p_1p_2-q_1q_2,p_1q_2+q_1p_2)\bullet (p_3,q_3)\\ &=((p_1p_2-q_1q_2)p_3-(p_1q_2+q_1p_2)q_3,(p_1p_2-q_1q_2)q_3+(p_1q_2+q_1p_2)p_3)\\ &=(p_1(p_2p_3-q_2q_3)-q_1(p_2q_3+q_2p_3),p_1(p_2q_3+q_2p_3)+q_1(p_2p_3-q_2q_3)) \\&=(p_1,q_1)\bullet (p_2p_3-q_2q_3,p_2q_3+q_2p_3) \\&=(p_1,q_1)\bullet ((p_2,q_2)\bullet (p_3,q_3)) \end{aligned} $$
    
- Identity element: $\forall (p,q)\in(\mathbb Q\times \mathbb Q)^*$:
    
    $$ (p,q)\bullet(1,0)=(p,q) $$
    
- Inverse element: $\forall (p,q)\in(\mathbb Q\times \mathbb Q)^*$:
    
    $$ (p,q)\bullet \left(\frac{p}{p^2+q^2},-\frac{q}{p^2+q^2}\right)=(1,0) $$
    
- Commutativity:
    
    $$ (p_1,q_1)\bullet (p_2,q_2)=(p_1p_2-q_1q_2,p_1q_2+q_1p_2)=(p_2p_1-q_2q_1,p_2q_1+q_2p_1)=(p_2,q_2)\bullet (p_1,q_1) $$
    

---

##### Problem 4

For $a,b\in G$

$$ \begin{aligned}a\circ b &= (a\circ e)\circ b \\&= (a\circ ((a\circ b)\circ (a\circ b))) \circ b \\&= ((a\circ (a\circ b))\circ (a\circ b)) \circ b \\&= (((a\circ a)\circ b)\circ (a\circ b)) \circ b \\&= ((e\circ b)\circ (a\circ b)) \circ b \\&= (b\circ (a\circ b)) \circ b \\&= b\circ ((a\circ b) \circ b) \\&= b\circ (a\circ (b\circ b)) \\&= b\circ (a\circ e) \\&= b\circ a \end{aligned} $$

---

##### Problem 5

1. Assume $G$ is not abelian, i.e. $\exists a,b\in G$ s.t. $ab\ne ba$. Then, neither $a$ nor $b$ are neutral elements. Further, as the neutral element is unique, $a$ and $b$ are not inverses. Therefore, the set $\{e,a,b,ab,ba\}$ has cardinality greater than 4, which is a contradiction.
2. $(\mathbb{Z}_4,+)$ and $(\{1,2,3,6\},\cdot)$.

---