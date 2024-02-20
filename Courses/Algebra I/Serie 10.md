#Series #Algebra

##### Exercise 53
1. Let $A,B\in \text{Mat}(n,\mathfrak{a})$. Then, 
	1. $(A+B)_{ij}=\underbrace{ A_{ij} }_{ \in \mathfrak{a} }+\underbrace{ B_{ij} }_{ \in \mathfrak{a} }\in \mathfrak{a}$. Therefore, $A+B\in \text{Mat}(n,\mathfrak{a})$.
	2. for $S\in \text{Mat}(n,R)$,$$(SA)_{ij}=\sum_{k=1}^{n}\underbrace{ s_{ik}a_{kj} }_{ \in \mathfrak{a} }\in \mathfrak{a},\quad (AS)_{ij}=\sum_{k=1}^{n}a_{ik}s_{kj}\in \mathfrak{a}$$
	   
	This shows that $\text{Mat}(n,\mathfrak{a})$ is an ideal of $\text{Mat}(n,R)$.
2. Let $\mathfrak{M}$ be an ideal in $\text{Mat}(n,R)$. We define: $$S=\{ a\in R:a\text{ appears in }\mathfrak{M} \}$$We will now show that $\mathfrak{M}=\text{Mat}(n,(S))$. From 1, we have that $\text{Mat}(n,(S))$ is an ideal. Further, by construction, $\mathfrak{M}\subseteq \text{Mat}(n,(S))$. We will now show that $\mathfrak{M}\supseteq \text{Mat}(n,(S))$. Let $P_{ij}$ denote a $(n\times n)$ matrix that has zero everywhere but $1$ at $(i,j)$. Firstly, for any $s\in S$, there exists a matrix $M\in \mathfrak{M}$ s.t. $M_{ij}=s$ for some $i,j\in[n]$.  Then, 
	- $sP_{ij}=P_{ii}MP_{jj}\in\mathfrak{M}$ and
	- $sP_{ij}\in \mathfrak{M}$ for any $i,j\in[n]$ by permutation matrices and
	- $t P_{ij}\in\mathfrak{M}$ for any $i,j\in[n]$ and $t\in(S)$.
	  
	Therefore, for any $A\in \text{Mat}(n,(S))$, $$A=\sum_{i,j=1}^{n}\underbrace{ a_{ij}P_{ij} }_{ \in\mathfrak{M} }\in\mathfrak{M}$$
	This shows that $\mathfrak{M}=\text{Mat}(n,(S))$.
3. Let us define the homomorphism: $$\begin{array}{cccc} {\varphi:}&{\text{Mat}(n,R)}&\to&{\text{Mat}(n, R / \mathfrak{a})}\\&{[a_{ij}]_{i,j=1}^n} &\mapsto & {[a_{ij}+\mathfrak{a}]_{i,j=1}^n} \end{array}{}$$It is easy to see that this defines a surjective ring homomorphism. Further, $$\text{ker}(\varphi)=\{ A\in \text{Mat}(n,R): a_{ij}+\mathfrak{a}=\mathfrak{a}\ \forall i,j\}=\{ A\in \text{Mat}(n,R): a_{ij}\in\mathfrak{a}\ \forall i,j\}=\text{Mat}(n,\mathfrak{a})$$Therefore, $$\text{Mat}(n,R) / \text{Mat}(n,\mathfrak{a})\cong \text{Mat}(n, R / \mathfrak{a})$$
---
##### Exercise 54
As $\mathbb{F}^{*}$ is finite and abelian, there exists not necessarily disjoint primes $p_{1},\dots,p_{r}$ and positive integers $n_{1},\dots,n_{r}$ s.t. $$\mathbb{F}^{*}\cong C_{p_{1}^{n_{1}}}\times\dots \times C_{p_{r}^{n_{r}}}$$Now, let $n:=\text{lcm}(p_{1}^{n_{1}},\dots,p_{r}^{n_{r}})$. Then, $n\leq p_{1}^{n_{1}}\dots p_{r}^{n_{r}}$. Now consider $a\in \mathbb{F}^{*}$. As $p_{i}^{n_{i}}|n$, $a^n=1$ for any $a\in \mathbb{F}^{*}$. However, as there are at most $n$ roots to the polynomial $x^n-1$,$$\left| \mathbb{F}^* \right|=p_{1}^{n_{1}}\dots p_{r}^{n_{r}}\leq n $$ and $n=p_{1}^{n_{1}}\dots p_{r}^{n_{r}}$. This shows that $p_{1}^{n_{1}},\dots,p_{r}^{n_{r}}$ are coprime and it follows that $\mathbb{F}^{*}\cong C_{n}$.

