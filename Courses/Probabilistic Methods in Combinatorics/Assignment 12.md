#Series #ProbabilisticMethods 

##### Problem 1

Let for any edge $e\in E(G)$, $A_{e}$ be the event that $e\nsubseteq S$. Then, notice that $A_{e}$ is an decreasing event for any $e\in E$. Indeed, for any sets $T\subseteq S\subseteq V(G)$, if $e \nsubseteq S$ then $e \nsubseteq T$. Therefore, by correlation inequality, $$\mathbb{P}(S\text{ is an independent set}) = \mathbb{P}\left( \bigcap_{e\in E(G)} A_{e} \right)\geq \prod_{e\in E(G)}^{}\mathbb{P}(A_{e})=\left( \frac{3}{4} \right) ^m$$

---
##### Problem 2
For $x\in[n]$ and $i,j\in[k]$ with $i\neq j$, $$\mathbb{P}(x\notin S_{i}\cap S_{j})=1-\mathbb{P}(x\in S_{i}\cap S_{j})=1-\frac{1}{n}$$As these events are independent over all $x\in [n]$, $$\mathbb{P}(S_{i}\cap S_{j}=\varnothing)=\mathbb{P}(\forall x\in[n]:x\notin S_{i}\cap S_{j})=\left( 1-\frac{1}{n} \right) ^n \leq \frac{1}{e}$$and we have that $\mathbb{P}(S_i\cap S_{j}\neq \varnothing)\geq 1-\frac{1}{e}$. Further, these are all increasing events. For $T_{i}\subseteq S_{i}$ and $T_{j}\subseteq S_{j}$, if $T_{i}\cap T_{j}\neq\varnothing$ then $S_{i}\cap S_{j}\neq\varnothing$. Therefore, by correlation inequality: $$\mathbb{P}\left(\forall \{ i,j \}\in {[k] \choose 2}:S_{i}\cap S_{j}\neq\varnothing\right)\geq \prod_{\{ i,j \}\in {[k] \choose 2}}^{}\mathbb{P}(S_{i}\cap S_{j}\neq\varnothing)\geq \left( 1-\frac{1}{e} \right) ^{k \choose 2}$$

---
##### Problem 3
We first let $\mathbb{P}$ be the uniform probability measure on $2^{[n]}$. Then, for any $\mathcal{F}\subseteq 2^{[n]}$, $\mathbb{P}(\mathcal{F})=\left| \mathcal{F} \right| / 2^n$. 

For each $\mathcal{F}_{i}$, let $\mathcal{G}_{i}:=\{ X\subseteq[n]:  \exists F\in \mathcal{F}_{i},F\subseteq X\}\supseteq \mathcal{F_{i}}$. Then, $\mathcal{G}_{i}$ is increasing as for $X\subseteq Y$, if there exists $F\in \mathcal{F}_{i}$ with $F\subseteq X\subseteq Y$, then $Y\in \mathcal{G_{i}}$. Further, $\mathcal{G_{i}}$ is an intersecting family as for $A,B\in \mathcal{G}_{i}$, there exists $F,F'\in\mathcal{F_{i}}$ with $F\subseteq A$ and $F'\subseteq B$ where $F\cap F'\neq \varnothing$. Hence, $\mathcal{G}_{i}^c$ is decreasing and by correlation inequalities: 
$$\mathbb{P}(\mathcal{F}_{1}\cup\dots \cup \mathcal{F_{k}})\leq \mathbb{P}(\mathcal{G}_{1}\cup\dots \cup \mathcal{G_{k}})=1-\mathbb{P}(\mathcal{G}_{1}^c\cap\dots \cap \mathcal{G}_{k}^c)\leq 1-\frac{1}{2^k}$$where $\mathbb{P}(\mathcal{G}_{i})\leq 1/2$ follows from the lecture. This proves the statement.
---
##### Problem 4
Let $G\sim G(2k, 1 / 2)$. For $i\in\{ k,\dots,2k-1 \}$, let $A_{i}$ be the event that there exists a node $x\in V(G)$ with degree $i$. Then, $$\mathbb{P}(\exists x\in V(G):d(x)=i)\leq \sum_{x\in V(G)}\mathbb{P}(d(x)=i)=\sum_{x\in V(G)}{}$$
