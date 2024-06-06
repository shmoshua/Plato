#Definition #LieGroups 

> [!definition]
> A [[Lie algebra]] $\mathfrak{g}$ is ***nilpotent*** if there exists a sequence of subspaces: $$\mathfrak{g}=\mathfrak{g}_{0}\supseteq \mathfrak{g}_{1}\supseteq\dots \supseteq\mathfrak{g}_{r}=(0)$$s.t. $[\mathfrak{g},\mathfrak{g}_{i-1}]:=\text{span}\{  [x,y]:x\in \mathfrak{g},y\in \mathfrak{g}_{i-1}\}\subseteq \mathfrak{g}_{i}$ for all $i\in [r]$. 
- **Related definition**: For any Lie algebra $\mathfrak{g}$, the ***central series*** of $\mathfrak{g}$ is a sequence $(C^i(\mathfrak{g}))_{i}$ where $C^0(\mathfrak{g})=\mathfrak{g}$ and $C^{i+1}(\mathfrak{g}):=[\mathfrak{g},C^i(\mathfrak{g})]$.
---
##### Properties
> [!lemma] Lemma 1
> For a nilpotent Lie algebra $\mathfrak{g}$, 
> 1. $\mathfrak{g}_{i}\unlhd \mathfrak{g}$ for all $i\in[r]$.
> 2. $\mathfrak{g}_{i-1} / \mathfrak{g}_{i}\subseteq Z(\mathfrak{g} / \mathfrak{g}_{i})$, the [[Center of a group|center]] of $\mathfrak{g} / \mathfrak{g}_{i}$.
> 3. $C^{i-1}(\mathfrak{g}) / C^{i}(\mathfrak{g})\subseteq Z(\mathfrak{g} / C^i(\mathfrak{g}))$

> [!proof]-
> We have that:
> 1. $[\mathfrak{g},\mathfrak{g}_{i}]\subseteq \mathfrak{g}_{i+1}\subseteq \mathfrak{g}_{i}$. 
> 2. Consider $\pi:\mathfrak{g}\to \mathfrak{g} / \mathfrak{g}_{i}$ the canonical projection. Then, $$[\mathfrak{g / \mathfrak{g}_{i}},\mathfrak{g}_{i-1}/ \mathfrak{g}_{i}]=\pi([\mathfrak{g} , \mathfrak{g}_{i-1}])\subseteq \pi(\mathfrak{g}_{i})=(0)$$Therefore, $\mathfrak{g}_{i-1} / \mathfrak{g}_{i}\subseteq Z(\mathfrak{g} / \mathfrak{g}_{i})$.
> 3. Analogous to 2.
---
> [!lemma] Proposition 2
> For a Lie algebra $\mathfrak{g}$, TFAE:
> 1. $\mathfrak{g}$ is nilpotent.
> 2. $C^r(\mathfrak{g})=(0)$ for some $r\geq 1$.
> 3. there exists $m\geq 1$ s.t. $$\text{ad}(x_{1})\dots \text{ad}(x_{m})y=0,\quad \forall x_{1},\dots,x_{m},y\in \mathfrak{g}$$

