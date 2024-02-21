#Definition #LieGroups 
> [!definition]
> A [[group]] $G$ is ***topological*** if the underlying set is a [[topological space]] and the group operations are continuous, i.e.
> 1. $G\times G\to G,(g,h)\mapsto gh$ is continuous (under the product topology) and
> 2. $G\to G,g\mapsto g^{-1}$ is continuous.
- **Remark**: $g\mapsto g^{-1}$ is a [[homeomorphism]].
- **Related definition**: For any $g\in G$, the ***left/right translation*** are: $$\begin{array}{cccc} {L_{g}:}&{G}&\to&{G}\\&{x} &\mapsto & {gx} \end{array}{}\quad\quad\quad\quad\quad \begin{array}{cccc} {R_{g}:}&{G}&\to&{G}\\&{x} &\mapsto & {xg} \end{array}{}$$continuous and homeomorphisms (with inverses as $L_{g^{-1}},R_{g^{-1}}$).
---
> [!lemma] Proposition 1
> Let $G_{1},G_{2}$ be topological groups. If $\varphi:G_{1}\to G_{2}$ is a [[group homomorphism]], it holds that: 
> ```tikz 
> \usepackage{tikz-cd} \usepackage{amsfonts} 
> \usepackage{amssymb} 
> \begin{document} 
> \begin{tikzcd}
> G_1 \arrow[r, "\varphi"] & G_2\arrow[d, "L_{\varphi(g)}"] \\G_1 \arrow[u,"L_{g^{-1}}"]\arrow[r, swap,"\overline{\varphi}"]&G_2
> \end{tikzcd}
> \end{document}
> ```
> Therefore, $\varphi$ is continuous if and only if it is continuous at one point.
---
> [!lemma] Proposition 2
> Let $G,\{ G_{\alpha} \}_{\alpha\in A}$ be a topological group. Then:
> 1. $H\leq G$ is a topological group.
> 2. $\prod_{\alpha\in A}^{}G_{\alpha}$ is a topological group with the product topology.
> 3. for $N\unlhd G$, $G / N$ is a topological group with the quotient topology.
---
##### Examples
> [!h] Example 1 (Elementary Topological Groups)
> We have:
> 1. Any group $G$ is a topological group with respect to the discrete topology. 
> 2. $(\mathbb{R}^n,+)$ is a topological group with respect to the Euclidean topology.
> 3. $\mathbb{R}^{*},\mathbb{C}^{*}$ are topological groups.
> 4. [[General Linear Group|$\text{GL}(n,\mathbb{R})$]] is a topological group.
---
> [!h] Example 2
> Let $X$ be a [[locally compact Hausdorff space]]. Then, with respect to the [[compact-open topology]],
> 1. $\text{Homeo}(X)$ is not necessarily a topological group.
> 2. $\text{Homeo}(X)$ is a topological group if $X$ is compact.
> 3. $\text{Homeo}(X)$ is a topological group if $X$ is locally connected.
> 4. $\text{Homeo}(X)$ is a topological group if $X$ is a [[topological manifold]].
---
> [!h] Example 3
> If $M$ is a [[smooth manifold]], for any $r\in \mathbb{N}$, and $$\text{Diff}^r:=\{ f\in \text{Homeo}(M):f,f^{-1}\in C^r(M) \}$$
> 1. $\text{Diff}^r$ is a topological group.
> 2. $\text{Diff}^r$ is not a closed subgroup of $\text{Homeo}(M)$.
---
> [!h] Example 4
> Let $(X,d)$ be a proper [[metric space]], i.e. all closed balls are compact. Then, the group of isometries $\text{Iso}(X)$ is a topologocial group w.r.t the compact-open topology.