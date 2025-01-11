#Definition #Topology 

> [!definition]
> Let $X,Y$ be [[topological space|topological spaces]]. For a continuous function $f:X\to Y$, 
> 1. the ***mapping cylinder*** $M_{f}$ is given by: $$M_{f}:=((X\times I)\sqcup Y) / {\sim}$$where $(x,0)\sim f(x)$ for all $x\in X$. 
---
##### Properties
> [!lemma] Proposition 1
> We have that: 
> 1. $\phi:M_{f}\to Z$ is continuous if and only if $\phi_{X\times I}:X\times I\to Z$ and $\phi_{Y}:Y\to Z$ are continuous.
> 2. Let: $$r:M_{f}\to Y,\quad [z]\mapsto\begin{cases}z&z\in Y\\f(x)&z=(x,t)\in X\times I\end{cases}$$be a retract. Then, $f=r\circ i_{X}$ and $\text{id}_{M_{f}}\sim i_{Y}\circ r$ where $i_{X}:X\to M_{f},x\mapsto [x,1]$ and $i_{Y}:Y\to M_{f}, y\mapsto [y]$

> [!proof]+
> We have that:
> 1. $\phi:M_{f}\to Z$ is continuous if and only if $q \circ\phi:(X\times I)\sqcup Y\to Z$ is continuous. This is again continuous if and only if $\phi_{X\times I}$ and $\phi_{Y}$ are continuous.
> 2. We have that $r$ is continuous as for $x\in X$, $r([x,0])=f(x)=r([f(x)])$. Then, $$r(i_{X}(x))=r([x,1])=f(x)$$Further, we have that $$i_{Y}(r([z])=\begin{cases}[z]&z\in Y\\ [f(x)]&z=(x,t)\in X \times I\end{cases}$$ We define: $$F:M_{f}\times I\to M_{f},\quad ([z],s)\mapsto \begin{cases}[z]&z\in Y\\ [(x,st)]& z=(x,t)\in X\times I\end{cases}$$which is continuous as: $$r([x,0],s)=[(x,0)]=[f(x)]=r([f(x)],s)$$Then, $F([z],0)=\begin{cases}[z]&z\in Y\\ [f(x)]&z=(x,t)\in X\times I\end{cases}$ and $F([z],0)=i_{Y}(r([z]))$ and $$F([z],1)=\begin{cases}[z]&z\in Y\\ [(x,t)]&z=(x,t)\in X\times I\end{cases}$$ and $F([z],1)=[z]$. This shows that $\text{id}_{M_{f}} \sim i_{Y} \circ r$ and 