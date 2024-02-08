#Definition #Analysis #FunctionalAnalysis

> [!definition]
> A _**normed space**_ is $(V,\|\cdot \|)$ where $V$ is a $\mathbb{K}$-vector space $V$ and $\|\cdot \|$ is a [[norm]].
- **Remark**: In a normed space $(V,\|\cdot\|)$, $d(v_1,v_2):=\|v_1-v_2\|$ defines the [[natural distance]].
- **Remark**:  A normed space is a [[topological space]] where the set of all open balls: $$\{ B(x,r): x\in V, r\in (0,+\infty) \}$$forms a basis of the topology.  
- **Related Definition**: A normed space $(V,\| \cdot \|)$ is ***separable***, if the underlying metric space $(V,d)$ is.
---
##### Properties

> [!Lemma] Lemma 1
> The scalar multiplication and vector addition are continuous:
> 1. $\mathbb{K} \times V \to V, (\lambda,v)\mapsto \lambda v$
> 2. $V\times V\to V,(v_{1},v_{2})\mapsto v_{1}+v_{2}$

> [!proof]-
> The direct product of two normed spaces $V_{1}\times V_{2}$ is a normed space with the norm:$$\left\| (v_{1},v_{2}) \right\| =\left\| v_{1} \right\| _{V_{1}}+\left\| v_{2} \right\| _{V_{2}}$$
> Therefore, a sequence $((v_{1,n},v_{2,n}))_{n}$ is Cauchy if and only if the sequences $(v_{1,n})_{n}$ and $(v_{2,n})_{n}$ are Cauchy. 
> 
> 1. Let $\lambda_{1},\lambda_{2}\in \mathbb{K}$ and $v_{1},v_{2}\in V$. Then,
>    $$\left\| \lambda_{1} v_{1}-\lambda_{2}v_{2} \right\| =\left\| (\lambda_{1}-\lambda_{2})v_{1}-\lambda_{2}(v_{2}-v_{1}) \right\|\leq \left| \lambda_{1}-\lambda_{2} \right| \left\| v_{1} \right\| +\left| \lambda_{2} \right| \left\| v_{2}-v_{1} \right\|  $$
> 2. Let $v_{1},v_{2},w_{1},w_{2}\in V$. Then, $$\left\| w_{1}+w_{2}-v_{1}-v_{2} \right\| \leq \left\| w_{1}-v_{1} \right\| +\left\| w_{2}-v_{2} \right\| $$It follows that $(v_{1,n}+v_{2,n})_{n}$ is Cauchy, if $((v_{1,n},v_{2,n}))_{n}$ are Cauchy.
> 
> Therefore, both maps are continuous.
---