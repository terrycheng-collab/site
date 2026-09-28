# SITE 2026 Session 2 (Financial Regulation) — Paper Deep Dives

Numbering follows program order (NN in `s02-NN_*.pdf`). Papers #10 (NPL market, Allen & Clark) and
#11 (Banking as a Service, Buchak & Koont) have no public draft. See `sessions/session-02.md`.

---

# 1. Regulatory Arbitrage within the Firm
**Nicola Cetorelli (NY Fed), Shohini Kundu (UCLA) — July 2026**

**Question.** Capital rules are written for "the bank," but modern bank holding companies (BHCs)
contain dozens of subsidiaries under very different regimes. Do tighter bank capital requirements
reduce risk for the whole organization, or does the BHC move risk to its lightly regulated nonbank
affiliates?

**Data/methods.** FR Y-9C (consolidated), FR Y-9LP (parent-only, including inter-entity flows),
Call Reports (bank subsidiaries), and FR Y-11 (nonbank subsidiaries), linked through the
Cetorelli–Stern organizational-structure database. The filings directly show parent–subsidiary
equity investments, dividends, and internal funding rates. The
shock is the phased Basel III implementation from 2015. Organizational complexity is instrumented
with the year each BHC's home state lifted interstate-banking restrictions (Jayaratne–Strahan /
Kroszner–Strahan), in a reduced-form difference-in-differences with permutation placebos. A
stress-test module applies 1–15% losses to nonbank assets using 2013Q1 balance sheets.

**Findings.** (1) Banks in BHCs from states that deregulated one year earlier accumulate 0.74pp more
excess capital after 2015, about 5pp at the median 7-year gap. Consolidated BHC capital, assets,
and lending do not change. (2) The money moves internally in three steps: parent equity investments
shift from nonbanks to banks one-for-one, nonbanks pay sharply higher upstream dividends, and banks
retain earnings. Equity transfers (10–11% of bank assets) dwarf intra-firm loans and deposits
(1–2%). Complex BHCs cut outside equity issuance and increase buybacks. Nonbanks pay about 300bp
more for internal funding. (3) Nonbanks are "equity reservoirs": median equity/assets is 69% vs.
10% for banks, and the median nonbank holds 16% of consolidated equity on 2% of assets.
Reallocation scales with this "equity multiplier." (4) Banks become safer and more profitable
(lower charge-offs, fewer risk-weighted assets). Nonbanks lose capital and profitability, shift
from trading, VC, and advisory into leveraged consumer lending, and see distance-to-default fall.
BHCs add nonbank lending subsidiaries and shed insurance affiliates. (5) Stress test: in the
baseline (5% loss, recapitalize to 40%), the average BHC would use 18% of its excess capital, the
95th percentile 99%, and 4% would exhaust their buffers (4–6% across
scenarios). For tail-risk BHCs, 50% transmission of
nonbank losses erodes 72% of the bank-safety gain, and more than about 70% reverses it.

**Why it matters.** Regulatory arbitrage happens inside firms, not only between banks and outside
shadow banks. About one in four dollars of US nonbank financial assets sits inside a BHC, so
migration "to nonbanks" often stays within supervised organizations.

**Financial-regulation link:** entity-level capital rules can make measured bank safety look
better than the true economic risk of the group. The authors argue for prudential standards on
material nonbank subsidiaries, limits on equity extraction, and monitoring of internal capital
flows, and more generally for treating organizational structure as a determinant of how a
regulation actually lands.

---

# 2. The Optimal Use of AI in Financial Regulation
**Christopher Clayton (Yale), Antonio Coppola (Stanford) — May 2026**

**Question.** Can deep learning on granular portfolio-holdings data improve macroprudential
regulation, and can a purely predictive model be used for policy despite the Lucas critique?

