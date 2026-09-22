# Centered Gaussian MaxCut: block escape and local stationarity

22 September 2026

**Status.** This continues the centered Gaussian approach for MaxCut. It proves a block-hitting transfer theorem, derives a necessary thermal balance condition for locally stationary laws, and proves that overcooling fixes every one-spin local maximum in the zero-temperature limit. It also tests repeated exact Gaussian-proxy updates from every suboptimal local maximum on the existing small instance. The random-regular near-optimal Glauber conjecture is still unproved.

## 1. Setting and existing comparison

For a d-regular graph,

$$
H(x)=-\frac{x^\top Ax}{2\sqrt d},\quad e(x)=H(x)/n,
\quad\pi(x)\propto e^{\beta H(x)}.
$$

P denotes one-coordinate random-scan heat-bath. The centered Gaussian chain $Γ$ is

$$
Y\mid x\sim N(Bx,B),\qquad
\nu_y(z)\propto\exp\{y\cdot z-\kappa(\sum_i z_i)^2/(2n)\},
$$

where $κ=β√d$ and $B=aI−β(A−d11^T/n)/√d$ is positive definite. Its conditional Curie–Weiss update is sampled by an exact cardinality/subset dynamic program, not by running an approximate conditional MCMC chain.

The preceding note proves reversibility and, using the conditional functional inequality of Mikulincer–Sohn, the comparison

$$
\mathcal E_\Gamma(g,g)\le Cn\mathcal E_P(g,g).
\tag{1}
$$

The regime includes fixed d,β as n→∞. More generally their parameter condition is κ/2≤n^{1−η}, for a fixed η>0. Dirichlet forms here contain the usual factor 1/2. For f=ν/π, write D_P(f)=E_P(f,log f).

Source for the conditional inequality: https://arxiv.org/pdf/2512.22803, Theorem 1 with its J=0 and u=1. The full construction and one-step Gaussian energy formula are included in maxcut_gaussian/MaxCut_Gaussian_Comparison.md.

## 2. A block comparison that permits temporary energy losses

**Theorem 1.** For any integer s≥1,

$$
\mathcal E_{\Gamma^s}(g,g)\le Cns\mathcal E_P(g,g),
\tag{2}
$$

and for any bounded observable b and positive density f=ν/π,

$$
|\mathbb E_\nu[\Gamma^s b-b]|
\le\operatorname{osc}(b)\sqrt{CnsD_P(f)/2}.
\tag{3}
$$

