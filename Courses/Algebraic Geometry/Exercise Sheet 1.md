#AlgebraicGeometry #Series 

#### Exercise 1
We have that:
1. for $x\in X$, we have that $x_{i}=x_{1}x_{i-1}$ for all $i=2,\dots,n$, i.e. $x=(x_{1},x_{1}^{2},\dots,x_{1}^n)$. Therefore, $$\pi ^{-1}:\mathbb{A}^{1}\to X,\quad a\mapsto (a,a^{2},\dots,a^n)$$is the inverse of $\pi$ given by: $\pi\pi ^{-1}(a)=a$ and $\pi ^{-1}\pi(x)=(x_{1},x_{1}^2,\dots,x_{1}^n)=x$ by above.
2. Consider the homomorphism: $$K[x_{1},\dots,x_{n}]\to K[x_{1}],\quad f\mapsto f(x_{1},x_{1}^{2}..,x_{1}^n)$$Then, as $K[x_{1}]\subseteq K[x_{1},\dots,x_{n}]$ it is surjective and the homomorphism admits $J$ as the kernel. Hence, $K[x_{1},\dots,x_{n}] / J\cong K[x_{1}]$ which is a PID. Hence, $J$ is a prime ideal.
3. As $J$ is prime hence radical, $J=I(V(J))=I(X)$ and the coordinate ring is given by: $$A(X)=K[x_{1},\dots,x_{n}] / J\cong K[x_{1}]$$

---
