#Definition #MeasureTheory 

> [!definition]
> Let $(\Omega,\mathcal{F},\mu)$ be a [[measure space]]. Then,
> 1. For an unsigned measurable [[simple function]] $f:\Omega\to[0,+\infty]$ given by $f=\sum_{i=1}^{n}a_{i}\chi_{E_{i}}$ with $a_{n}\in [0,+\infty]$, $$\int_{\Omega}f \, d\mu:=\sum_{i=1}^{n}a_{i}\mu(E_{i}) $$
> 2. For an unsigned measurable function $f:\Omega\to[0,+\infty]$, $$\int_{\Omega}^{} f \, d\mu:=\sup_{0\leq g\leq f, g\in \mathcal{S}(\Omega)}\int_{\Omega}^{} g \, d\mu  $$
> 3. For a real-valued absolutely integrable function $f:\Omega\to \mathbb{R}$, i.e. $\int_{\Omega}^{} \left| f \right| \, d\mu<+\infty$, then $f=f_{1}-f_{2}$ for $f_{1},f_{2}$ unsigned absolutely integrable and: $$\int_{\Omega}f \, d\mu:=\int_{\Omega}^{} f_{1} \, d\mu-\int_{\Omega}^{} f_{2} \, d\mu$$
> 4. For a complex-valued absolutely integrable function $f:\Omega\to \mathbb{C}$, i.e. $\int_{\Omega}^{} \left| f \right| \, d\mu<+\infty$, $$\int_{\Omega}f \, d\mu:=\int_{\Omega}^{} \text{Re}(f) \, d\mu+i\int_{\Omega}^{} \text{Im}(f) \, d\mu$$
---
##### Properties
> [!lemma] Lemma 1 (Properties of the Lebesgue Integral for Simple Functions)
> Let $f,g:\Omega\to[0,+\infty]$ be unsigned measurable simple functions and $c\in [0,+\infty]$. Then, 
> 1. $\int_{\Omega}^{} f \, d\mu$ is well-defined.
> 2. **linearity**: $\int_{\Omega}^{} f+g \, d\mu=\int_{\Omega}^{} f \, d\mu+\int_{\Omega}^{} g \, d\mu$ and $\int_{\Omega}^{} cf \, d\mu=c\int_{\Omega}^{} f \, d\mu$
> 3. $\int_{\Omega}^{} f \, d\mu\geq 0$ with equality if and only if $f=0$ almost everywhere.
> 4. if $f=g$ almost everywhere, $\int_{\Omega}^{} f \, d\mu=\int_{\Omega}^{} g \, d\mu$.
> 5. if $f\leq g$ almost everywhere, $\int_{\Omega}f  \, d\mu\leq \int_{\Omega}^{} g \, d\mu$.
> 6. **Markov inequality**: for any $0<t<+\infty$, $$\mu(\{ \omega\in \Omega: f(\omega)\geq t \})\leq \frac{1}{t}\int_{\Omega}^{} f \, d\mu $$

