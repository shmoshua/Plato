#Series #FunctionalAnalysis 

> [!def] Problem 1
> Let $F$ be a finite abelian group. Prove $\widehat{F}\cong F$.

We show that: $$\begin{array}{cccc} {J:}&{F}&\to&{\widehat{F}}\\&{x} &\mapsto & {y\mapsto \exp(2\pi i \text{ord}(y)/\text{ord}(x))} \end{array}{}$$is an isomorphism. We first have that: $$J(xy)(z)=\exp \left( 2\pi i \frac{\text{ord}(z)}{\text{ord}(xy)} \right) =\exp\left( 2\pi i \frac{\text{ord}(z)}{\text{ord}(x)} \right)=J(x)(z)J(y)(z)$$