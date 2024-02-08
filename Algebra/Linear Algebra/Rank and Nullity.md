#Definition #LST #LinearAlgebra 

> [!Definition]
> For a field $F$, let $A\in F^{n,m}$ be a matrix and $\mathcal{A}:(F^m,F) \to (F^n,F)$ the [[Linear Map| linear map]] defined by $\mathcal{A}(x)=Ax$ for all $x\in F^m$. The ***rank*** $\text{Rank}(A)$ of the matrix $A$ is the dimension of the [[Kernel and Image|range space]], $\text{Range}(\mathcal{A})$ and the ***nullity*** $\text{Nullity}(A)$ of $A$ is the dimension of the [[Kernel and Image|null space]], $\text{Null}(\mathcal{A})$.

---
##### Properties
> [!lemma] Theorem RankNull.1
> Let $A\in F^{n,m}$ and $B\in F^{m,p}$. It holds that:
> 1. $\text{Rank}(A)+\text{Nullity}(A)=m$
> 2. $0\leq \text{Rank}(A)\leq \min\{ m,n \}$
> 3. $\text{Rank}(A)+\text{Rank}(B)-m \leq \text{Rank}(AB)\leq \min\{  \text{Rank}(A),\text{Rank}(B)\}$
> 4. If $P\in F^{m,m}$ and $Q\in F^{n,n}$ are invertible, then:
> 	$$\text{Rank}(A)=\text{Rank}(AP)=\text{Rank}(QA)=\text{Rank}(QAP)$$
>    and
> 	$$\text{Nullity}(A)=\text{Nullity}(AP)=\text{Nullity}(QA)=\text{Nullity}(QAP)$$

> [!proof]-
> We can see that:
> 1. Let $B:=\{ b_{i} \}_{i=1}^m$ be the basis of $(F^m,F)$. Now, we define $C:=\{ c_{1},\dots,c_{k} \}$ as the greatest linearly independent subset of $\{ Ab_{i} \}_{i=1}^m$. Wlog we can assume that $C=\{Ab_{i}\}_{{i=1}}^{k}$ and that $Ab_{k+1},\dots,Ab_{m}$ can be represented with vectors from $C$.
>     
>     First, we will show that $C$ is a basis for $\text{Range}(\mathcal{A})$. By definition, $C$ is linearly independent and for any $v\in F^n$, we have $u\in F^m$ s.t. $Au=v$. Then, as $Ab_{k+1},\dots,Ab_{n}$ can be represented with linear combination of $c_{1},\dots,c_{k}$:
> 	$$v=Au=\sum_{i=1}^{m}\xi_{i}Ab_{i}=\sum_{i=1}^{m}\xi_{i}Ab_{i}=\sum_{i=1}^k{\mu_{i}c_{i}}$$
> 	for $\mu_{1},\dots,\mu_{k} \in F$. Therefore, $C$ spans $\text{Range}(\mathcal{A})$ and is a basis. Therefore, $\text{Rank}(A)=k$
> 	
> 	Now consider the rest. For every $b_{j}$ for $k<j\leq m$, $Ab_j$ can be represented using vectors from $C$ i.e. $$Ab_{j}=\sum_{i=1}^{k}\mu_{i}c_{i}=\sum_{i=1}^{k}\mu_{i}Ab_{i}$$ Let $b'_{j}:=b_{j}-\sum_{i=1}^{k}\mu_{i}b_{i}$. We will now show that $N:=\{ b'_{j}: k < j \leq m\}$ forms a basis for the null space $\text{Null}(\mathcal{A})$. For any $b'_{j}\in N$, we have:
> 	$$
> 	 Ab'_{j}=A\left( b_{j}-\sum_{i=1}^{k}\mu_{i}b_{i} \right)=Ab_{j}-\sum_{i=1}^{k}\mu_{i}Ab_{i}=Ab_{j}-Ab_{j}=\theta_{n}
> 	 $$
> 	Therefore, $N \subseteq \text{Null}(\mathcal{A})$. Now, $N$ is linearly independent by construction. Assume $\text{dim}\text{ Null}(\mathcal{A})>m-k$. Then, there exists a non-zero vector $b\in F^m$ s.t. that cannot be represented by vectors in $N$. Furthermore, $b$ cannot be represented by $b_{1},\dots,b_{k}$ as $Ab=\theta_{n}$. Therefore, $b$ cannot be represented by $\{ b_{1},\dots,b_{k},b'_{k+1},\dots,b'_{m} \}$ and further by $B$. This is a contradiction and therefore, $N$ is the basis of $\text{Null}(\mathcal{A})$.
> 	
>     Finally, we have: $$\text{Rank}(A)+\text{Nullity}(A)=k+m-k=m$$
>  2. From 1) we know that $\text{Rank}(A)=|C|$. Then, by construction, $\text{Rank}(A)\leq |B|=m$
>  and $|C|\leq n$ as there cannot be more than $n$ linearly independent vectors in $F^n$. Therefore, $0\leq \text{Rank}(A) \leq \min\{ m,n \}$.
>  3. Firstly, as $\text{Null}(\mathcal{B})\subseteq \text{Null}(\mathcal{A}\mathcal{B})$, we have $\text{Nullity}(B)\leq \text{Nullity}(AB)$. Let's define $\tilde{\mathcal{B}}:\text{Null}(\mathcal{A}\mathcal{B})\to F^m$. Then, $\text{Null}(\mathcal{B})=\text{Null}(\tilde{\mathcal{B}})$. Since $\text{Range}(\tilde{\mathcal{B}})\subseteq \text{Null}(\mathcal{A})$, we have: $\text{dim Range}(\tilde{\mathcal{B}})\leq \text{dim Null}(\mathcal{A})$. All together,$$\text{Nullity}(AB)=\text{dim Range}(\tilde{\mathcal{B}})+\text{dim Null}(\tilde{\mathcal{B}})\leq \text{Nullity}(A)+\text{Nullity}(B)$$
>      Then, $$p-\text{Rank}(AB)=\text{Nullity}(AB)\leq \text{Nullity}(A)+\text{Nullity}(B)=p-\text{Rank}(B)+m-\text{Rank}(A)$$ and $$\text{Rank}(A)+\text{Rank}(B)-m \leq \text{Rank}(AB)$$
>      Now, let's show that $\text{Rank}(AB)\leq \min\{  \text{Rank}(A),\text{Rank}(B)\}$. As $\text{Range}(AB)\subseteq \text{Range}(A)$, $\text{Rank}(AB)\leq \text{Rank}(A)$. Also, as $\text{Nullity}(B)\leq \text{Nullity}(AB)$, $$\text{Rank}(AB)=p-\text{Nullity}(AB)\leq p-\text{Nullity}(B)=\text{Rank}(B)$$
>  4. We will show it for $\text{Rank}(A)=\text{Rank}(QAP)$. From 3), $$\text{Rank}(QAP)\leq\min\{ \text{Rank}(A),\text{Rank}(Q),\text{Rank}(P) \}=\min\{ \text{Rank}(A),n,m\}=\text{Rank}(A)$$ Also,
>      $$\text{Rank}(QAP)\ge \text{Rank}(QA)+m-m\ge \text{Rank}(A)+n-n=\text{Rank}(A)$$
>      Similarly, $$\text{Nullity}(A)=m-\text{Rank}(A)=m-\text{Rank}(QAP)=\text{Nullity}(QAP)$$
---
