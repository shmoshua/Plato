#Algebra #Definition 

> [!definition]
> Let $R$ be a [[ring]]. The ***nilradical*** of $R$ is defined as the [[Radical (Ring)|radical]] of $(0)$, i.e.: $$\sqrt{ (0) }:=\{ a\in R: a^n=0\text{ for some }n\in \mathbb{N} \}$$

^2063c5

- **Related definition**: The elements of the nilradical are called ***nilpotent***. ^107274
- **Related definition**: A ring $R$ is ***reduced*** if $\sqrt{ (0) }=(0)$, i.e. $(0)$ is radical. ^417ef2
- **Remark**: the nilradical is given by $\sqrt{ (0) }=\bigcap_{P\unlhd R, P\text{ prime}}^{} P$. (cf. [[Radical (Ring)|Lemma 2]])
---
##### Property
> [!lemma] Lemma 1
> For a ring $R$ and $I\unlhd R$, TFAE:
> 1. $I$ is radical.
> 2. $R / I$ is reduced.

^ec2c2e

> [!proof]-
> Obvious as $(0)_{R / I} = I$. 

^f5705d

---