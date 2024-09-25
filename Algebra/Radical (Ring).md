#Definition #Algebra 

> [!definition]
> For a [[ring]] $R$ and an [[Ideal (Ring)|ideal]] $I\unlhd R$, the ***radical*** of $I$ is: $$\sqrt{ I }:=\{ a\in R\ | \exists n\in \mathbb{N}: a^n \in I\}$$

^134f35

- **Related definition**: An ideal is a ***radical ideal*** if $\sqrt{ I }=I$. ^3cd183
---
##### Properties
> [!lemma] Proposition 1:
> For any ideal $I\unlhd R$,
> 1. $\sqrt{ I }\unlhd R$. 
> 2. $\sqrt{ I }\supseteq I$
> 3. $\sqrt{ I }$ is a radical ideal.

^ef8725

> [!proof]-
> We have:
> 1. Let $a,b\in \sqrt{ I }$ where $a^n,b^m\in I$. Then, $$(a+b)^{n+m}=\sum_{k=0}^{n+m}{n+m \choose k}a^kb^{n+m-k}$$As for each summand either $k\geq n$ or $n+m-k>m$, we have that $(a+b)^{n+m}\in I$. Further, for $r\in R$ and $a^n\in I$, $(ra)^n=r^na^n\in I$. Therefore, $\sqrt{ I }$ is an ideal.
> 2. Let $a\in \sqrt{  (\sqrt{ I })}$. Then, $a^n\in \sqrt{ I }$ and $a^{mn}\in I$. Therefore, it holds that $a\in \sqrt{ I }$.

^ac2252

---
##### Examples
> [!h] Example 1
> We have:
> 1. $\sqrt{ (x^2) }=(x)$.

^1e2e72