**Proof.** Since Γ is reversible, spectral calculus and 1−λ^s≤s(1−λ), λ∈[−1,1], give E_{Γ^s}≤sE_Γ. Apply (1). For any reversible R, factoring f−f'=(√f−√f')(√f+√f') and using Cauchy–Schwarz gives

$$
|\mathbb E_\nu[Rb-b]|\le\operatorname{osc}(b)
\sqrt{2\mathcal E_R(\sqrt f,\sqrt f)}.
$$

Finally 4E_P(√f,√f)≤D_P(f). □

This permits a negative first-step drift followed by positive drift over a block. It also controls hitting probabilities, so success need not persist to the final block step.

**Theorem 2 (block-hitting transfer).** For a target set G, define

$$
p_s(\nu)=\Pr_{X_0\sim\nu,\,\Gamma}
\{X_t\in G\text{ for some }0\le t\le s\}.
$$

Then

$$
\boxed{\nu(G)\ge\frac{p_s(\nu)}{s+1}
-\sqrt{CnsD_P(\nu/\pi)/2}.}
\tag{4}
$$

**Proof.** Apply (3) to b=1_G at each t≤s. A union bound yields

$$
p_s(\nu)\le\sum_{t=0}^s\nu\Gamma^t(G)
\le(s+1)\nu(G)+(s+1)\sqrt{CnsD_P(f)/2}.
$$

Rearrange. □

For continuous-time P−I Glauber, let \barν_T=T^{-1}∫_0^Tν_tdt and K_0=KL(ν_0||π). Entropy dissipation gives D_P(\barν_T/π)≤K_0/T. If p_s(\barν_T)≥p>0 and

$$
T\ge\frac{2Cn\,s(s+1)^2K_0}{p^2},
\tag{5}
$$

then \barν_T(G)≥p/[2(s+1)]. A uniform observation time, followed by independent repetitions if needed, gives polynomial-time success when s and p^{-1} are polynomial. Keeping the best visited cut can only help.

This is a comparison theorem, not a proof that p_s is large. The initial law in p_s must be the relevant outer Glauber law; success of Γ from some different initialization alone does not establish the hypothesis.

## 3. Local stationarity imposes thermal field balance

One-spin local maxima are useful test configurations, but distributions supported on them do not describe a positive-temperature locally stationary law.

Let p_i(·|x_{−i}) be the one-spin conditional under ν and q_i(·|x_{−i}) its Gibbs counterpart. Heat-bath gives the exact identity

$$
\boxed{D_P(f)=\frac1n\sum_i\mathbb E_{\nu_{-i}}
\left[\operatorname{KL}(p_i\|q_i)+\operatorname{KL}(q_i\|p_i)\right].}
\tag{6}
$$

To verify it, write f=a p_i/q_i on each two-point conditional fiber, where a=ν_{−i}/π_{−i}. Its conditional covariance Cov_{q_i}(f,log f) equals a times the displayed sum of KL divergences. Average over the fibers and sites.

Define the normalized local margin

$$
\ell_i(x)=-\frac{x_i}{\sqrt d}\sum_{j\sim i}x_j,
\quad p_u=\Pr_{X\sim\nu,I\sim\mathrm{Unif}[n]}(\ell_I(X)=u).
$$

For u>0, let b_β(u)=1/(1+e^{−2βu}). Then

$$
\boxed{\sum_{u>0}\left|p_u-b_\beta(u)(p_u+p_{-u})\right|
\le\sqrt{D_P(f)/2}.}
\tag{7}
$$

**Proof.** By Pinsker and Jensen, (6) bounds the mean conditional total-variation distance between p_i and q_i by √(D_P(f)/2). Resampling the selected central spin from q_i leaves the absolute margin unchanged; conditional on absolute margin u>0, its new sign is positive with probability b_β(u). Total variation contracts under taking the margin observable. Positive and negative discrepancies cancel pairwise, giving exactly the left side of (7). □

At exact local equilibrium this becomes p_{−u}=e^{−2βu}p_u. Approximate local stationarity requires the corresponding approximate relation. It does not imply global mixing: a thermalized metastable basin can obey local balance while exchanging negligible mass with other basins.

This constraint alone cannot force Parisi-scale energy. For odd d, the formal margin distribution supported on u=±1/√d with probabilities b_β(1/√d) and 1−b_β(1/√d) satisfies the balance relation, but its formal energy is tanh(β/√d)/(2√d). At fixed β this tends to zero as d grows. This does not assert that such a distribution is realizable by a locally stationary law on the random graph; it proves that additional spatial/edge constraints are essential to exclude it.

Consequently, the previous negative one-step drift on isolated stable cuts does not by itself refute a drift statement for locally stationary laws. Conversely, escaping those isolated cuts does not prove escape from thermalized low-energy basins. This is the distinction that the next asymptotic argument must address.

## 4. Repeated-proxy experiment from every bad local maximum

We used the existing exact-uniform simple d=5,n=16 graph, seed 78600. Exhaustive enumeration gives maximum cut 33 and exactly 16 one-spin local maxima modulo global reversal. One is optimal; the remaining 15 have cut sizes 26 (six states), 28 (eight states), and 32 (one state).

For each of these **15 suboptimal local maxima**, at each β∈{2,4,8}, we ran 128 independent centered Gaussian trajectories, recording checkpoints 1,4,16,64,256,1024. Thus there are 5,760 trajectories. The shift was a/β=1.4167093020712966. The exact conditional cardinality/subset sampler is used at every update, with floating-point arithmetic.

Here are the minimum observed optimum-hitting fractions across the 15 initial states:

| Gaussian updates | β=2 | β=4 | β=8 |
|---:|---:|---:|---:|
| 16 | 0.0078 | 0 | 0 |
| 64 | 0.4922 | 0 | 0 |
| 256 | 0.9844 | 0.1406 | 0 |
| 1024 | 1.0000 | 0.7266 | 0 |

The zero at β=8 means at least one initial state had no observed optimum hits; averaged across all 15 states, the optimum-hit fraction there was 0.00833 by step 1024.

Minimum observed **terminal** mean cut gains across the 15 initial states were:

| Gaussian updates | β=2 | β=4 |
|---:|---:|---:|
| 1 | −0.4063 | −0.0313 |
| 16 | −0.5859 | −0.1328 |
| 256 | +0.2813 | +0.2188 |
| 1024 | +0.2266 | +0.7891 |

Thus a block can have positive mean drift even when one step has negative drift. At β=2, all 1,920 simulated runs hit an optimum by step 1024. These are empirical finite-instance results, not certified probabilities or an n-uniform theorem. The reported minimum means are also subject to sampling noise; state-by-state standard errors are recorded in summary.json. No multiple-comparison confidence claim is made.

## 5. A theorem explaining why simply cooling harder is insufficient

Fix the graph and choose a_0>0 such that

$$
B_0=a_0I-(A-d11^T/n)/\sqrt d\succ0.
$$

Run the centered chain with B=βB_0 and κ=β√d. Let x be any one-spin local maximum, so ℓ_i(x)≥0. Put v_0=a_0+√d/n, the common diagonal of B_0.

**Theorem 3 (zero-temperature trapping).** Its one-step exit probability satisfies

$$
\boxed{\Gamma_\beta(x,\{x\}^c)\le
\min\left\{1,\ n e^{-\beta a_0^2/(8v_0)}
+(1+e^{-\beta a_0})^n-1\right\}.}
\tag{8}
$$

Here the target is the complement of the singleton {x}, not global spin reversal. In particular, for fixed graph and fixed block length s,

$$
\Gamma_\beta^s e(x)\longrightarrow e(x)\quad(\beta\to\infty).
\tag{9}
$$

**Proof.** Write Y=βB_0x+√β Z, Z∼N(0,B_0). If x^S flips the sites of S, direct cancellation of the global-magnetization terms gives

$$
\log\frac{\nu_Y(x^S)}{\nu_Y(x)}
=-2\beta\sum_{i\in S}(a_0+\ell_i)
-\frac{2\beta\sqrt d}{n}\left(\sum_{i\in S}x_i\right)^2
-2\sqrt\beta\sum_{i\in S}x_iZ_i.
$$

On the event x_iZ_i≥−a_0√β/2 for every i, these odds are at most exp(−βa_0|S|). Summing over nonempty S bounds the conditional exit probability by (1+e^{−βa_0})^n−1. A Gaussian tail bound and union bound bound the exceptional event by n exp(−βa_0²/(8v_0)). This proves (8).

Until the first exit, the chain remains at x, so the probability of an exit within s steps is at most s times the bound in (8). Multiply by osc(e) to obtain (9). □

When n e^{−βa_0}≤1, (8) is at most (1+e)n e^{−cβ}, with c=min{a_0,a_0²/(8v_0)}. Accordingly the expected first-exit time is at least e^{cβ}/[(1+e)n] whenever this lower bound is informative.

This gives a rigorous limitation of the strategy: every suboptimal one-spin local maximum also becomes a fixed point in the Gaussian chain's zero-temperature limit. A fixed-length block at arbitrarily low temperature cannot inherit the near-optimal-energy property of the exact binary noisy-copy posterior.

This is **not** a counterexample to polynomial-time optimization at fixed accuracy: β may be fixed as n→∞, block length may grow, and an annealing schedule may escape before cooling. The order of limits matters.

## 6. The remaining MaxCut theorem

The comparison and block-hitting implication are established. The unresolved claim is an n-uniform lower bound

$$
\Pr_{X_0\sim\bar\nu_T,\Gamma}
\{\exists t\le s(n): e(X_t)\ge e_*-\varepsilon\}
\ge p(n),
$$

with s polynomial and p at least inverse-polynomial, for the actual uniform-start annealing law \barν_T at the relevant phase.

The finite experiment establishes neither that bound nor its failure. It concerns one graph with only 15 suboptimal local maxima and cannot exclude rare thermalized basins whose escape time grows superpolynomially. Equation (7) constrains such basins but does not eliminate them. The zero-temperature theorem shows why an indiscriminate increase in β cannot supply the missing argument.

The concrete next mathematical target is therefore a block-escape estimate for **thermalized, trajectory-selected** local-type distributions on random regular graphs, at an intermediate temperature. This continuation does not prove Parisi-quality annealed Glauber.

## 7. Validation and reproduction

The conditional cardinality distribution from the dynamic program was compared with enumeration of all 65,536 configurations for 36 external fields: maximum probability discrepancy 1.70×10^{-14}. In a separate stationarity pilot, 8,192 exact Gibbs initial samples at β=2 underwent one C++ Gaussian-chain update. The mean cut change was 0.00745 with empirical standard error 0.00669, consistent with the exactly proved invariance.

Run from the archive root:

```bash
OPENBLAS_NUM_THREADS=1 python maxcut_blocks/setup.py
g++ -O3 -std=c++17 maxcut_blocks/blocks.cpp -o maxcut_blocks/blocks
maxcut_blocks/blocks < maxcut_blocks/input.txt > maxcut_blocks/results.jsonl
OPENBLAS_NUM_THREADS=1 python maxcut_blocks/summarize.py
OPENBLAS_NUM_THREADS=1 python maxcut_blocks/validate.py
```

Requirements: Python, NumPy, SciPy, and a C++17 compiler. Raw trajectories, the complete graph, initial states, seeds, and summaries are included. Temperatures multiply the normalized H, and one Gaussian update is a global update costing more than a single Glauber coordinate update; the comparison explicitly accounts for an O(n) Dirichlet factor.


# A MaxCut-specific Gaussian auxiliary chain

22 September 2026

**Conclusion.** There is an exact Gaussian-augmentation chain for MaxCut with a rigorous Glauber comparison. A centered variant has simple antiferromagnetic Curie–Weiss conditional components, rather than noisy-copy posteriors on the original graph. A known uniform functional inequality controls those components. We also derive an explicit one-step energy map with a vanishing error for fixed degree and temperature as n grows. This does not yet prove Parisi-quality optimization: favorable drift for the relevant local-type distributions remains to be established.

## 1. Normalization

Let A be the adjacency matrix of a simple d-regular graph, let L=dI−A, and write

$$
H(x)=-\frac{x^\top Ax}{2\sqrt d},\quad e(x)=H(x)/n,
\quad\pi(x)\propto e^{\beta H(x)}.
$$

P is ordinary random-scan heat-bath for π, normalized to one selected coordinate per step. Dirichlet forms use the convention

$$
\mathcal E_P(g,g)=\tfrac12\sum_{x,z}\pi(x)P(x,z)[g(x)-g(z)]^2.
$$

For a density f=ν/π, D_P(f)=E_P(f,log f).

## 2. A simple exact Gaussian chain

Set B=βL/√d, a positive semidefinite matrix. Given x, perform

$$
Y\sim N(Bx,B),\qquad
\Pr(X'_i=+1\mid Y)=\frac{e^{Y_i}}{2\cosh Y_i},
$$

with all X'_i conditionally independent. Denote the resulting chain by Γ_L.

**Exactness.** Let γ_B be the centered Gaussian law with covariance B, allowing a singular covariance. The joint law with unnormalized density exp(y·x) against counting measure in x and γ_B(dy) has x-marginal

$$
\int e^{y\cdot x}\,\gamma_B(dy)=e^{x^\top Bx/2}
=e^{\beta n\sqrt d/2}\,e^{\beta H(x)}.
$$

Its two conditional distributions are precisely the two updates above. Alternating these conditionals is a reversible chain with stationary law π.

This update can be sampled using independent Gaussian variables on edges. If C is an oriented vertex-edge incidence matrix, L=CC^T; therefore
Y=Bx+sqrt(β/√d)Cg for independent standard-normal edge variables g. One update costs O(nd) arithmetic operations.

**Unconditional comparison.** Conditional on Y, the spin law is a product measure. Its random-scan heat-bath gap is 1/n. For every g,

$$
\boxed{\mathcal E_{\Gamma_L}(g,g)
=\mathbb E_Y\operatorname{Var}(g(X)\mid Y)
\le n\mathcal E_P(g,g).}
\tag{1}
$$

The final inequality follows from product tensorization and the fact that conditioning on Y reduces expected single-site conditional variance. No low-temperature mixing claim for the original MaxCut measure is used.

**Why this version can be too inertial.** Its diagonal is B_ii=β√d. If c_i(x) is the number of cut edges at i, then

$$
x_i\mathbb E[Y_i\mid x]=2\beta c_i(x)/\sqrt d.
$$

Around a stable high-degree cut this is of order β√d, whereas the Gaussian standard deviation is of order (β√d)^{1/2}. The update increasingly retains the current spins. This motivates separating the constant-vector mode.

## 3. The centered Gaussian chain

Define

$$
\Pi=\frac{\mathbf1\mathbf1^\top}{n},\quad A_0=A-d\Pi,
\quad\kappa=\beta\sqrt d,
$$

and choose a>0 large enough that

$$
B=aI-\frac\beta{\sqrt d}A_0\succ0.
\tag{2}
$$

For example, take a=(β/√d)λ_max(A_0)+a small positive margin. The auxiliary chain Γ performs

$$
Y\mid x\sim N(Bx,B),
\tag{3}
$$

then samples

$$
\boxed{\nu_y(z)\propto
\exp\left(y\cdot z-\frac\kappa{2n}(\mathbf1^\top z)^2\right).}
\tag{4}
$$

This conditional is an antiferromagnetic Curie–Weiss model with arbitrary external field. It has only a quadratic penalty on the total magnetization; the original graph interaction is gone.

**Exactness.** Use the joint density exp(y·x−κ(1^Tx)^2/(2n)) against γ_B. Integrating out Y gives

$$
\frac12x^\top Bx-\frac\kappa{2n}(\mathbf1^\top x)^2
=\frac{an}{2}-\frac\beta{2\sqrt d}x^\top Ax.
$$

Thus Γ is exactly reversible with stationary law π. This is a Gaussian noising–denoising construction of the RGD/auxiliary-variable type; it is not an identification with a differently parameterized RGD kernel from another model.

For random-regular graphs with nontrivial eigenvalues O(√d), a can be O(β), instead of β√d. The Gaussian mean at a vertex is

$$
\mu_i=(Bx)_i=ax_i-\frac\beta{\sqrt d}\sum_{j\sim i}x_j
+\kappa\bar x,
\quad\bar x=n^{-1}\sum_i x_i.
\tag{5}
$$

All marginal Gaussian variances equal v=a+κ/n; for an edge ij the covariance is b=−β/√d+κ/n.

## 4. The conditional law is both samplable and controllable

### Exact sampling

Let w_i=exp(2y_i), and let E_k(w) be the kth elementary symmetric polynomial. The number k of positive spins in (4) has probabilities proportional to

$$
E_k(w)\exp[-\kappa(2k-n)^2/(2n)].
$$

Conditional on k, the positive-spin set S has weight proportional to ∏_{i∈S}w_i. Elementary-symmetric-polynomial dynamic programming computes these probabilities and samples the weighted subset in O(n²) arithmetic operations. Log-domain implementation avoids overflow. Thus this step has no hidden intractable posterior-sampling oracle.

### A uniform conditional functional inequality

Mikulincer–Sohn, *Fast mixing in Ising models with a negative spectral outlier via Gaussian approximation*, Theorem 1, gives discrete-time entropy contraction (1−o(1))/n for (4), uniformly in y, when κ/2≤n^{1−η} for fixed η>0. Apply their theorem with J=0, u=1, and their inverse-temperature parameter κ/2. Fixed d and β satisfy this condition for large n.

Their entropy-contraction convention implies a spectral gap at least (1−o(1))/(2n) by linearizing around density 1. Consequently,

$$
\boxed{\mathcal E_\Gamma(g,g)\le Cn\mathcal E_P(g,g)}
\tag{6}
$$

for a universal constant C and sufficiently large n in this regime. Indeed E_Γ(g,g)=E_Y Var_{ν_Y}(g); apply the conditional gap and then the same mixture conditional-variance comparison as in (1).

Source: https://arxiv.org/pdf/2512.22803, Theorem 1. Gaussian augmentation for Ising samplers is also discussed in https://drops.dagstuhl.de/storage/00lipics/lipics-vol353-approx-random2025/html/LIPIcs.APPROX-RANDOM.2025.46/LIPIcs.APPROX-RANDOM.2025.46.html, Section 5. The latter paper's rapid-mixing regime is not asserted to cover low-temperature MaxCut.

For any law ν and bounded observable b, (6) gives

$$
\boxed{|\mathbb E_\nu[\Gamma b-b]|
\le\operatorname{osc}(b)\sqrt{CnD_P(\nu/\pi)/2}.}
\tag{7}
$$

Thus local stationarity of ordinary Glauber transfers to this exact Gaussian proxy without the original noisy-copy posterior-gap hypothesis.

This is a comparison of Dirichlet forms and observables, not a coupling of trajectories. In particular, success of Γ from a uniform start alone does not automatically imply success of P from a uniform start.

## 5. An analyzable one-step energy law

We can approximate the conditional energy in (4) using a single scalar, with a uniform error bound.

For each y let m_y be the unique solution of

$$
m_y=\frac1n\sum_i\tanh(y_i-\kappa m_y).
\tag{8}
$$

Uniqueness follows because m−n^{-1}Σ tanh(y_i−κm) has derivative at least 1 and changes sign between −1 and 1. Put t_i(y)=tanh(y_i−κm_y).

**Lemma.** For every external field y,

$$
\boxed{\left|\nu_y(e)+\frac1{n\sqrt d}\sum_{ij\in E}t_i(y)t_j(y)\right|
\le\sqrt{\frac{d\kappa}{2n}}.}
\tag{9}
$$

**Proof.** Let q_y be the product measure with fields y_i−κm_y, and set M=Σ_i z_i. Then

$$
\nu_y(z)\propto q_y(z)\exp[-\kappa(M-nm_y)^2/(2n)].
$$

Since E_q M=nm_y and Var_q M≤n, Jensen's inequality gives a normalizing factor at least exp(−κ/2). Hence KL(ν_y||q_y)≤κ/2.

Shearer's entropy inequality for the d-regular edge cover gives

$$
\sum_{ij\in E}\operatorname{KL}((\nu_y)_{ij}\|(q_y)_i(q_y)_j)
\le d\operatorname{KL}(\nu_y\|q_y).
$$

Pinsker's inequality controls each pair-correlation discrepancy by the square root of twice its pair KL. Sum over edges and apply Cauchy–Schwarz to obtain (9). □

For fixed d,β this error tends to zero as n→∞, uniformly in y. The bound can be loose on small graphs.

### Reducing the Gaussian average to one- and two-dimensional integrals

Let μ=Bx and v=B_ii=a+κ/n. Define a deterministic scalar r_x by

$$
r_x=\frac1n\sum_i\mathbb E_{Z\sim N(0,1)}
\tanh(\mu_i+\sqrt v Z-\kappa r_x).
\tag{10}
$$

It is again unique. Define

$$
F_{v,b}(p,q)=\mathbb E[\tanh(p+Z_1)\tanh(q+Z_2)],
$$

where (Z_1,Z_2) is centered Gaussian with variances v and covariance b. Then

$$
\boxed{\Gamma e(x)=
-\frac1{n\sqrt d}\sum_{ij\in E}
F_{v,b}(\mu_i-\kappa r_x,\mu_j-\kappa r_x)+R_n(x),}
\tag{11}
$$

with the explicit bound

$$
\boxed{|R_n(x)|\le
\sqrt{\frac{d\kappa}{2n}}
+\kappa\sqrt{\frac{d\|B\|_{op}}n}.}
\tag{12}
$$

**Proof of the additional error term.** For Y∼N(μ,B), monotonicity in (8) gives

$$
|m_Y-r_x|\le\left|n^{-1}\sum_i\tanh(Y_i-\kappa r_x)-r_x\right|.
$$

The expression inside absolute values has mean zero. Gaussian Poincaré and a squared gradient norm at most 1/n bound its variance by ||B||_op/n. The product-energy expression in (9) is κ√d-Lipschitz as a function of m. Replace m_Y by r_x, average, and use the bivariate marginals of Y. This proves (11)–(12). □

The law in (11) retains empirical local types. If c_i is the cut degree and ℓ_i=(2c_i−d)/√d, then μ_i=x_i(a+βℓ_i)+κ\bar x. Therefore the scalar equation uses vertex types (x_i,c_i), and the energy sum uses adjacent pairs of those types. For fixed degree the number of types is finite. No independence of signed incident edges is assumed.

This is a one-step drift formula, not a closed multi-step evolution for those types. Their distribution after repeated updates may depend on larger neighborhoods and trajectory history.

## 6. What this resolves and what remains

The noisy-copy approach had two hard parts: understanding its posterior and transferring local stationarity through that posterior. The centered Gaussian construction changes the conditional family so that the transfer can be justified by a uniform known theorem. Its one-step energy can be analyzed by (10)–(12).

**The earlier cold-drift bound for the binary noisy-copy chain does not apply to Γ.** These are different kernels, although both preserve π. The tractable conditional law in (4) need not have near-optimal graph energy. Combining the old proxy's drift with the new proxy's comparison would be invalid.

The remaining mathematical task is to show that the resulting drift functional, or a controlled multi-step analogue, excludes low-energy locally stationary laws in the relevant annealing regime. One must establish that claim for the vertex/edge-type distributions actually possible along the dynamics; replacing them by independent signs is not justified.

For example, if one proves Γe(x)−e(x)≥c_ε>0 below the target on the required class, then (7), entropy dissipation, and the earlier drift-to-hitting argument produce a polynomial-time conclusion for ordinary Glauber. The comparison alone does not prove such a drift inequality, and no Parisi-quality theorem is asserted here.

An update to the preceding investigation: the Mikulincer–Sohn paper also proves exponential worst-case mixing lower bounds for sufficiently large fixed-degree random-regular antiferromagnetic Ising models at low temperature (Proposition 1). That result does not address uniform-start optimization. The present construction uses its positive conditional-model result; it does not assume the full MaxCut chain mixes rapidly.

## 7. Finite-instance experiment

We used the existing n=16,d=5 graph (seed 78600) and 512 independently generated uniform-start annealing reference states, with β increased from 0 to 2 over 16 sweeps. For each reference and each tested temperature, one Gaussian field was sampled. For Γ, its conditional expected energy was computed by summing all 2^16 configurations; for Γ_L the product conditional energy is analytic. Thus randomness here is in the Gaussian field and reference state, not in an approximate posterior sampler.

The centered shift was a/β=1.416709, versus √5=2.236068 for the Laplacian version. Bayes cancellation was checked over every spin configuration for a test field at each temperature, with maximum log-density residual below 5.5×10^{-13}. The product-tilt KL inequality used in (9) was checked on every sampled field.

All results, including initially suboptimal and initially suboptimal one-spin-stable subsets, are in results.json. These small-graph Gaussian estimates do not establish a uniform drift theorem or asymptotic scaling. Standard errors refer to independent reference/field replicates; they are not rigorous confidence bounds.

For the centered chain, the observed mean one-step energy drifts were:

| β | All 367 initially suboptimal references | The 67 also one-spin-stable |
|---:|---:|---:|
| 1 | −0.04748 ± 0.00326 | −0.07641 ± 0.00699 |
| 2 | 0.00568 ± 0.00165 | −0.00699 ± 0.00126 |
| 4 | 0.00684 ± 0.00154 | −0.00053 ± 0.00045 |

The difference between these two groups matters: improvement among all suboptimal references can come from states that still have improving single-spin moves. These measurements do not support simply postulating positive one-step drift at every suboptimal local maximum. Multi-step excursions, additional observables, or stronger information about locally stationary distributions may be required. At colder temperatures rare Gaussian events are especially hard to resolve with this sample size.

To reproduce:

```bash
OPENBLAS_NUM_THREADS=1 python maxcut_gaussian/experiment.py
```

Requirements: Python, NumPy, SciPy. The archive contains the frozen reference states and source dependencies. The earlier annealing generator is included for their provenance. No claim of literature novelty is made for Gaussian augmentation or its standard comparison principle.