**Data/methods.** Quarterly security-level holdings of about 37,000 non-bank financial
intermediaries in about 85,000 assets (nearly $40tn), with FactSet/Morningstar reference data. The
model is a "graph transformer," an attention-augmented graph neural network over the bipartite
investor–asset holdings network. Portfolio exposures bias the attention weights, and the model is
permutation-invariant and inductive. Inputs are the current holdings cross-section plus a realized
or scenario aggregate stress level. The target is the change in each investor-asset position.
Evaluation is strict walk-forward out-of-sample, with held-out asset classes and investors and
conformal prediction intervals. A fire-sale model with regulatory wedges supplies the theory.

**Findings.** (1) The model beats balance-sheet measures, econometric models, and other
deep-learning benchmarks at forecasting trading on both the extensive and intensive margins,
including in crises. It stays informative for entire asset classes (e.g., all corporate bonds)
withheld from training. (2) Although never trained on prices, its embeddings add 18pp of adjusted
R² for crisis-period bond returns beyond standard characteristics, vs. about 1pp from the best
low-dimensional fire-sale summaries (more than 10×). One interpretable embedding dimension,
crowdedness among flow-sensitive holders × illiquidity, carries about a quarter of that power. (3)
Institution-level predicted selling beats ΔCoVaR, fund outflows, trailing returns, and
concentration as a systemic-risk metric. (4) Theory: the optimal intervention is τ* = Ω·L̂, where
Ω is causal policy impact and L̂ is predicted forced selling. Under stated information conditions,
the structural loadings do not depend on the regulator's model choice, so a predictive model is
robust to the Lucas critique. A Θ-weighted predictive R² is a sufficient statistic for the welfare
gain, and prediction is most valuable where causal knowledge is strongest.

**Why it matters.** It gives a disciplined division of labor between machine-learning prediction
(recovering high-dimensional heterogeneity) and structural modeling (counterfactuals). It also
directly maps forecast accuracy to welfare.

**Financial-regulation link:** a concrete blueprint for supervisors with rich holdings data
(e.g., Form PF, N-PORT, insurance filings): use predictive models to *target* fire-sale
interventions across nonbanks and assets, and rely on structural elasticities for *how much* to
intervene.

---

# 3. Credit Commitments by Nonbanks
**Jing Huang (Texas A&M), David X. Xu (SMU) — June 2026**

**Question.** Banks are thought to have a structural advantage in credit lines because they are
deposit-funded (Kashyap–Rajan–Stein 2002). As credit moves to nonbanks, can nonbanks supply
liquidity insurance, and how do they manage the risk?

**Data/methods.** Hand-collected facility-level data on business development companies' (BDCs')
commitment books (revolvers, delayed-draw term loans), linked to their loan holdings, balance
sheets, cash flows, and the credit lines they receive from third-party lenders (mostly banks).
Liquidity shocks are measured as quarterly changes in unfunded commitments, and their volatility as
the time-series standard deviation. The theory is a layered Holmström–Tirole model: firms → BDC
(partial pooling) → bank (diversified, with sleepy depositors).

**Findings.** (1) BDC commitment-to-asset ratios have risen for a decade and reached bank-like
levels by 2025Q4. (2) Commitment books are much more concentrated (by industry, geography, and
sponsor) than on-balance-sheet loans. BDCs pick borrowers with better credit, sponsor backing, and
dual debt-equity exposure, and draws share a common component (e.g., 2020Q1). A typical BDC's
shock volatility is about 2.5× an equal-weighted all-BDC benchmark. A 1-SD shock would exhaust cash
in about a fifth of BDC-quarters. (3) BDCs with more commitments hold more undrawn bank lines, and
these lines, not cash, are the backstop. BDCs draw them and expand them (upsizing or new
facilities) when needed, and limits did not shrink during the 2023 regional-bank stress. (4) Only
about $0.53 of bank-line slack backs each $1 of unfunded commitments, consistent with the model's
prediction that BDCs optimally ration insurance because they lack a public backstop. (5) Rationing
creates an ex ante tragedy of the commons: each borrower underinvests in liquidity management
because it ignores how its draws crowd out others in the shared pool.