> [!proof]-
> We have:
> 1. Let $f=\sum_{i=1}^{n}a_{i}\chi_{E_{i}}=\sum_{j=1}^{m}b_{j}\chi_{F_{j}}$. First, let's assume that $F_{j}$ are disjoint and non-empty. Then, we know that $E_{i}$ is expressible as the union of the subcollection of $F_{j}$s. By grouping them appropriately we have that: $$\sum_{i=1}^{n}a_{i} \mu(E_{i})=\sum_{j=1}^{m}b_{j}\mu(F_{j})$$
>    Now, if $F_{j}$ are not disjoint, we can refactor them into finite number of disjoint sets. therefore, we get that the integral is well-defined.
> 2. Holds trivially from simple functions and the integral definition. 
> 3. It is trivially non-negative. If $\int_{\Omega}^{} f \, d\mu=\sum_{i=1}^{n}a_{i}\mu(E_{i})=0$, then for all $i$ either $\mu(E_{i})=0$ or $a_{i}=0$. Hence, $f=0$ almost everywhere. Conversely, if $f$ is $0$ almost everywhere, we have that $\int_{\Omega}^{} f \, d\mu=0$. 
> 4. if $f=g$ almost everywhere $f-g=0$ almost everywhere and by 3 $\int_\Omega f-g  \, d\mu=0$. By linearity, $\int_{\Omega}^{} f \, d\mu=\int_{\Omega}^{} g \, d\mu$.
> 5. if $f\leq g$ almost everywhere, let: $h:=\max(0,g-f)$ which is a unsigned measurable simple function where $f+h=g$ almost everywhere. Therefore, $$\int_{\Omega}^{} f \, d\mu \leq \int_{\Omega}^{} f+h \, d\mu =\int_{\Omega}^{} g \, d\mu $$
> 6. For any $0<t<+\infty$, let $E:=\{ \omega\in \Omega:f(\omega)\geq t \}$ which is measurable. Then, $t\chi_{E}\leq f$ almost everywhere and: $$t\mu(E)\leq \int_{\Omega} f \, d\mu $$
---
> [!lemma] Lemma 2 (Properties of the Lebesgue Integral for Unsigned Functions)
> Let $f,g:\Omega\to[0,+\infty]$ be unsigned measurable functions and $c\in [0,+\infty]$. Then, 
> 1. **superadditivity**: $\int_{\Omega}^{} f+g \, d\mu\geq\int_{\Omega}^{} f \, d\mu+\int_{\Omega}^{} g \, d\mu$ and $\int_{\Omega}^{} cf \, d\mu=c\int_{\Omega}^{} f \, d\mu$
> 3. $\int_{\Omega}^{} f \, d\mu\geq 0$ with equality if and only if $f=0$ almost everywhere.
> 4. if $f=g$ almost everywhere, $\int_{\Omega}^{} f \, d\mu=\int_{\Omega}^{} g \, d\mu$.
> 5. if $f\leq g$ almost everywhere, $\int_{\Omega}f  \, d\mu\leq \int_{\Omega}^{} g \, d\mu$.
> 6. **Markov inequality**: for any $0<t<+\infty$, $$\mu(\{ \omega\in \Omega: f(\omega)\geq t \})\leq \frac{1}{t}\int_{\Omega}^{} f \, d\mu $$In particular, if $\int_{\Omega}^{} f \, d\mu<+\infty$, then $f$ is finite almost everywhere.
> 7. if $f$ is simple, $\int_{\Omega}^{} f \, d\mu$ is well-defined.
> 9. **Linearity**: $\int_{\Omega}^{} f+g \, d\mu=\int_{\Omega}^{} f \, d\mu+\int_{\Omega}^{} g \, d\mu$. 

