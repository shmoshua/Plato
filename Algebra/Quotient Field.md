#Definition #Algebra

> [!definition]
> For an [[integral domain]] $R$, let $\dot{R}:=R \backslash \{ 0 \}$. We define a binary relation $\sim$ on $R\times \dot{R}$ as follows: $$(a,b)\sim(a',b') \iff ab'=ba'$$Then, $\sim$ is an equivalence relation and: $$\text{Quot}(R)=\left\{   \frac{a}{b}:(a,b)\in R\times \dot{R}  \right\}$$where $\frac{a}{b}$ denotes the equivalence class of $(a,b)$. The ***field of quotients*** is a field $(\text{Quot}(R),+,\cdot)$ where: $$\frac{a}{b}+\frac{a'}{b'}=\frac{ab'+ba'}{bb'},\quad \frac{a}{b}\cdot \frac{a'}{b'}=\frac{aa'}{bb'}$$We further define: $$\begin{array}{cccc} {\iota:}&{R}&\to&{\text{Quot}(R)}\\&{a} &\mapsto & {\frac{a}{1_{R}}} \end{array}{}$$Then, $0_{Q}=\iota(0_{R})$ and $1_{R}=\iota(1_{R})$.
- **Remark**: $\text{Quot}(R)$ is the smallest field that includes $R$.
- **Remark**: There is a more general construction of a ring: A commutative ring $R$ can always be made into a subring of a larger ring $Q$ in which every non-zero non-zero divisor element in $R$ is a unit in $Q$.
---
##### Properties
> [!lemma] Proposition 1
> $(\text{Quot}(R),0_{Q},1_{Q},+,\cdot)$ is a [[Field|field]].

> [!proof]-
> Let $\frac{a}{b}\in \text{Quot}(R)\backslash\{ 0_{Q} \}$. Then, $a\neq 0_{R}$ and $a\in \dot{R}$. Therefore, $\frac{b}{a}\in \text{Quot}(R)$ and it holds that: $$\frac{a}{b}\cdot \frac{b}{a}=\frac{ab}{ba}=\frac{1}{1}=1_{Q}$$
---
> [!lemma] Theorem 2
> Let $R$ be a commutative ring. Further, let $D\neq \varnothing$ be a subset of $R$ which does not contain $0$ or any zero-divisors and is closed under multiplication. Then, there exists a commutative ring $Q$ s.t.:
> 1. $R$ is a subring of $Q$ and
> 2. $D\subseteq Q^{*}$
> 
> $Q$ is often denoted as $D^{-1}R$.
---
##### Examples
> [!h] Example 1
> We have:
> 1. For an integral domain $R$ and $D=\dot{R}$, $D^{-1}R=\text{Quot}(R)$.
> 2. For a commutative ring $R$ and $0\neq d\in R$ that is not a zero divisor, $D=\{ 1,d,d^{2},\dots \}$ then: $$D^{-1}R=R[ 1/d]$$