**Why it matters.** It redraws the bank/nonbank boundary. Nonbanks now supply liquidity insurance,
but it ultimately rests on bank credit lines and depositors, through a chain that FSOC's 2024
report flagged as a possible "dash for liquidity." This is the first data documentation of it.

**Financial-regulation link:** capital rules push banks to lend to middle-market firms indirectly
through BDCs. Supervisors therefore need to track bank lines to NBFIs as a contingent liquidity
exposure. The paper also identifies a nonbank-specific inefficiency (constrained pooling) that
bank-centric liquidity regulation does not address.

---

# 4. Real Origins of Financial Structure: The Role of Household and Firm Heterogeneity
**Greg Buchak (Stanford), Erica Xuewei Jiang (UCLA) — May 2026**

**Question.** Why are some financial systems bank-centered and others market-based? Standard
answers emphasize regulation and financial development. This paper asks how much comes from the
*real sector*: the characteristics of the households and firms being served.

**Data/methods.** Cross-country panel regressions of deposit shares and bank-loan shares on
household wealth, age, and inequality and on firm-sector composition (services, intangibles, size),
with year fixed effects and institutional controls. A structural equilibrium model:
- Households, indexed by net worth, age, and income, choose among deposits, money market funds
  (MMFs), bonds, and equity, and between bank and nonbank borrowing.
- Firms, by industry and size, choose real vs. financial assets, deposits vs. MMFs, and bank vs.
  nonbank debt.
- Banks compete monopolistically under capital and liquidity wedges; MMFs and nonbank lenders are
  competitive.

Elasticities come from Financial Accounts time series and policy instruments. Heterogeneity comes
from the Survey of Consumer Finances and the Census Quarterly Financial Report. The rest is
calibrated to 2019 prices and balance sheets.

**Findings.** (1) Cross-country: a 1-SD rise in household wealth per capita goes with about 6pp
lower deposit share. Services shares 10pp above the OECD median go with 5–7pp lower bank-loan
shares. (2) Micro: deposit shares fall steeply with wealth, while the bank share of *borrowing*
rises with wealth. Among firms, bank reliance is hump-shaped in size. (3) Model, 1983→2019
real-sector shift with intermediary technology and regulation held fixed: bank funding share −5.5pp,
liquidity ratio (securities/deposits) −17.4pp, bank credit share roughly flat (−0.5pp). Almost all
of this is household-driven (wealth, aging, concentration), while firm heterogeneity mainly changes
the composition of credit demand. (4) Shifting the US real sector toward other countries' profiles
explains a meaningful share of cross-country deposit reliance but leaves large residual dispersion
on the credit side.

**Why it matters.** It gives a demand-side foundation for the rise of private credit, private
equity, and market-based finance. Some of what looks like regulatory-driven disintermediation is
the financial system accommodating a wealthier, older, more service-oriented economy.

**Financial-regulation link:** to assess how much of the shift toward nonbanks is regulatory
arbitrage, one must first net out demand-driven structural change. Rules aimed at pulling activity
back into banks may fight secular real-sector forces.

---

# 5. The Elasticity of Home Purchases to Financing Costs: Evidence from Recent GSE Pricing Changes
**You Suk Kim (FRB), Feng Liu (CFPB), David Zhang (Rice) — June 2026**

**Question.** How much does homebuying respond to the price of mortgage credit, among a broad (not
just constrained) population? How much of the response runs through debt-to-income (DTI) limits
vs. direct demand? What does this imply for guarantee-fee (g-fee) policy as the GSEs prepare to
exit conservatorship?

**Data/methods.** Confidential HMDA (2022–2023) home-purchase loans above area-median income. Low-
and moderate-income borrowers are excluded because of the first-time-buyer fee waiver. The shock is
the May 2023 restructuring of GSE loan-level price adjustments. The design is a stacked
difference-in-differences comparing borrowers just above vs. below FICO cutoffs 640/680/720/760/780,
with no manipulation and no pre-trends. Heterogeneity is examined by county days on market (DOM)
and by counterfactual DTI. A structural housing-search model (logit entry and loan-type choice,
continuous-time search and bargaining) is fit to search moments to recover aggregate elasticities.

