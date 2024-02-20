#Definition #Algebra
> [!definition]
> For a commutative [[Ring|ring]] $R$, an [[ideal]] $\mathfrak{m}\subseteq R$ is ***maximal***, if $\mathfrak{m}\neq R$ and there exists no ideal $\mathfrak{a}$ s.t. $$\mathfrak{m}\subsetneq\mathfrak{a}\subsetneq R$$
- **Remark**: every maximal ideal is a [[prime ideal]]. 
---
##### Properties
> [!lemma]
> Let $R$ be a commutative ring and $\mathfrak{m}\subseteq R$ an ideal. Then, $\mathfrak{m}$ is maximal if and only if $R / \mathfrak{m}$ is a [[Field|field]].

> [!proof]-
> (=>): Let $\mathfrak{m}\subseteq R$ be a maximal ring and $\mathfrak{b}\subseteq R / \mathfrak{m}$ is an ideal. Then, $\pi ^{-1}[\mathfrak{b}]\subseteq R$ is an ideal s.t. $\mathfrak{m}\subseteq \pi ^{-1}(\mathfrak{b})$. However, as $\mathfrak{m}$ is maximal, $\pi ^{-1}(\mathfrak{b})=\mathfrak{m}$ or $\pi ^{-1}(\mathfrak{b})=R$. Therefore, $\mathfrak{b}=\pi[\pi ^{-1}[\mathfrak{b}]]=\pi[\mathfrak{m}]=(\overline{0})$ or $\mathfrak{b}=\pi[\pi ^{-1}[\mathfrak{b}]]=\pi[R]=R / \mathfrak{m}$. Hence, from [[Field|Proposition 1]], $R / \mathfrak{m}$ is a field.
> 
> (<=): Let $R / \mathfrak{m}$ be a field and let $\mathfrak{a}\subseteq R$ s.t. $\mathfrak{m}\subseteq \mathfrak{a}$. Then, $\pi[\mathfrak{a}]\subseteq R / \mathfrak{m}$ is an ideal and therefore, $\pi[\mathfrak{a}]=(\overline{0})$ or $\pi[\mathfrak{a}]=R / \mathfrak{m}$. Hence, $\mathfrak{a}=\mathfrak{m}$ or $\mathfrak{a}=R$, which proves that $\mathfrak{m}$ is maximal. 

- **Corollary**: $R$ is a field if and only if $(0)\subseteq R$ is maximal.
---
