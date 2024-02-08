#Definition #Algebra-I 

> [!definition]
> Let $H \leq G$. Then, we define the ***core*** of $H$ as:$$\text{Core}(H):=\bigcap_{a\in G}^{}aHa^{-1}$$

- **Remark**: If $N \unlhd G$ s.t. $N \leq H$, then $N\leq \text{Core}(H)$, i.e. $\text{Core}(H)$ is the largest [[Normal Subgroup|normal subgroup]] of $G$ contained in $H$.
---
##### Properties
> [!lemma] Theorem 1
> Let $H\leq G$ with index $[G:H]=n$. Then, it holds that: $$[G:\text{Core}(H)]|n!$$

> [!proof]+
> Consider $G \curvearrowright G / H$ by $x\circ gH = xgH$. Then, we have a homomorphism: $$\begin{array}{cccc} {\psi:}&{G}&\to&{S(G / H)}\\&{x} &\mapsto & {\psi_{x}} \end{array}{}$$where $\psi_{x}(gH)=xgH$. Then, $$\text{ker}(\psi)=\{ x\in G:\psi_{x}=\iota \}=\{ x\in G:g^{-1}x\in gHg^{-1} \text{ for all }g\in G\}=\text{Core}(H)$$
> 
> Therefore, $$G / \text{ker}\psi\cong \text{Im}(\psi)\leq S_{n}$$Thus, $[G:\text{ker}\psi]|n!$.
---
