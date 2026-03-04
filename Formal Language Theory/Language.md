#Definition #FormalLanguageTheory

> [!definition]
> An ***alphabet*** is a finite, non-empty set $\mathcal{A}$.
> 1. a ***symbol*** of an alphabet $\mathcal{A}$ is $a\in \mathcal{A}$. 
> 2. a ***word/string*** is an element $w\in \mathcal{A}^{*}:= \bigsqcup_{i=0}^{\infty}\mathcal{A}^i$ where $\mathcal{A}^0:=\{ \varepsilon \}$ with the ***empty word*** $\varepsilon$.
> 3. a ***language*** is a subset $\mathcal{L}\subseteq \mathcal{A}^{*}$.

- **Related definition**: For words $w,w_{1},w_{2}$, 
	1. the ***length*** $\left| w \right|\in \mathbb{N}$ s.t. $w\in \mathcal{A}^\left| w \right|$.
	2. $\circ:\mathcal{A}^{*}\times \mathcal{A}^{*}\to \mathcal{A}^{*},(w_{1},w_{2})\mapsto w_{1}w_{2}$ is the ***concatenation*** operator.


---
##### Properties
> [!lemma] Proposition 1
> $\mathcal{A}^{*}$ is a [[Group|monoid]] w.r.t. concatenation called the ***free monoid***.

---
