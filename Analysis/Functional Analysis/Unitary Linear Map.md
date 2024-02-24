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

> [!proof]+
> We have that:
> 1. **Showing that the composition is continuous**:
> 	Let $(S_{i},T_{i})_{i}\subseteq \mathcal{U}(\mathcal{H})\times\mathcal{U}(\mathcal{H})$ s.t. $(S_{i},T_{i})\to(S,T)$ in the product topology. As the strong operator topology is equivalent to the topology of pointwise convergence, for any $x\in \mathcal{H}$, 
> 	1. $S_{i}(x)\to S(x)$ and
> 	2. $T_{i}(x)\to T(x)$
> 	
> 	Now let $x\in \mathcal{H}$. We
---
