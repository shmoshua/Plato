#Definition #MeasureTheory 

> [!definition]
> Let $X$ be a set and $\mu$ a [[Positive Measure]] on $X$. Then, $x\in X$ is an ***atom*** of $\mu$ if 
> 1. $\{ x \}$ is [[Measurable Set|$\mu$-measurable]] and
> 2. $\mu(\{ x \})>0$
> 
> We denote the set of atoms with $A_{\mu}$.
---
##### Properties
> [!lemma] Proposition 1
> If $\mu(X)<+\infty$, $A_{\mu}$ is at most countable.

> [!proof]-
> For $n\in \mathbb{N}$, we define: $$A_{n}:=\left\{  x\in X:\{ x \}\text{ is measurable and }\mu(\{ x \})> \frac{1}{n}  \right\}$$Then, $A_{\mu}=\bigcup_{n\geq 1}^{}A_{n}$. If $A_{\mu}$ is not countable, then there exists $N\in \mathbb{N}$ s.t. $A_{N}$ is not countable. Let $(a_{i})_{i}$ be a sequence in $A_{N}$ s.t. $a_{i}\neq a_{j}$ for $i\neq j$. Then, $$ \infty =\sum_{i=1}^\infty\frac{1}{k}<\sum_{i=1}^\infty\mu(\{a_i\})\overset{*}{=}\mu(\{a_i\}_i)\le \mu(X) $$which is a contradiction.
---
