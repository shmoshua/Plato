#Definition #Algebra-I 

> [!definition]
> The ***symmetry group***, also known as ***permutation group***, of degree $n\in \mathbb{N}$, denoted as $(S_{n},\circ)$ is defined as: $$S_{n}:=\{  \sigma :[n]\to [n]\ | \ \sigma \text{ is a bijection} \}$$
> The identity mapping $\iota$ is the neutral element. 
> 
> For a set $M$, we can also define a ***symmetric group*** $S(M)$ as the set of bijections $\varphi:M\to M$.
- **Remark**: $\left| S_{n} \right|=n!$
- **Related definition**: A permutation $\rho\in S_{n}$ is a ***$k$-cycle*** for $k\geq 1$, if there exists $i\in[n]$ s.t. 
	1. $k=\min\{ k'\geq 1:\rho^{k'}(i)=i \}$
	1. for all $j\in[n] \backslash\{ \rho^s(i):s\in \mathbb{N} \}$, it holds that $\rho(j)=j$.
	   
	Then, $\rho$ is also written as: $(i\ \rho(i)\ \rho^{2}(i) \ \dots\ \rho^{k-1}(i))$.
- **Related definition**: Two permutations $\rho,\sigma\in S_{n}$ are ***disjoint***, if for all $i\in[n]$:$$(\rho(i)\neq i \to\sigma(i)=i)\land(\sigma(i)\neq i \to \rho(i)=i)$$
---
##### Properties
> [!lemma] Theorem 1 (Cayley)
> Every group $G$ of order $n$ is isomorphic to a subgroup of $S_{n}$. 

> [!proof]-
> We can define a homomorphism $\varphi:G \to S(M)$ where $\varphi(a)(b)=ab$. Then, we have: $$\text{ker }\varphi=\{ a\in G:ab=b\quad \forall b\in G \}=\{ e \}$$Therefore, by the [[Group Homomorphism|first isomorphism theorem]], we have that: $$G\cong \text{Im}\ \varphi$$which proves the statement.
---
> [!lemma] Proposition 2
> Let $\pi\in S_{n}$, $i\in[n]$ and let $k$ be the smallest positive number, s.t. $$\pi^k(i)\in \{ i,\pi(i),\dots,\pi^{k-1}(i) \}$$Then, $\pi^k(i)=i$.

>[!proof]-
> Assume that $\pi^k(i)=\pi^\ell(i)$ where $1\leq \ell<k$. Then, as $\pi$ is a bijection, $\pi^{k-\ell}(i)=i$. However, this is a contradiction as $k$ is the smallest positive number. 
---
> [!lemma] Proposition 3
> If $\rho,\sigma\in S_{n}$ are disjoint, it holds that: 
> 1. $(\rho\sigma)^m=\rho^m\sigma^m$ for all $m\in \mathbb{N}$.
> 1. If $\rho$ is a $k$-cycle, then $\text{ord}(\rho)=k$.
> 2. If $\pi$ is a product of disjoint cycles of length $k_{1},\dots,k_{r}$, then $\text{ord}(\pi)=\text{lcm}(k_{1},\dots,k_{r})$