> [!proof]-
> We have:
> 1. Let $\tilde{f},\tilde{g}$ be simple functions s.t. $0\leq \tilde{f}\leq f$ and $0\leq \tilde{g}\leq g$. Then, $0\leq\tilde{f}+\tilde{g}\leq f+g$ and: $$\int_{\Omega}^{} f+g \, d\mu\geq \int_{\Omega}^{} \tilde{f}+\tilde{g} \, d\mu=\int_{\Omega}^{} \tilde{f} \, d\mu+\int_{\Omega}^{} \tilde{g} \, d\mu    $$Further it holds trivially that $\int_{\Omega}^{} cf \, d\mu=c\int_{\Omega}^{} f \, d\mu$.
> 2. It is non-negative as $f\geq 0$. If $f>0$ on $E\subseteq\Omega$ that is not a null set, then we can find $\varepsilon>0$ and $E'\subseteq\Omega$ s.t. $f\geq \varepsilon \chi_{E'}$ where $E'$ is measurable. Hence, $\int_{\Omega}^{} f \, d\mu\geq \varepsilon \mu(E')>0$. Conversely, if $\int_{\Omega}^{} f \, d\mu>0$, then there exists a simple function $\tilde{f}\leq f$ with $\int_{\Omega}^{} \tilde{f} \, d\mu >0$ and by Lemma 1.3, $\tilde{f}$ is not $0$ almost everywhere, which implies that neither is $f$.
> 4. if $f=g$ almost everywhere $f-g=0$ almost everywhere and by 3 $\int_\Omega f-g  \, d\mu=0$. By linearity, $\int_{\Omega}^{} f \, d\mu=\int_{\Omega}^{} g \, d\mu$.
> 5. if $f\leq g$ almost everywhere, let: $h:=\max(0,g-f)$ which is an unsigned measurable function where $f+h=g$ almost everywhere. Therefore, $$\int_{\Omega}^{} f \, d\mu \leq \int_{\Omega}^{} f+h \, d\mu =\int_{\Omega}^{} g \, d\mu $$
> 6. For any $0<t<+\infty$, let $E:=\{ \omega\in \Omega:f(\omega)\geq t \}$ which is measurable. Then, $t\chi_{E}\leq f$ almost everywhere and: $$t\mu(E)\leq \int_{\Omega} f \, d\mu $$
> 7. Trivially we have that $\text{Simp}\int_{\Omega}f  \, d\mu\leq \int_{\Omega}^{} f \, d\mu$. Now, for any simple $\tilde{f}\leq f$, we have by monotonicity: $$\text{Simp}\int_{\Omega}^{} f \, d\mu \geq\text{Simp}\int_{\Omega}^{} \tilde{f} \, d\mu $$Therefore, $\text{Simp}\int_{\Omega}^{} f \, d\mu \geq \int_{\Omega}^{} f \, d\mu$ and we have the equality.
> 9. Assume that a function $f$ is bounded and has finite measure support $E$. Then, for $\varepsilon>0$, we can define: $$A_{k}:=\{ \omega\in E: k\varepsilon\leq f(\omega)\leq(k+1)\varepsilon \}$$which are measurable. Then, as $f$ is bounded $E=\bigcup_{k\geq 0}^{}A_{k}$ and by considering the simple functions:
> 	1. $\ell(\omega):=\varepsilon \sum_{k=0}^{\infty}k\chi_{A_{k}}$ and 
> 	2. $u(\omega):=\varepsilon \sum_{k=0}^{\infty}(k+1)\chi_{A_{k}}$
> 	   
>     we have $\ell\leq f\leq u$ and by monotonicity:$$\int_{\Omega}^{} \ell \, d\mu \leq \int_{\Omega}^{} f \, d\mu \leq \inf_{f\leq g,g\in \mathcal{S}(\Omega)}\int_{\Omega}g \, d\mu\leq \int_{\Omega}^{} u \, d\mu=\int_{\Omega}^{} \ell \, d\mu+\varepsilon \mu(E) $$Therefore, $\int_{\Omega}^{} f \, d\mu = \inf_{f\leq g,g\in \mathcal{S}(\Omega)}\int_{\Omega}g \, d\mu$ by letting $\varepsilon\to 0$. 
>     
>     Hence, whenever $f,g$ are both bounded and finite measure supported, we have: $$\int_{\Omega}^{} f+g \, d\mu= \int_{\Omega}^{} f \, d\mu+\int_{\Omega}^{} g \, d\mu   $$
>     
>     Now, let $f$ be an unsigned measurable function. We first show that $\int_{\Omega}^{} \min(f,n) \, d\mu \to \int_{\Omega}^{} f \, d\mu$ when $n\to \infty$. 
>     
>     1. if $\int_{\Omega}^{} f \, d\mu<+\infty$, by definition for any $\varepsilon>0$, we can find an unsigned simple function $0\leq g\leq f$ s.t. $\int_{\Omega}^{} f \, d\mu-\varepsilon\leq\int_\Omega g\, d\mu\leq \int_{\Omega}^{} f \, d\mu<+\infty$. Now, let $n$ be the greatest value $a_{i}$ $g$ takes for which $\mu(E_{i})>0$. Then, $g=\min(g,n)\leq\min(f,n)\leq f$ and by monotonicity, $\int_{\Omega}^{} \min(f,n) \, d\mu\to \int_{\Omega}^{} f \, d\mu$.
>     2. if $\int_{\Omega}^{} f \, d\mu=+\infty$, then for any $M>0$, there exists an unsigned simple function $0\leq g\leq f$ s.t. $M\leq\int_{\Omega}^{} g \, d\mu\leq \int_{\Omega}^{} f \, d\mu$. Similarly as above, if the greatest value $g$ takes with non-zero measure is $+\infty$, then the statement holds trivially. Otherwise it is analogous to the previous case.
>        
>     Therefore, if $f,g$ are unsigned measurable functions with finite measure support, then so is $f+g$ and as $\min(f,n)$ are finite measure supported and bounded: $$\begin{align}\int_{\Omega}^{} f+g \, d\mu&=\lim_{ n \to \infty } \int_{\Omega}^{} \min(f+g,n) \, d\mu=\lim_{ n \to \infty } \int_{\Omega}^{} \min(f,n) \, d\mu+\lim_{ n \to \infty } \int_{\Omega}^{} \min(g,n) \, d\mu\\&=\int_{\Omega}^{} f \, d\mu+\int_{\Omega}^{} g \, d\mu  \end{align}    $$
>     
>     Similarly, we now have that for any unsigned measurable function $f$, $\int_{\Omega}^{} f 1_{f\geq 1 / n} \, d\mu\to \int_{\Omega}^{} f \, d\mu$ as $n\to + \infty$. Therefore, for any unsigned measurable functions $f,g$, $$\begin{align}\int_{\Omega}^{} f+g \, d\mu&=\lim_{ n \to \infty } \int_{\Omega}^{} (f+g)1_{f+g\geq  1 / n} \, d\mu =\lim_{ n \to \infty } \int_{\Omega}^{} f1_{f\geq  1 / n} \, d\mu+\lim_{ n \to \infty } \int_{\Omega}^{} g1_{g\geq  1 / n} \, d\mu\\&=\int_{\Omega}^{} f \, d\mu+\int_{\Omega}^{} g \, d\mu  \end{align} $$
---
> [!lemma] Lemma 3 (Properties of the Lebesgue Integral for Real-Valued Functions)
> Let $f,g:\Omega\to \mathbb{R}$ be real-valued absolutely integrable functions and $c\in \mathbb{R}$. Then, 
> 1. $\int_{\Omega}^{} f \, d\mu$ is independent of the choice of $f_{1},f_{2}$. 
> 2. there always exists $f_{1},f_{2}$ unsigned and absolutely integrable. 
> 3. **Linearity**: $\int_{\Omega}^{} f+g \, d\mu=\int_{\Omega}^{} f \, d\mu+\int_{\Omega}^{} g \, d\mu$ and $\int_{\Omega}^{} cf \, d\mu=c\int_{\Omega}^{} f \, d\mu$. 
> 4. $\int_{\Omega}^{} \left| f \right| \, d\mu\geq 0$ with equality if and only if $f=0$ almost everywhere. 
> 5. if $f=g$ almost everywhere, $\int_{\Omega}^{} f \, d\mu=\int_{\Omega}^{} g \, d\mu$.
> 6. if $f\leq g$ almost everywhere, $\int_{\Omega}^{} f \, d\mu\leq \int_{\Omega}^{} g \, d\mu$.
> 7. **Markov inequality**: for any $0<t<+\infty$, $$\mu(\{ \omega\in \Omega:\left| f(\omega) \right| \geq t \})\leq \frac{1}{t}\int_{\Omega}^{} \left| f \right|  \, d\mu $$