---
##### Exercise 55
Let $\mathbb{Z} / m\mathbb{Z}$ be field. Then, every non-zero element $a$ has a multiplicative inverse, and therefore is a unit. In other words, for every $0<a<m$, $\gcd(a,m)=1$. This shows that $m$ is prime. 

Conversely, if $m$ is prime, $\left| (\mathbb{Z} / m\mathbb{Z})^{*} \right|=\varphi(m)=m-1$. As $0$ cannot be in the unit group, every other element is. This shows that every non-zero element has a multiplicative inverse. Hence, $\mathbb{Z} / m\mathbb{Z}$ is a field.


---
##### Exercise 56
1. For $a,b\in \varphi ^{-1}[\mathfrak{a}]$, we have $\varphi(a),\varphi(b)\in \mathfrak{a}$. Therefore, $$\varphi(a+b)=\varphi(a)+\varphi(b)\in\mathfrak{a}$$and $a+b\in \varphi ^{-1}[\mathfrak{a}]$. Further, for any $r\in R$: $$\varphi(ra)=\varphi(r)\varphi(a)\in \mathfrak{a},\quad \varphi(ar)=\varphi(a)\varphi(r)\in\mathfrak{a}$$Therefore, $ra,ar\in \varphi^{-1}[\mathfrak{a}]$.
2. For $a,b\in \varphi[\mathfrak{a}]$, we have $c,d\in \mathfrak{a}$ s.t. $\varphi(c)=a$ and $\varphi(d)=b$. Then, $$a+b=\varphi(c)+\varphi(d)=\varphi(\underbrace{ c+d }_{ \in\mathfrak{a} })\in\varphi[\mathfrak{a}]$$
	Further, for $s\in S$, as $\varphi$ is surjective, there exists $r\in R$ s.t. $\varphi(r)=s$ and: $$sa=\varphi(r)\varphi(c)=\varphi(rc)\in\varphi[\mathfrak{a}],\quad as=\varphi(c)\varphi(r)=\varphi(cr)\in\varphi[\mathfrak{a}]$$
---
##### Exercise 57
1. Let $r_{1}+\mathfrak{a}=r_{2}+\mathfrak{a}$. Then, $r_{1}-r_{2}\in \mathfrak{a}$ and: $$\varphi(r_{1})-\varphi(r_{2})=\varphi(r_{1}-r_{2})\in \varphi[\mathfrak{a}]$$ Therefore, $\varphi(r_{1})+\varphi[\mathfrak{a}]=\varphi(r_{2})+\varphi[\mathfrak{a}]$.
2. We show that: $$\psi((r_{1}+\mathfrak{a})+(r_{2}+\mathfrak{a}))=\psi((r_{1}+r_{2})+\mathfrak{a})=\varphi(r_{1}+r_{2})+\varphi[\mathfrak{a}]=\underbrace{ \varphi(r_{1})+\varphi[\mathfrak{a}] }_{ \psi(r_{1}+\mathfrak{a}) }+\underbrace{ \varphi(r_{2})+\varphi[\mathfrak{a}] }_{ \psi(r_{2}+\mathfrak{a}) }$$
	$$\psi((r_{1}+\mathfrak{a})(r_{2}+\mathfrak{a}))=\psi(r_{1}r_{2}+\mathfrak{a})=\varphi(r_{1}r_{2})+\varphi[\mathfrak{a}]=\underbrace{ (\varphi(r_{1})+\varphi[\mathfrak{a}]) }_{ \psi(r_{1}+\mathfrak{a}) }\underbrace{ (\varphi(r_{2})+\varphi[\mathfrak{a}]) }_{ \psi(r_{2}+\mathfrak{a}) }$$
	$$\psi(1_{R}+\mathfrak{a})=\varphi(1_{R})+\varphi[\mathfrak{a}]=1_{S}+\varphi [\mathfrak{a}]$$
	Therefore, $\psi$ is a ring homomorphism.
3. Let $s+\varphi[\mathfrak{a}]\in S / \varphi[\mathfrak{a}]$. As $\varphi$ is surjective, there exists $r\in R$ s.t. $\varphi(r)=s$. Then, $$\psi(r+\mathfrak{a})=\varphi(r)+\varphi[\mathfrak{a}]=s+\varphi[\mathfrak{a}]$$This shows the surjectivity. For injectivity, $$\begin{align}\text{ker}(\psi)&=\{ r+\mathfrak{a}\in R / \mathfrak{a}:\varphi(r)+\varphi[\mathfrak{a}]=\varphi[\mathfrak{a}] \}\\&=\{ r+\mathfrak{a}\in R / \mathfrak{a}:\varphi(r)\in \varphi[\mathfrak{a}] \}\\&=\{ r+\mathfrak{a}\in R / \mathfrak{a}:r\in \mathfrak{a} \}\\&=\mathfrak{a}\end{align}$$This proves the statement.
---