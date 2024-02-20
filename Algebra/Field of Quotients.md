#Definition #Algebra

> [!definition]
> For an [[integral domain]] $R$, let $\dot{R}:=R \backslash \{ 0 \}$. We define a binary relation $\sim$ on $R\times \dot{R}$ as follows: $$(a,b)\sim(a',b') \iff ab'=ba'$$Then, $\sim$ is an equivalence relation and: $$\text{Quot}(R)=\left\{   \frac{a}{b}:(a,b)\in R\times \dot{R}  \right\}$$where $\frac{a}{b}$ denotes the equivalence class of $(a,b)$. The ***field of quotients*** is a field $(\text{Quot}(R),+,\cdot)$ where: $$\frac{a}{b}+\frac{a'}{b'}=\frac{ab'+ba'}{bb'},\quad \frac{a}{b}\cdot \frac{a'}{b'}=\frac{aa'}{bb'}$$We further define: $$\begin{array}{cccc} {\iota:}&{R}&\to&{\text{Quot}(R)}\\&{a} &\mapsto & {\frac{a}{1_{R}}} \end{array}{}$$Then, $0_{Q}=\iota(0_{R})$ and $1_{R}=\iota(1_{R})$.
- **Remark**: $\text{Quot}(R)$ is the smallest field that includes $R$.
---
##### Properties
> [!lemma] Proposition 1
> $(\text{Quot}(R),0_{Q},1_{Q},+,\cdot)$ is a [[Field|field]].

> [!proof]+
> Let $\frac{a}{b}\in \text{Quot}(R)\backslash\{ 0_{Q} \}$. Then, $a\neq 0_{R}$ and $a\in \dot{R}$. Therefore, $\frac{b}{a}\in \text{Quot}(R)$ and it holds that: $$\frac{a}{b}\cdot \frac{b}{a}=\frac{ab}{ba}=\frac{1}{1}=1_{Q}$$
---