**Findings.** (1) A 100bp g-fee cut lowers the fee-adjusted GSE rate by 28–33bp and raises relative
home purchases by 13.9%. That is a 21–25% semi-elasticity per 50bp, 1.5–1.8× Bhutta–Ringo (2021)
and about 2× Hacamo. (2) DTI-unconstrained borrowers show elasticities about half those of
constrained ones. This is some of the first evidence of non-DTI rate sensitivity, and among highly
leveraged borrowers the effect is fully DTI-mediated, as in Bhutta–Ringo. (3) The semi-elasticity
more than doubles from the loosest to the tightest DOM quartile. (4) Model-implied aggregate
elasticities are much smaller (up to 16.4% per 100bp) because relative pricing mostly reallocates
*who* buys when inventory is tight. (5) Counterfactuals:
- A uniform +25bp g-fee cuts GSE volume 3.1–5.9% and total purchases up to 2.6%, but raises GSE
  profits by $1.26–1.39bn a year (about 1% of equity). Low-FICO borrowers shift to FHA.
- The result is nearly identical in a looser (2019-DOM) market.
- The 2023 reform itself reallocated across FICO bands (middle bands −1–4%) with small aggregate
  and income effects and +$0.24bn a year in GSE profits.

**Why it matters.** It pins down a key parameter for user-cost and macro-housing models (e.g.,
Greenwald–Guren) and shows that tight supply amplifies relative financing-cost effects.

**Financial-regulation link:** direct evidence for GSE reform. Higher g-fees can rebuild GSE
capital without making volume collapse. Risk-based pricing (the 2023 LLPA grid) had modest
distributional costs. Targeted rate subsidies (VA, employer programs) have strong effects in tight
markets.

---

# 6. Household Migration and Collateral Constraint: Cash-based Housing Resettlement in China
**Zhiguo He (Stanford), Zehao Liu, Xinle Pang, Yang Su, Kunru Zou — March 2026**

**Question.** Does relaxing household borrowing constraints have bigger effects when households can
relocate, because the binding constraint is the one in the city they *want* to live in?

**Data/methods.** China's cash-based shantytown renovation program (2015–2018, more than ¥4tn of
cash compensation), China Population Census micro-data, shantytown renovation loan data, and city
house-price indices. `loan_orig` is the cash paid in a city, scaled by its 2014 housing
transactions. `loan_dest` is a Bartik measure of cash flowing into a destination along the pre-2015
migration network, split by city-pair house-price gap. A dynamic spatial GE model has:
- life-cycle households choosing location, tenure, and savings;
- a collateral constraint;
- illiquid "shanty" vs. liquid housing;
- ownership in one city while living in another;
- a strong homeownership preference.

It is calibrated to 5 city tiers, with one 5-year period.

**Findings.** (1) House prices did *not* rise faster in cities paying out more cash (`loan_orig`),
but accelerated in cities receiving more migration-linked cash (`loan_dest`), with a small,
temporary supply response. (2) The `loan_dest` effect from high-price-gap origins is about 3× that
from low-gap origins, consistent with moves up the price ladder. (3) Mechanisms: cash in origin
cities makes existing urban migrants more likely to stay and buy in the destination (downgrade
mitigation), and raises new out-migration to pricier cities after 2014 (upgrade facilitation).
Both effects are stronger for high-gap pairs, with no effect for rural migrants. (4) Model:
- The housing-spending multiplier is 1.14 (1.18 with equilibrium prices) under cash vs. 0.80
  (0.84) under local-only vouchers, so migration amplifies spending by about 40%.
- The program explains more than 20% of 2016–20 house-price growth.
- Without the program, recipients' welfare would be about 22.8% lower; vouchers instead of cash
  would cost them about 5.3%.