>[!proof]-
>We have: 
>  1. Let $\rho,\sigma\in S_{n}$ be disjoint permutations. We will show that $\rho$ and $\sigma$ commute. Assume there exists $i_{0}\in[n]$ s.t. $(\rho\sigma)(i_{0})\neq(\sigma\rho)(i_{0})$. Then, we can perform a case distinction:
> 	 - If $\sigma(i_{0})=i_{0}$, then:$$\sigma(i_{0})=i_{0}\implies\rho(i_{0})\neq\sigma\rho(i_{0})\implies\rho(\rho(i_{0}))=\rho(i_{0})\implies\rho(i_{0})=i_{0}$$Plugging this back, we get that: $(\rho\sigma)(i_{0})= i_{0}\neq i_{0}=(\sigma\rho)(i_{0})$.
> 	 - If $\sigma(i_{0})\neq i_{0}$, then: $$\rho(i_{0})=i_{0}\implies(\rho\sigma)(i_{0})\neq\sigma(i_{0})\implies\sigma(\sigma(i_{0}))=\sigma(i_{0})\implies\sigma(i_{0})=i_{0}$$
> 	 
> 	 Therefore, $\rho$ and $\sigma$ commute and it follows that $(\rho\sigma)^k=\sigma^k\rho^k$.
> 2. Let $\rho$ be a $k$-cycle in $S_{n}$ and $i$ be an element s.t. $\rho^k(i)=i$. Then,
> 	1. If $j\in \{ \rho^s(i):s\in \mathbb{N} \}$, then:$$\rho^k(j)=\rho^k(\rho^s(i))=\rho^s(\rho^k(i))=\rho^s(i)=j$$
> 	2. If $j\in [n] \backslash\{ \rho^s(i):s\in \mathbb{N} \}$, then $\rho(j)=j$ and $\rho^k(j)=j$.
> 
> 	Therefore, $\rho^k=\iota$ and $\text{ord}(\rho)=k$.
> 3. First, we show that if $\rho$ is disjoint with $\sigma_{1},\dots,\sigma_{s}$, $\rho$ is disjoint with the product $\sigma$ as well. We have that:
> 	- If $\rho(i)\neq i$, then for all $i\in[s]$, $\sigma_{i}(i)=i$ and $\sigma(i)=i$.
> 	- If $\sigma(i)\neq i$, then there exists $i\in[s]$ s.t. $\sigma_{i}(i)\neq i$. Therefore, $\rho(i)=i$.
> 
> 	Therefore, let $\pi=\rho_{1}\circ\dots \circ\rho_{r}$ where $\rho_{1,\dots,}\rho_{r}$ are pairwise disjoint cycles of length $k_{1},\dots,k_{r}$. Then, for any $j\in \mathbb{N}$: $\pi^j=\rho_{1}^j\circ \dots \circ \rho^j_{r}$. As they are all pairwise disjoint, we have that the smallest number $j$ that would make $\pi^j=\iota$ is $\text{ord}(\pi)=\text{lcm}(k_{1},\dots,k_{r})$.

---
> [!lemma] Proposition 4
> Every $\pi\in S_{n}$ can be written as a product of pairwise disjoint cycles called the ***cycle decomposition***.

>[!proof]+
>Let $\pi\in S_{n}$. Then, from Proposition 2, there exists for all $i\in[n]$ a smallest positive number $k_{i} \geq 1$ s.t. $\pi^{k_{i}}(i)=i$ and $\rho_{i}=(i,\pi(i),\dots,\pi^{k_{i}-1}(i))$ is a $k_{i}$-cycle. Let: $$Z_{i}:=\{ i,\pi(i),\dots,\pi^{k_{i}-1}(i) \}$$i.e. the set of numbers that appear in the cycle $\rho_{i}$. Then for every $i,j\in[n]$: $$Z_{i}=Z_{j}\lor Z_{i}\cap Z_{j}=\varnothing$$
>- If $Z_{1}=[n]$, then $\pi=\rho_{1}$. Otherwise, there exists $\ell\in[n]$ s.t. $\ell\in[n] \backslash Z_{1}$. Therefore, $Z_{1}\cap Z_{\ell}=\varnothing$. 
>- If $Z_{1}\cup Z_{\ell}=[n]$, then $\pi=\rho_{1}\rho _{\ell}$. Otherwise, there exists $s\in[n]$ s.t. $s\in[n] \backslash (Z_{1} \cup Z_{\ell})$. 
>
> After at most $n$ steps, we have that $\pi$ is a product of pairwise disjoint cycles.
---
> [!lemma] Proposition 5
> Let $\pi,\rho\in S_{n}$. Then, the cycle decomposition of $\rho \pi \rho ^{-1}$ can be written as the cycle decomposition of $\pi$, where $i$ is replaced with $\rho(i)$. 

