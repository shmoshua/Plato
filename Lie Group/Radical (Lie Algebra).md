#Definition #LieGroups 

> [!definition]
> A ***radical*** of a [[Lie algebra]] $\mathfrak{g}$ is the maximal solvable ideal of $\mathfrak{g}$.
---
##### Properties
> [!h] Proposition 1 (Existence and Uniqueness of Radicals)
> For any Lie algebra $\mathfrak{g}$, 
> 1. there exists a unique solvable radical $\mathfrak{z}\subseteq \mathfrak{g}$
> 2. it holds that $\mathfrak{g} / \mathfrak{z}$ is [[Semisimple Lie Algebra|semisimple]].

> [!proof]-
> The existence and uniqueness follows from [[Solvable Lie Algebra|Proposition 1.5]] and finite dimensionality. 
> 
> Now, we first show that $\mathfrak{g} / \mathfrak{z}$ has no non-zero solvable ideals. Let $\pi:\mathfrak{g}\to \mathfrak{g / z}$ be the canonical projection. Let $\mathfrak{h}\unlhd \mathfrak{g / z}$ be a solvable ideal. Then, $\mathfrak{a}:=\pi ^{-1}(\mathfrak{h})\unlhd \mathfrak{g}$. Moreover, as $\pi(\mathfrak{a})=\mathfrak{h}$ is solvable and $\text{ker }\pi|_{\mathfrak{a}}=\mathfrak{a}\cap \mathfrak{h}$ is solvable,  therefore, $\mathfrak{a}$ is solvable by [[Solvable Lie Algebra|Lemma 3.2]].
> 
> Then, by maximality, $\mathfrak{a}\subseteq \mathfrak{z}$ and $\mathfrak{h}=\pi(\mathfrak{a})=(0)$. Now it suffices to show that $K_{\mathfrak{g} / \mathfrak{z}}$ is non-generate by [[Semisimple Lie Algebra|Theorem 1]]. Assume that $K_{\mathfrak{g} / \mathfrak{z}}$ is not non-degenerate. Then, for $\mathfrak{n}:=\mathfrak{g / z}$, $\mathfrak{n}^{\bot}=\text{rad}(K_{\mathfrak{n}})\neq \{ 0 \}$. By [[Ideal (Lie Algebra)|Example 1]], $\mathfrak{n}^{\bot}\unlhd \mathfrak{n}$. Therefore, $$K_{\mathfrak{n}^{\bot}}=K_{\mathfrak{n}}|_{\mathfrak{n}^{\bot}\times \mathfrak{n}^{\bot}}$$Hence $K_{\mathfrak{n}^{\bot}}=0$. Hence, by [[Killing Form|Cartan's criterion]], $\mathfrak{n}^{\bot}$ is solvable. This is a contradiction as $\mathfrak{n}=\mathfrak{g / z}$ has no non-zero solvable ideals.
---