**Why it matters.** Borrowing constraints measured at current locations understate true "shadow"
constraints once location choice is endogenous. That changes estimates of household responses to
credit relaxation.

**Financial-regulation link:** the design of credit and transfer policy (cash vs. place-restricted
vouchers, local LTV/down-payment rules) has spatial spillovers. Policy aimed at one city's housing
market can raise prices elsewhere, and macroprudential housing tools need to account for migration.

---

# 7. Buying from the Family: Private Equity-Owned Insurers and Their Affiliated Investments
**Amy W. Huber, Stefan Huber, Bella Shan, Christina Zhu (Wharton) — September 2026**

**Question.** PE firms now own insurers outright *and* run private-credit origination businesses.
When policyholder-backed capital sits in the same organization as credit businesses that need
funding, how does it change insurer investment?

**Data/methods.** Novel ownership map from NAIC Schedule Y combined with the universe of PE
insurance deals. "PE-owned" insurers (over 50% held by a PE firm directly, 100% in 95% of cases)
are distinguished from "PE-portfolio" insurers held by funds for their LPs and from independent
insurers. The map is linked to NAIC Schedules D and BA (security-level holdings, trades, affiliation
flags, prices, fair values, impairments) and to NAIC CLO stress tests. Valuation uncertainty and
performance are measured with arm's-length fair values assigned by independent insurers.
Specifications include same-security, same-day price comparisons.

**Findings.** (1) Scale: the number of PE-owned insurers rose more than 30-fold after the financial
crisis, and their assets grew from under $1bn in 2009 to $696bn in 2024. By 2024 they outnumber PE-portfolio insurers 2:1.
(2) After a PE takeover, structured securities are more than 40% of new investment (about 2× the
share at independent insurers), and more than 60% of those are affiliate-issued (under 2% for
independents). Nearly half are privately placed with no CUSIP. (3) Affiliated capital goes to
securities with higher fair-value dispersion. PE-owned insurers pay more for the same security on
the same day, 47bp more in private primary-market deals. (4) They keep capital committed when
affiliated positions go underwater. PE ownership offsets about 80% of the higher impairment
propensity that affiliation normally brings (and all of it the next year). PE-owned insurers sell
more often in general, but affiliation shrinks that extra selling by about 75% (62% for underwater
positions). (5) Securities with more affiliated PE-insurer money are more often below
cost after one year and have lower fair values from year two. The effect is concentrated outside
broadly syndicated CLOs. (6) Even within broadly syndicated CLOs, stress-test losses are larger for
tranches with more affiliated money. Scaled to the portfolio (26.1pp incremental × 32% structured
share × 49% affiliated), that is about a 4pp extra loss under a 2008 scenario, more than half of
the 7.6% equity buffer.

**Why it matters.** It documents empirically how the insurer + private-credit conglomerate model
weakens arm's-length discipline over beneficiary capital. The resulting risk shows up in pricing,
loss recognition, and stress losses.

**Financial-regulation link:** directly relevant to NAIC and state regulators' scrutiny of
affiliated and privately rated investments, CLO/ABS capital charges, and the FSOC/Fed focus on
private credit–insurance linkages. The paper suggests affiliated transactions warrant independent
valuation and higher capital charges. Forced sales by capital-depleted insurers could transmit
private-credit stress to public fixed-income markets.

---

# 8. Bank Runs With and Without Bank Failure
**Sergio Correia (Richmond Fed), Stephan Luck (NY Fed), Emil Verner (MIT) — July 2026 version**

**Question.** Are runs the cause of banking crises, turning small shocks into self-fulfilling
failures, or mainly a symptom of weak fundamentals? When do runs lead to failure and real damage?

