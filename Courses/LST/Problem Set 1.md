#Series #LST 

##### Exercise 1

1. We will show that $\text{Null}(\mathcal A)=\{u\in F^n|Au=\theta_m\}\subseteq F^n$ is a linear space: For all $u,v\in \text{Null}(\mathcal A)$ and all $a,b\in F$, we have:
    
    $$ A(au+bv)=aAu+bAv = a\theta _m+b\theta_m=(a+b)\theta_m=\theta_m $$
    
    Therefore, $\text{Null}(\mathcal A)$ is a subspace of $(F^n,F)$.
    
    Similarly, for $\text{Range}(\mathcal A)=\{v\in F^m|\exists u\in F^n:v=Au\}\subseteq F^m$, for any $v,v'\in \text{Range}(\mathcal A)$ and all $a,b\in F$, we have:
    
    $$ av+bv'=aAu+bAu'=A(au+bu') $$
    
    for some $u,u'\in F^n$. As $au+bu'\in F^n$, $av+bv'\in \text{Range}(\mathcal A)$.
    
    
    
1. We first show that $\text{Rank}(A)+\text{Nullity}(A)=n$. Let $B:=\{ b_{i} \}_{i=1}^n$ be the basis of $(F^n,F)$. Now, we define $C:=\{ c_{1},\dots,c_{k} \}$ as the greatest linearly independent subset of $\{ Ab_{i} \}_{i=1}^n$. W.l.o.g. we can assume that $C=\{Ab_{i}\}_{{i=1}}^{k}$, i.e. the linearly independent $k$ vectors are from the first $k$ vectors $b_{1},\dots,b_{k}$, and that $Ab_{k+1},\dots,Ab_{n}$ can be represented with vectors from $C$. Then, for $k < i \leq n$ the vector $Ab_{i}$ has a unique representation $\eta_{i}\in F^k$ with respect to $\{ c_{j} \}_{j=1}^k$.
 
	 First, we will show that $C$ is a basis for $\text{Range}(\mathcal{A})$. By definition, $C$ is linearly independent and for any $v\in F^m$, we have $u\in F^n$ s.t. $Au=v$.  Further, let $\xi\in F^n$ be the representation of $u$ w.r.t. $B$. It follows that:
	 $$v=Au=A\sum_{i=1}^{n}\xi_{i}b_{i}=\sum_{j=1}^{k}\xi_{j}c_{j}+\sum_{i=k+1}^{n}\xi_{i}\sum_{j=1}^{k}\eta_{i,j}c_{j}=\sum_{j=1}^{k}\left( \xi_{j}+\sum_{i=k+1}^{n}\xi_{i}\eta_{i,j} \right)c_{j}$$
	 Therefore, $C$ spans $\text{Range}(\mathcal{A})$ and is a basis. Consequently, $\text{Rank}(A)=k$.
 
	 Now consider the rest of the basis vectors. For $k<i\leq n$, let $b'_{i}:=b_{i}-\sum_{j=1}^{k}\eta_{i,j}b_{j}$. We will now show that $\{ b'_{i}\}_{i=k+1}^n$ forms a basis for the null space $\text{Null}(\mathcal{A})$. For any $b'_{i}$, we have:
	 $$
     Ab'_{i}=A\left( b_{i}-\sum_{j=1}^{k}\eta_{i,j}b_{j} \right)=Ab_{i}-\sum_{j=1}^{k}\eta_{i,j}c_{j}=Ab_{i}-Ab_{i}=\theta_{m}
    $$
	 Therefore, $\{ b'_{i}\}_{i=k+1}^n \subseteq \text{Null}(\mathcal{A})$. Now, if $b'_{n}$ wlog can be represented by $\{ b'_{i} \}_{i=k+1}^{n-1}$, then: 
	 $$b_{n}=b'_{n}+\sum_{j=1}^{k}\eta_{n,j}b_{j}=\sum_{i=k+1}^{n-1}a_{i}b'_{i}+\sum_{j=1}^{k}\eta_{n,j}b_{j}=\sum_{i=k+1}^{n-1}a_{i}\left( b_{i}+\sum_{j=1}^{k}\eta_{i,j}b_{j} \right)+\sum_{j=1}^{k}\eta_{n,j}b_{j}$$
	 which means $b_{n}$ could be represented by $\{ b_{i} \}_{i=1}^{n-1}$, contrary to our basis assumption. It follows that $\{ b'_{i}\}_{i=k+1}^n$ is linearly independent.
	 
 	 Assume $\text{dim}\text{ Null}(\mathcal{A})>n-k$. Then, there exists a non-zero vector $b\in \text{ Null}(\mathcal{A})$ s.t. that cannot be represented by vectors in $\{ b'_{i}\}_{i=k+1}^n$. Furthermore, $b$ cannot be represented by $b_{1},\dots,b_{k}$ as $Ab=\theta_{m}$ and $b$ is non-zero. Therefore, $b\in F^n$ cannot be represented by $\{ b_{1},\dots,b_{k},b'_{k+1},\dots,b'_{n} \}$ and further by $\{ b_{i} \}_{i=1}^n$. This is a contradiction and therefore, $N$ is the basis of $\text{Null}(\mathcal{A})$.
 
	 Finally, we have: $$\text{Rank}(A)+\text{Nullity}(A)=k+n-k=n$$
	 
	 To show that $0 \leq \text{Rank}(A)\leq\min\{ m,n \}$, we first know that $\text{Rank}(A)=|C|$. Therefore, $0 \leq \text{Rank}(A)\leq|B|=n$. We also have $\text{Rank}(A)\leq m$ as there cannot be more than $m$ linearly independent vectors in $F^m$. Therefore, $0\leq \text{Rank}(A) \leq \min\{ m,n \}$.
3. Firstly, as $\text{Null}(\mathcal{B})\subseteq \text{Null}(\mathcal{A}\circ\mathcal{B})$, we have $\text{Nullity}(B)\leq \text{Nullity}(AB)$. Let's define $\tilde{\mathcal{B}}:\text{Null}(\mathcal{A}\circ\mathcal{B})\to F^n$. Then, $\text{Null}(\mathcal{B})=\text{Null}(\tilde{\mathcal{B}})$. Since $\text{Range}(\tilde{\mathcal{B}})\subseteq \text{Null}(\mathcal{A})$, we have: $\text{dim Range}(\tilde{\mathcal{B}})\leq \text{dim Null}(\mathcal{A})$. All together,$$\text{Nullity}(AB)=\text{dim Range}(\tilde{\mathcal{B}})+\text{dim Null}(\tilde{\mathcal{B}})\leq \text{Nullity}(A)+\text{Nullity}(B)$$
    Then, from Rank-Nullity Theorem,$$p-\text{Rank}(AB)=\text{Nullity}(AB)\leq \text{Nullity}(A)+\text{Nullity}(B)=p-\text{Rank}(B)+m-\text{Rank}(A)$$ and $$\text{Rank}(A)+\text{Rank}(B)-m \leq \text{Rank}(AB)$$
    Now, let's show that $\text{Rank}(AB)\leq \min\{  \text{Rank}(A),\text{Rank}(B)\}$. We have that $\text{Range}(AB)\subseteq \text{Range}(A)$, as $\text{Range}(B)$ is a subspace of $F^n$ and therefore, $\text{Rank}(AB)\leq \text{Rank}(A)$. Also, as $\text{Nullity}(B)\leq \text{Nullity}(AB)$ from above, $$\text{Rank}(AB)=p-\text{Nullity}(AB)\leq p-\text{Nullity}(B)=\text{Rank}(B)$$
    Combining all together we get: $$\text{Rank}(A)+\text{Rank}(B)-m \leq \text{Rank}(AB)\leq\min\{ \text{Rank}(A),\text{Rank}(B) \}$$
    

---

##### Exercise 2

1. We define the basis as follows:
    
    $$ \mathcal B=\{(1,...,0),(\imath,...,0),(0,1,...,0),(0,\imath,...,0),...,(0,...,1),(0,...,\imath)\} $$
    
    Therefore, the dimension is $2n$.
    
2. We will first show the linear independence: Assume we have $\alpha,\beta\in \mathbb C$ s.t.
    
    $$ \alpha e^{ix}+\beta e^{-ix}=0 $$
    
    for all $x$. Then,
    
    $$ \alpha e^{ix}+\beta e^{-ix}=(\alpha+\beta)\cos x+(\alpha-\beta)i\sin x=0 $$
    
    if and only if:
    
    $$ \alpha+\beta = 0\land \alpha -\beta = 0 $$
    
    Therefore, $\alpha = \beta = 0$.
    
    Furthermore, for any $a,b\in\mathbb C$,
    
    $$ a\sin x+b\cos x = \frac{b-ai}{2}e^{ix}+\frac{b+ai}{2}e^{-ix} $$
    
    Therefore, $\{e^{ix},e^{-ix}\}$ is a basis.
    

    
3. Assume we have $p,q\in \mathbb Q$ s.t.
    
    $$ p+q\sqrt{2} = 0 $$
    
    We have that $q=0$ as if $q\ne 0$, then $q\sqrt{2}$ is irrational, therefore $p$ cannot be rational. If $q=0$, then $p=0$. This proves the independence.

---

##### Exercise 3

1. **Not linear**. Consider $\mathbf 0$, i.e. $\mathbf{0}(t)=0$ for any $t$. Then, for any $t\in \mathbb{R}:$
    
    $$ [H(2\cdot \mathbf 0)](t)=b\ne 2b=2\cdot [H(\mathbf 0)](t) $$
    
2. **Linear**. For all $u,u'\in\mathcal C(\mathbb{R})$ and $s,s'$ and $t\in \mathbb{R}$:
    
    $$ \begin{aligned} \ [H(su+s'u')](t)&=\int_0^te^{-\tau}(su(t-\tau)+s'u'(t-\tau))\text{d}\tau\\&=s\int_0^te^{-\tau}u(t-\tau)\text d\tau+s'\int_0^te^{-\tau}u'(t-\tau)\text{d}\tau\\&=s[H(u)](t)+s'[H(u')](t)\end{aligned} $$
    
3. **Linear**. For all $u,u'\in\mathcal C(\mathbb{R})$ and $s,s'$:
    
    $$ \begin{aligned}H(su+s'u')&=\int_0^1su(-t)+s'u'(-t)\text dt\\&=s\int_0^1u(-t)\text dt+s'\int_0^1u'(-t)\text dt\\&=sH(u)+s'H(u')\end{aligned} $$
    
4. **Linear**. For all $u,u'\in\mathcal C(\mathbb{R})$ and $s,s'$:
    
    $$ \begin{aligned}H(su+s'u')&=su(0)+s'u'(0)=sH(u)+s'H(u')\end{aligned} $$
    