> [!proof]-
> We consider $\rho \pi \rho^{-1}$ on the element $\rho(i)$. $$\rho \pi \rho ^{-1}(\rho(i))=\rho (\pi(i))$$Therefore, in the cycle decomposition of $\rho \pi \rho^{-1}$, we have that $\rho(i)\to \rho(\pi(i))$. Therefore, the cycle decomposition of $\pi$ and $\rho \pi \rho^{-1}$ have the same structure, besides that we can replace every $i$ in that of $\pi$ as $\rho(i)$.
---
> [!lemma] Lemma 6
> A $k$-cycle is [[Transpostion|even]] if and only if $k$ is odd.

> [!proof]-
> $$(i_{1},i_{2},\dots,i_{k})=(i_{1},i_{2})(i_{2},i_{3})\dots(i_{k-1},i_{k})$$Therefore, we have $k-1$ transpositions. 
---
> [!lemma] Proposition 7
> For any symmetry group $S_{n}$ for $n\geq 3$, 
> 1. $Z(S_{n})=\{ \iota \}$.
> 2. $\text{Inn}(S_{n})\cong S_{n}$

> [!proof]-
> We have:
> 1. Let $\sigma\in S_{n}$ s.t. $\sigma\neq \iota$. Then, there exists $x\in [n]$ s.t. $\sigma(x)=y\neq x$. Now, consider $\rho\in S_{n}$ s.t. $\rho(x)=x$ but $\rho(y)\neq y$. Then, $$(\rho\sigma)(x)=\rho(y)\neq y=\sigma(x)=(\sigma\rho)(x)$$Therefore, $\sigma\notin Z(S_{n})$.
> 2. $\text{Inn}(S_{n})\cong S_{n}/Z(S_{n})\cong S_{n}$
---

We defined transposition as 2-cycles. Then, any permutation can be written as a product of transpositions. Therefore, we can define $\text{sign}(\tau)$ as the parity of the number of transpositions in its write-up. Then, [[Alternating Group|alternating group]] $A_{n}$ is the group of permutations with $\text{sign}(\tau)=1$, i.e. the number of transpositions is even.

---
- $|S_{n}|=n!$. For $n>2$, we then have $|S_{n}|>n$. 
- $|S_{1}|=1$, which is the identity mapping $\text{id}:1\mapsto 1$. We also have $S_{1}\cong C_{1}$.
- $|S_{2}|=2$, the identity mapping and the swap, i.e. $\sigma(a)=3-a$. Every group with two elements is isomorphic to $C_{2}$, i.e. $S_{2}\cong C_{2}$.
- For $n>2$, $S_{n}$ is a non-abelian group.
---
##### Examples
- [[Cube Group]] $\cong S_{4}$
---
##### Examples
**Examples of Cyclic Notation**
- The 5 $k$-cycles of $S_{3}$ are: $(1\ 2\ 3), (3\ 2\ 1),(1\ 3), (1\ 2), (2\ 3)$.
- $(1\ 3)$ and $(2 \ 4)$ are two $2$-cycles of $S_{4}$. But $(1\ 3)(2\ 4)$ cannot be written as a cycle, i.e. the product of a cycle is not necessarily a cycle.
- $(1 \ 2)(1\ 3) = (1\ 3\ 2)$
  
**Examples of Cyclic Decomposition**
- Let: $$\begin{array}{cccccccc}&1&2&3&4&5&6&7\\ \pi:&\downarrow&\downarrow&\downarrow&\downarrow&\downarrow&\downarrow&\downarrow\\&3&7&2&5&6&4&1\end{array}$$Then, $\pi=(1\ 3\ 2\ 7)(4\ 5\ 6)$


---
