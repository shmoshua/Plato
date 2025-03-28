#Definition #AlgebraicTopology 

> [!definition]
> For a [[topological space]] $X$ and a subspace $A\subseteq X$, let $\mathcal{S}(X)$ and $\mathcal{S}(A)$ be the [[chain complex]] of [[p-Simplex|singular $p$-chains]] $S_{p}(X)$ and $S_{p}(A)$. Then, for the [[Chain Complex|quotient chain complex]]: $$\mathcal{S}(X,A):= \mathcal{S}(X) / \mathcal{S}(A)$$
> We have that:
> 1. the ***relative homology*** is given as $H_{p}(X,A):=H_{p}(\mathcal{S}(X, A))$ for all $p\in \mathbb{Z}$.

^40f092

---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\mathcal{S}(X,A)$ is well-defined.
> 2. there exists a long exact sequence: $$\cdots\to H_{p}(A)\xrightarrow{i_{*}} H_{p}(X)\xrightarrow{j_{*}} H_{p}(X,A)\xrightarrow{\partial_{*}} H_{p-1}(A)\to\cdots$$where $i:\mathcal{S}(A)\to \mathcal{S}(X)$ is the inclusion and $j:\mathcal{S}(X)\to \mathcal{S}(X,A)$ be the standard projection.
> 3. $S_{p}(X,A)$ is free abelian.

^63d319

> [!proof]-
> We have that:
> 1. It suffices to show that $\mathcal{S}(A)$ is a chain subcomplex of $\mathcal{S}(X)$. Let $\sigma:\Delta_{p}\to A$ be a singular $p$-simplex in $A$. Then, $\sigma$ is also a $p$-simplex in $X$. Hence, $S_{p}(A)\leq S_{p}(X)$. This shows the statement.
> 2. This follows from [[Chain Complex|Theorem 5]] and [[Chain Complex|Theorem 3]].
> 3. Let $I:=\{ \sigma:\Delta_{p}\to X|\text{im}(\sigma)\nsubseteq A \}\subseteq S_{p}(X)$. Then, $\{ [\sigma] \}_{\sigma\in I}$ freely generates $S_{p}(X,A)$. 

^4c27aa

---
> [!lemma] Proposition 2
> Let $f:(X,A)\to(Y,B)$ be a continuous map, i.e. $f:X\to Y$ with $f(A)\subseteq B$. Then,
> 1. $f$ induces [[Chain Complex|chain maps]] $f_{c}:\mathcal{S}(A)\to \mathcal{S}(B)$, $f_{c}:\mathcal{S}(X)\to \mathcal{S}(Y)$ and $f_{c}:\mathcal{S}(X,A)\to \mathcal{S}(Y,B)$. 
> 2. The following diagram commutes:$$\begin{CD}
>    0 @>>> \mathcal{S}(A)@>>>\mathcal{S}(X)@>>> \mathcal{S}(X , A)@>>> 0\\&@Vf_{c}VV@Vf_{c}VV@Vf_{c}VV\\0 @>>> \mathcal{S}(B)@>>>\mathcal{S}(Y)@>>> \mathcal{S}(Y,B)@>>> 0\end{CD}$$
> 3. The following diagram commutes:$$\begin{CD}
  \cdots @>>> H_{p}(A) @>i_{*}>> H_{p}(X) @>j_{*}>> H_{p}(X,A) @>\partial_{*}>> H_{p-1}(A) @>>>\cdots\\
  &@Vf_{*}VV@Vf_{*}VV@Vf_{*}VV@Vf_{*}VV
  \\ \cdots @>>> H_{p}(B) @>>i'_{*}> H_{p}(Y) @>>j'_{*}> H_{p}(Y,B) @>>\partial_{*}> H_{p-1}(B) @>>>\cdots
  \end{CD}$$

^3e1df9

> [!proof]-
> We have that:
> 1. for $c=\sum_{\sigma}^{}n_{\sigma}\sigma\in S_{p}(A)$ we have that: $$f_{c}(\partial c)=f_{c}\left( \sum_{\sigma}^{}n_{\sigma}\partial\sigma \right)=\sum_{\sigma}n_{\sigma}f_{c}\left( \sum_{i=0}^{p}(-1)^i\sigma^{(i)} \right)=\sum_{\sigma}n_{\sigma}\partial(f_{c}(\sigma))=\partial\left( f_{c}\left( \sum_{\sigma}^{}n_{\sigma}\sigma \right) \right)$$Analogous for $X$ and $(X,A)$
> 2. We have that for $c=\sum_{\sigma}n_{\sigma}\sigma\in S_{p}(A)$, $$f_{c}(i(c))=f_{c}(c)=f_{c}(i(c))$$
> 	Further, for $c=\sum_{\sigma}n_{\sigma}\sigma\in S_{p}(X)$, $$f_{c}(j(c))=f_{c}([c])=[f_{c}(c)]=j(f_{c}(c))$$
> 3. Follows from [[Chain Complex|Theorem 4]].

^cca685

---

