#Definition #LST 

> [!definition]
> A ***$\mathbb{K}$-vector space*** $(V,\oplus,\odot)$ is a set of vectors $V$ equipped with two binary operations, $\oplus:V\times V \to V$ (vector addition) and $\odot:\mathbb{K} \times V \to V$ (scalar multiplication) s.t.:
> 1. **Associativity** of $\oplus$: for all $x,y,z\in V$: $x\oplus(y\oplus z)=(x\oplus y)\oplus z$
> 2. **Commutativity** of $\oplus$: for all $x,y\in V$: $x\oplus y=y\oplus x$.
> 3. **Identity** of $\oplus$: there exists $\theta\in V$ s.t. for all $x\in V$: $x\oplus\theta = x$
> 4. **Inverse** of $\oplus$: for every $x\in V$ there exists $\ominus x\in V$ s.t. $x\oplus(\ominus x)=\theta$.
> 5. **Associativity** of $\odot$: for all $a,b\in \mathbb{K}$ and $x\in V$: $a\odot (b\odot x)=(ab)\odot x$
> 6. **Identity** of $\odot$: for the identity of $1\in \mathbb{K}$: for all $x\in V$: $1\odot x=x$.
> 7. **Distributivity** of $\odot$: for all $a,b\in \mathbb{K}$ and $x,y\in V$, $$(a+b)\odot x=a\odot x\oplus b\odot x\quad \text{and}\quad a\odot(x\oplus y)=(a\odot x) \oplus (a \odot y)$$
---
##### Construction
- For a field $(F,+,\cdot )$, $(F,F,+,\cdot)$ is a linear space.
- The identity $\theta$ is unique and the inverse $\ominus x$ is also unique for each $x\in V$.

> [!lemma] Fact LinSpace.1
> If $(V,F,\oplus,\odot)$ is a vector space and $0$ is the additive identity of $F$, then the following holds:
> 1. for all $x\in V$: $0 \odot x=\theta$.
> 2. for all $a\in F$ and $x\in V$: $(-a)\odot x=\ominus(a\odot x)=a \odot(\ominus x)$

> [!proof]-
> We have that for all $x\in V$
> 1. $x + 0 \odot x =1\odot x+0\odot x=(1+0)\odot x=1\odot x=x$. Therefore, $0\odot x=\theta$.
> 2. $$\begin{align}(-a)\odot x&=((-a)\odot x)\oplus \theta\\&=((-a)\odot x)\oplus (a\odot x)\oplus (\ominus (a\odot x)) \\&=((-a+a)\odot x) \oplus  (\ominus (a\odot x)) \\&=(0\odot x) \oplus  (\ominus (a\odot x)) \\&=\theta \oplus  (\ominus (a\odot x)) \\&= \ominus (a\odot x) \end{align}$$

---
##### Related Definitions
- [[Product Space]]
- [[Vector Subspace]]