> [!proof]-
> We have:
> 1. Let $f=f_{1}-f_{2}=g_{1}-g_{2}$ where $f_{1},f_{2},g_{1},g_{2}$ are all unsigned and absolutely integrable. Then, $f_{1}+g_{2}=g_{1}+f_{2}$ and by linearity $\int_{\Omega}^{} f_{1} \, d\mu+\int_{\Omega}^{} g_{2} \, d\mu=\int_{\Omega}^{} g_{1} \, d\mu+\int_{\Omega}^{} f_{2} \, d\mu$. We have the independence by the absolute integrability of the four functions. 
> 2. Set $f_{1}:=\max (f,0)$ and $f_{2}:=\max(-f,0)$. Then, $\left| f_{1} \right|,\left| f_{2} \right|\leq \left| f \right|$ and by monotonicity they are unsigned and absolutely integrable.
> 3. We have that $f+g=(f_{1}+g_{1})-(f_{2}+g_{2})$ where $f_{1}+g_{1}$ and $f_{2}+g_{2}$ are unsigned and absolutely integrable by triangle inequality. Therefore, the statement holds by linearity of unsigned integrals. 
>    
>    Similarly, if $c\geq 0$, then $cf=cf_{1}-cf_{2}$ where $cf_{1},cf_{2}$ are absolutely integrable and unsigned. Now, if $c=-1$, then: $$-\int_{\Omega}^{} f \, d\mu=-\int_{\Omega}^{}f_{1}  \, d\mu+\int_{\Omega}^{} f_{2} \, d\mu=\int_{\Omega}^{} (-f) \, d\mu    $$as $-f=f_{2}-f_{1}$. Finally, we have that for $c=-d$ for $d>0$: $$c\int_{\Omega}^{} f \, d\mu=-d\int_{\Omega}^{}  f\, d\mu=d \int_{\Omega}^{} (-f) \, d\mu=\int_{\Omega}^{} cf \, d\mu    $$
> 4. This holds from the fact that $\left| f \right|$ is unsigned measurable.
> 5. Holds from $f-g=0$ almost everywhere and linearity. 
> 6. $g-f\geq0$ almost everywhere and $h:=\max(g-f,0)$ is an unsigned measurable function. Therefore, $$\int_{\Omega}g  \, d\mu-\int_{\Omega}^{} f \, d\mu=\int_{\Omega}^{}h  \, d\mu\geq 0   $$
> 7. Holds from $\left| f \right|$ being unsigned measurable.
---
> [!lemma] Lemma 4 (Properties of the Lebesgue Integral for Complex-Valued Functions)
> Let $f,g:\Omega\to \mathbb{C}$ be complex-valued absolutely integrable functions and $c\in \mathbb{C}$. Then, 
> 1. **Linearity**: $\int_{\Omega}^{} f+g \, d\mu=\int_{\Omega}^{} f \, d\mu+\int_{\Omega}^{} g \, d\mu$ and $\int_{\Omega}^{} cf \, d\mu=c\int_{\Omega}^{} f \, d\mu$. 
> 4. $\int_{\Omega}^{} \left| f \right| \, d\mu\geq 0$ with equality if and only if $f=0$ almost everywhere. 
> 5. if $f=g$ almost everywhere, $\int_{\Omega}^{} f \, d\mu=\int_{\Omega}^{} g \, d\mu$.
> 7. **Markov inequality**: for any $0<t<+\infty$, $$\mu(\{ \omega\in \Omega:\left| f(\omega) \right| \geq t \})\leq \frac{1}{t}\int_{\Omega}^{} \left| f \right|  \, d\mu $$
> 8. **Triangle inequality**: $\left| \int_{\Omega}^{} f \, d\mu \right|\leq \int_{\Omega}^{} \left| f \right| \, d\mu$.

