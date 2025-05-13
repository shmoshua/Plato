#Roadmap #Algorithms 

### 1. Basic Optimization

![[Optimization Problem#^228705]]
![[Optimization Problem#^72e4bb]]

---
#### 1.1. Convex Sets and Convex Functions
![[Convex Set#^a3c9f3]]

---
![[Convex Function#^c94c8e]]

---
![[Taylor's Theorem#^baca64]]

---
##### 1.1.1 First Order Convexity
![[Convex Function#^4455df]]
![[Convex Function#^7dbca8|p]]

---
##### 1.1.2 Conditions for Optimality
![[Stationary Point#^ea5579]]

---
![[Stationary Point#^2510d3]]
![[Stationary Point#^a5cce7|p]]

---
![[Stationary Point#^6b3517]]
![[Stationary Point#^7d64c2|p]]

---
##### 1.1.3 Second Order Convexity
![[Positive Definite#^fd40d2]]

---
![[Spectral Theorem#^9a1dbe]]
![[Spectral Theorem#^9514ed]]

---
![[Positive Definite#^39de24]]
![[Positive Definite#^a74f2b|p]]

---
![[Positive Definite#^0e2d57]]


---





$f:S\subseteq \mathbb{R}^n\to \mathbb{R}$ is ***twice differentiable*** at $x\in S$ if there exists $M\in \text{Mat}_{n,n}(\mathbb{R})$ s.t. $$f(x+\delta)=f(x)+(\nabla f_{9}x)^\top \delta+\frac{1}{2}\delta^\top M\delta+o(\left\| \delta \right\| ^{2}_{2}),\quad \forall\delta\in \mathbb{R}^n$$
Then, there exists a symmetric matrix $M$ s.t. the property above holds. If $M$ is not symmetric, we can replace it by $(M+M^\top) / 2$.