#Definition #Algebra #AlgebraicTopology 

> [!definition]
> A [[Exact Sequence|short exact sequence (SES)]] of abelian groups  $0\to A\xrightarrow{i} B\xrightarrow{j} C\to 0$ is ***split*** if: 
> 1. there exists a [[Group Homomorphism|group isomorphism]] $\tau:B\to A\oplus C$ s.t. the following diagram commutes:$$\begin{CD}0 @>>> A@>i>> B@>j>> C @>>> 0\\&@V\text{id}VV @V\tau VV@V\text{id}VV\\0 @>>> A@>>i_{A}> A\oplus C@>>\text{pr}> C @>>> 0  \end{CD}$$where $i_{A}(a) = (a,c)$ and $\text{pr}(a,c)=c$.
---
##### Properties
> [!lemma] Proposition 1
> Let $0\to A\xrightarrow{i} B\xrightarrow{j} C\to 0$ be an SES of abelian groups. Then, TFAE:
> 1. the sequence is exact.
> 2. there exists a homomorphism $e:B\to B$ with $e^2 = e$ s.t. $\text{ker}(e)=\text{im}(i)=\text{ker}(j)$.
> 3. there exists a homomorphism $s:C\to B$ with $j\circ s = \text{id}$. (right inverse)
> 4. there exists a homomorphism $u:B\to A$ with $u \circ i = \text{id}$. (left inverse)

> [!proof]+
> We have that:
> 1. (1=>2): We define $e:B\to B,b\mapsto \tau ^{-1}(i_{C}(j(b)))$. We have that: $$e\circ  e=\tau ^{-1}\circ  i_{C}\circ  j\circ \tau ^{-1}\circ  i_{C}\circ  j=\tau ^{-1}\circ  i_{C}\circ  j\circ \tau ^{-1}\circ  i_{C}\circ  j$$