> [!proof]-
> We have:
> 1. The addition is trivial by checking the decomposition.
>    
>    If $c\in \mathbb{R}$, then: $$\int_{\Omega}^{} cf \, d\mu=\int_{\Omega}^{} c\text{Re}(f) \, d\mu+i\int_{\Omega}^{} c\text{Im}(f) \, d\mu=c\int_{\Omega}^{} f \, d\mu    $$Further, $$\int_{\Omega}^{} if \, d\mu=\int_{\Omega}^{} \text{Re}(if) \, d\mu+i\int_{\Omega}^{} \text{Im}(if) \, d\mu=-\int_{\Omega}\text{Im}(f) \, d\mu+i\int_{\Omega}^{} \text{Re}(f) \, d\mu=i\int_{\Omega}^{} f \, d\mu      $$Therefore, $$(a+ib)\int_{\Omega}^{} f \, d\mu=\int_{\Omega}^{} (a+ib) f\, d\mu  $$
> 4. This holds from the fact that $\left| f \right|$ is unsigned measurable.
> 5. Holds from $f-g=0$ almost everywhere and linearity. 
> 7. Holds from $\left| f \right|$ being unsigned measurable.
> 8. Let $\alpha\in \mathbb{T}$ s.t. $\alpha \int_{\Omega}f \, d\mu=\left| \int_{\Omega}^{} f \, d\mu \right|$. Then, $$\left| \int_{\Omega}^{} f \, d\mu  \right| =\text{Re}\int_{\Omega}^{} \alpha f \, d\mu=\int_{\Omega}^{} \text{Re}(\alpha f) \, d\mu\leq \int_{\Omega}^{} \left| \alpha f \right|  \, d\mu=\int_{\Omega}^{} \left| f \right|  \, d\mu    $$
---
> [!lemma] Proposition 2
> Let $f:\Omega\to[0,+\infty]$ be $\mu$-measurable. Then, $f$ is $\mu$-integrable.

> [!proof]-
> Assume that $\underline{\int_{\Omega}}f \, d\mu<+\infty$ (otherwise, we're done).
> 
> Then, we have $f(x)<+\infty$ $\mu$-a.e.
> 1. Assume $\mu(\Omega)<+\infty$. Then for $\varepsilon>0$, we define: $$A_{k}:=\{ x\in \Omega:k\varepsilon\leq f(x)<(k+1)\varepsilon \}=f^{-1}[k\varepsilon,(k+1)\varepsilon)$$If we now set $\Omega':=\bigcup_{k\geq 0}^{}A_{k}=f^{-1}[0,+\infty)$ Then, $\mu(\Omega \backslash \Omega')=\mu(f^{-1}[\{ +\infty \}])=0$.
>  
>    Now, consider the simple functions: 
>    $$\begin{align}e(x)&:=\varepsilon \sum_{k=0}^{\infty}k\chi_{A_{k}}(x)\\g(x)&:=\varepsilon \sum_{k=0}^{\infty}(k+1)\chi_{A_{k}}(x)\end{align}$$Then, $e(x)\leq f(x)\leq g(x)$ $\mu$-a.e. Therefore, $$\int_{\Omega}^{} e \, d\mu\leq\underline{\int_{\Omega}}f  \, d\mu\leq  \overline{\int_{\Omega}} f\, d\mu\leq \int_{\Omega}^{} g \, d\mu\leq \int_{\Omega}^{} e \, d\mu+\varepsilon \mu(\Omega)    $$By letting $\varepsilon\to{0}$, we get that $f$ is $\mu$-integrable.
>  2. If $\mu(\Omega)=+\infty$, we choose [[Dyadic Cubes]] $\mathbb{R}^n=\bigcup_{\ell =0}^{\infty}Q_{\ell}$ where $\mu(Q_{\ell})<+\infty$ as $\mu$ is Radon and the compact sets have finite measure. 
>     
>     Then, we compute with $\Omega_{\ell}:=\Omega \cap Q_{\ell}$. Then for all $\ell\geq 0$, there exists $e_{\ell},g_{\ell}:\Omega_{\ell}\to \mathbb{R}^n$ s.t. $$e_{\ell}\leq f\leq g_{\ell}$$in $\Omega_{\ell}$. Then, we take:
>     - $e=\sum_{\ell=0}^{\infty}e_{\ell}\chi_{\Omega_{\ell}}$
>     - $g=\sum_{\ell=0}^{\infty}g_{\ell}\chi_{\Omega_{\ell}}$
>     
>     Then, $$\sum_{\ell=0}^{\infty}\int_{\Omega_{\ell}}^{} e_{\ell} \, d\mu \leq \underline{\int_{\Omega}}f \, d\mu \leq \overline{\int_{\Omega}}f \, d\mu \leq \sum_{\ell=0}^{\infty}\int_{\Omega_{\ell}}^{} g \, d\mu\leq \sum_{\ell=0}^{\infty}\left( \int_{\Omega_{\ell}} e_{\ell}  \, d\mu+\frac{\varepsilon}{2^\ell} \right) $$By letting $\varepsilon\to{0}$, we conclude the proof.



