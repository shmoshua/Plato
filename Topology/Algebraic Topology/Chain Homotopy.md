#Definition #AlgebraicTopology 

> [!definition]
> Let $\mathcal{A},\mathcal{B}$ be [[Chain Complex|chain complexes]].
> 1. Chain maps $\phi,\psi:\mathcal{A}\to \mathcal{B}$ are ***chain homotopic*** if there exists a sequence of homomorphisms $D:A_{n}\to B_{n+1}$ for all $n\in \mathbb{Z}$ s.t. $$\partial D+D\partial=\phi-\psi$$
> 	$D$ is then called a ***chain homotopy*** and denoted $\phi \underset{ D }{ \sim }\psi$.
> 2. A chain map $\phi:\mathcal{A}\to \mathcal{B}$ is a ***chain homotopy equivalence*** if there exists a chain map $\psi:\mathcal{B}\to \mathcal{A}$ s.t. $\phi \circ\psi \sim \text{id}_{\mathcal{B}}$ and $\psi \circ\phi \sim \text{id}_{\mathcal{A}}$.
> 3. A chain map $\phi:\mathcal{A}\to \mathcal{B}$ is ***null chain homotopic*** if $\phi \sim 0$. 

^4bb319

---
##### Properties
> [!lemma] Proposition 1
> Let $\mathcal{A},\mathcal{B}$ be chain complexes.
> 1. if $\phi \sim \psi$ then $\phi_{*}=\psi_{*}:H_{*}(\mathcal{A})\to H_{*}(\mathcal{B})$.
> 2. $\sim$ is an equivalence relation. 
> 3. If $\phi:\mathcal{A}\to \mathcal{B}$ is a chain homotopy equivalence with inverse $\psi$, then $\phi_{*},\psi_{*}$ are isomorphisms with $\phi_{*}^{-1}=\psi_{*}$.
> 4. If $\phi:\mathcal{A}\to \mathcal{B}$ is null chain homotopic, then $\phi_{*}=0$.

^24d8c9

> [!proof]-
> We have that:
> 1. Let $a\in A_{i}$ be a cycle. Then, $\partial [a]=0$. Therefore, $\phi(a)-\psi(a)=\partial D(a)\in B_{n}(\mathcal{B})$. Hence, $$\phi_{*}(a)=[\phi(a)]=[\psi(a)]=\psi_{*}(a)$$
> 2. For $\phi,\psi,\eta:\mathcal{A}\to \mathcal{B}$ chain maps, 
> 	1. For $D=0$, $\partial D+D\partial=0=\phi-\phi$. 
> 	2. If $\partial D+D\partial=\phi-\psi$ then $\partial(-D)+(-D)\partial=\psi-\phi$.
> 	3. If $\partial D+D\partial=\phi-\psi$ and $\partial D'+D'\partial=\psi-\eta$, then, $$\partial(D+D')+(D+D')\partial=\phi-\eta$$
> 3. We have that $\phi \circ\psi \sim \text{id}_{\mathcal{B}}$ and $\phi_{*}\circ\psi_{*}=\text{id}$ and vice versa.
> 4. Obvious.

^5c1240

---
