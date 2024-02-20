#Definition #Algebra

> [!definition]
> Let $(G,\circ)$ and $(H,\bullet)$ be two groups and let $\varphi:G \to H$ be a function. $\varphi$ is a ***group homomorphism*** if for all $x,y\in G$: $$\varphi(x \circ y)=\varphi(x)\bullet \varphi(y)$$
> 
> - If $\varphi$ is bijective, $\varphi$ is called an ***isomorphism***.
> - If $G=H$, then $\varphi$ is called an ***endomorphism***.
> - If $G=H$ and $\varphi$ is bijective, $\varphi$ is called an ***automorphism***. The set of all automorphisms $\varphi$ on $G$ is denoted as $\text{Aut}(G)$.
---
##### Properties
> [!lemma] Proposition 1
> If $\varphi:G \to H$ is a homomorphism, then:
> 1. $\varphi(e_{G})=e_{H}$ and 
> 2. for all $x\in G$: $\varphi(x^{-1})=\varphi(x)^{-1}$ 
> 3. $\varphi[G]\leq H$

> [!proof]-
> We have:
> 1. $\varphi(x)=\varphi(xe)=\varphi(x)\varphi(e)$. Therefore, $\varphi(e)=e_{H}$.
> 2. $\varphi(x)\varphi(x ^{-1})=\varphi(xx ^{-1})=\varphi(e_{G})=e_{H}$.
> 3. for $\varphi(g),\varphi(h)\in \varphi[G]$, $gh^{-1}\in G$ and $\varphi(gh^{-1})=\varphi(g)\varphi(h)^{-1}\in \varphi[G]$.
---
> [!lemma] Proposition 2
> For a group $G$, $\text{Aut}(G)$ is a group.

> [!proof]-
> Let $\varphi,\psi,\theta\in \text{Aut}(G)$, then we need to show that:
> 1. $\varphi \circ\psi\in \text{Aut}(G)$ is bijective as the composition of bijective functions is bijective.
> 2. $\circ$ is associative as function composition is associative.
> 3. $\iota$ is a neutral element.
> 4. Every element has an inverse.
---
> [!lemma] Theorem 3 (First Isomorphism Theorem)
> Let $\psi:G \to H$ be a homomorphism s.t. $\text{ker}(\psi)=N$ and $\pi:G \to G / N$ the natural homomorphism. Then, there exists exactly one isomorphism $$ \varphi:G / N \to \text{Im}(\psi)$$ s.t. $\psi=\varphi \circ\pi$. In other words, we have that $$\text{Im}(\psi)\cong G / \text{ker}(\psi)$$

> [!proof]-
> Let's define $\varphi:G / N \to H$ s.t. for all $x\in G$: $$\varphi(xN):=\psi(x)$$ 
> Then, it holds that: $$\psi(x)=\varphi(xN)=\varphi(\pi(x))=(\varphi \circ \pi)(x)$$
> We will then show the well-definedness of $\varphi$. If $xN=yN$ for $x,y\in G$, then $x^{-1}y\in N$. 
> As $N=\text{ker}(\psi)$, we have that: $$e_{H}=\psi(x^{-1}y)=\psi(x^{-1})\psi(y)=\psi(x)^{-1}\psi(y)$$ and therefore $\varphi(xN)=\psi(x)=\psi(y)=\varphi(yN)$.
> 
> We further show that $\varphi$ is a homomorphism. 
> $$ \varphi(xNyN)=\varphi(xyN)=\psi(xy)=\psi(x)\psi(y)=\varphi(xN)\varphi(yN)$$
> Thirdly, we show that $\varphi$ is bijective. We have: $$\begin{align}\varphi(xN)&=\varphi(yN)\\ \psi(x)&=\psi(y)\\e_{H}&=\psi(x)^{-1}\psi(y)\\e_{H}&=\psi(x^{-1}y)\\x^{-1}y&\in \text{ker}(\psi)\end{align}$$
> which implies that $xN=yN$. Similarly, $\varphi$ is surjective as $\psi$ is surjective we have for every $z\in H$ that there exists $x\in G$ s.t. $\psi(x)=z$. Therefore, $\varphi(xN)=\psi(x)=z$ and $\varphi$ is surjective.
> 
> Lastly, we will show that $\varphi$ is unique. Let $\varphi':G / N \to H$ be a different isomorphism s.t. $\varphi'\circ \pi = \psi$. Let $xN\in G / N$ be arbitrary. Then, $$\varphi'(xN)=(\varphi'\circ \pi)(x)=\psi(x)=(\varphi \circ \pi)(x)=\varphi(xN)$$
> Therefore, $\varphi'=\varphi$.
---
> [!lemma] Theorem 4 (Second Isomorphism Theorem)
> Let $N\unlhd G$ and $K\leq G$, then: 
> 1. $KN=NK\leq G$
> 2. $N\unlhd KN$
> 3. $(N\cap K)\unlhd K$
> 4. $K/(N\cap K)\cong KN / N$

> [!proof]-
> We have: 
> 1. [[Inner Product of Groups|Theorem 2]]
> 2. For $kn\in KN$ and $x\in N$: $$knxn^{-1}k^{-1}\in kNk^{-1}=N$$
> 3. For $k\in K$ and $x\in N\cap K$, $kxk^{-1}\in N$ as $x\in N$. Further, $kxk^{-1}\in K$ as $x\in K$.
> 4. We define $\varphi:K\to KN / N, k\mapsto kN$. Then, 
> 	- $\varphi(k_{1}k_{2})=k_{1}k_{2}N=(k_{1}N)(k_{2}N)=\varphi(k_{1})\varphi(k_{2})$
> 	- for $knN=kN\in KN / N$, $\varphi(k)=kN$, i.e. $\text{Im }\varphi=KN / N$.
> 	- $\text{ker }\varphi=\{ k\in K:\varphi(k)=kN=N \}=N\cap K$

---
> [!lemma] Theorem 5 (Third Isomorphism Theorem)
> Let $K,N\unlhd G$ and $N\unlhd K$. Then, 
> 1. $K / N\unlhd G / N$ and
> 2. $G / K\cong (G / N) / (K / N)$

> [!proof]-
> We have: 
> 1. for any $gN\in G / N$ and $kN\in K / N$, $$(gN)(kN)(g^{-1}N)=(gkg^{-1})N\in K / N$$
> 2. We define the isomorphism $$\begin{array}{cccc} {\varphi:}&{G}&\to&{(G / N) / (K / N)}\\&{x} &\mapsto & {(xN)(K / N)} \end{array}{}$$
> 	Then, 
> 	- $\varphi(xy)=(xyN)(K / N)=(xN)(K / N)(yN)(K/N)=\varphi(x)\varphi(y)$
> 	- for $(xN)(K / N)\in (G / N) / (K / N)$, $\varphi(x)=(xN)(K / N)$.
> 	- $\text{ker }\varphi=\{ x\in G: (xN)(K / N)=K / N \}=\{ x\in G: (xN)\in K / N \}=K$
---