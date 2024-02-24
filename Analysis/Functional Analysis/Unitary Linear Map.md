#Definition #Analysis #FunctionalAnalysis 

> [!definition]
> Let $\mathcal{H}$ be a [[Hilbert space]]. A [[bounded linear map]] $T:\mathcal{B}(\mathcal{H})$ is ***unitary***, if $$T T^{*}=T^{*}T=\text{id}_{\mathcal{H}}$$
> The [[group]] of unitary operators are denoted as $\mathcal{U}(\mathcal{H})$.

- **Remark**: For a unitary map $T\in \mathcal{B}(\mathcal{H},\mathcal{H})$ and $u\in \mathcal{H}$: $$\left\| Tu \right\| ^{2}=\braket{ Tu , Tu } =\braket{ u , T^*Tu } =\braket{ u , u } =\|u\|^{2}$$
---
##### Properties
> [!lemma] Lemma 1
> Let $\mathcal{H}$ be a separable $\mathbb{C}$-Hilbert space. W.r.t. the strong operator topology, whose basis is given by:$$U(T;u_{1},\dots,u_{n};\varepsilon):=\{ S\in \mathcal{U}(\mathcal{H}):\left\| Su_{i}-Tu_{i} \right\| <\varepsilon,\forall i\in[n] \}$$
> 1. $\mathcal{U}(\mathcal{H})$ is a [[topological group]].
> 2. $\mathcal{U}(\mathcal{H})$ is [[Locally Compact Topological Group|locally compact]] if and only if $\text{dim }\mathcal{H}<+\infty$, in which case $\mathcal{U}(\mathcal{H})$ is also compact. 

> [!proof]-
> We have that:
> 1. **Showing that the composition is continuous**:
> 	Let $(S_{i},T_{i})_{i}\subseteq \mathcal{U}(\mathcal{H})\times\mathcal{U}(\mathcal{H})$ s.t. $(S_{i},T_{i})\to(S,T)$ in the product topology. As the strong operator topology is equivalent to the topology of pointwise convergence, for any $x\in \mathcal{H}$, 
> 	1. $S_{i}(x)\to S(x)$ and
> 	2. $T_{i}(x)\to T(x)$
> 	
> 	Now let $x\in \mathcal{H}$. We have: $$\begin{align}\left\| (S_{i}T_{i}-S T)x \right\| &\leq \left\|  (S_{i}T_{i}-S_{i}T)x \right\|+ \left\| (S_{i}T-ST)x \right\|\\&\leq \left\| S_{i}(T_{i}-T)x \right\|+\left\| (S_{i}-S)Tx \right\| \\&\leq \left\| (T_{i}-T)x \right\|  +\left\| (S_{i}-S)Tx \right\|  \end{align}$$Then, choose $i_{0}\in \mathbb{N}$ s.t. 
> 	1. $T_{i}\in U(T,x,\varepsilon/2)$ for all $i\geq i_{0}$
> 	2. $S_{i}\in U(S,Tx,\varepsilon /2)$ for all $i\geq i_{0}$
> 	 
> 	 It follows that $S_{i}T_{i}\in U(ST,x, \varepsilon)$ for all $i\geq i_{0}$ and therefore continuous.
> 2. **Showing that the inversion is continuous**:
> 	Let $T,(T_{i})_{i}\subseteq \mathcal{U}(\mathcal{H})$ s.t. $T_{i}\to T$ in strong operator topology. Then, for $\varepsilon>0$, $$\begin{align}\left\| T^{*}_{i}x-T^{*}x \right\| &=\left\| T^{*}T(T^{*}_{i}-T^{*}) x\right\| \\&\leq \left\| (TT^{*}_{i}-\text{id}_{\mathcal{H}}) x\right\| \\&=\left\| (TT_{i}^{*}-T_{i}T_{i}^{*})x \right\|\\&=\left\| (T-T_{i})T_{i}^{*}x \right\|  \end{align}$$Therefore, for $i_{0}\in \mathbb{N}$ s.t. $T_{i}\in U(T;T_{i}^{*}x;\varepsilon)$ for all $i\geq i_{0}$, $T_{i}^{*}\in U(T^{*},x,\varepsilon)$. This proves the statement.
> 3. **Showing if $\text{dim}\mathcal{H}<+\infty$ $\mathcal{U}(\mathcal{H})$ is compact**:
> 	Let $n=\text{dim }\mathcal{H}<+\infty$.  Then, $\mathcal{U}(\mathcal{H})=\text{U}(n)$ which is compact.
> 4. **Showing that $\mathcal{U}(\mathcal{H})$ cannot be compact if $\mathcal{H}$ is infinite-dimensional**:
> 	As we can find a sequence $(T_{k})_{k}$ that weakly converges to $0$, there is no convergent subsequence in $\mathcal{U}(\mathcal{H})$. Therefore, $\mathcal{U}(\mathcal{H})$ is not compact.
> 5. **Showing if $\mathcal{U}(\mathcal{H})$ is locally compact it is finite-dimensional**:
>    Assume that it is infinite-dimensional. Let $U(\text{id},F,\varepsilon)$ be an open neighborhood of $\text{id}$. As $\mathcal{U}(\mathcal{H})$ is locally compact, there exists a compact set $C\subseteq \mathcal{U}(\mathcal{H})$ s.t. $U(\text{id},F,\varepsilon)\subseteq C$. 
>    
>    Let $\mathcal{H}:=\braket{ F }\oplus \braket{ F  }^\bot$. Then, the subgroup: $$\Gamma:=\begin{bmatrix}\text{id}&0\\0&\mathcal{U}(\braket{ F }^{\bot} )\end{bmatrix}\subseteq U(\text{id},F,\varepsilon)$$as for $T\in \Gamma$, $Tx=x$ for all $x\in F$. However, as $\mathcal{U}(\braket{ F }^{\bot})\cong\Gamma$ as it is closed, it is compact. As $\braket{ F  }^{\bot}$ is infinite-dimensional Hilbert space, this is a contradiction to 4. 
>     
---
