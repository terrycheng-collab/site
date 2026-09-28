# SITE 2026 Session 1 — Deep dives
*Empirical Implementation of Theoretical Models of Strategic Interaction and Dynamic Behavior (Jul 20–21, 2026)*

Numbering matches `sessions/session-01.md` and the `s01-NN_*.pdf` files. Paper 5 ("Who Gets a Patent?",
Hong-Lemus-Shea) has no public text or abstract and is omitted.

---

# 1. Measuring the Option Value of Change: Theory and an Application to Operation Ceasefire
**Sylvain Chassang, Meichen Chen, Michal Kolesár (March 2026)**

**Question.** If a program's effect differs across sites but persists over time within a site, a policymaker can adopt it everywhere and then keep it only where early results look good. How do we estimate the value of such a *dynamic* adoption rule from observational data, and how much does it improve on static adoption?

**Data/methods.** Potential-outcomes framework with unit-level heterogeneous, time-varying effects and auto-correlated errors; treatment varies across units but not within a unit over time. The core problem is that period-by-period unbiased effect estimates are correlated across periods through the *errors*, so a plug-in estimate of "keep if early effect is good" is biased upward. The fix exploits structure on the outcome time series — an exclusion restriction that limits how past treatment affects future outcomes, satisfied by an observed-Markov-state model or an unobserved Markov state independent of treatment history — to extrapolate outcomes for never-observed "treat then drop" histories. A powered placebo test uses random subsets of controls as fake treated units. Data: a newly assembled list of Operation Ceasefire–style adoptions (122 rollouts counted 1996–2018) matched to UCR homicide data for large local police departments, estimated under a latent-state model and an autoregressive model.

**Findings.** Average effect: −0.76 homicides per 100k (insignificant; treated-city mean 15.74). Dynamic adoption — drop the program if the first-two-year estimate is unfavorable — yields −1.82 (insignificant) to −2.43 (significant at 5%) per treatment year depending on the model, a significant improvement on static adoption under both. Naive plug-in estimates of the dynamic rule's value (−3.02 to −4.49) are badly inflated.

