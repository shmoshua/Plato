#Definition #LST 

> [!definition]
> Let $(V,F)$ be a [[Vector Space|vector space]] and $W\subseteq V$. $(W,F)$ is a ***vector subspace*** of $V$, if and only if it is a vector space on its own, i.e. for all $w_{1},w_{2}\in W$ and $a_{1},a_{2}\in F$:
> $$a_{1}w_{1}+a_{2}w_{2}\in W$$
---
> [!definition]
> Let $(V,F)$ be a linear space and $S\subseteq V$. The ***vector subspace generated by $S$*** of $V$ is the smallest subspace of $(V,F)$ that contains $S$.

---
##### Properties

> [!lemma] Lemma 1
> For a linear space $V$ and its subspace $W$ over field $F$, we have that:
> 1. $\theta_{V}\in W$
> 2. $\theta_{V}=\theta_{W}$

> [!proof]-
> For any $w\in W$, as $W$ is a linear subspace, $-w\in W$. Therefore, $\theta_{V}=-w+w\in W$. Then, as $\theta_{W}\in V$ we have: $$\theta_{W}=\theta_{W}+\theta_{V}=\theta_{V}$$

---

> [!lemma] Proposition 2
> Let $\{ (W_{i},F) \}_{i=1}^n$ be a finite family of linear subspaces of $(V,F)$. Then, $(\bigcap_{i=1}^{n}W_{i},F)$ is also a linear subspace of $(V,F)$.

> [!proof]-
> For any $w_{1},w_{2}\in \bigcap_{i=1}^{n}W_{i}$ and $a_{1},a_{2}\in F$, $w_{1},w_{2}\in W_{i}$ for any $i$. As $W_{i}$ is a linear subspace, $a_{1}w_{1}+a_{2}w_{2}\in W_{i}$. Therefore, $a_{1}w_{1}+a_{2}w_{2}\in  \bigcap_{i=1}^{n}W_{i}$.

---

> [!lemma] Proposition 3
> Let $(W_{1},F)$ and $(W_{2},F)$ be linear subspaces of $(V,F)$. We define $$W_{1}+W_{2}:=\{ w_{1}+w_{2}:w_{1}\in W_{1},w_{2}\in W_{2} \}$$ Then, $(W_{1}+W_{2},F)$ is a linear subspace of $(V,F)$.

> [!proof]-
> For any $w_{1}+w_{2},w_{1}'+w_{2}'\in W_{1}+W_{2}$ and $a,a'\in F$, we have: $$a(w_{1}+w_{2})+a'(w_{1}'+w_{2}')=(aw_{1}+a'w_{1}')+(aw_{2}+a'w_{2}')\in W_{1}+W_{2}$$

---

> [!lemma] Proposition 4
> If $W$ is a finite-dimensional linear subspace of a normed linear space $(V,F,\|\cdot\|)$, then $W$ is [[Norm|closed]].

> [!proof]-
> As $W$ is finite-dimensional and therefore Banach, it is closed.

---