**Data/methods.** LLMs applied to digitized historical newspapers build a near-universe of US bank
runs, 1863–1934: 3,984 runs, 13,772 suspensions, and 10,341 failures, each backed by articles
(finhist.com/bank-runs). Validation: runs line up with crisis chronologies; failures with a
reported run show 5pp larger pre-failure outflows; about 95% match on four ground-truth samples.
The runs are merged with national-bank balance sheets, macro and stock-market data, and newly
digitized local business-failure and manufacturing data. LLM classification also isolates 53
"non-fundamental" (misinformation or confusion) runs.

**Findings.** (1) The unconditional annual run probability for national banks is 0.39% (1.4% in
crisis years). Runs are far more likely at poorly capitalized, illiquid, noncore-funded banks, but
fundamentals alone predict runs poorly. Adding news helps: stock declines, local business failures,
and runs on other local banks. (2) A run raises the annual failure probability by 38pp (base
0.89%), but runs without failure outnumber runs with failure. In the bottom fundamentals decile,
59% of run banks fail; the top decile rarely fails. (3) Survivors accommodate withdrawals, signal
strength (equity or deposit injections), borrow from other banks, get clearinghouse support (11%),
or suspend temporarily (28% of non-failure runs). (4) Runs following other local runs are *less*
likely to cause failure ("jittery" depositors). Runs following local business failures are more
likely to (solvency). (5) Non-fundamental runs lead to failure only 11% of the time, and only at
weak or fraudulent banks. (6) Surviving banks' deposits and loans fall about 7% of pre-run assets
for more than four years, mostly at weak banks. City-level deposits, lending, and manufacturing
(about −5%) fall only after runs on weak banks or runs with failure.

**Why it matters.** It gives large-scale micro evidence on the Diamond–Dybvig vs.
fundamentals/information debate, and the authors read it as largely favoring fundamentals. Runs can
decide the *timing* of distress, but insolvency determines failure and real costs.

**Financial-regulation link:** supports prioritizing solvency supervision and early recognition of
losses over purely liquidity-focused tools. Deposit insurance and lender-of-last-resort facilities
mainly guard against runs that were not very costly historically. Crisis costs come from weak banks
failing.

---

# 9. Competing for Loan Informal Seniority: Theory and Evidence
**Theo C. Martins (BCB/FGV), Bernardo Ricca (Insper), Arthur Taburet (Duke) — April 2026**

**Question.** Retail borrowers with several lenders can choose whom to repay, because there are no
cross-default clauses. How common is selective default, what determines repayment priority, and
what does competition for that "informal seniority" imply for contract terms, welfare, and
bankruptcy rules?

**Data/methods.** Central Bank of Brazil credit register covering the universe of retail loans
(cards, mortgages, auto, consumer) with a common borrower ID across lenders. Selective-default
regressions use borrower×time and bank×time fixed effects. A difference-in-differences exploits
payroll-bank partnership changes: workers at the same firm with vs. without a prior relationship
with the new partner bank. The non-exclusive lending model extends Bizer–DeMarzo by allowing
repayment prioritization and lender investment in "relationship benefits." Welfare comes from a
sufficient-statistic calibration.

**Findings.** (1) Of 85M card users (June 2022), 46.5% hold cards from two or more issuers, which
make up more than 70% of balances. About half revolve, and 9% default on at least one card. (2)
Only 16% of defaulters default on all cards; with two cards, 76% default on only one. Defaulting on
one card barely changes limits or rates on the others. (3) Default rises with the number of cards
(7% with one vs. 17% with four or more). The difference-in-differences implies one more card lender
raises default by about 10pp (1.1pp for 0.11 new lenders), which is causal debt dilution. (4)
Selective defaulters default on 45% of their cards and prioritize those with higher limits (+4pp),
from digital banks (+14pp), or from lenders that also hold their mortgage (+14pp) or auto loan
(+5pp). Cross-selling therefore buys implicit seniority. (5) Model: debt dilution pushes toward
underprovision of relationship benefits, and the seniority race toward overprovision. The
calibration gives credit limits 7% below first-best (−9.5% dilution, +2.5% race). Equal-recovery
rules would remove the race and lower limits by a further 2.5%.

