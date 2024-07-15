#Definition #Algebra

> [!definition]
> For a [[Ring|ring]] $R$ and an [[Ideal (Ring)|ideal]] $\mathfrak{a}\subseteq R$, $R / \mathfrak{a}$ is the ***quotient ring*** of $R$ w.r.t. $\mathfrak{a}$. 
> 
> We say that for $a,b\in R$, $a$ and $b$ are ***congruent modulo $\mathfrak{a}$***, i.e. $a\equiv b\mod \mathfrak{a}$, if $a-b\in \mathfrak{a}$. Then, $$\overline{a}:=\{ b\in R:a\equiv b\mod \mathfrak{a} \}=a+\mathfrak{a}$$is called the ***rest classes***.
---
##### Properties
> [!lemma] Proposition 1
> The map $$\begin{array}{cccc} {\pi:}&{R}&\to&{R / \mathfrak{a}}\\&{a} &\mapsto & {a+\mathfrak{a}} \end{array}{}$$defines a [[Ring Homomorphism]], called the*** natural homomorphism***.

>[!proof]-
>We have that: 
>1. Well-definedness: for $a+\mathfrak{a}=a'+\mathfrak{a}$ and $b+\mathfrak{a}=b'+\mathfrak{a}$, we have that $a-a'\in \mathfrak{a}$ and $b-b'\in\mathfrak{a}$. Therefore, 
>	$$\begin{align}ab-a'b'=(a-a')b +a'(b-b')\in\mathfrak{a}\end{align}$$Therefore, $(a+\mathfrak{a})(b+\mathfrak{a})=ab+\mathfrak{a}=a'b'+\mathfrak{a}=(a'+\mathfrak{a})(b'+\mathfrak{a})$.
---
##### Examples
- For $m\in \mathbb{N}$, $R=\mathbb{Z} / m\mathbb{Z}$, then: $\overline{a}\cdot \overline{b}=\overline{a\cdot b}$.