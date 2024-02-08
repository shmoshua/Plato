#Definition #MeasureTheory 

> [!definition]
> For $a,b\in\mathbb{R}^n$, the ***volume of the interval*** $(a,b)$ (or $[a,b]$, $(a,b]$, $[a,b)$) is defined as: $$\text{vol}(a,b)=\begin{cases}\prod_{i=1}^{n}(b_{i}-a_{i})\leq+\infty&\text{if }a_i<b_i\text{ for all }i\in[n]\\0&\text{otherwise}\end{cases}$$
> The ***volume of an elementary set***, i.e. a disjoint union of intervals $I:=\bigcup_{i=1}^{m}I_{i}$ for $I_{i}\cap I_{j}=\varnothing$ with $i \neq j$, is defined as: 
> $$\text{vol}(I)=\sum_{i=1}^{m}\text{vol}(I_{i})$$

- **Remark**: If we can partition $I$ into a different set of intervals, i.e. $I=\bigcup_{j=1}^{l}J_{j}$, then the volume is still conserved, i.e. $$\text{vol}(I)=\sum_{i=1}^{m}\text{vol}(I_{i})=\sum_{j=1}^{l}\text{vol}(J_{j})$$
- **Remark**: The [[Lebesgue Measure]] is the [[Pre-measure|Carathéodory-Hahn extension]] of the volume function.
---
 ##### Properties
> [!lemma] Theorem 1
> The system of elementary sets form an algebra $\mathcal{A}$. Then, $\text{vol}$ is an additive, $\sigma$-finite and a $\sigma$-additive function. 

> [!proof]+ Proof (Incomplete) (In the exercise)
---