**Why it matters.** It is the first empirical and theoretical treatment of non-exclusive retail
lending with selective default. It also gives a new rationale for cross-selling: it earns repayment
priority.

**Financial-regulation link:** standard bankruptcy features such as equal recovery and cross-default
can *lower* welfare when lenders compete for seniority. Credit-register design (common borrower IDs
across products, which the US FR Y-14M lacks) is essential for supervising household
over-indebtedness.

---

# 12. Financial Supermarkets? Cross-Selling in Retail Banking
**Shengmao Cao, Lulu Wang (Northwestern) — June 2026**

**Question.** Consumers often hold several products at one bank. What drives this, and how does it
change franchise value, entry, regulation, and merger analysis, which are usually done one product
market at a time?

**Data/methods.** The Survey of Consumer Finances, the MRI-Simmons Ultimate Survey, and an original
Prolific survey. The Prolific survey reconstructs search (consideration sets, prior accounts,
direct-mail exposure), switching histories, and stated responses to hypothetical price changes and
product discontinuation. The structural model has consumers who get stochastic chances to switch
one product. They form consideration sets and choose banks with correlated preferences,
consideration spillovers, and same-bank complementarity. Consumers are transactors or revolvers.
Banks set deposit rates, card rewards, and APRs in a dynamic Nash equilibrium. Estimation is by
Monte Carlo EM.

**Findings.** (1) About 35% of consumers with one checking account and one card hold both at the
same bank, against 6.4% under independence. Depositors are about 6× more likely than non-depositors
to hold the bank's card at megabanks and more than 60× at regionals. Similar patterns hold for auto
loans, mortgages, and brokerage, and across credit scores, so screening information does not
explain it. (2) The surveys support all three mechanisms (correlated consideration, relationship-
driven consideration, and switching if the complementary product were discontinued). (3) Rewards
cards are about 16% of accounting profits, but eliminating them costs about 26% of total profits.
Cards roughly break even and act as a loss leader for high-margin deposits; large banks' card
margins would be a third higher without this strategy. (4) A deposit-only narrow-bank entrant is
at a steep disadvantage, which helps explain rare deposit entry despite high spreads. Interchange-
fee regulation spills over into deposit competition. (5) A Citi + super-regional merger is
anticompetitive without complementarity but pro-competitive with it: the merged bank sweetens card
rewards and rivals *raise* deposit rates. A deposit-HHI screen cannot see this.

**Why it matters.** It identifies cross-selling as a major, previously unmeasured source of bank
franchise value and market power.

**Financial-regulation link:** merger review based on deposit HHI (the DOJ/FTC bank guidelines),
interchange caps (Durbin-style), and narrow-bank or stablecoin entry all need multi-product
analysis. Regulating one product market moves competition in the others.

---

# 13. How Do Banks Compete? Evidence from Advertising Videos
**Xugan Chen (Yale), Allen Hu (UBC), Song Ma (Yale) — newer 88-page draft (vs. 73-page copy in Session 12)**

**Question.** Which concrete actions, especially non-price ones, do banks use to compete and build
franchise value, and how do they affect monetary transmission?

**Data/methods.** 51,349 Nielsen Ad Intel clips (2,739 institutions, 210 local TV markets (DMAs),
3,098 counties, 2004–2020), merged with Call Reports, FDIC Summary of Deposits, HMDA, and CRA. An
unsupervised multimodal video-embedding pipeline clusters content into pricing, service, and trust
with no human labels. New in this draft is a formal framework. Banks differing in operational reach
set rates and allocate ads across content types. Pricing ads raise rate attention; service
(informative) and trust (persuasive) ads divert it. A two-period sleepy-depositor extension covers
monetary policy. Empirics use county-year fixed-effect panels, entry/M&A/fintech/Wells Fargo events,
a Drechsler–Savov–Schnabl deposits-channel design, and a DMA-border discontinuity.

