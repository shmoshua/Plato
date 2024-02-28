#Definition #Topology 

> [!definition]
> Let $(X,\mathcal{T})$ be a [[Topological Space|topological space]] and  $A \subseteq X$. The ***interior*** $A^\circ$ of $A$ is defined as: $$A^\circ :=\{ x\in A:A\text{ is a neighborhood of }x \}$$
- **Remark**: In a [[Metric Space|metric space]], $A^\circ=\{ x\in A:\exists r>0. B_{<r}(x)\subseteq A \}$
---
##### Properties
> [!lemma] Proposition 1
> For any set $A\subseteq X$, $A^\circ$ is the largest open set contained in $A$.

> [!proof]-
> We first show that $A^\circ$ is open. For any $x\in A^\circ$, let $r>0$ s.t. $B(x,r)\subseteq A$. For any $y\in B(x,r)$, then $B(y,r-d(x,y))\subseteq B(x,r)\subseteq A$. Therefore, $y\in A^\circ$ and $B(x,r)\subseteq A^\circ$. This shows that $A^\circ$ is open.
> 
> Now, we show that if $B\subseteq A$ is open, then $B\subseteq A^\circ$. For any $x\in B$, there exists $r>0$ s.t. $B(x,r)\subseteq B\subseteq A$. Therefore, $x\in A^\circ$. Therefore, $B \subseteq A^\circ$. 
---
> [!lemma] Proposition 2
> For $A,B\subseteq X$:
> 1. $A$ is open if and only if $A=A^\circ$.
> 2. $(A^\circ)^\circ=A^\circ$.
> 3. If $A\subseteq B$, then $A^\circ \subseteq B^\circ$.
> 4. $(A\cap B)^\circ=A^\circ \cap B^\circ$

> [!proof]-
> We prove as follows: 
> 1. If $A=A^\circ$, then $A$ is open by Proposition 1. Conversely, if $A$ is open, $A$ is the largest open set contained in $A$, i.e. $A=A^\circ$.
> 2. $A^\circ$ is open, therefore, $A^\circ=(A^\circ)^\circ$.
> 3. Let $x\in A^\circ$. Then, there exists $r>0$ s.t. $B(x,r)\subseteq A\subseteq B$. Therefore, $x\in B^\circ$ and $A^\circ \subseteq B^\circ$.
> 4. Let $x\in (A\cap B)^\circ$. Then, there exists $r>0$ s.t. $B(x,r)\subseteq A\cap B$. Therefore, $B(x,r)\subseteq A$ and $B(x,r)\subseteq B$. It follows that $x\in A^\circ \cap B^\circ$.
>    
>    Conversely, if $A^\circ \cap B^\circ$, we have that $A^\circ \cap B^\circ \subseteq A\cap B$ and $A^\circ \cap B^\circ$ is open. Therefore, $$A^\circ  \cap B^\circ  = (A^\circ  \cap B^\circ )^\circ  \subseteq (A \cap B)^\circ $$
> 	   It follows that $(A \cap B)^\circ =A^\circ \cap B^\circ$.
---
