#Definition #Algebra 

> [!definition]
> Let $\{ C_{i} \}_{i\in \mathbb{Z}}$ be a [[graded abelian group]], i.e. a sequence of abelian groups. 
> 1. A ***chain complex*** is a pair of a graded abelian group $\{ C_{i} \}_{i\in \mathbb{Z}}$ and [[Group Homomorphism|group homomorphisms]] $\{ \partial:C_{i}\to C_{i-1} \}_{i\in \mathbb{Z}}$ s.t. $\partial^{2}=0$. 

^8f3281

- **Related definition**: For a chain complex $\mathcal{C}:=(\{ C_{i} \}_{i\in \mathbb{Z}},\partial)$, we have that: ^925675
	1. $Z_{i}(\mathcal{C}):=\text{ker}(\partial)$ for $\partial:C_{i}\to C_{i-1}$ are the ***cycles***.
	2. $B_{i}(\mathcal{C}):=\text{im}(\partial)$ for $\partial:C_{i+1}\to C_{i}$ are the ***boundaries***.
	3. $H_{i}(\mathcal{C}):=Z_{i}(\mathcal{C}) / B_{i}(\mathcal{C})$ is the ***homology*** of $\mathcal{C}$ in degree $i$, which is well-defined as $\partial^{2}=0$. 
- **Related definition**: For two chain complexes $\mathcal{A}:=(\{ A_{i} \}_{i},\partial^A)$ and $\mathcal{B}:=(\{ B_{i} \}_{i},\partial^B)$, a ***chain map*** $f:\mathcal{A}\to \mathcal{B}$ is a collection of group homomorphisms $f:A_{i}\to B_{i}$ for all $i\in \mathbb{Z}$ s.t. the following diagram commutes:
  $$\begin{CD}\cdots @>>> A_{i+1}@>\partial^A>>A_{i}@>\partial^A>>A_{i-1}@>>> \cdots
  \\& @VfVV@VfVV@VfVV\\\cdots @>>> B_{i+1}@>>\partial^B> B_{i}@>>\partial^B>B_{i-1}@>>> \cdots\end{CD}$$ 
  
  ^4afe22
  
- **Related definition**: Chain complexes $\mathcal{A},\mathcal{B},\mathcal{C}$ form a ***short exact sequence (SES)*** with chain maps $i:\mathcal{A}\to \mathcal{B}$ and $j:\mathcal{B}\to \mathcal{C}$, if $0\to A_{k}\xrightarrow{i}B_{k}\xrightarrow{j} C_{k}\to 0$ is a [[Exact Sequence|SES]] for all $k\in \mathbb{Z}$.
   ^4bd728
---
##### Properties
> [!lemma] Proposition 1
> Let $f:\mathcal{A}\to \mathcal{B}$ be a chain map. Then, for all $i\in \mathbb{Z}$:
> 1. $f(Z_{i}(\mathcal{A}))\subseteq Z_{i}(\mathcal{B})$
> 2. $f(B_{i}(\mathcal{A}))\subseteq B_{i}(\mathcal{B})$
> 3. $f_{*}:H_{i}(\mathcal{A})\to H_{i}(\mathcal{B}),[c]\mapsto[f(c)]$ is a group homomorphism.

^7f03b3

> [!proof]-
> We have that:
> 1. Let $c\in Z_{i}(\mathcal{A})$. Then, $\partial^A c=0$ and we have that $$\partial^B(f(c))=f(\partial^A(c))=f(0)=0$$
> 2. Let $c\in B_{i}(\mathcal{A})$. Then, there exists $c'\in C_{i+1}$ s.t. $\partial^A(c')=c$. Hence, $$\partial^B(f(c'))=f(\partial^A(c'))=f(c)$$
> 3. We have that $f_{*}$ is well-defined as if $c-d\in B_{i}(\mathcal{A})$, then $f(c)-f(d)\in B_{i}(\mathcal{B})$. Further, $f_{*}$ is a homomorphism as $f$ is. 

^eb9885

---
> [!lemma] Proposition 2
> Let $f:\mathcal{A}\to \mathcal{B}$ and $g:\mathcal{B}\to \mathcal{C}$ be chain maps. Then, 
> 1. $g \circ f$ is a chain map.
> 2. $(g\circ f)_{*}=g_{*}\circ f_{*}$
> 3. $\text{id}:\mathcal{A}\to \mathcal{A}$ is a chain map with $\text{id}_{*}=\text{id}_{H_{i}(\mathcal{A})}$.

^8cac80

> [!proof]-
> We have that:
> 1. $g\circ f$ is a homomorphism and we have that: $$\partial^C\circ  g \circ  f=g\circ  \partial^B \circ  f=g\circ f\circ  \partial^A$$
> 2. For a cycle $c\in Z_{i}(\mathcal{A})$, $$(g\circ f)_{*}([c])=[g(f(c))]=g_{*}([f(c)])=g_{*}(f_{*}([c]))$$
> 3. Obvious. 

^8e49fb

---
> [!lemma] Theorem 3 (Long Exact Sequence in Homology)
> Let $0\to A_{k}\xrightarrow{i}B_{k}\xrightarrow{j} C_{k}\to 0$ be a SES of chain complexes. Then, 
> $$\cdots\to H_{p+1}(\mathcal{C})\xrightarrow{\partial_{*}}H_{p}(\mathcal{A})\xrightarrow{i_{*}}H_{p}(\mathcal{B})\xrightarrow{j_{*}}H_{p}(\mathcal{C})\xrightarrow{\partial_{*}}H_{p-1}(\mathcal{A})\to\cdots$$is an [[exact sequence]] where 