**Findings.** (1) Content is 18% pricing, 29% service, and 53% trust. Variation is mostly
bank-level, bank×year, and bank×county, not product or region. (2) The model predicts a deposit-
market "fat cat" effect: high-reach banks displace pricing content, soften price competition, and
sustain wider spreads. High-reach banks tilt toward service; thin-franchise banks lean on trust;
banks with neither must compete on price. Because ads are broadcast, lower rate awareness spills
over to the whole market. (3) An interquartile rise in local mortgage market share goes with 2.5%
fewer pricing mentions. (4) Organic branch entrants push pricing and trust, while M&A entrants push
service. Incumbents answer fintech entry with service content. Wells Fargo raised trust content
about 14% after 2016, and nearby rivals followed. (5) Content matches fundamentals: high-rate banks
advertise pricing, and low-complaint banks advertise service. (6) When the Fed hikes,
service-heavy banks widen spreads more and shrink more, amplifying the deposits channel. (7) The
border discontinuity shows ad content causally shifts demand for deposits, mortgages, and
small-business loans.

**Why it matters.** It is direct evidence that a budgeted non-price action (about 9.5% of bank
budgets) manufactures deposit-franchise value. It also supplies a content-based microfoundation for
sleepy depositors.

**Financial-regulation link:** franchise value that rests on attention and persuasion rather than
service quality is relevant to consumer-protection rules (advertising and disclosure of deposit
rates), to interest-rate-risk supervision (deposit betas that depend on advertising strategy), and
to merger review of non-price competition.

---

# 14. Household Portfolio and Deposit Insurance: Implications for the Supply of Safe Assets
**Pulak Ghosh (IIM Bangalore), Nicola Limodio (Bocconi), Nishant Vats (WashU)**

**Question.** Deposit insurance (DI) caps limit the supply of truly safe assets to households. How
do DI limits shape household allocation between deposits and risky assets outside crises?

**Data/methods.** A portfolio model in which limited DI kinks the capital allocation line. The
empirical sample is a 4% random sample of depositors at a large Indian private bank, linked to
stock, mutual-fund, and illiquid-investment holdings, spending, loans, credit scores, demographics,
and family members. The natural experiment is India's February 2020 increase of the DI limit from
₹1 lakh to ₹5 lakh. The bunching-in-differences design compares bunchers at the old limit with
non-bunchers, using depositor and ZIP×month fixed effects. Security-level portfolio tilts use
ISIN×time fixed effects. A model calibrated to the mass of bunchers recovers perceived failure
risk and welfare.

**Findings.** (1) Depositors bunch at the ₹1 lakh threshold. Before the change, bunchers hold more
stocks, mutual funds, or illiquid long-term assets and look like non-bunchers on demographics,
income, and credit. (2) After the expansion, bunchers raise deposits 3.6–5.1% relative to
non-bunchers, a 2.1–3.1% elasticity per pp of coverage in line with De Roux–Limodio. This survives
pre-trend, placebo, bandwidth, within-household, and COVID checks. (3) The increase comes from
bunchers who trade. They liquidate stocks and mutual funds (within security-time), which accounts
for about 72% of the deposit increase. (4) Bunchers had tilted toward state-owned-enterprise stocks
as quasi-guaranteed substitutes and unwind them, with a transient price drop that reverts within a
month. (5) The share of bunchers is a sufficient statistic for depositors' perceived bank-failure
probability: about 0.54% at risk aversion 3 and 1.74% at 10. (6) Welfare rises by at least 0.04%
even after bank moral hazard. The gains grow with risk aversion but are smaller for very wealthy
depositors who remain partly uninsured. No evidence of spending, intra-household, or lending
channels.

**Why it matters.** It shows DI is a supply lever for household safe assets, with spillovers to
equity and mutual-fund markets, especially in emerging markets where deposits are the main safe
asset.

**Financial-regulation link:** informs the post-SVB debate on DI limits by quantifying portfolio
reallocation, market spillovers, and welfare. It also gives regulators a cheap, depositor-implied
bank-risk indicator (the bunching mass).
