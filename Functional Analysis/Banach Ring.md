#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a normed [[ring]], i.e. it is equipped with a [[Seminorm|norm]] $\|\cdot\|$.
> 1. $A$ is a ***Banach ring*** if it is [[Banach Space|Banach]] w.r.t. the norm.

---
##### Properties
> [!lemma] Proposition 1 (Quotient and Product Banach Ring)
> Let $A$ and $(A_{i})_{i\in I}$ be Banach rings. 
> 1. for a proper closed ideal $I\unlhd A$, $A / I$ is Banach w.r.t. [[Seminorm|residue norm]].
> 2. $\prod_{i\in I}^{}A_{i}:=\{ (f_{i})_{i\in I}: \exists c>0, \|f\|_{i}\leq c, \forall i\in I \}$ is Banach w.r.t. $\|(f_{i})_{i\in I}\|:=\sup_{i\in I}\left\| f_{i} \right\|$.

---
##### Examples
> [!h] Example 1
> We have that:
> 1. Any ring $A$ is a Banach ring with $\left| \cdot \right|_{0}:A \to \mathbb{R}_{\geq 0},f\mapsto \mathbb{1}_{f\neq 0}$.
> 2. $\mathbb{Z}$ is a Banach ring with absolute value $\left| \cdot \right|$.

> [!proof]+
> We have that:
> 1. Obviously $\left| \cdot \right|_{0}$ is a seminorm on $A$ as a ring. Further by definition it is a norm as well. 
---
