#Definition #RepresentationTheory 

> [!definition]
> Given a $K$-vector space $V$, the ***tensor algebra*** is given as: $$TV:=\bigoplus_{n\geq 0}V^{\otimes n} $$with multiplication as $ab=a\otimes b$ for $a\in V^{\otimes n},b\in V^{\otimes m}$.
---
##### Examples
> [!h] Example 1
> We have that:
> 1. **Symmetric algebra**: $SV:=TV / \braket{ v\otimes w-w\otimes v\ |v,w\in V  }$
> 2. **Exterior algebra**: $\land V:=TV / \braket{ v\otimes v\ |v\in V  }$
> 3. [[Universal Enveloping Algebra]]: $\land V:=TV / \braket{ v\otimes w-w\otimes v-[v,w]\ |v,w\in V  }$ if $V$ is a [[Lie algebra]].