**Why it matters.** It gives a principled middle ground between reporting only curated success stories (as the program's network does) and reporting a diluted average, and it shows early outcomes can target continuation even when ex-ante covariates predict nothing.

**Strategic/dynamic-methods link:** a dynamic decision problem (stop/continue treatment) is evaluated from observational panels by imposing just enough Markov structure to identify counterfactual histories, which is the session's theme of counterfactuals under minimal maintained assumptions.

---

# 2. Synthetic Blips: Generalizing Synthetic Controls for Dynamic Treatment Effects
**Anish Agarwal, Sukjin Han, Dwaipayan Saha, Vasilis Syrgkanis, Haeyeon Yoon (April 2026)**

**Question.** How can we identify unit-specific counterfactual outcomes under *arbitrary sequences* of treatments when treatments are assigned adaptively based on an unobserved, endogenously evolving state? Standard sequential-exogeneity (g-methods) assumptions fail under unobserved confounding, and staggered-adoption DiD/event studies don't cover reversible, multi-valued treatment paths.

**Data/methods.** A low-rank latent-factor model for "blip" effects, i.e., a structural nested mean model with low-rank structure, which nests linear time-varying and time-invariant dynamical systems. Identification is backward induction: the blip of treatment *d* at period *t* for a target unit is a linear combination of blips of donor units that received *d* at *t*. This avoids needing donors for every full treatment sequence, which is combinatorially explosive for naive synthetic interventions. The paper gives PCR-based estimation algorithms (SBE-PCR) with asymptotic theory and quantifies the tradeoff between sample complexity and how adaptive the policy may be. Application: 2,052 Korean firms 2006–2015 (Statistics Korea SBA merged with K-SURE export-insurance and EXIM export-loan records; 167 firms first treated 2011–15), with four treatment values (none / insurance / loan / both) and 119 covariates/pre-periods.

**Findings.** Insurance has little early effect but large gains from year 4. Loans reduce exports for two years and then turn positive (a working-capital channel). Cumulative five-year ATEs are ≈85.4 bn KRW for insurance and ≈33.6 bn KRW for loans. Timing matters: back-loaded support (0,0,d,d,d) beats front-loading, and spreading support evenly performs worst, especially for insurance. Firm-specific estimates feed "retrospective" policy learning, which finds reallocations that raise exports with less spending, and "prospective" decision-tree rules for new applicants.

**Why it matters.** This is the first synthetic-control method for dynamic, adaptively assigned treatment regimes. It links econometric panel methods with the biostatistics SNMM/g-estimation literature and yields individualized dynamic effects and targeting rules.

**Strategic/dynamic-methods link:** it identifies the value of alternative *dynamic* treatment policies (sequencing and timing) under unobserved, time-varying confounding, a reduced-form counterpart to estimating counterfactuals in dynamic single-agent models.

---

# 3. Inference for Treatment Effects Conditional on Generalized Principal Strata using Instrumental Variables
**Yuehao Bai, Shunzhuang Huang, Sarah Moon, Andres Santos, Azeem Shaikh, Edward Vytlacil**

**Question.** Many IV treatment-effect papers each develop bespoke bounds for a specific parameter under specific response-type restrictions. Is there one general inference method for any parameter of the form E[g(R) | R ∈ R′], where R is the full response type (all potential outcomes and potential treatments)?

**Data/methods.** Discrete treatment and instrument, general outcome; instrument exogeneity plus restrictions ruling out certain response types. This nests Imbens-Angrist monotonicity, one-sided noncompliance, Kirkeboen-Kline-Walters and Heckman-Pinto revealed-preference restrictions, and Manski-Pepper-type ordering restrictions. The parameter class includes ATE, LATE, principal-strata effects, probability of benefit or no harm, and persuasion rates. Key theorem: the identified set and the model's testable implications reduce to existence of a *nonnegative solution to a specially structured linear system*. Building on Fang et al. (2023), with new strong approximations and better coupling rates, they construct tests of H₀: θ₀ ∈ identified set and of model validity. These tests are uniformly valid even when the treatment/instrument or response-type support is large relative to n, and they extend to infinite-support outcomes.

**Findings.** Simulations support size and power. Revisiting Blattman, Jamison & Sheridan's (2017) Liberia factorial RCT (CBT × cash, n=999) under one-sided noncompliance, with and without "no harm": specification tests don't reject (p = 1.00; 0.91/0.18 with no-harm). There is no short-run evidence that both treatments beat either alone. In the long run, at least ≈5% of the population would not sell drugs with therapy+cash but would with cash alone (CI [0.048, 0.298]). Among tc/c pairwise compliers, the ATE CI [−0.232, −0.047] excludes zero. Results versus therapy alone are inconclusive.

**Why it matters.** It replaces case-by-case closed-form bound derivations, which are feasible only for small response-type spaces, with a single computationally feasible LP-based inference engine that applies to settings where no method existed.

**Strategic/dynamic-methods link:** this is theme (1), inference on partially identified models: behavioral (revealed-preference) restrictions on response types become linear constraints, and inference remains valid in high dimensions.

---

# 4. From Unstructured Data to Demand Counterfactuals: Theory and Practice
**Timothy Christensen, Giovanni Compiani (April 2026)**

**Question.** BLP-style demand models need product attributes that capture the true dimensions of differentiation. When those attributes are proxied by ML embeddings of images, text, reviews, or surveys (or by noisy, dimension-reduced numeric attributes), counterfactuals can be biased and inference invalid. How can researchers correct this without knowing the form of the mismeasurement?

**Data/methods.** Poor proxies are treated as *model misspecification*, not observation-level measurement error. The model is reparameterized with a composite parameter capturing how proxies and structural parameters jointly enter utility. This turns counterfactual estimation into a two-step problem, with a closed-form, one-step bias correction added to the naive estimator. The corrected estimator is efficient, has analytic standard errors (no bootstrap, no re-optimization; derivatives via autodiff), and allows data-dependent proxies such as embeddings fine-tuned on the same choice data. LM-statistic diagnostics guide how many and which proxies to include. The approach covers market-level BLP with IVs (optionally with micro data) and individual-choice models with product fixed effects, and is not tied to mixed-logit functional forms.

**Findings.** In simulations, the corrected estimator has lower bias *and* lower variance than the naive one at every level of mismeasurement, with only a small efficiency loss in the knife-edge case of perfect proxies. Using Compiani et al.'s (2025) experimental first- and second-choice data, parameters are estimated on first choices and then used to predict second choices after product removal. The correction raises the hit rate for a product's closest substitute from 40% to 70% in the preferred specification, and the diagnostics correctly flag the best proxy set.

**Why it matters.** It makes ML-derived product representations usable in structural IO with valid inference, and it doubles as a cheap robustness check for conventional attribute-based demand models.

**Strategic/dynamic-methods link:** this is theme (4): it targets the *counterfactual* (substitution, merger or removal effects) directly and protects it against misspecification of a first-stage input, in the same debiasing spirit as the session's DML-flavored papers.

---

# 6. Bidding for Reputation
**Jingyi Cui (Yale job market paper, November 2025)**

**Question.** On platforms for experience goods, new sellers "invest" in reputation through low introductory prices, generating information spillovers to future buyers and diverting business from rivals. Do forward-looking sellers and a profit-maximizing platform push the market toward the social optimum?

**Data/methods.** Proprietary Freelancer.com data: 3 million wage bids by 100k+ workers on 83k jobs (one skill category, 7 months of 2018), including losing bids. Workers are tracked as they accumulate reviews. The dynamic equilibrium auction model has discrete persistent public worker types (differing in opportunity cost, baseline productivity, quality distribution, and human-capital accumulation), symmetric Bayesian learning about latent quality from reviews, and human capital from experience. Workers bid anticipating future reputation and experience, and in equilibrium perceived win probabilities equal actual ones. Estimation extends two-step dynamic-game methods. Step 1 uses EM (Arcidiacono-Miller style) adapted to continuous actions, multidimensional unobserved heterogeneity, win-probability transitions that depend on *rivals'* types, and exchange-rate instruments for bids endogenous to match shocks. Step 2 uses MSM with forward-simulated continuation values in the bid FOCs.

**Findings.** Higher-productivity types also have higher opportunity costs. Employers pay 22–24pp more for a worker with five good reviews, roughly half for expected quality and half for human capital. Information and human-capital gains from a match often exceed the job's flow surplus, especially for inexperienced workers. The first review's value goes 35% to the worker and 65% to future employers. Relative to myopic bidding, forward-looking bidding raises the number of reviewed workers by 52% and quadruples matches, but investment is still below the social optimum. The surplus-maximizing platform subsidy for hiring new workers raises total surplus 22% and also raises platform profit. The profit-maximizing subsidy is smaller but captures 80% of that gain. Larger subsidies trade off exploration against exploitation, since hiring shifts away from experienced workers.

**Why it matters.** It quantifies the classic information free-riding/experimentation problem and shows that private incentives (seller investment plus platform commissions) close much, but not all, of the gap.

**Strategic/dynamic-methods link:** this is theme (3): estimating a dynamic game with continuous actions and persistent unobserved heterogeneity, using two-step CCP-style methods extended with EM and instruments, then running equilibrium counterfactuals.

---

# 7. Statistical Inference of Optimal Allocations I: Regularities and their Implications
**Kai Feng, Han Hong, Denis Nekipelov (arXiv 2403.18248v5, February 2026)**

**Question.** Plug-in optimal allocation rules (assign each unit the option with the largest estimated weighted conditional mean) involve indicator functions, which break standard asymptotics. When is the *value* of the optimal allocation (the "social welfare potential function") differentiable in its inputs, and what inference follows?

**Data/methods.** Pure theory. The analysis studies the sorting operator using Hausdorff measure and area/coarea formulas from geometric measure theory, generalizing Chernozhukov et al.'s (2018) integration-on-manifolds approach. It proves Hadamard differentiability of γ(λ, g) in both the welfare weights λ and the conditional-mean functions g under primitive rather than assumed conditions. The value function is positively homogeneous and convex in g given λ, and in λ given g, which gives an envelope theorem.

**Findings.** (i) Functional-delta-method asymptotics for the value-function process of binary *resource-constrained* allocation and for the plug-in ROC curve, with a computationally feasible bootstrap validated when the propensity model is correctly specified. (ii) The first-order derivative with respect to the policy is degenerate. Combined with DML/sample splitting, this yields a debiased value-function estimator. (iii) The same regularity conditions imply the margin assumption from classification, which justifies fast regret rates for multi-class plug-in rules.

**Why it matters.** It puts inference on "how much welfare does targeting buy?" on a rigorous footing for the common two-step ML-then-threshold workflow.

**Strategic/dynamic-methods link:** this is theme (4) at its most abstract. It gives valid inference for a counterfactual welfare object defined by an optimization, the same technical issue that arises in single-agent decision models.

---

# 8. Testing Inequalities Linear in Nuisance Parameters
**Gregory Fletcher Cox, Xiaoxia Shi, Yuya Shimizu (arXiv 2510.27633, November 2025)**

**Question.** How can we test H₀: ∃δ such that Cδ ≤ b, where C (the Jacobian) and b are estimated reduced-form objects and δ is partially identified, simply and without tuning parameters? This covers subvector inference and specification tests in linear moment (in)equality models and inference on parameters bounded by linear programs (discrete IV with shape restrictions, PRTE/MTR bounds).

**Data/methods.** First, an elementary closed-form formula for the data-dependent degrees of freedom in Cox-Shi's (2023) sCC test. It replaces a sequence of LPs and reveals that the sCC test is a Sargan-Hansen J test on the active inequalities. Second, the new generalized conditional chi-squared (GCC) test allows an *estimated* Jacobian. A "stable rank" condition on minimal submatrices (weaker than full-rank strong identification) ensures constraint-set convergence, and a first-stage δ estimate that converges to a point in the identified set gives a consistent variance, analogous to two-step optimal GMM. A refined RGCC variant has slightly more power.

**Findings.** Uniform asymptotic validity. Simulations based on MST18 show good size and power at low computational cost. Re-analyzing Kline-Tartari (2016) Jobs First labor-supply transition probabilities, GCC/RGCC CIs are qualitatively the same as KT16's naive and conservative CIs: significant extensive-margin outflows from 0r and intensive-margin inflows into 1r, especially from 2n. Sometimes they are narrower (π₀ᵣ,₁ₙ), and they need no manual elimination of nuisance parameters. All nine CIs take ≈4s (GCC) or ≈220s (RGCC).

**Why it matters.** It makes subvector inference in linear partially identified models about as easy as computing a QP statistic, and it is the only method in this class that is both tuning-parameter-free and simulation-free.

**Strategic/dynamic-methods link:** this is theme (1). Revealed-preference bounds from structural choice models become linear inequalities, and the paper supplies plug-and-play inference that allows partially identified nuisance parameters.

---

# 9. Inference for Linear Systems with Unknown Coefficients
**Yuehao Bai, Kirill Ponomarev, Max Tabord-Meehan, Andres Santos, Azeem M. Shaikh, Alexander Torgovitsky (arXiv 2604.24904)**

**Question.** How can we test whether a linear system A₀x₀ + A₁x₁ = β has a solution with x₁ ≥ 0 when *all* coefficients are estimated? Examples include NPIV with shape restrictions (Freyberger-Horowitz), average marginal effects in random-coefficient models (Fox et al.), MTR bounds (Mogstad-Santos-Torgovitsky), synthetic parallel trends with convex weights, and counterfactual choice probabilities in distribution-free binary choice.

**Data/methods.** First, an impossibility result: the null can be dense in total variation, so no test has power above size. Second, a Farkas-lemma characterization of (a subset of) the null's TV closure: for every unit vector, the minimum of a set of linear inequalities in the projection of (A₁, β) onto the orthogonal complement of A₀'s column span must be non-positive. Third, a sample-splitting test: the first half finds the most-violating direction (two LPs), and the second half computes a closed-form statistic compared with a normal quantile. The "direct" variant tests all inequalities. The "screening" variant tests one inequality, assuming the others are positive with high probability, and has one tuning parameter.

**Findings.** Uniform validity under weak, interpretable rank conditions while p, d₀, d₁ grow with n. Competing methods (Cox et al. 2025; Goff-Mbakop 2025) need rank conditions that may fail and don't cover high dimensions. In simulations, the screening variant gives shorter CIs than the direct variant.

**Why it matters.** It is a fast, simulation-free, high-dimensional-valid tool for the large class of problems where partial identification reduces to LP feasibility with estimated coefficients.

**Strategic/dynamic-methods link:** this is theme (1), and it complements paper 8. Together they are two answers to "LP-based bounds with estimated coefficients," one via conditional chi-squared and one via sample splitting.

---

# 10. Production Function Estimation without Invertibility: Imperfectly Competitive Environments and Demand Shocks
**Ulrich Doraszelski, Lixiong Li (August 2025)**

**Question.** The OP/LP/ACF proxy approach, now also the engine of De Loecker-Warzynski markup estimation, requires invertibility: equal productivity must imply equal input or investment choices. That fails with firm-specific demand shocks, imperfect competition with unobserved rivals, unobserved conduct changes such as M&A or collusion, and heterogeneous input prices or financial constraints. What goes wrong, and what can still be done?

**Data/methods.** When invertibility fails, productivity is a hidden Markov state, and (by Kalman/particle-filter logic) the entire history of observables improves its prediction. That yields tests: add lags of observables to the step-1 regression. Building on Doraszelski-Jaumandreu (2024), the lagged step-1 prediction error enters the step-2 moment and invalidates capital as an instrument. The paper then derives a necessary and sufficient condition for the step-2 moment to hold for the true production function and *some* law of motion, a Neyman-orthogonal modified moment, a sensitivity diagnostic dθ(λ)/dλ at λ = 1 (λ scales the step-1 prediction error), Monte Carlo evidence, and applications to Spanish manufacturing firms and US manufacturing industries.

**Findings.** Invertibility is strongly rejected in both datasets. The fix is simple: include every step-2 instrument in the step-1 regression (at a minimum, add the *lead* of capital), model the law of motion flexibly, and use a "kitchen-sink" step 1. In several examples this eliminates the bias, and in general it gives a first-order bias correction. The orthogonalized moment makes step-2 asymptotics invariant to step-1 noise, so ML first stages (neural nets, forests) can be used, and it substantially improves finite-sample performance in Monte Carlo experiments. The diagnostic flags when remaining higher-order bias could be large.

**Why it matters.** Productivity and markup estimates underlie large literatures on market power and misallocation. This paper shows their core assumption is testable and rejected, and it provides low-cost, practical repairs.

**Strategic/dynamic-methods link:** invertibility fails because of strategic interaction (rivals' unobserved productivities enter each firm's policy) and dynamics (hidden-state productivity). The paper retools a standard dynamic-model estimator to work without solving the game.

---

# 11. Tractable Identification of Strategic Network Formation Models with Unobserved Heterogeneity
**Wayne Yuan Gao, Ming Li, Zhengyan Xu (March 2026)**

**Question.** Can structural parameters in network formation be identified when links depend both on endogenous network statistics (strategic interdependence, e.g., number of common friends) and on individual fixed effects (degree heterogeneity)? The equilibrium map is intractable because the space of possible networks is enormous, equilibria are often multiple, and iterative procedures may not converge.

**Data/methods.** "Bounding-by-c", extending Gao-Wang (2026): endogenous covariates are treated as random variables, and monotonicity plus indicator-function arguments give inequalities that hold whatever equilibrium is realized. Subnetwork configurations produce identifying restrictions. Tetrads difference out *all* fixed effects, leaving bounds that depend only on the idiosyncratic-shock distribution. Triads and weighted "incomplete differencing" restrictions difference out some fixed effects and profile over the rest, conditional on observables. General weighted cycles unify these cases. Primitive conditions come from embedding the model in Leung's (2019) sparse-network framework, with a greedy packing argument for consistency of tetrad conditional probabilities.

**Findings.** Point identification holds with logistic shocks and a comparison-pattern invariance condition (satisfied by common-friends counts and the Jaccard index). A log-odds ratio of tetrad probabilities, conditioned on diagonal link absences that isolate the endogenous covariates, identifies a linear index of the parameters. This gives a simple conditional-logit estimator that generalizes Graham's (2017) tetrad logit to strategic settings. Preliminary simulations show nontrivial bounds on the strategic-interaction parameter in the full model. Formal inference, larger Monte Carlo studies, and an application are left to future work.

**Why it matters.** It closes a long-standing gap between the fixed-effects dyadic literature (Graham, Gao) and the strategic-formation literature (Mele; de Paula-Richards-Shubik-Tamer; Sheng), which previously had to give up one feature to handle the other.

**Strategic/dynamic-methods link:** this is theme (3), identification of a static game with multiple equilibria and unobserved heterogeneity. Moment inequalities that hold regardless of equilibrium selection make it possible.

---

# 12. Identification of Structural Parameters in Dynamic Discrete Choice Games with Fixed Effects Unobserved Heterogeneity
**Victor Aguirregabiria, Jiaying Gu, Pedro Mira** — *summary based on the March 3, 2021 draft (Gu's website); the April 2026 program version is public only as a title/abstract page*

**Question.** In dynamic discrete games, persistent unobserved heterogeneity is confounded with both kinds of key parameters. It mimics state dependence (switching, adjustment, and entry costs) and, when correlated across players, mimics strategic or peer effects. Existing dynamic-game estimators use random effects (finite mixtures). With short panels (many markets, small T), which parameters can be identified with *fixed effects*, leaving the heterogeneity distribution and initial conditions unrestricted?

**Data/methods.** The paper extends Cox-Rasch-Andersen-Chamberlain sufficient-statistic conditional likelihood, building on Honoré-Kyriazidou's fixed-effects discrete-choice VAR, to two-player dynamic games. The cases are myopic vs forward-looking players (whose continuation values are nonlinear in the fixed effects), complete vs incomplete information, and triangular (Stackelberg) vs full contemporaneous interaction. When conditional likelihood fails, a Bonhomme (2012) / Dobronyi-Gu-Kim functional-differencing approach derives moment equalities and inequalities. For multiple equilibria, Lemma 1 shows how sufficient statistics for the incidental parameters in *upper and lower bounds* of history probabilities yield partial identification.

**Findings (by proposition).** In the myopic triangular game, the competition effect γ₂ is identified iff own switching cost β₁₁ or cross-lag effect β₁₂ is zero, so the model with β₁₂ = 0 is fully identified. Functional differencing identifies γ₂ and β₁₂ when players share a common market fixed effect, which conditional likelihood cannot do. With full contemporaneous interaction under complete information, switching costs are point identified for particular histories (robust to private vs common knowledge), and strategic effects are partially identified. Under incomplete information with sign restrictions (β ≥ 0, γ ≤ 0, γ₁γ₂ ≤ 16), all parameters are partially identified. With forward-looking players, switching costs are point identified in the triangular game and partially identified with contemporaneous effects. The authors describe the combination of fixed-effects sufficient statistics with bounds/partial identification as a first. The 2021 draft's estimation, empirical application (a dynamic price-competition game, per the 2026 abstract), and conclusion sections are "TBW".

**Why it matters.** It gives a way to estimate switching costs and competitive or peer effects in dynamic games that is robust to arbitrary persistent heterogeneity, the main threat to both sets of parameters.

**Strategic/dynamic-methods link:** this is theme (3) at its core: identification of dynamic non-cooperative games in short panels with nonparametric fixed effects and multiple equilibria.
