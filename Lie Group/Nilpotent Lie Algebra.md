#Definition #LieGroups 

> [!definition]
> A [[Lie algebra]] $\mathfrak{g}$ is ***nilpotent*** if there exists a sequence of subspaces: $$\mathfrak{g}=\mathfrak{g}_{0}\supseteq \mathfrak{g}_{1}\supseteq\dots \supseteq\mathfrak{g}_{r}=(0)$$s.t. $[\mathfrak{g}:\mathfrak{g}_{i-1}]:=\text{span}\{  [x,y]:x\in \mathfrak{g},y\in \mathfrak{g}_{i-1}\}\subseteq \mathfrak{g}_{i}$ for all $i\in [r]$. 
- **Related definition**: For any Lie algebra $\mathfrak{g}$, the ***central series*** of $\mathfrak{g}$ is a sequence $(C^i(\mathfrak{g}))_{i}$ where $C^0(\mathfrak{g})=\mathfrak{g}$ and $C^{i+1}(\mathfrak{g}):=[\mathfrak{g},C^i(\mathfrak{g})]$.
---
##### Properties
> [!lemma] Lemma 1
> For a nilpotent Lie algebra $\mathfrak{g}$, 
> 1. $\mathfrak{g}_{i}\unlhd \mathfrak{g}$ for all $i\in[r]$.
> 2. $\mathfrak{g}_{i-1} / \mathfrak{g}_{i}\subseteq Z(\mathfrak{g} / \mathfrak{g}_{i})$, the [[Center of a group|center]] of $\mathfrak{g} / \mathfrak{g}_{i}$.
> 3. $C^{i-1}(\mathfrak{g}) / C^{i}(\mathfrak{g})\subseteq Z(\mathfrak{g} / C^i(\mathfrak{g}))$

> [!proof]+
> 