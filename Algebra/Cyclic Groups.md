#Definition #Algebra 

> [!definition]
> The ***cyclic group*** of order $n\in \mathbb{N}^+$, denoted as $(C_{n},\cdot)$ is defined as: $$C_{n}:=\{ a^0,a^1,a^{2},\dots,a^{n-1} \}$$
> for some $a$ where $a^\ell a^m=a^{\ell+m \mod n}$. Then, $a^0$ is the neutral element. 
> 
> Further, the ***$\infty$-cyclic group*** is defined as $G = \braket{ x  }$ and $G \cong (\mathbb{Z},+)$

- $C_{n}$ is abelian for any $n$.
---
##### Propositions
> [!lemma] Proposition 1
> Subgroups of cyclic groups are cyclic.

>[!proof]-
>Let $H$ be a subgroup of $G=C_n=\{e,a,a^2,...,a^{n-1}\}$. If $H=\{e\}$, then it is isomorphic to $C_1$ and is cyclic. Therefore, assume that $H\ne \{e\}$. Then, there is at least one $a^i\in H$ where $i\in\{1,...,n-1\}$. Let $m=\min\{i\in\{1,...,n-1\}:a^i\in H\}$. We will now show that for any $a^k\in H$ for $k\in\{0,...,n-1\}$, $m|k$. Assume that $k=qm+r$ where $0< r<m$. Then, $a^r\in H$ and this is a contradiction as $r<m$. This proves that $H\le \langle a^m\rangle$ and therefore $H=\langle a^m\rangle$.
---
> [!lemma] Proposition 2
> For natural numbers $m,n \geq 1$, we have that: $$C_{n}\times C_{m}\cong C_{mn}$$ if and only if $\gcd(m,n)=1$.

>[!proof]-
>Assume $\gcd(m,n)=1$. Then, we can define the bijection $\varphi:C_{n\cdot m}\to C_m\times C_n$ as follows:
$$\varphi(c^{k})=\braket{a^{k\mod m},b^{k\mod n}}$$ for $k\in \mathbb{Z}_{nm}$. Then, let’s show that $\varphi$ is injective. For $k,k'$:$$ \begin{aligned}\varphi(r^k)=\varphi(r^{k'})&\Longrightarrow (k\mod m,k\mod n)=(k'\mod m,k'\mod n)\\&\Longrightarrow(k-k')\mod m = 0\land (k-k')\mod n=0\\&\Longrightarrow (k-k')\mod mn = 0&|\gcd(m,n)=1\\&\Longrightarrow c^k=c^{k'}\end{aligned} $$Further, as $|C_{nm}|=|C_m\times C_n|$, $\varphi$ is surjective. Finally, we have that$$ \begin{aligned}\varphi(c^{k}c^{k'})&=\varphi(c^{k+k'})\\&=(a^{k+k'\mod m},b^{k+k'\mod n})\\&=(a^{k\mod m},b^{k\mod n})\cdot (a^{k'\mod m},b^{k'\mod n})\\&=\varphi(c^k)\varphi(c^{k'})\end{aligned} $$ Now assume that $\gcd(m,n)>1$. Then, $k:=\text{lcm}(m,n)<mn$. Notice that for any element $g\in C_m,h\in C_n$:
> - $(g,h)^k=(g^k,h^k)=(e,e)$. Therefore, every element of $C_m\times C_n$ has an order $\le k$.
> - However, $C_{mn}$ has an element whose order is $mn>k$. 
> 
> Therefore, the two groups cannot be isomorphic.
---
> [!lemma] Lemma 3
> For $C_{m}$, we can define a bijective map: $$\begin{align}\{ H:H \leq G \}&\to \{ k\in \mathbb{N}:k |m\}\\H\quad \quad \ &\mapsto \quad \quad \ |H|\end{align}$$

>[!proof]-
>For any $H\le G$, we know that $H$ is also cyclic. Let $g\in G$ be the generator of $H$. Then, $\text{ord}(g)=|H|$. Therefore, $|H|\in\{k\in \mathbb{N}:k|m\}$. For any $k\in\mathbb{N}$ s.t. $k|m$, we will define the group $H_k:=\{g\in G:g^k=e\}$. Then, $H_k\le G$, because for $x,y\in H_k$, $(xy^{-1})^k=x^ky^{-k}=e$.
> 
> Firstly, for surjectivity, let $h\in H_k$. Then, $h=a^p$ for some $0\le p<m$ and as $h^k=a^{pk}=e$, it holds that $pk=mt$ for some $t$. As $0\le p<m$, we have that $0\le t<k$ and therefore $|H|\le k$. Similarly, we have for all $0\le t<k$, $(a^{mt/k})^k=a^{mt}=e$. Therefore, $|H_k|= k$.
> 
> Now, we show injectivity. We will show that any subgroup $H\le G$ with order $k$ will be equal to $H_k$. As $H$ is also cyclic, $H=\braket{a^p}$ for some $0\le p<n$ s.t. $\text{ord}(a^p)=k$. Therefore, $a^p\in H_k$ and $H\le H_k$. Similarly, As $|H|=|H_k|$, we have that $H=H_k$. 
> 
> This proves that the mapping is well-defined and bijective.
---