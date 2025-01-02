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

- **Related definition**: A chain complex $\mathcal{C}$ is a ***chain subcomplex*** of a chain complex $\mathcal{D}$, if:
	1. $C_{i}\leq D_{i}$ for all $i\in\mathbb{Z}$ and:
	2. $\partial^C=\partial^D|_{C_{i}}$ for all $i\in \mathbb{Z}$.
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
> Let $0\to \mathcal{A}\xrightarrow{i}\mathcal{B}\xrightarrow{j} \mathcal{C}\to 0$ be a SES of chain complexes. Then, 
> 1. there exists $\partial_{*}:H_{p}(\mathcal{C})\to H_{p-1}(\mathcal{A})$ for all $p\in \mathbb{Z}$ s.t.:
> $$\cdots\to H_{p+1}(\mathcal{C})\xrightarrow{\partial_{*}}H_{p}(\mathcal{A})\xrightarrow{i_{*}}H_{p}(\mathcal{B})\xrightarrow{j_{*}}H_{p}(\mathcal{C})\xrightarrow{\partial_{*}}H_{p-1}(\mathcal{A})\to\cdots$$is an [[exact sequence]].

^7f660e

> [!proof]-
> Consider the following diagram. We define $\partial_{*}$ as follows:
> $$\begin{CD}0 @>>> A_{p}@>i>>B_{p}@>j>>C_{p}@>>> 0
  \\& @V\partial VV@V\partial VV@V\partial VV\\0 @>>> A_{p-1}@>>i> B_{p-1}@>>j>C_{p-1}@>>> 0\end{CD}$$ 
