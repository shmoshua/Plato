#Definition #Algebra #AlgebraicTopology 

> [!definition]
> A [[Exact Sequence|short exact sequence (SES)]] of abelian groups  $0\to A\xrightarrow{i} B\xrightarrow{j} C\to 0$ is ***split*** if: 
> 1. there exists a [[Group Homomorphism|group isomorphism]] $\tau:B\to A\oplus C$ s.t. the following diagram commutes:$$\begin{CD}0 @>>> A@>i>> B@>j>> C @>>> 0\\&@V\text{id}VV @V\tau VV@V\text{id}VV\\0 @>>> A@>>i_{A}> A\oplus C@>>\text{pr}> C @>>> 0  \end{CD}$$where $i_{A}(a) = (a,c)$ and $\text{pr}(a,c)=c$.

^350e24

---
##### Properties
> [!lemma] Proposition 1
> Let $0\to A\xrightarrow{i} B\xrightarrow{j} C\to 0$ be an SES of abelian groups. Then, TFAE:
> 1. the sequence is split.
> 2. there exists a homomorphism $e:B\to B$ with $e^2 = e$ s.t. $\text{ker}(e)=\text{im}(i)=\text{ker}(j)$.
> 3. there exists a homomorphism $s:C\to B$ with $j\circ s = \text{id}$. (right inverse)
> 4. there exists a homomorphism $u:B\to A$ with $u \circ i = \text{id}$. (left inverse)

^edefd6

> [!proof]-
> We have that:
> 1. (1=>2): We define $e:B\to B,b\mapsto \tau ^{-1}(i_{C}(j(b)))$. We have that: $$e\circ  e=\tau ^{-1}\circ  i_{C}\circ  j\circ \tau ^{-1}\circ  i_{C}\circ  j=\tau ^{-1}\circ  i_{C}\circ  \text{pr} \circ  i_{C}\circ  j=\tau ^{-1}\circ  i_{C}\circ  \circ  j=e$$Further, $b\in \text{ker}(e)$ if and only if $i_{C}(j(b))=(0,0)$ and $j(b)=0$. Therefore, $\text{ker}(e)=\text{ker}(j)$.
> 2. (2=>1): Let $b\in B$. Note that, $b-e(b)\in \text{im}(i)$. Indeed, $$e(b-e(b))=e(b)-e(b)=0$$Hence, $b-e(b)\in \text{ker}(e)=\text{im}(i)$. Hence, there exists a unique $a\in A$ with $i(a)=b-e(b)$ and we define $$\tau:B\to A\oplus C,\quad b\mapsto (a,j(b))$$We need to show that $\tau$ is an isomorphism.
> 	1. Let $b,b'\in B$. Then, $$i(a+a')=i(a)+i(a')=b-e(b)+b'-e(b')=(b+b')-e(b+b')$$Hence, $\tau(b+b')=(a+a',j(b)+j(b'))=\tau(b)+\tau(b')$.
> 	2. $\tau$ is invertible. Let $(a,c)\in A\oplus C$. As $j$ is surjective, there exists $b\in B$ with $j(b)=c$. Then, we let $\rho:A\oplus C\to B,(a,c)\mapsto i(a)+e(b)$. Now,$$\rho(\tau(b))=\rho(a,j(b))=i(a)+e(b)=b-e(b)+e(b)=b$$and we also have that $e(i(a))=0$ and therefore, $i(a)=i(a)-e(i(a))$. Further, $i(0)=e(b)-e(e(b))=0$ and $j(e(b))=j(e(b)+b-b)=j(b)-j(b-e(b))=j(b)=c$. Hence,  $$\tau(\rho(a,c))=\tau(i(a))+\tau(e(b))=(a,\underbrace{ j(i(a)) }_{ =0 })+(0,c)=(a,c)$$
> 	3. We have that for $a\in A$, $$\tau(i(a))=(a,j(i(a)))=(a,0)=i_{A}(a)$$and $\text{pr}(\tau(b))=j(b)$.
> 3. (3=>2): Let $e:=s \circ j$. Then, $e^{2}=s\circ j \circ s \circ j= s \circ j = e$ and for $b\in \ker(e)$, $$j(b)=j\circ s\circ  j(b)=j (e(b))=j(0)=0$$and $\text{ker}(j)\subseteq \text{ker}(e)$ by definition.
> 4. (1=>3): Let: $$s:C\to B,\quad c\mapsto \tau ^{-1}(i_{C}(c))$$ Then, $$j(s(c))=j(\tau ^{-1}(i_{C}(c)))=\text{pr}(i_{C}(c))=c$$
> 5. (4=>2): Let $e:= \text{id}_{} - i \circ u$. Then, $$e(e(b))=e(b-i(u(b)))=b-i(u(b))-i(u(b))+i(u(i(u(b))))=e(b)$$Now, let $b\in \text{ker}(e)$. Then, $b-i(u(b))=0$ and $b=i(u(b))$. Hence, $b\in \text{im}(i)$. Conversely, for $a\in A$, we have that: $$e(i(a))=i(a)-i(u(i(a)))=i(a)-i(a)=0$$
> 6. (1=>4): Let $u:B\to A$ be defined as $u(b)=\text{pr}_{A}(\tau(b))$. Then, $$u(i(a))=\text{pr}_{A}(\tau(i(a)))=\text{pr}_{A}(i_{A}(a))=a$$

^26d5e8

- **Remark**: This also holds for SES of chain complexes. Further, by [[Chain Complex|Proposition 1.3]] and [[Chain Complex|Theorem 6]], if the SES is split, we have that $H_{p}(\mathcal{B})\cong H_{p}(\mathcal{A})\oplus H_{p}(\mathcal{C})$. ^6a0784
---
> [!lemma] Proposition 2
> Let $0\to A\to B\xrightarrow{j} C \to 0$ be a SES of abelian groups. 
> 1. If $C$ is free abelian, then the sequence is split. 

^22ebc8

> [!proof]-
> Let $\{ c_{\alpha} \}_{\alpha\in I}$ be the basis for $C$. Then, we define $s:C\to B$ as follows. For each $\alpha\in I$, choose $b_{\alpha}\in j^{-1}(c_{\alpha})\subseteq B$ and let $s(c_{\alpha}):= b_{\alpha}$. We can then extend $s$ linearly. 
> 
> We have that $j\circ s(c_{\alpha})=j(b_{\alpha})=c_{\alpha}$. This proves the statement.

^63bc3a

- **Remark**: This doesn't necessarily hold for chain complexes. For topological spaces $(X,A)$, $H_{p}(X)\not\cong H_{p}(A)\oplus H_{p}(X,A)$ in general. ^4b7fbe
---
##### Examples
> [!h] Example 1
> $0 \to \mathbb{Z} \xrightarrow{\times2} \mathbb{Z}\xrightarrow{p} \mathbb{Z} / 2\mathbb{Z} \to 0$ is not split.

^784a07

> [!proof]-
> The only homomorphism $s:\mathbb{Z} / 2\mathbb{Z} \to \mathbb{Z}$ is the zero map, hence by proposition 1. 

^25dda7

---
 