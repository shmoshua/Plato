#Definition #Algebra 

> [!definition]
> We have that:
> 1. [[Abelian Group|Abelian groups]] $A,B,C$ and [[Group Homomorphism|homomorphisms]] $A\xrightarrow{i}B\xrightarrow{j} C$ forms an ***exact sequence*** if $\text{ker}(j)=\text{im}(i)$. 
> 2. A sequence $\cdots \to A_{k+1}\xrightarrow{f}A_{k}\xrightarrow{f}A_{k-1}\to \cdots$ of abelian groups is ***exact*** if every subsequence of 3 groups is exact.

^ce710c

- **Remark**: The [[Chain Complex|homology]] of an exact sequence is always zero. ^fcbe50
- **Related definition**: An exact sequence of the type $0\to A\xrightarrow{i} B\xrightarrow{j} C\to 0$ is called a ***short exact sequence (SES)***.  ^c2ad1a
---
##### Properties
> [!lemma] Proposition 1
> For abelian groups $A,B$ and a homomorphism $f$,
> 1. $0\to A\xrightarrow{f} B$ is exact if and only if $f$ is injective.
> 2. $A\xrightarrow{f} B\to 0$ is exact if and only if $f$ is surjective.
> 3. $0\to A\xrightarrow{f} B\to 0$ is exact if and only if $f$ is an isomorphism.

^75c17f

> [!proof]-
> Obvious.

^94e7ab

- **Corollary**: For a SES $0\to A\xrightarrow{i} B\xrightarrow{j} C\to 0$, $i$ is injective, $j$ is surjective and $j$ induces an isomorphism $B /i(A)\to C$.  ^729f68
---
#####