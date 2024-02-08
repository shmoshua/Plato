#Definition #Topology 

> [!definition]
> For a [[Metric Space|metric space]] $(X,d)$, a subset $V \subseteq X$ is **open** if for every $x\in V$ there exists $\epsilon > 0$ s.t. the ball $$B(x,\epsilon):=\{ y\in X:d(x,y) \leq \epsilon \}$$
> lies completely in $V$. Then, the set $\mathcal{ O}(d)$ of all open subsets of $X$ are called the ***topology of the metric space*** $(X,d)$.
---
##### Properties

> [!lemma] Fact TopMet.1
> For a metric space $(X,d)$, $(X,\mathcal{O}(d))$ is a [[Topological Space| topological space]].

> [!proof]-
> We will show the three axioms:
> 1. $\varnothing$ is open by definition. For $X$, for any $x\in X$ and $\epsilon>0$, $B(x,\epsilon)\subseteq X$ by definition.
> 2. Let $\Lambda$ be an arbitrary index set and for all $\lambda\in \Lambda$, $S_{\lambda}$ is an open set. Then, for any point $x\in \bigcup_{\lambda\in \Lambda}^{}S_{\lambda}$, there exists some $\lambda'\in \Lambda$ and $\epsilon>0$ s.t. $B(x,\epsilon)\in S_{\lambda}\subseteq \bigcup_{\lambda\in\Lambda}^{}S_{\lambda}$.
> 3. Let $S_{1}$ and $S_{2}$ be two open subsets. Then, for any $x\in S_{1}\cap S_{2}$, we have $\epsilon_{1},\epsilon_{2}>0$ s.t. $B(x,\epsilon_{1})\subseteq S_{1}$ and $B(x,\epsilon_{2})\subseteq S_{2}$. Take $\epsilon:=\min \{  \epsilon_{1},\epsilon_{2} \}$. Then, $B(x,\epsilon)\subseteq S_{1}$ and $B(x,\epsilon)\subseteq S_{2}$, therefore, $B(x,\epsilon)\subseteq S_{1}\cap S_{2}$.
---