> 
> 1. Let $c\in Z_{p}(\mathcal{C})$. Then, as $j$ is surjective, there exists $b\in B_{p}$ with $j(b)=c$. Then, we have that: $$j(\partial b)=\partial(j(b))=\partial(c)=0$$However, as $\text{ker}(j)=\text{im}(i)$ and $i$ is injective, there exists a unique $a\in A_{p-1}$ with $i(a)=\partial b$. Further, we have that: $$i(\partial a)=\partial(i(a))=\partial(\partial b)=0$$By injectivity, $\partial a=0$ and $a\in Z_{p-1}(\mathcal{A})$. Hence, we can define $\partial_{*}([c])=[a]$.  
> 2. We now show that $\partial_{*}$ is well-defined. First, we show that for a fixed $c$, it doesn't depend on the choice of $b$. Let $b'\in B_{p}$ with $j(b')=c$. Further, let $a'\in A_{p-1}$ be the unique element s.t. $i(a')=\partial b'$. Then, $j(b-b')=c-c=0$ and $b-b'\in \text{ker}(j)=\text{im}(i)$. Hence, there exists $a_{0}\in A_{p}$ with $i(a_{0})=b-b'$. Now, $$i(\partial a_{0})=\partial(i(a_{0}))=\partial b-\partial b'=i(a)-i(a')=i(a-a')$$Hence, by injectivity of $i$, $a-a'=\partial a_{0}\in B_{p-1}(\mathcal{A})$ and $[a]=[a']$.
>    
>    Now, let $[c]=[c']\in H_{p}(\mathcal{C})$. Then, $c-c'\in B_{p}(\mathcal{C})$ and there exists $c''\in C_{p+1}$ with $c'=c+\partial c''$. Choose $b$ with $j(b)=c$ and $b''$ with $j(b'')=c''$. Set $b':=b+\partial b''$. Then, $$j(b')=j(b+\partial b'')=c+\partial(j(b''))=c+\partial c''=c'$$By choosing $a'\in A_{p-1}$ with $i(a')=\partial b'$, we have that $$i(a')=\partial b'=\partial b+\partial \partial b''=i(a)$$By injectivity of $i$, we have that $a'=a$. This proves the claim.
> 3. We show that $\partial_{*}$ is a homomorphism. Let $c_{1},c_{2}\in C_{p}$ be cycles. Let $b_{1},b_{2}\in B_{p}$ with $j(b_{i})=c_{i}$ and $a_{1},a_{2}$ with $i(a_{i})=\partial b_{i}$. 
>    
>    For $[c_{1}]+[c_{2}]=[c_{1}+c_{2}]$, we choose $c_{1}+c_{2}$ as the cycle and we have that $j(b_{1}+b_{2})=c_{1}+c_{2}$. Then, $$i(a_{1}+a_{2})=i(a_{1})+i(a_{2})=\partial b_{1}+\partial b_{2}=\partial(b_{1}+b_{2})$$Hence, $$\partial_{*}([c_{1}]+[c_{2}])=[a_{1}+a_{2}]=[a_{1}]+[a_{2}]=\partial_{*}([c_{1}])+\partial_{*}([c_{2}])$$which proves the claim.
> 4. Now, we show the exactness of the sequence. 
> 	1. **Claim 1**: $j_{*}\circ i_{*}=0$: We have that: $j_{*}\circ  i_{*}=(j \circ  i)_{*}=0_{*}=0$.
> 	2. **Claim 2**: $\partial_{*}\circ j_{*}=0$.
> 	   Let $\beta\in H_{p}(\mathcal{B})$. Let $b\in B_{p}$ be a cycle with $\beta=[b]$. Then, we have that $\partial_{*}(j_{*}(\beta))=\partial_{*}([j(b)])$ and we can choose $c:=j(b)$ and $a\in A_{p-1}$ with $i(a)=\partial b=0$. Hence, $a=0$ and $\partial_{*}\circ j_{*}=0$.
> 	3. **Claim 3**: $i_{*}\circ \partial_{*}=0$.
> 	   Let $c\in C_{p}$ be a cycle. Then, $i_{*}(\partial_{*}([c]))=[i(a)]$ where $a\in A_{p-1}$ with $i(a)=\partial b$ and $b\in B_{p}$ with $j(b)=c$. Hence, $i_{*}(\partial_{*}([c]))=[i(a)]=[\partial b]=0$ as $\partial b\in B_{p-1}(\mathcal{B})$. 
> 	4. **Claim 4**: $\text{ker}(j_{*})\subseteq \text{im}(i_{*})$.
> 	   Let $b\in B_{p}$ be a cycle with $j_{*}([b])=0$. In other words, $j(b)\in B_{p}(\mathcal{C})$ and there exists $c\in C_{p+1}$ with $j(b)=\partial c$. Now, pick $b'\in B_{p+1}$ with $j(b')=c$, which exists as $j$ is surjective. 
> 	   
> 	   Now, $j(b-\partial b')=j(b)-\partial(j(b'))=\partial c-\partial c=0$. Hence, $b-\partial b'\in \text{ker}(j)$ and there exists $a\in A_{p}$ with $i(a)=b-\partial b'$. Notice that: $$i(\partial a)=\partial(i(a))=\partial b-\partial \partial b'=\partial b=0$$Hence, by injectivity, $\partial a=0$ and $i_{*}([a])=[b-\partial b']=[b]$.
> 	5. **Claim 5**: $\text{ker}(i_{*})\subseteq \text{im}(\partial_{*})$.
> 	   Let $a\in A_{p}$ be a cycle with $i_{*}([a])=0$. In other words, $i(a)\in B_{p}(\mathcal{B})$ and there exists $b\in B_{p+1}$ with $i(a)=\partial b$. First, note that $j(b)$ is a cycle. Indeed, $$\partial (j(b))=j(\partial b)=j(i(b))=0$$
> 	   Therefore, we have that: $\partial_{*}([j(b)])=[a]$.
> 	6. **Claim 6**: $\text{ker}(\partial_{*})\subseteq \text{im}(j_{*})$
> 	   Let $c\in C_{p}$ be a cycle with $\partial_{*}([c])=0$. Choose $b\in B_{p}$ with $j(b)=c$ and $a\in A_{p-1}$ with $i(a)=\partial b$. Then, we have that $a\in B_{p-1}(\mathcal{A})$ and there exists $a'\in A_{p}$ with $a=\partial a'$. Now, we have: $$\partial i(a')=i(\partial a')=i(a)=\partial b$$Hence, $\partial(b-i(a'))=0$ and $b-i(a')$ is a cycle. Further, we have: $$j(b-i(a'))=j(b)=c$$It follows that $j_{*}([b-i(a')])=[c]$.

^6537e1

