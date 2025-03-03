#ProbabilityTheory 

#### 0. Serie 1 Feedback
1. Proving things with axiom, formality.

---
#### 2. Limit
1. Limsup and Liminf
	$$\limsup_{ n \to \infty }x_{n}=\inf \sup $$
2. Upper lower semicontinuity

---
#### 2. Bayes Theorem
1. A city owns two taxi companies: "green" which owns 300 cars and "yellow" which owns 500 cars. A car has made a crash and ran away from the accident area. There was a single witness who saw a yellow car. it is known that during same circumstances witnesses give correct feedback with a probability of 0.8. what is the probability that "yellow" company driver is the one who made a crash.
   
   Then, $A:=$ it was yellow taxi. $B$:= the witness saw yellow taxi.
   $$P(A|B)=\frac{P(B|A)P(A)}{P(B)}=\frac{0.8\cdot  \frac{5}{8}}{0.8\cdot  \frac{5}{8}+0.2\cdot \frac{3}{8}}=\frac{\frac{1}{2}}{\frac{1}{2}+\frac{3}{40}}=\frac{20}{23}$$


2. 10 students out of whom 4 are "good friends", ordered cinema spots in the last row which has 10 seats. All the "good friends" except for one arrived together and got spots next to one another. what is the probability of last friend getting a seat next to his friends?
   
   $A$:= He got a seat next to his friends, $B:=$ His 3 friends got a seat next to each other.
	$$P(A|B)=\frac{P(A\cap B)}{P(B)}=\frac{2\cdot 6 \cdot  7!}{6\cdot  8!}=\frac{1}{4}$$

---
#### 3. 
1. If $\mathbb{P}(A)\in\{ 0,1 \}$, then $A$ is independent of every other event.
   
   Let $\mathbb{P}(A)=1$. Then, $\mathbb{P}(A^c)=0$. Let $B\in \mathcal{F}$. Then, $$\mathbb{P}(B^c)\leq\mathbb{P}(A^c\cup B^c)\leq \mathbb{P}(A^c)+\mathbb{P}(B^c)=\mathbb{P}(B^c)$$$$\mathbb{P}(A\cap B)=1-\mathbb{P}(A^c\cup B^c)=1-\mathbb{P}(B^c)=\mathbb{P}(B)=\mathbb{P}(B)\mathbb{P}(A)$$
   If $\mathbb{P}(A)=0$, then $0\leq\mathbb{P}(A\cap B)\leq \mathbb{P}(A)=0$.If $\mathbb{P}(A)=1$.

2. $A$ is independent with $B$ iff $A$ is independent with $B^c$. $$\mathbb{P}(A\cap B^c)=\mathbb{P}(A)-\mathbb{P}(A\cap B)=\mathbb{P}(A)-\mathbb{P}(A)\mathbb{P}(B)=\mathbb{P}(A)\mathbb{P}(B^c)$$
3. A constant function is independent to every other event. 