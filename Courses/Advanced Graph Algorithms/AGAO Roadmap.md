#Roadmap #Algorithms 

### 1. Basic Optimization

![[Optimization Problem#^228705]]
![[Optimization Problem#^72e4bb]]

---
#### 1.1. Convex Sets
![[Convex Set#^a3c9f3]]
![[Convex Function#^c94c8e]]


---


$f:S\subseteq \mathbb{R}^n\to \mathbb{R}$ is ***twice differentiable*** at $x\in S$ if there exists $M\in \text{Mat}_{n,n}(\mathbb{R})$ s.t. $$f(x+\delta)=f(x)+(\nabla_{x}f)^\top \delta+\frac{1}{2}\delta^\top M\delta+o(\left\| \delta \right\| ^{2}_{2}),\quad \forall\delta\in \mathbb{R}^n$$
Then, there exists a symmetric matrix $M$ s.t. the property above holds. If $M$ is not symmetric, we can replace it by $(M+M^\top) / 2$.