> [!proof]-
> We have:
> 1. (1=>2): We show that $\mathfrak{g}_{i}\supseteq C^i(\mathfrak{g})$. We have that $\mathfrak{g}_{1}\supseteq[\mathfrak{g},\mathfrak{g}]=C^1(\mathfrak{g})$. Then, $$\mathfrak{g}_{i}\supseteq[\mathfrak{g},\mathfrak{g}_{i-1}]\supseteq[\mathfrak{g},C^{i-1}(\mathfrak{g})]=C^i(\mathfrak{g})$$and $C^r(\mathfrak{g})=(0)$. 
> 2. (2=>1): By definition.
> 3. (2<=>3): We claim that: $$C^k(\mathfrak{g})=\text{span}\{ \text{ad}(x_{1})\dots \text{ad}(x_{k})y: x_{1},\dots,x_{k},y\in \mathfrak{g} \}$$We have that: $$C^1(\mathfrak{g})=[\mathfrak{g},\mathfrak{g}]=\text{span}\{ [x,y]: x,y\in \mathfrak{g} \}=\text{span}\{\text{ad}(x)y: x,y\in \mathfrak{g} \}$$Further, $$\begin{align}C^k(\mathfrak{g})=[\mathfrak{g},C^{k-1}(\mathfrak{g})]&=\text{span}\{ [x,y]: x\in \mathfrak{g},y\in C^{k-1}(\mathfrak{g}) \}\\&=\text{span}\{ \text{ad}(x_{1})\dots \text{ad}(x_{k})y: x_{1},\dots,x_{k},y\in \mathfrak{g} \}\end{align}$$This proves the statement.
- **Related definition**: The ***nilpotency length*** of a nilpotent Lie algebra is $\text{nil}(\mathfrak{g}):=\text{min}\{ r\geq 1 :C^r(\mathfrak{g})=(0)\}$
- **Corollary**: For a nilpotent Lie algebra $\mathfrak{g}$ with $r:=\text{nil}(\mathfrak{g})\geq 1$, $(0)\subsetneq C^{r-1}(\mathfrak{g})\subseteq Z(\mathfrak{g})$ by Lemma 1.3 and the center is non-trivial.
---
![[Solvable Lie Algebra#^5ae9c5]]
![[Solvable Lie Algebra#^dc3d92|p]]

---
> [!lemma] Lemma 3
> For $\mathfrak{h}\unlhd \mathfrak{g}$,
> 1. if $\mathfrak{g}$ is nilpotent, then $\mathfrak{h}$ and $\mathfrak{g / h}$ are nilpotent.
> 2. if $\mathfrak{g / h}$ is nilpotent and $\mathfrak{h}\subseteq Z(\mathfrak{g})$, then $\mathfrak{g}$ is nilpotent.

> [!proof]-
> We have:
> 1. Follows from $C^j(\mathfrak{h})\subseteq C^j(\mathfrak{g})$ and $C^j(\mathfrak{g / h})=\pi(C^j(\mathfrak{g}))$.
> 2. Let $r\geq 1$ with $\pi(C^r(\mathfrak{g}))=C^r(\mathfrak{g / h})=(0)$. Then, $$C^r(\mathfrak{g})\subseteq \mathfrak{h}\subseteq Z(\mathfrak{g})$$Therefore, $C^{r+1}(\mathfrak{g})=[\mathfrak{g},C^{r}(\mathfrak{g})]=(0)$.
- **Remark**: $\mathfrak{g / h}$ and $\mathfrak{h}$ being nilpotent are not enough to guarantee $\mathfrak{g}$'s nilpotency (cf. Example 2)
---
> [!lemma] Theorem 4
> For a Lie algebra $\mathfrak{g}$, TFAE:
> 1. $\mathfrak{g}$ is solvable. 
> 2. $[\mathfrak{g},\mathfrak{g}]$ is nilpotent.

> [!proof]-
> We have:
> 1. (2<=1): We have: $\mathfrak{g}^{(r+1)}=(\mathfrak{g}^{(1)})^{(r)}\subseteq C^r(\mathfrak{g}^{(1)})$. Hence, if $\mathfrak{g}^{(1)}$ is nilpotent, $\mathfrak{g}^{(r+1)}=(0)$ and $\mathfrak{g}$ is solvable with $\text{sol}(\mathfrak{g})\leq r+1$.
> 2. (1=>2): Let $\mathfrak{g}_{\mathbb{C}}:=\mathfrak{g}\otimes_{\mathbb{R}} \mathbb{C}$. Then, consider: $$\begin{array}{cccc} {}\text{ad}_{\mathbb{C}}:&\mathfrak{g}&\to&{\mathfrak{gl(g)}}&\to&\mathfrak{gl}(\mathfrak{g}_{\mathbb{C}})\\&{x} &\mapsto & {\text{ad}(x)}&\mapsto&\text{ad}(x)\otimes 1 \end{array}{}$$Then, by the [[Solvable Lie Algebra|1st Lie Theorem]], there exists a basis $e_{1},\dots,e_{m}\in \mathfrak{g}_{\mathbb{C}}$ s.t. $$\text{ad}_{\mathbb{C}}(\mathfrak{g})\subseteq \text{UpperTriangular}(m,\mathbb{C})$$Then, $\text{ad}_{\mathbb{C}}([\mathfrak{g},\mathfrak{g}])$ are complex upper triangular matrices with zero diagonal. Therefore, $\text{ad}_{\mathbb{C}}([\mathfrak{g},\mathfrak{g}])$ is nilpotent as the RHS is. But, $$\mathfrak{n}:=\text{ker }\text{ad}_{\mathbb{C}}|_{[\mathfrak{g},\mathfrak{g}]}\subseteq Z(\mathfrak{g})\cap[\mathfrak{g},\mathfrak{g}]\subseteq Z([\mathfrak{g},\mathfrak{g}])$$ By Lemma 3.2, we have that $[\mathfrak{g,g}]$ is nilpotent.
---
> [!lemma] Theorem 5 (Engel)
> Let $\mathfrak{g}$ be a Lie group and $\rho:\mathfrak{g}\to \mathfrak{gl}(V)$ a [[Lie algebra representation]] into a $\mathbb{R}$-vector space s.t. $\rho(x)$ is nilpotent, i.e. $\rho(x)^n=0$ for some $n\in \mathbb{N}$, for all $x\in \mathfrak{g}$. Then,
> 1. there exists a basis of $V$ s.t. $\rho(x)$ is strictly upper triangular in the basis for all $x\in\mathfrak{g}$.

> [!proof]-
> Let us define a ***common null vector*** of a representation: For $\rho:\mathfrak{g}\to \mathfrak{gl}(V)$, $v\in V$ is a common null vector if: $$\rho(x)v=0,\quad \forall x\in \mathfrak{g}$$Let $V_{0}$ denote the space of all null vectors.
> 1. **Claim 1: for nilpotent $X\in \mathfrak{gl}(V)$,  $\text{ad}(X):\mathfrak{gl}(V)\to \mathfrak{gl}(V)$ is nilpotent**:
>    Assume $X^\ell=0$. Let us define: $\ell_{X}:\mathfrak{gl}(V)\to \mathfrak{gl}(V),Y\mapsto XY$  and $r_{X}:\mathfrak{gl}(V)\to \mathfrak{gl}(V),Y\mapsto YX$. Then, $\text{ad}(X)=[X,\cdot]=\ell_{X}-r_{X}$ and $\ell_{X}$, $r_{X}$ commute. Therefore, $$\text{ad}(X)^{2\ell}=\sum_{k=0}^{2\ell}{2\ell\choose k} \ell_{X}^kr_{X}^{2\ell-k}=0$$as $\ell_{X}^{\ell}=0$ and $r_{X}^{\ell}=0$.
> 2. **Claim 2: for a representation $\rho:\mathfrak{g}\to \mathfrak{gl}(V)$ with $\rho(x)$ is nilpotent for all $x\in \mathfrak{g}$. Then, $V_{0}\neq(0)$**
>    We show by induction on $n:=\text{dim }\mathfrak{g}$. 
>    
>    Let $n=1$ and $\mathfrak{g}=\mathbb{R}x$. As $\rho(x)$ is nilpotent, there is $v\neq 0$ s.t. $\rho(x)v=0$. Therefore, $V_{0}\neq(0)$.
>    Let $n\geq 2$. If $\mathfrak{\rho}$ is not injective, then $\text{dim }\text{ker }\rho\geq 1$ and as $\text{dim}(\mathfrak{g} / \text{ker }\rho)<n$, we are done by induction hypothesis.
>    
>    Assume $\rho$ is injective. Then, we can identify $\mathfrak{g}$ with a Lie subalgebra $\mathfrak{g}\leq \mathfrak{gl}(V)$ s.t. for all $x\in \mathfrak{g}$, $x$ is a nilpotent endomorphism on $V$. Let $\mathfrak{h}\leq\mathfrak{g}$ be a maximal proper subalgebra. Then, by Claim 1, for all $x\in \mathfrak{h}$, $\text{ad}(x):\mathfrak{gl}(V)\to \mathfrak{gl}(V)$ is nilpotent. Further, $\text{ad}(x)$ preserves $\mathfrak{h}$ and $\mathfrak{g}$ s.t. we can define: $$\overline{\text{ad}(x)}:\mathfrak{g} / \mathfrak{h}\to \mathfrak{g / h}$$Therefore, we have the representation: $\mathfrak{h}\mapsto \mathfrak{gl}(\mathfrak{g / h}),x\mapsto \overline{\text{ad}(x)}$ of nilpotent elements. By induction hypothesis, there exists $x_{0}\in \mathfrak{g} \backslash \mathfrak{h}$ s.t. $x_{0}+\mathfrak{h}$ is a common null-vector for $\mathfrak{h}$. This means, for all $x\in \mathfrak{h}$, $[x,x_{0}]\in \mathfrak{h}$.
>    
>     Hence, $\mathbb{R}x_{0}+\mathfrak{h}$ is a subalgebra of $\mathfrak{g}$. Indeed, for $y,z\in \mathfrak{h}$ and $\lambda,\mu\in \mathbb{R}$, we have: $$[\lambda x_{0}+y,\mu x_{0}+z]=\lambda[x_{0},z]+\mu[y,x_{0}]+[y,z]\in\mathfrak{h}$$By maximality, we have that $\mathfrak{g}=\mathbb{R}x_{0}+\mathfrak{h}$ and $\mathfrak{h}\unlhd \mathfrak{g}$. By induction hypothesis, the space of common null vectors $W_{0}$ of the representation $\rho|_{\mathfrak{h}}$ is non-zero. 
>     
>     However, for all $w\in W_{0}$, $x\in \mathfrak{h}$ and $y\in \mathfrak{g}$, $$xyw=(xy-yx)w+y\underbrace{ xw }_{ =0 }=\underbrace{ [x,y] }_{ \in \mathfrak{h} }w=0$$Therefore, $W_{0}$ is $\mathfrak{g}$-invariant. Since $x_{0}$ is nilpotent, so is $x_{0}|_{w_{0}}$ and there exists $v_{0}\in W_{0}$ with $v_{0}\neq 0$ with $x_{0}v_{0}=0$. Then, $v_{0}$ is a common null vector for $\mathfrak{g}$.
> 3. **Proof for theorem:**
> 	Induction on $n:=\text{dim }V$. For $n=1$, there exists $0\neq v\in V$ s.t. $\rho(x)v=0$ for all $x\in \mathfrak{g}$. Hence, it is strictly upper triangular. 
> 	
> 	For $n\geq 2$, the proof follows that of [[Lie Group|Lie's 1st Theorem]].
>    
---
> [!lemma] Corollary 6
> For a Lie algebra $\mathfrak{g}$, TFAE:
> 1. $\mathfrak{g}$ is nilpotent.
> 2. $\text{ad}(\mathfrak{g})$ is strictly upper triangular w.r.t. some basis of $\mathfrak{g}$.

> [!proof]-
> We have:
> 1. (1=>2): If $\mathfrak{g}$ is nilpotent then by Proposition 2, $\text{ad}(x)$ is a nilpotent endomorphism for all $x\in \mathfrak{g}$. Therefore, by Engel, there exists a basis $V$ s.t. $\text{ad}(\mathfrak{g})$ is strictly upper triangular w.r.t. this basis.
> 2. (2=>1): If there exists a basis of $\mathfrak{g}$ s.t. $\text{ad}(\mathfrak{g})$ is strictly upper triangular, then $\text{ad}(\mathfrak{g})$ is nilpotent. In addition, $\text{ker }\text{ad}=Z(\mathfrak{g})$. Therefore, by Lemma 3.2, $\mathfrak{g}$ is nilpotent. 
---
##### Examples
> [!h] Example 1
> Let $\mathfrak{g}$ be the space of all $n\times n$ upper triangular matrices with zero diagonal. Then, 
> 1. $C^1(\mathfrak{g})$ is the space of all $n\times n$ upper triangular matrices with zero diagonal and zero upper diagonal.
> 2. $C^{(n-1)}=(0)$.
---
> [!h] Example 2 (Counterexample Lemma 3)
> Consider the Lie algebras: $$\mathfrak{g}:=\left\{ \begin{bmatrix}*&*\\0&*\end{bmatrix} :*\in \mathbb{R}\right\}\subseteq \mathfrak{gl}(n,\mathbb{R}),\quad \mathfrak{h}:=\left\{ \begin{bmatrix}0&*\\0&0\end{bmatrix} :*\in \mathbb{R}\right\}$$Then, 
> 1. $\mathfrak{h}\unlhd \mathfrak{g}$.
> 2. $\mathfrak{g} / \mathfrak{h}$ and $\mathfrak{h}$ are abelian and nilpotent.
> 3. $\mathfrak{g}$ is not nilpotent.

> [!proof]-
> We have that:
> 1. it holds that:$$\left[\begin{bmatrix}a&b\\0&c\end{bmatrix},\begin{bmatrix}0&x\\0&0\end{bmatrix}\right]=\begin{bmatrix}0&xa\\0&0\end{bmatrix}+\begin{bmatrix}0&cx\\0&0\end{bmatrix}\in \mathfrak{h}$$
> 2. we have: $$\mathfrak{g} / \mathfrak{h}=\left\{ \begin{bmatrix}*&0\\0&*\end{bmatrix} :*\in \mathbb{R}\right\}$$and one easily checks that they are abelian. Then, $C^1(\mathfrak{g / h})=[\mathfrak{g / h},\mathfrak{g / h}]=(0)$.
> 3. Assume $\mathfrak{g}$ is nilpotent. As $\mathfrak{g}$ is non-zero, we have that the center is non-trivial. However, we have: $$\begin{bmatrix}a&b\\0&c\end{bmatrix}\begin{bmatrix}x&y\\0&z\end{bmatrix}=\begin{bmatrix}ax&ay+bz\\0&cz\end{bmatrix},\quad\begin{bmatrix}x&y\\0&z\end{bmatrix}\begin{bmatrix}a&b\\0&c\end{bmatrix}=\begin{bmatrix}ax&bx+cy\\0&cz\end{bmatrix}$$and we have that $ay+bz=bx+cy$ for all $a,b,c\in \mathbb{R}$. Therefore, $Z(\mathfrak{g})=(0)$, which is a contradiction.
---