---
> [!lemma] Theorem 4 (Commutativity of Long Exact Sequences)
> Let $0\to \mathcal{A}\xrightarrow{i}\mathcal{B}\xrightarrow{j} \mathcal{C}\to 0$ and $0\to \mathcal{A}'\xrightarrow{i'}\mathcal{B}'\xrightarrow{j'} \mathcal{C}'\to 0$ be two SES's of chain complexes.
> 1. Let $f:\mathcal{A}\to \mathcal{A}',g:\mathcal{B}\to \mathcal{B}',h:\mathcal{C}\to \mathcal{C}'$ be chain maps s.t. $$\begin{CD}0 @>>> \mathcal{A}@>i>>\mathcal{B}@>j>>\mathcal{C}@>>> 0
  \\& @Vf VV@Vg VV@Vh VV\\0 @>>> \mathcal{A}'@>>i'> \mathcal{B}'@>>j'>\mathcal{C}'@>>> 0\end{CD}$$ commutes. Then, 
>  $$\begin{CD}
  \cdots @>>> H_{p}(\mathcal{A}) @>i_{*}>> H_{p}(\mathcal{B}) @>j_{*}>> H_{p}(\mathcal{C}) @>\partial_{*}>> H_{p-1}(\mathcal{A}) @>>>\cdots\\
  &@Vf_{*}VV@Vg_{*}VV@Vh_{*}VV@Vf_{*}VV
  \\ \cdots @>>> H_{p}(\mathcal{A}') @>>i'_{*}> H_{p}(\mathcal{B}') @>>j'_{*}> H_{p}(\mathcal{C}) @>>\partial_{*}> H_{p-1}(\mathcal{A}) @>>>\cdots
  \end{CD}$$
  commutes.

^fed84b

> [!proof]-
> We have that:
> 1. The first square commutes as by Proposition 2.2: $$i'_{*}\circ  f_{*}=(i' \circ  f)_{*}=(g \circ  i)_{*}=g_{*}\circ  i_{*}$$ 
> 2. The second square commutes as by Proposition 2.2: $$j'_{*}\circ  g_{*}=(j' \circ  g)_{*}=(h \circ  j)_{*}=h_{*}\circ  j_{*}$$ 
> 3. For the last square, let $c\in C_{p}$ be a cycle. Then, $\partial_{*}([c])=[a]$ where $a\in A_{p-1}$ and $i(a)=\partial b$ where $b\in B_{p}$ with $j(b)=c$. Then, $$i'(f(a))=g(i(a))=g(\partial b)=\partial (g(b))$$Hence, $$j'(g(b))=h(j(b))=h(c)\in Z_{p}(\mathcal{C}')$$Therefore, $\partial_{*}(h_{*}([c]))=\partial_{*}([h(c)])=[f(a)]=f_{*}([a])=f_{*}(\partial_{*}([c]))$, which proves the statement.

^267869

---
> [!lemma] Theorem 5 (Quotient Chain Complex)
> Let $\mathcal{D}$ be a chain complex and $\mathcal{C}$ a chain subcomplex of $\mathcal{D}$. Then, for: $$\partial: D_{p} / C_{p}\to D_{p-1} / C_{p-1},\quad [d]\mapsto[\partial^D(d)]$$we have that: 
> 1. $\mathcal{D} / \mathcal{C}:=(\{ D_{i} / C_{i} \}_{i\in \mathbb{Z}},\partial)$ is a chain complex, called the ***quotient chain complex***.
> 2. $0\to \mathcal{C}\xrightarrow{i} \mathcal{D}\xrightarrow{j} \mathcal{D} / \mathcal{C}\to0$ is a [[Exact Sequence|SES]] for inclusion $i$ and projection $j$. 

> [!proof]+
> We have that: 
> 1. $\partial$ is well-defined as if $d-d'\in C_{p}$, then $\partial^D(d)-\partial^D(d')=\partial^D(d-d')\in C_{p-1}$. Further, we have that for any $d\in D_{p}$, $$\partial(\partial([d]))=\partial([\partial^D(d)]=[\partial^D(\partial^D(d))]=0$$
> 2. We show that $i,j$ are chain maps. For $c\in C_{p}$, 
> 	$$i(\partial^C(c))=\partial^C(c)=\partial^D(c)=\partial^D(i(c))$$
> 	For $d\in D_{p}$, $$j(\partial^D(d))=[\partial^D(d)]=\partial([d])=\partial(j(d))$$
