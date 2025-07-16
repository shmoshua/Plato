#Definition #AlgebraicTopology 

> [!definition]
> Let $X$ be a [[topological space]] and $R$ a [[ring]].
> 1. the ***cup product*** is an operation: $$\cup:H^p(X;R)\otimes  H^q(X;R)\to H^{p+q}(X;R),\quad \alpha \otimes  \beta\mapsto d^{*}(\alpha \times\beta)$$where $d:X\to X\times X,x\mapsto (x,x)$ is the diagonal map and $\alpha \times\beta$ is the [[cross product]].
- **Remark**: $\alpha \cup \beta$ is independent of the choice of $\Theta$ from [[Singular Homology|EZ theorem]] as $\alpha \times\beta$ is.

---
##### Properties
> [!lemma] Proposition 1 (Properties of Cup Product)
> For $\alpha\in H^p(X;R)$, $\beta\in H^q(X;R)$ and $\gamma\in H^r(X;R)$:
> 1. **graded commutativity**: $\alpha \cup \beta=(-1)^{pq}(\beta \cup \alpha)$.
> 2. **associativity**: $(\alpha \cup\beta)\cup\gamma=\alpha \cup(\beta \cup\gamma)$.
> 3. **unity**: $\alpha \cup 1=1\cup \alpha=\alpha$.

---
> [!lemma] Proposition 2 (Cup Product and Cross Product)
> Let $X,Y$ be topological spaces.
> 1. Let  $\alpha_{1}\in H^p(X;R), \alpha_{2}\in H^q(X;R)$ and $\beta_{1}\in H^r(Y;R),$ and $\beta_{2}\in H^s(Y;R)$. Then, 
> $$(\alpha_{1}\times\beta_{1})\cup(\alpha_{2}\times\beta_{2})=(-1)^{\left| \beta_{1} \right| \left| \alpha_{2} \right| }(\alpha_{1}\cup\alpha_{2})\times(\beta_{1}\cup\beta_{2})$$
> 2. Let $\pi_{X}:X\times Y\to X$ and $\pi_{Y}:X\times Y\to Y$ be projections. For $\alpha\in H^p(X;R)$ and $\beta\in H^q(Y;R)$, 