#Series #Algebra-I 
##### Problem 6
1. Let $t:=\text{lcm}(k,\text{ord}(g))/k$. From the definition, $t$ is the smallest number s.t. $\text{ord}(g)|kt$ . However, we also have that for any $n$:
    
    $$ g^n=e\iff \text{ord}(g)|n $$
    
    Therefore, $t$ is the smallest number s.t. $g^{kt}=e$. It follows that $\text{ord}(g^k)=t$.
    
2. Let $\text{org}(g)=m$ and $\text{org}(h)=n$, s.t. $\gcd(m,n)=1$. Let $x$ be s.t. $(gh)^x = e$. Then, we have:
    
    - $e=(gh)^{xm}=h^{xm}$ and $n|xm$ and $n|x$.
    - $e=(gh)^{xn}=g^{xn}$ and $m|xn$ and $m|x$.
    
    Combining these two, we have $mn|x$ and $\text{ord}(gh)$ is smallest such $x$, therefore, $\text{ord}(gh)=mn$.
    

    
3. Consider $S_3$. More specifically,
    
    $$ \sigma:\begin{cases}1\mapsto 2\\2\mapsto 1\\3\mapsto 3\end{cases}\quad \text{and}\quad\tau:\begin{cases}1\mapsto 2\\2\mapsto 3\\3\mapsto 1\end{cases} $$
    
    Then, $\text{ord}(\sigma) = 2$ and $\text{ord}(\tau)=3$ but $\text{ord}(\tau\circ \sigma)=2$.
    

---

### Problem 7

Assume $\gcd(m,n)=1$. Then, we can define the bijection $\varphi:C_{n\cdot m}\to C_m\times C_n$ as follows:

- $\varphi(c^{k})=\braket{a^{k\mod m},b^{k\mod n}}$ for $k\in\mathbb{Z}_{nm}$

Then, let’s show that $\varphi$ is injective. For $k,k'$:

$$ \begin{aligned}\varphi(r^k)=\varphi(r^{k'})&\Longrightarrow (k\mod m,k\mod n)=(k'\mod m,k'\mod n)\\&\Longrightarrow(k-k')\mod m = 0\land (k-k')\mod n=0\\&\Longrightarrow (k-k')\mod mn = 0&|\gcd(m,n)=1\\&\Longrightarrow c^k=c^{k'}\end{aligned} $$

Further, as $|C_{nm}|=|C_m\times C_n|$, $\varphi$ is surjective.

Finally, we have that

$$ \begin{aligned}\varphi(c^{k}c^{k'})&=\varphi(c^{k+k'})\\&=(a^{k+k'\mod m},b^{k+k'\mod n})\\&=(a^{k\mod m},b^{k\mod n})\cdot (a^{k'\mod m},b^{k'\mod n})\\&=\varphi(c^k)\varphi(c^{k'})\end{aligned} $$

Now assume that $\gcd(m,n)>1$. Then, $k:=\text{lcm}(m,n)<mn$. Notice that for any element $g\in C_m,h\in C_n$:

- $(g,h)^k=(g^k,h^k)=(e,e)$. Therefore, every element of $C_m\times C_n$ has an order $\le c$.
- However, $C_{mn}$ has an element whose order is $mn>c$.

Therefore, the two groups cannot be isomorphic.

---

### Problem 8

Let $G$ be a group of order 4. Then, for any element $a\in G$, we have that $\text{ord}(g)|4$. If $a$ is non-neutral, then $\text{ord}(a)\ne 1$ therefore, $\text{ord}(a)\in\{2,4\}$.

We will consider the following two cases.

1. $G$ has a non-neutral element $a$ with $\text{ord}(a)=4$. Then, $G$ is a cyclic group with $a$ as the generator. This is isomorphic to $C_4$.
    
2. Every non-neutral element $a\in G$ has $\text{ord}(a)=2$. Then, we have the following table:
    
    $$ \begin{array}{c|c} &e&a&b&c\\ \hline e&e&a&b&c\\a&a&e&c&b \\b&b&c&e&a\\ c&c&b&a&e \end{array} $$
    
    As every group is cancellative, each row and column should contain all elements. This proves that there is only one way to set up the multiplication table and this is isomorphic to $C_2\times C_2$.
    

---

### Problem 9

1. Let $H$ be a subgroup of $G=C_n=\{e,a,a^2,...,a^{n-1}\}$. If $H=\{e\}$, then it is isomorphic to $C_1$ and is cyclic. Therefore, assume that $H\ne \{e\}$. Then, there is at least one $a^i\in H$ where $i\in\{1,...,n-1\}$. Let $m=\min\{i\in\{1,...,n-1\}:a^i\in H\}$.
    
    We will now show that for any $a^k\in H$ for $k\in\{0,...,n-1\}$, $m|k$. Assume that $k=qm+r$ where $0< r<m$. Then, $a^r\in H$ and this is a contradiction as $r<m$. This proves that $H\le \langle a^m\rangle$ and therefore $H=\langle a^m\rangle$.
    
2. For any $H\le G$, we know that $H$ is also cyclic. Let $g\in G$ be the generator of $H$. Then, $\text{ord}(g)=|H|$. Therefore, $|H|\in\{k\in \N:k|m\}$.
    
    For any $k\in\N$ s.t. $k|m$, we will define the group $H_k:=\{g\in G:g^k=e\}$. Then, $H_k\le G$, because for $x,y\in H_k$, $(xy^{-1})^k=x^ky^{-k}=e$.
    
    Firstly, for surjectivity, let $h\in H_k$. Then, $h=a^p$ for some $0\le p<m$ and as $h^k=a^{pk}=e$, it holds that $pk=mt$ for some $t$. As $0\le p<m$, we have that $0\le t<k$ and therefore $|H|\le k$. Similarly, we have for all $0\le t<k$, $(a^{mt/k})^k=a^{mt}=e$. Therefore, $|H_k|= k$.
    
    Now, we show injectivity. We will show that any subgroup $H\le G$ with order $k$ will be equal to $H_k$. As $H$ is also cyclic, $H=\braket{a^p}$ for some $0\le p<n$ s.t. $\text{ord}(a^p)=k$. Therefore, $a^p\in H_k$ and $H\le H_k$. Similarly, As $|H|=|H_k|$, we have that $H=H_k$.
    
    This proves that the mapping is well-defined and bijective.
    

---

### Problem 10

1. Let $G$ be a group of order $p$. Then, for any element $a\in G$, we have that $\text{ord}(g)|p$. For all non-neutral elements $a$, we have that $\text{ord}(a)=p$. Therefore, $G$ is a cyclic group $C_p$ with $a$ as the generator. (In fact, every non-neutral element is the generator)
    
    
2. Let $H$ be the only proper non-trivial subgroup of $G$. Then, there exists $x\in G\backslash H$. Consider the subgroup $\braket{x}$. As $\langle x\rangle \ne H$ and $x\ne e$, we have that $\langle x\rangle =G$ and $G\cong C_n$ where $n=\text{ord}(x)$. As the number of subgroups of a cyclic group equals the number of divisors, $n$ has 3 divisors. This is only the case if $n=p^2$ for some prime $p$.
    

---

### Problem 11

Assume that $(H_1\cup H_2)\le G$. Further, we assume that $H_1\not\le H_2$, i.e. there exists $x\in H_1\backslash H_2$. Then, for any $h\in H_2$, $xh^{-1}\in (H_1\cup H_2)$ but as $xh^{-1}\notin H_2$, $xh^{-1}\in H_1$. Therefore, $hx^{-1}\in H_1$ and consequently, $h\in H_1$. This shows that $H_2\le H_1$.

Conversely, assume that $H_1\le H_2$. Then, $H_1\cup H_2=H_2\le G$.

---

### Problem 12

Let $H\le (\mathbb{Z},+)$. If $H=\{0\}$, then $H$ is $0\mathbb{Z}$. We will now show that for $H\ne \{0\}$, $H$ is in the form $n\mathbb{Z}$ where $n$ is the smallest positive integer in $H$.

For $h\in n\mathbb{Z}$, we can express $h=nk$. Then, as $n\in H$, $h=nk\in H$. Conversely, assume that $h\in H$ and $h\notin n\mathbb{Z}$. This means that $h=nk+r$ for some $k$ where $0<r<n$. As $nk+r\in H$, we also have that $r\in H$. However this is a contradiction as $n$ is the smallest positive integer in $H$. Therefore, $H$ is in the form $n\mathbb{Z}$.

---