- **Remark**: There exist $\mu$-measurable functions $f:\Omega\to[-\infty,\infty]$ that is not $\mu$-integrable.
---
> [!lemma] Proposition 3 (Monotonicity)
> Let $f_{1},f_{2}:\Omega\to \overline{\mathbb{R}}$ be $\mu$-integrable with $f_{1}\leq f_{2}$ $\mu$-a.e. Then, $$\int_{\Omega}^{} f_{1} \, d\mu \leq \int_{\Omega}^{} f_{2} \, d\mu $$

> [!proof]-
> For any simple, $\mu$-measurable $g$ s.t. $f_{2}\leq g$ $\mu$-a.e., we have $f_{1}\leq g$ $\mu$-a.e. Therefore, $$\int_{\Omega}^{} f_{1} \, d\mu \leq \int_{\Omega}^{} g \, d\mu $$and consequently, $$\int_{\Omega}^{} f_{1} \, d\mu \leq \overline{\int_{\Omega}}f_{2} \, d\mu =\int_{\Omega}^{} f_{2} \, d\mu  $$
---
> [!lemma] Theorem 4 (Fatou's Lemma)
> Let $f_{k}:\Omega\to[0,+\infty]$ be $\mu$-measurable. Then, $$\int_{\Omega}^{} \liminf_{ k \to \infty } f_{k} \, d\mu\leq \liminf_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu  $$

> [!proof]-
> By Proposition 2, $f_{k}$ and $f:=\liminf_{ k \to \infty }f_{k}$ are $\mu$-integrable. Therefore, it is sufficient to show that it holds: $$\int_{\Omega}^{} g \, d\mu\leq \liminf_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu  $$for every simple function $g=\sum_{j=0}^{\infty}a_{j}\chi _{A_{j}}$ with $g\leq f$ $\mu$-a.e.
> 
> Wlog we can assume that $a_{0}=0$ and $a_{j}>0$ for $j\geq 1$. We choose $0<t<1$. Now, for all $j\geq 0$ and $k\geq 1$, we define: $$B_{j,k}:=\{ x\in A_{j}:f_{\ell}(x)>ta_{j}\quad \ell\geq k \}$$Then, $B_{j,k}\subseteq B_{j,k+1}$. 
> > [!claim]
> > We have that: $A_{j}=\bigcup_{k=1}^{\infty}B_{j,k}$
> 
> > [!proof]-
> > $\supseteq$ is clear. Assume that we have $x\in A_{j}$. Then, $$ta_{j}<a_{j}=g(x)\leq \liminf_{ k \to \infty }f_{k}(x)=\sup_{n\geq 1}\inf_{k\geq n}f_{k}(x)$$
> > Therefore, there exists $\overline{n}\geq 1$ s.t. $$\inf_{k\geq \overline{n}}f_{k}(x)>ta_{j}$$In other words, $x\in B_{j,\overline{n}}$. This proves the statement.
> 
> Since $A_{j}=\bigcup_{k=1}^{\infty}B_{j,k}$, $$\lim_{ k \to \infty } \mu(B_{j,k})=\mu(A_{j})$$For $J,k\in \mathbb{N}$, we have: $$\begin{align}\int_{\Omega}f_{k}  \, d\mu\geq \sum_{j=1}^{J}\int _{A_{j}}f_{k} \, d\mu\geq \sum_{j=1}^{J}\int_{B_{j,k} }^{}  f_{k}\, d\mu\geq t\cdot \sum_{j=1}^{J}a_{j}\mu(B_{j,k})   \end{align}$$Then, by letting $k\to+\infty$, $$\liminf_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu\geq t\cdot \sum_{j=1}^{J}a_{j}\mu(A_{j}) $$Then, by letting $J\to \infty$, then:$$\liminf_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu\geq t\cdot \sum_{j=1}^{\infty}a_{j}\mu(A_{j})=t\int_{\Omega}^{} g \, d\mu  $$We conclude the proof by $t\to 1$.

- **Remark**: $f_{k}\geq 0$ is necessary. **Example**: $\mu=\mathcal{L}^n$, $\Omega=\mathbb{R}^n$, $f_{k}=-\frac{1}{k^n}\chi_{B_{<k}(0)}$. Then, 
	- $\liminf_{ k \to \infty }\int_{\Omega}^{} f_{k} \, d\mathcal{L}^n=-\liminf_{ k \to \infty } \frac{1}{k^n}\mathcal{L}^n(B_{<k}(0))=-w_{n}$
	- $\liminf_{ k \to \infty }f_{k}=0$.
---
> [!lemma] Theorem 5 (Monotone Convergence Theorem, Beppo-Levi)
> Let $f_{k}:\Omega\to[0,+\infty]$ be $\mu$-measurable and increasing, i.e. $f_{1}\leq f_{2}\leq\dots$ $\mu$-a.e. Then, $$\int_{\Omega}^{} \lim_{ k \to \infty } f_{k} \, d\mu=\lim_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu  $$

> [!proof]-
> As we have $f_{j}\leq \lim_{ k \to \infty }f_{k}$ $\mu$-a.e. By monoticity, $$\int_{\Omega}^{} f_{j} \, d\mu\leq \int_{\Omega}^{} \lim_{ k \to \infty}f_{k}  \, d\mu  $$By taking the limit, we have $\int_{\Omega}^{} \lim_{ k \to \infty } f_{k} \, d\mu\geq\lim_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu$.
> 
> For the opposite inequality we have: $$\begin{align}\int_{\Omega}^{} \lim_{ k \to \infty } f_{k} \, d\mu&=\int_{\Omega}^{} \liminf_{ k \to \infty } f_{k} \, d\mu \leq \liminf_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu=\lim_{ k \to \infty } \int_{\Omega}^{} f_{k} \, d\mu   \end{align}$$
---
> [!lemma] Corollary 6
> Let $f_{k}:\Omega\to[0,+\infty]$ be a sequence of $\mu$-measurable functions. Then, $$\int_{\Omega}^{} \sum_{k=1}^{\infty}f_{k} \, d\mu=\sum_{k=1}^{\infty}\int_{\Omega}^{} f_{k} \, d\mu  $$

> [!proof]-
> We define $s_{n}:=\sum_{k=1}^{n}f_{k}$. Then, $(s_{n})_{n}$ is an increasing sequence of $\mu$-measurable functions. Therefore, using monotone convergence theorem: $$\int_{\Omega}^{}\sum_{k=1}^{\infty}f_{k} \, d\mu=\int_{\Omega}^{} \lim_{ n \to \infty } \sum_{k=1}^{n}f_{k} \, d\mu=\lim_{ n \to \infty } \int_{\Omega}^{} \sum_{k=1}^{n}f_{k} \, d\mu=\lim_{ n \to \infty } \sum_{k=1}^{n}\int_{\Omega}^{} f_{k} \, d\mu =\sum_{k=1}^{\infty}\int_{\Omega}^{} f_{k} \, d\mu  $$
---
> [!lemma] Lemma 7 (Borel-Cantelli)
> Let $\{ E_{k} \}$ be $\mu$-measurable sets in $\mathbb{R}^n$ s.t. $\sum_{k=1}^{\infty}\mu(E_{k})<+\infty$. Then, $$\mu \left( \limsup_{ k \to \infty } E_{k} \right)=0 $$

> [!proof]-
> We have that $\chi_{E_{k}}$ are $\mu$-measurable functions. Then, $$\int_{\Omega}^{} \sum_{k=1}^{\infty}\chi_{E_{k}} \, d\mu=\sum_{k=1}^{\infty}\int_{\Omega}^{} \chi_{E_{k}} \, d\mu =\sum_{k=1}^{\infty}\mu(E_{k})<+\infty $$Therefore, since $f$ is $\mu$-summable, by [[Summable Function|Proposition 2]],$$\mu\left(\limsup_{ k \to \infty } E_{k}\right)=\mu(\{ x\in \Omega: f(x)=+\infty \})=0$$
---
> [!lemma] Theorem 8 (Radon-Nikodym)
> Let $(X,\Sigma)$ be a measurable space and $\mu,\nu$ are finite measures on $(X,\Sigma)$ s.t. $\nu\ll \mu$, i.e. for every $E\in \Sigma$, $$\mu(E)=0 \implies \nu(E)=0$$Then, there exists a unique function $\rho\in L^1(X,\mu)$ s.t. for any $E\in \Sigma$:$$\nu(E)=\int_{E}^{} \rho \, d\mu $$

> [!proof]-
> We have: 
> 1. **Proving the existence**: We define the auxiliary measure $\lambda:=\mu+\nu$. Then, $\nu \ll \mu\ll \lambda$ and $\lambda(X)<+\infty$. We now define a functional: $$\begin{array}{cccc} {T:}&{L^2(X,\lambda)}&\to&{\mathbb{C}}\\&{u} &\mapsto & {\int_{X}^{} u \, d\nu } \end{array}{}$$which is well-defined, because by Hölder, $$\left( \int_{X}^{} \left| u \right|  \, d\nu  \right) ^{2}\leq \left( \int_{X}^{} \left| u \right|  \, d\lambda  \right) ^{2}\leq\lambda(X)\int_{X}^{} \left| u \right| ^{2} \, d\lambda $$Furthermore, $T$ is linear and bounded as: $$\left| T(u) \right| \leq \lambda(X)^{1/2}\|u\|$$Therefore, by Riesz-representation, there exists a unique function $f\in L^2(X,\lambda)$ s.t. $$T(u)=\int_{X}^{} u \, d\nu=\int_{X}^{} fu \, d\lambda  $$for all $u\in L^2(X,\lambda)$. As $\lambda=\nu+\mu$, $$\int_{X}^{}(1-f) u \, d\nu=\int_{X}^{} fu \, d\mu$$Then, by using $u:=\chi_{\{ f<0 \}}$, $$0\leq \int_{\{ f<0 \}}^{}\underbrace{ (1-f) }_{ \geq0 }  \, d\nu=\int_{\{ f<0 \}}^{} f \, d\mu \leq 0 $$which means $\mu(\{ f<0 \})=0$. Further, by $u:=\chi_{\{ f\geq 1 \}}$, we get: $$0\geq\int_{\{ f\geq 1 \}}^{}\underbrace{ (1-f) }_{ \leq 0 }  \, d\nu=\int_{\{ f\geq 1 \}}^{}f  \, d\mu  \geq \mu(\{ f\geq 1 \})$$Therefore, $\mu(\{ f\geq 1 \})=0$ and for $\mu$-a.e. $x$, $0\leq f(x)<1$. As $\nu\ll \mu$, we have that $f\in L^\infty(X,\lambda)$. 
>    
>    Let's define $\rho_{n}=1+f+f^{2}+\dots+f^n$. Then, $\rho_{n}\in L^\infty(X,\lambda)$ and for any $E\in \Sigma$, we can use $u:=\rho_{n}\chi_{E}$ to see that: $$\int_{E}^{} (1-f^{n+1}) \, d\nu=\int_{E}^{} (f+f^{2}+\dots+f^{n+1}) \, d\mu  $$ Now, we have that $1-f^{n+1}\leq 1-f^{n+2}$ for all $n$ $\nu$-a.e and $\sum_{k=1}^{n}f^k\leq\sum_{k=1}^{n+1}f^k$ for all $n$ $\mu$-a.e. Therefore, $$\begin{align}\nu(E)&=\int_{E}^{} \lim_{ n \to \infty } (1-f^{n+1}) \, d\nu\\&=\lim_{ n \to \infty } \int_{E}^{} (f+f^{2}+\dots+f^{n+1}) \, d\mu \\&=\int_{E}^{}\sum_{k=1}^{\infty}f^k  \, d\mu \\&=\int_{E}^{} \frac{f}{1-f} \, d\mu \end{align} $$By defining $\rho:= \frac{f}{1-f}$, we have the statement.
> 2. **Proving the uniqueness**: Suppose there are two functions $\rho_{1},\rho_{2}$ and define $E_{1}:=\{ \rho_{1}(x)>\rho_{2}(x) \}$. Then, $$0=\nu(E_{1})-\nu(E_{1})=\int_{E_{1}}^{} (\rho_{1}-\rho_{2}) \, d\mu $$Therefore, $\mu(E_{1})=0$ By symmetry, we have that $\rho_{1}=\rho_{2}$ $\mu$-a.e.
---
