#Definition #AlgebraicTopology 

> [!definition]
> Let $\mathcal{A},\mathcal{B}$ be [[Cochain Complex|cochain complexes]].
> 1. Cochain maps $\phi,\psi:\mathcal{A}\to \mathcal{B}$ are ***cochain homotopic*** if there exists a sequence of homomorphisms $D:A^n\to B^{n-1}$ for all $n\in \mathbb{Z}$ s.t. $$\delta_{B} D+D\delta_{A}=\phi-\psi$$
> 	$D$ is then called a ***cochain homotopy*** and denoted $\phi \underset{ D }{ \sim }\psi$.
> 2. A cochain map $\phi:\mathcal{A}\to \mathcal{B}$ is a ***cochain homotopy equivalence*** if there exists a cochain map $\psi:\mathcal{B}\to \mathcal{A}$ s.t. $\phi \circ\psi \sim \text{id}_{\mathcal{B}}$ and $\psi \circ\phi \sim \text{id}_{\mathcal{A}}$.
> 3. A cochain map $\phi:\mathcal{A}\to \mathcal{B}$ is ***null cochain homotopic*** if $\phi \sim 0$. 

^4bb319

---
##### Properties
> [!lemma] Proposition 1
> Let $\mathcal{A},\mathcal{B}$ be cochain complexes.
> 1. if $\phi \sim \psi$ then $\phi_{*}=\psi_{*}:H^{*}(\mathcal{A})\to H^{*}(\mathcal{B})$.
> 2. $\sim$ is an equivalence relation. 
> 3. If $\phi:\mathcal{A}\to \mathcal{B}$ is a cochain homotopy equivalence with inverse $\psi$, then $\phi ^{*},\psi ^{*}$ are isomorphisms with $(\phi ^{*})^{-1}=\psi ^{*}$.
> 4. If $\phi:\mathcal{A}\to \mathcal{B}$ is null cochain homotopic, then $\phi ^{*}=0$.

^24d8c9

> [!proof]-
> We have that:
> 1. Let $a\in A^i$ be a cocycle. Then, $\delta(a)=0$. Therefore, $\phi(a)-\psi(a)=\partial D(a)\in B^n(\mathcal{B})$. Hence, $$\phi ^{*}([a])=[\phi(a)]=[\psi(a)]=\psi ^{*}([a])$$
> 2. For $\phi,\psi,\eta:\mathcal{A}\to \mathcal{B}$ cochain maps, 
> 	1. For $D=0$, $\partial D+D\partial=0=\phi-\phi$. 
> 	2. If $\partial D+D\partial=\phi-\psi$ then $\partial(-D)+(-D)\partial=\psi-\phi$.
> 	3. If $\partial D+D\partial=\phi-\psi$ and $\partial D'+D'\partial=\psi-\eta$, then, $$\partial(D+D')+(D+D')\partial=\phi-\eta$$
> 3. We have that $\phi \circ\psi \sim \text{id}_{\mathcal{B}}$ and $\phi ^{*}\circ\psi ^{*}=\text{id}$ and vice versa.
> 4. Obvious.

^5c1240

---
