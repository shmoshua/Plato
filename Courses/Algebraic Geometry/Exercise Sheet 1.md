#AlgebraicGeometry #Series 

#### Exercise 1
We have that:
1. for $x\in X$, we have that $x_{i}=x_{1}x_{i-1}$ for all $i=2,\dots,n$, i.e. $x=(x_{1},x_{1}^{2},\dots,x_{1}^n)$. Therefore, $$\pi ^{-1}:\mathbb{A}^{1}\to X,\quad a\mapsto (a,a^{2},\dots,a^n)$$is the inverse of $\pi$ given by: $\pi\pi ^{-1}(a)=a$ and $\pi ^{-1}\pi(x)=(x_{1},x_{1}^2,\dots,x_{1}^n)=x$ by above.
2. Consider the homomorphism: $$K[x_{1},\dots,x_{n}]\to K[x_{1}],\quad f\mapsto f(x_{1},x_{1}^{2}..,x_{1}^n)$$Then, as $K[x_{1}]\subseteq K[x_{1},\dots,x_{n}]$ it is surjective and the homomorphism admits $J$ as the kernel. Hence, $K[x_{1},\dots,x_{n}] / J\cong K[x_{1}]$ which is a PID. Hence, $J$ is a prime ideal.
3. As $J$ is prime hence radical, $J=I(V(J))=I(X)$ and the coordinate ring is given by: $$A(X)=K[x_{1},\dots,x_{n}] / J\cong K[x_{1}]$$

---
#### Exercise 2
Notice that we have: $$x_{1}^3-x_{2}^6=(x_{1}-x_{2}^2)(x_{2}^4+x_{1}x_{2}^2+x_{1}^{2}),\quad x_{1}x_{2}-x_{2}^3=x_{2}(x_{1}-x_{2}^2)$$Therefore, $(a,b)\in V(J)$ if and only if $a-b ^{2} = 0$ or if $b=0$ and $a^{2}=0$, i.e. $(a,b)=(0,0)$. As $(0,0)\in V(x_{1}-x_{2}^2)$, we have that: $$\sqrt{ J }=I(V(J))=I(V(x_{1}-x^2_{2}))=(x_{1}-x^2_{2})$$as this is prime. 

---
#### Exercise 3
This is given by the fact that $I(\cdot)$ and $V(\cdot)$ forms a bijection between single points and maximal ideals. The rest follows as $A(X)=K[x_{1},\dots,x_{n}] / I(X)$ is a field if and only if $I(X)$ is a maximal ideal.

---
#### Exercise 4
We have that:
1. Let $X_{1},X_{2},X_{3}$ be each axis. Then, $$I(X_{1}\cup X_{2}\cup X_{3})=I(X_{1})\cap I(X_{2})\cap I(X_{3})$$where $I(X_{1})=(x_{2},x_{3})$, $I(X_{2})=(x_{1},x_{3})$ and $I(X_{3})=(x_{1},x_{2})$. Then, $$(x_{2},x_{3})\cap(x_{1},x_{3})=(x_{1}x_{2},x_{1}x_{3},x_{2}x_{3},x_{3})=(x_{1}x_{2},x_{3})$$and $(x_{1}x_{2},x_{3})\cap(x_{1},x_{2})=(x_{1}x_{2},x_{1}x_{3},x_{2}x_{3})=I(X)$.
2. 