5. **Linear**. For all $X,X'\in\mathbb C^{n,n}$ and $s,s'$:
    
    $$ \begin{aligned}H(sX+s'X')&=A(sX+s'X')+(sX+s'X')B\\&=sAX+s'AX'+sXB+s'X'B\\&=s(AX+XB)+s'(AX'+X'B)\\&=sH(X)+s'H(X')\end{aligned} $$
    

---

##### Exercise 4

For a vector $x\in V$, assume there are two representations $\xi,\xi'\in F^n$ with respect to $B$. Then,

$$ \sum_{i=1}^n(\xi_i-\xi'_i)v_i=\sum_{i=1}^n\xi_{i}v_i-\sum_{i=1}^{n}\xi'_{i}v_{i}=x-x=0 $$

But from linear independence, for all $i$,

$$ \xi_i-\xi_i'=0\Longrightarrow \xi_i=\xi'_i $$
Therefore, $\xi=\xi'$.

---

##### Exercise 5

1. We will show:
    
    - **Associativity**: for $A,B,C\in\mathbb{R}^{N,N}_{> 0}$ and all $0\leq i,j\leq N$:
        
        $$ [(A\star B)\star C]_{ij}=[A\star B]_{ij}\cdot C_{ij}=A_{ij}\cdot B_{ij}\cdot C_{ij}=A_{ij}\cdot [B\star C]_{ij}=[A\star (B\star C)]_{ij} $$
        
    - **Neutral element**: for $A\in \mathbb{R}^{N,N}_{> 0}$:
        
        $$ [A\star \mathbf 1]_{ij}=A_{ij}\quad \forall i,j\le N $$
        
        where $\mathbf{1}\in \mathbb{R}^{N,N}_{>0}$ is a constant matrix of $1$. Therefore, $A\star \mathbf 1=\mathbf{1}\star A=A$.
        
    - **Inverse element**: for $A\in \mathbb{R}^{N,N}_{> 0}$, we define $A^{-1}\in \mathbb{R}^{N,N}_{> 0}$ as:
        
        $$ [A^{-1}]_{ij}=A_{ij}^{-1}\quad \forall i,j\le N $$
        which exists as $A_{ij}>0$.
    - **Commutativity**: for $A,B\in\mathbb{R}^{N,N}_{> 0}$ and all $0\leq i,j\leq N$:
        
        $$[A\star B]_{ij}=A_{ij}\cdot B_{ij}=B_{ij}\cdot A_{ij}=[B \star A]_{ij}$$
    
    Therefore, $(\mathbb{R}^{N,N}_{>0},\star)$ is an Abelian group.
    
2. We have that:
    1. We need $T_{R}$ that transforms a representation of $u\in \mathcal{ U}$ in the standard basis into the given basis. As the given basis vectors are represented in the standard basis, we have that the inverse of $$\begin{bmatrix} \frac{1}{3}& \frac{2}{9} & \frac{7}{9}\\0&-\frac{1}{3}& -\frac{2}{3}\\0&0&-1\end{bmatrix}$$ will be $T_{R}$. Therefore, $$T_R=\begin{bmatrix} 3&2&1\\0&-3&2\\0&0&-1 \end{bmatrix} $$ On the other hand, $T_{L}$ needs to take a vector $v\in \mathcal{ V}$ in the given basis and output the representation in the standard basis. Therefore, $$T_L=\begin{bmatrix} 1&6&-1&1\\0&3&0&1\\0&0&-1&4\\0&0&0&3 \end{bmatrix}$$
    2. The matrix $A$ has a rref: $$\text{rref}(A)=\begin{bmatrix}1&0&0\\0&1&0\\0&0&1\\0&0&0\end{bmatrix}$$
        Therefore, $A$'s columns are linearly independent and the columns $B:=\left\{  \begin{bmatrix}-7\\ \frac{2}{3}\\ -8\\ -2\end{bmatrix}, \begin{bmatrix} \frac{4}{3}\\ -\frac{5}{9}\\ -\frac{16}{3}\\ -\frac{4}{3}\end{bmatrix} , \begin{bmatrix}-7\\1\\-3\\-1\end{bmatrix} \right\}$ form a basis of $\text{Range}(\mathcal{A})$.
      And we have: $\text{Range}(\mathcal{A})=\text{Span}(B)$ and $\text{Rank}(A)=3$. Therefore, we have $\text{Nullity}(A)=3-3=0$ and $\text{Null}(\mathcal{A})=\{ \theta_{\mathcal{U}} \}$. As rank and nullity are preserved by multiplication with invertible maps, we also have $\text{Rank}(\tilde{ A})=3$ and $\text{Nullity}(\tilde{A})=0$.
    

---