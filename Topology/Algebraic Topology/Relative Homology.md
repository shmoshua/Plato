#Definition #AlgebraicTopology 

> [!definition]
> For a [[topological space]] $X$ and $A\subseteq X$, consider the [[Chain Complex|quotient chain complex]]: $$\mathcal{S}(X,A):= \mathcal{S}(X) / \mathcal{S}(A)$$
> We have that:
> 1. the ***relative homology*** is given as $H_{p}(X,A):=H_{p}(\mathcal{S}(X, A))$ for all $p\in \mathbb{Z}$.
> 2. the ***relative cohomology*** for a ring $R$ is given as $H^p(X,A;R)$.

^40f092

- **Remark**: If $X$ is path connected and $\phi\neq A\subseteq X$, then the relative cohomology doesn't have a [[Singular Cohomology|unity]], i.e. in $H^0(X,A;R)$. ^614e58
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
> [!lemma] Proposition 3 (Relative Cross Product)
> Let $X,Y$ be topological spaces and $A\subseteq X$. Further, let $R$ be a ring. Then, 
> 1. $S^p(X,A;R)\cong\text{ker }J\subseteq S^p(X;R)$ where $$J:S^p(X;R)\to S^p(A;R),\quad \varphi\mapsto \varphi|_{S_{p}(A)}$$
> 2. for $\varphi\in S^p(X,A;R)$ and $\psi\in S^q(Y;R)$, $\varphi \times \psi\in S^{p+q}((X,A)\times Y;R)$
> 3. the following diagram commutes: $$\begin{CD}H^p(X,A;R)\otimes H^q(Y;R) @>\times>>H^{p+q}((X,A)\times Y;R)\\ @Vj^{*}\otimes  \text{id}VV @VVk^{*}V\\H^p(X;R)\otimes H^q(Y;R) @>>\times>H^{p+q}(X\times Y;R)\end{CD}$$where $j:(X,\varnothing)\to (X,A)$ and $k:X\times Y\to (X,A)\times Y$ are the inclusions.
> 4. the following diagram commutes: $$\begin{CD}H^p(A;R)\otimes H^q(Y;R) @>\times>>H^{p+q}(A\times Y;R)\\ @V\delta ^{*}\otimes  \text{id}VV @VV\delta ^{*}V\\H^{p+1}(X,A;R)\otimes H^q(Y;R) @>>\times>H^{p+q+1}((X,A)\times Y;R)\end{CD}$$

^14638d


> [!proof]-
> We have that:
> 1. Recall that:$$S^p(X,A;R)=\text{Hom}(S_{p}(X,A),R)=\text{Hom}(S_{p}(X) / S_{p}(A),R)$$Now, let $\varphi\in S^p(X,A;R)$. Then, $\varphi:S_{p}(X) / S_{p}(A)\to R$ and $\varphi \circ q:S_{p}(X)\to R$ where: $$J(\varphi \circ  q)=\varphi \circ  q|_{S_{p}(A)}=\varphi(0)=0$$ Similarly, if $\varphi|_{S_{p}(A)} = 0$, then $\overline{\varphi}: S_{p}(X) / S_{p}(A)\to R$ is induced.
> 2. Consider the commutative diagram: $$\begin{CD}\mathcal{S}_{*}(A\times Y) @>\Theta>> \mathcal{S}_{*}(A)\otimes \mathcal{S}_{*}(Y)\\ @V(i_{A}\times \text{id})_{c}VV @VV(i_{A})_{c}\otimes  \text{id}V\\ \mathcal{S}_{*}(X\times Y) @>\Theta>> \mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y)\end{CD}$$Let $\varphi\in S^p(X,A;R)$. Then, $\varphi \circ q\in S^p(X;R)$ with $\varphi \circ q|_{S_{p}(A)}=0$. Now, for $c\in S_{p+q}(A\times Y)$, we have that: $$\begin{aligned}((\varphi \circ  q)\times \psi)(c)&=((\varphi \circ  q)\otimes  \psi)\circ  \Theta_{X,Y}(c)\\&=((\varphi \circ  q)\otimes  \psi)\circ( (i_{A})_{c}\otimes \text{id})\circ   \Theta_{A,Y}(c)\\&=((\varphi \circ  \underbrace{ q \circ   (i_{A})_{c} }_{ =0 })\otimes  \psi)\circ   \Theta_{A,Y}(c)=0\end{aligned}$$
> 3. Follows from 2. 
> 4. Let $\varphi\in S^p(A;R)$ and $\psi\in S^q(Y;R)$ by cocycles. We first try to find what $\delta ^{*}([\varphi])$ is.  Consider the diagram: $$\begin{CD}0  @>>> S^p(X,A) @>>> S^p(X)@>>> S^p(A) @>>> 0\\ &@VVV &@VVV&@VVV\\ 0  @>>> S^{p+1}(X,A) @>>> S^{p+1}(X)@>>> S^{p+1}(A) @>>> 0\end{CD}$$Then, we can extend $\varphi$ to $\tilde{\varphi}\in S^p(X)$. As $\delta\varphi=0$, $\varphi|_{B_{p}(A)}=0$ and $\delta \tilde{\varphi}|_{S_{p+1}(A)}=0$. Now, we can view $\delta \tilde{\varphi}$ as an element in $S^{p+1}(X,A;R)$, which we denote with $\varphi'$. Hence, $$\delta ^{*}([\varphi])=[\delta \tilde{\varphi}]=[\varphi']\in H^{p+1}(X,A;R)$$Then, we have that: $$\times \circ (\delta ^{*}\otimes  \text{id})([\varphi]\otimes [\psi])=\times([\varphi']\otimes [\psi])=[\varphi'\times \psi]$$To show the rest, we first claim that $\tilde{\varphi}\times \psi\in S^{p+q}(X\times Y;R)$ extends $\varphi \times \psi\in S^{p+q}(A\times Y;R)$. This is from the fact that: $$\begin{CD}S^{p}(X;R)\otimes  S^q(Y;R) @>\times>> S^{p+q}(X\times Y;R)\\ @V(i_{A})^c\otimes  \text{id}VV@VV(i_{A}\times \text{id})^cV \\ S^{p}(A;R)\otimes  S^q(Y;R) @>>\times> S^{p+q}(A\times Y;R)\end{CD}$$commutes from naturality. Therefore, $$(i_{A}\times \text{id})^c(\tilde{\varphi} \times \psi)=\varphi \times \psi$$Hence, we have that: $$\begin{aligned}\ [\delta(\varphi \times \psi)]&=[\delta\varphi \times \psi+(-1)^p\varphi \times\underbrace{ \delta \psi }_{ =0 }]\\&=[\delta\varphi \times \psi]=[\varphi'\times \psi]\end{aligned}$$This shows that the diagram commutes.

^8840d9

- **Remark**: Similarly, for $B\subseteq Y$, we have: $$H^p(X;R)\otimes H^q(Y,B;R)\to H^{p+q}(X\times(Y,B);R)$$and a diagram as 4 above commutes up to $(-1)^p$, which incurs in the last step.   ^85bd50