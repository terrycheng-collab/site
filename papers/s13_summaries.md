# SITE 2026 Session 13 (Market Failures and Public Policy): deep dives

Paper numbers match `sessions/session-13.md`. Papers #5–#8 were not available (see the coverage
section there), so there is no deep dive for them.

---

# 1. Fraud, Evasion, and Enforcement in Decentralized Environmental Regulation (Jacob Bradt, Jackson Dorsey; UT Austin; Mar 2026)

**Question.** When a regulator hands enforcement to private inspectors, how big is the market for
fraud that results? How much pollution does it cause? And what happens when the regulator shuts
the fraudulent suppliers down?

**Data/method.** Covers 100 million Texas vehicle emissions inspections (2016–2024) in the 17
non-attainment counties, about 5,500 licensed stations, plus DPS station and enforcement records.
The measurement contribution is a mixture model built on several statistical fraud indicators
(e.g., eVIN mismatches and reused calibration IDs). The indicators come from independent data
streams, so only a common latent cause (fraud) can make them covary. The size of the
cross-indicator covariance therefore identifies station-level fraud rates. Pollution effects come
from TOR VET roadside remote-sensing emissions, valued with AP4 county marginal damages. Demand for
fraud comes from a nested-logit model of repair vs. fraud vs. abandonment (with a margin for
unregistered driving). It is identified from variation in repair cost across the specific
diagnostic failure, within make × model-year × station.

**Findings.** (1) About 11.2% of inspections (≈10.7M tests) are fraudulent, peaking at 13.4% in 2022
before the Operation Cinderblock crackdown. Fraud is concentrated in a small tail of stations and
among older vehicles. (2) Fraud-passed vehicles emit more than three times the NO and HC of
legitimately passed cars, ≈$121 per vehicle per year in excess health damages and ≈$1.1bn
cumulatively. (3) Demand for noncompliance is elastic and heterogeneous: 2% at a $93 repair, 24% at
$276, 68% at $750. The median switch point is $501. (4) Removing all fraud stations (2022) takes
fraud from 13.6% to 0%, but repair rises only 3.8pp while abandonment rises 9.8pp, and many of
those drivers go unregistered. This is **enforcement leakage**. (5) Per failing driver, pollution
benefits ($4.6–10.2) are about the size of drivers' surplus losses ($8.6) once repair-shop profits
are counted. Net welfare excluding fraud-station rents ranges from −$1.4 to +$4.2. Fraud-station
rents (≈$20 per driver) exceed the environmental gains.

**Why it matters.** The paper gives a portable way to measure *how much* misconduct exists, not just
whether it exists. It also shows that crackdowns on the supply side alone partly move
noncompliance to a less visible margin.

**Market-failures & public-policy link:** a pollution externality made worse by an agency problem
in delegated enforcement. The policy answer is to pair supply-side enforcement with demand-side
tools (on-road registration checks, repair subsidies or waivers). Otherwise the externality simply
moves elsewhere.

---

# 2. Battery Bidding and Market Efficiency in Energy Transition (Hunt Allcott, Luming Chen, Julia Park; Mar 2026, preliminary)

**Question.** How efficiently do grid batteries arbitrage in real-time markets? And how much does
a common market-design rule, the **bid lead time** (committing bids ahead of dispatch), cost?

**Data/method.** 15-minute bidding and settlement data for every utility-scale battery in ERCOT,
2018–2025. ERCOT has essentially no real-time lead time, which makes it a clean frictionless
benchmark. The authors estimate a semi-parametric price process that keeps intraday dynamics and
spikes. They then fit a dynamic bidding model in which charge and discharge bids encode the
opportunity cost of stored energy, with battery-specific cycling costs estimated by simulated
method of moments. The model is embedded in a market equilibrium to get price and surplus effects.

**Findings.** (1) Batteries bid actively and strategically. They post high discharge offers to keep
option value, cut them sharply near price peaks, and adjust quickly to unexpected shocks. Recent
prices sharply reduce forecast errors. (2) Estimated cycling costs are ≈$4–20/MWh, in line with
engineering benchmarks. (3) A 30-minute lead time (MISO/SPP/ISO-NE) cuts profits ≈17%, and a
75-minute lead time (CAISO) cuts them ≈25%. Batteries discharge too early and miss the peaks. The
losses are bigger with volatility and smaller for longer-duration batteries. (4) Two-point
state-of-charge-dependent bids recover 12.3% (30-min) and 15.8% (75-min) of profit. (5) In
equilibrium, removing lead time lowers average and especially upper-tail prices. Consumers and
batteries gain, conventional generators lose, and batteries complement solar more.

**Why it matters.** Storage is scaling fast, and most US ISOs impose lead times. The paper puts a
number on a rule that regulators (e.g., CAISO's Market Surveillance Committee) have flagged but
not quantified.

**Market-failures & public-policy link:** an inefficiency created by market design rather than by
a classic failure. A timing rule limits storage's ability to smooth prices and to complement
renewables, and the fix is a low-cost rule change (shorter lead times, SoC-contingent bids).

---

# 3. Default Options and Market Power: Evidence from Target-Date Funds (Marco Loseto, Hanbin Yang; Jul 2026)

**Question.** Do 401(k) defaults, which are good at overcoming inertia on saving, also create
market power that lets fund managers extract rents from inattentive default investors?

**Data/method.** Mutual-fund and TDF fee and flow data, with TDF holdings linked to their
underlying funds. The key quantity is the "wrapper fee": TDF fee minus the asset-weighted fee of its
underlying funds. The equilibrium model has four groups: employers choosing a default TDF,
participants opting in or out, 401(k) participants in non-TDFs, and non-401(k) investors. Managers
sell the same funds in both markets and set fees by Nash-Bertrand pricing. Demand is estimated
BLP-style with Hausman instruments (fees in the manager's other categories), a custodian and
transfer-agency cost shifter, and differentiation instruments.

**Findings.** (1) Wrapper fees average 22bp in 2019 (≈60bp at the 90th percentile), more than 100%
of underlying fees, costing more than $3bn a year. They are not explained by rebalancing costs (the
federal TSP's TDFs carry about zero wrapper) or by cross-subsidizing recordkeeping. (2) TDF flows
are much less fee-sensitive. Elasticities are below 1 for TDF investors and employers, and 2–3 for
non-TDF investors. (3) TDF markups are ≈20bp above those of their underlying funds, ≈$2.8bn in
profit. (4) Counterfactuals: banning price discrimination (zero wrapper) cuts TDF fees 13bp and
gives TDF investors +$1.2bn a year. Managers raise non-TDF fees only 3bp, and their profits fall
1.3%. A 20bp cap is worth +$1.9bn to TDF investors, with profits down 5%. Making employers as
fee-sensitive as outside investors cuts TDF fees 27bp (+$1.8bn). (5) A 60bp wrapper cuts a TDF's
lifetime-wealth gain from ≈50% to ≈35%.

**Why it matters.** It measures a hidden cost of the post-2006 Pension Protection Act default
architecture and points to fixes (fee caps, employer fiduciary incentives) that keep the
behavioral benefit.

**Market-failures & public-policy link:** market power that comes from consumer inertia, plus an
agency problem at employer sponsors. Defaults are a policy fix for one failure (undersaving) that
creates another (price discrimination against inattentive savers), and regulating fees addresses
the second.

---

# 4. Regulation by Public Options: Evidence from Pension Funds (Pablo Blanchard, Sebastian Fleitas, Rodrigo González Valdenegro; Mar 2026)

**Question.** Is a state-owned competitor (a "public option") a good way to discipline an
oligopoly? How does it compare with direct price regulation?

**Data/method.** Uruguayan social-security administrative panel of workers' pension-administrator
(PFA) enrollment, 1996–2020, plus market-level fees, returns, switching and sales-force data. One
high-quality SOE competes with three private PFAs. Demand has two stages. At entry, workers choose
using a logit that maximizes expected retirement savings, with fee and return sensitivity varying
by wage quartile. Afterwards, an awareness shock (probit) triggers re-optimization. Supply is a
stationary dynamic Nash-Bertrand model in which firms set fees and mean returns and trade off
investing in new cohorts against harvesting inert stayers. The SOE puts weight on workers' savings.
Two policy changes (the SOE's objective shift in 2005 and a fee cap in 2020) give three equilibria.

**Findings.** (1) Higher-wage workers are more fee-sensitive and make better choices. (2)
Enrollment marginal costs are positive (sales-force commissions), unlike the zero-cost assumption
in earlier PFA work. (3) Privatizing the SOE raises average fees 44% (more than 150% for the ex-SOE)
and private rivals' fees ≈8%. Returns fall 3%, and representative retirement savings fall 6.7%
(−11% for ex-SOE enrollees). (4) Making workers more responsive helps, but the responsiveness
needed to offset privatization is unrealistically high. (5) Making the SOE even more
savings-oriented increases segmentation and hurts low-wage workers at private funds. The 2020 fee
cap raises savings for all workers, especially low earners, and narrows the SOE–private savings
gap (ratio from 91.3% to 98%).

**Why it matters.** Public options are proposed across health insurance, banking and pensions. This
is a clean equilibrium comparison showing that a public option helps but can be beaten by
old-fashioned price regulation.

**Market-failures & public-policy link:** market power made worse by consumer inertia. The paper
compares two remedies directly, competition through an SOE and a price cap. The price cap wins on
both efficiency and equity.

---

# 9. Dying Better: Hospice Care and the End of Life (Yunan Ji, Edward Kong, Maya Roy; Jul 2026)

**Question.** Does wider hospice availability lower public end-of-life spending, and does it make
patients better or worse off? If hospice is good value, why is it underused?

**Data/method.** A stacked difference-in-differences design around 1,518 county hospice-agency
entries (1999–2019), each treated county matched to ever-treated control counties. The data are
twenty years of Medicare claims linked to Minimum Data Set nursing-home assessments. The MDS lets
the authors observe pain, function, cognition, restraints and other care processes, not just
utilization. A structural referral model has providers recommend hospice when patient benefit,
weighted by provider altruism, exceeds forgone revenue. Access constraints raise the effective
enrollment threshold further. The model is estimated at the patient-group level from baseline
mortality, take-up and the reduced-form responses of use and revenue.

**Findings.** (1) Entry raises hospice spending $4.26 per beneficiary-quarter (+7.1%) and lowers
non-hospice spending $9.00 (inpatient −$5.29, SNF −$2.12), a ≈2:1 fiscal return. (2) Care
becomes less intensive and more comfort-oriented: catheters −1.6%, restraints −4.8%, swallowing
therapy +2.7%, sleep medication +4%. Per 1% more hospice use, institutional deaths fall 0.22% and
home deaths rise 0.12%. There are no adverse effects on mortality, pain or function. (3) The
effects vary: dementia roughly breaks even, while COPD and heart disease save ≈$3 per $1. (4)
Providers refer at an average quarterly mortality cutoff of 11.7% (range 6.7–17.4%), and cutoffs
are higher where referral loses more revenue. Each 0.1pp of mortality risk offsets ≈$5.8k of lost
revenue, against an average $36.5k revenue loss per referral. (5) Removing financial disincentives
and expanding capacity could raise patient welfare by up to 64%.

**Why it matters.** End-of-life care is up to 25% of Medicare spending. This is rare evidence of a
policy lever that saves money *and* improves measured patient welfare.

**Market-failures & public-policy link:** provider agency problems (fee-for-service incentives
against referral) and supply constraints (certificate-of-need laws, workforce shortages) produce
underuse of a high-value service. Payment reform and easing entry barriers are the remedies.

---

# 10. Predictably Unpredictable Inspections (Ashvin Gandhi, Andrew Olenski, Maggie Shi; NBER w34491, rev. Jun 2026; AER forthcoming)

**Question.** Inspections are nominally unannounced but follow predictable cycles. Does that
predictability weaken compliance, and what is the trade-off between incentives and information
from randomizing the timing?

**Data/method.** CMS nursing-home standard surveys (2010–2023) with daily Payroll-Based Journal
staffing and assessment-based care inputs, combined into an effort index, plus patient mortality.
Descriptive hazard plots cover nine regulatory settings (CMS, NYC restaurants, MSHA mines, HUD,
FDA). The dynamic structural model has facilities choose effort against the anticipated inspection
arrival process. Each inspection generates a decaying signal of latent quality for the regulator.

**Findings.** (1) The inspection hazard is ≈0 for about 35 weeks after an inspection, then rises
sharply. (2) Effort is low early in the cycle and rises with the hazard, and the relationship is
**concave**. (3) Mortality tracks effort: a one-SD rise in effort lowers mortality 5.4%, and
balance tests rule out changes in patient composition. (4) Compared with no inspections, the
current regime saves 886 lives a year (57 per 1,000 inspections) and cuts regulator uncertainty
56%. (5) Randomizing timing at fixed frequency saves 10% more lives, equal to 10% more inspections,
at a 2.7% information cost. Perfectly scheduled inspections would save 12.9% fewer lives. (6)
Unpredictability and frequency are complements: extra inspections are 50% more effective when
timing is unpredictable.

**Why it matters.** It is the first empirical measure of a margin that theory (Varas et al.; Ball
and Knoepfle) says is ambiguous. It is also nearly budget-neutral at a time when state survey
agencies cannot meet current frequency mandates.

**Market-failures & public-policy link:** asymmetric information about quality in a
government-funded, privately provided service. The paper shows that *how* monitoring is scheduled,
not just how much of it there is, determines how well regulation corrects hidden-effort moral
hazard.

---

# 11. Government Monitoring of Health Care Quality: Evidence from the Nursing Home Sector (Yiqun Chen, Marcus Dillender; NBER w34037, rev. Aug 2025)

**Question.** Do nursing homes game inspections? If they do, do inspection ratings still carry
information about quality, and do citations produce lasting improvement?

**Data/method.** Daily PBJ staffing for nearly all US nursing homes and MDS patient data. Outcomes
around inspection end dates are compared within nursing-home × (year, month, day-of-week) cells,
with dynamic balance checks and checks that inspections are spread evenly through the year. Rating
informativeness is tested with a McClellan–McNeil–Newhouse differential-distance IV: distance to
the nearest above-median-rated home vs. the nearest below-median home, using 5.6M Medicare
admissions to more than 15,000 homes. A control-function approach following Einav–Finkelstein–
Mahoney gives facility-level mortality effects. The paper also estimates event-study effects of
deficiency citations.

**Findings.** (1) During inspections, nurse hours rise 10.2 and aide hours 6.6 on the peak day
(26% and 38% of the weekday–weekend gap). Every staff type increases, and the skill mix shifts
toward RNs. Admissions fall 9%, and temporary discharges rise 4% (patients held in hospital, then
readmitted). Vaccinations rise. (2) Almost everything reverts the day after the inspection ends.
(3) Gaming is larger at for-profits, at homes with low prior ratings, and in competitive or
high-staff-availability markets, which points to both incentives and capacity to respond. (4)
Admission to a higher-rated home lowers 90-day mortality by 0.8pp (−5.2%), and the effect persists
for at least a year. It is stronger where gaming is weaker. Ratings explain ≈10.3% of the variance
in facility mortality effects. (5) Citations with precise criteria and larger fines produce
sustained improvement in the cited metrics.

**Why it matters.** Certification and compliance rules rely on *absolute* quality readings, which
gaming inflates. Patients and referrers can still rely on *relative* rankings.

**Market-failures & public-policy link:** hidden quality in publicly financed, privately run care.
Monitoring partly fixes the information problem, but the paper shows its limits (window-dressing,
unintended hospital transfers) and which design features (precise standards, meaningful penalties)
make it work. It pairs naturally with #10's randomization remedy.

---

# 12. Patent Vouchers as Innovation Incentives: Theory and Evidence from Europe (Pierre Dubois, Paul-Henri Moisson, Jean Tirole)

*Read from the earlier public version: "The Economics of Transferable Patent Extensions," TSE
Working Paper 22-1377, December 2022 (same authors, model and 15-country data). The 2026
conference draft may differ.*

**Question.** For antibiotics and neglected diseases, where there is no viable market, is it
cheaper for society to reward inventors with a transferable exclusivity extension (a voucher sold
to another pharma firm) than with a cash prize?

**Data/method.** The theory prices the branded drug by Nash bargaining with a national regulator.
Some consumers stay captive to the brand after the patent expires, and the rest consider generics.
The key statistic is the **cost-over-reward ratio**: social surplus lost per $1 of reward, compared
with 1+λ for a tax-funded prize (it is closely related to the MVPF). The length of the extension
does not affect this ratio. The model is calibrated to all drugs sold in 15 European countries,
2002–2012. The authors estimate demand and market parameters, the value of a one-year voucher and
its likely buyers, and the ratio by country and for a hypothetical 15-country union with
contributions proportional to income.

**Findings.** (1) If generic competition after the patent is imperfect (collusion, captive
consumers, regulated generic prices such as France's 60%-of-brand rule), extending exclusivity
mostly moves quasi-rents from generics makers rather than destroying consumer surplus. The voucher
sale also raises money. (2) Empirically, a $1 voucher reward costs consumers and taxpayers *less
than $1* in most of the 15 countries, so less than a cash prize. (3) In the union, 10 countries
would clearly prefer vouchers, 3 are nearly indifferent and 2 prefer cash. Countries with high
generic prices, low generic shares and a high cost of public funds favor vouchers. (4) Adverse
selection (vouchers bought for the drugs with the highest ratios) is estimated and does not
overturn the result. Auctions help capture the buyer's rents. Scaling up raises inframarginal
buyers' rents, so the ratio worsens as the program grows.

**Why it matters.** It directly informs the EU pharmaceutical reform's transferable exclusivity
vouchers for priority antimicrobials, and US proposals of the same kind.

**Market-failures & public-policy link:** innovation is a public good with a large wedge between
social and private value (antimicrobial resistance), and cash prizes suffer from international
free-riding. The paper shows how the imperfect competition in generics that already exists can be
turned into a cheap source of public funds.

---

# 13. Generous Long-Term Contracts (Sylvain Chassang, Princeton; Mar 2026)

**Question.** Consumers often refuse efficient but complex contracts (variable electricity
pricing, high-deductible insurance) even when those contracts would save them money. Can a
producer replace the menu with one contract that skeptical consumers will accept and that still
delivers the menu's efficiency?

**Data/method.** A dynamic principal–agent model without discounting. A consumer evaluates a
non-dominant new contract adversarially (ambiguity aversion) and a dominant one neutrally. The
"generous" contract charges, at every date, the cumulative payment of whichever menu option is best
*in hindsight*. The key results are the approximate-implementation result and a class of "Pareto
alignments" (a weighted average of the default tariff and the producer's profit change against a
counterfactual-profit bound). The calibration uses French EDF "Tempo" red-day pricing, RTE spot
prices and simulated household load data, plus a health-insurance cost-sharing exercise.

**Findings.** (1) The generous contract dominates the default, so it is adopted. With i.i.d.
preferences and states (or fast learning), it approximately implements the rational consumer's
outcome under the original menu. (2) Under slow learning, generous Pareto alignments give an
approximate Pareto improvement over the default, at a per-period profit penalty of order 1/√N. (3)
Tempo motivates the problem: nearly all households would save ≈20% without changing behavior, yet
only ≈3% adopt. (4) In the calibration, a pooled counterfactual-profit benchmark gives penalties
above 10% of profit unless the inflation coefficient is large, which kills the efficiency gains.
Individualized benchmarks that capture persistent household differences cut penalties to ≈5% at
c=0 and below 1% at c=10%.

**Why it matters.** It is a "minimalist design" tool: it takes an existing menu and makes it
adoptable, rather than redesigning from scratch. It suggests that regulated utilities and insurers
could get demand response or cost-sharing efficiency without large adoption subsidies.

**Market-failures & public-policy link:** it addresses low take-up of welfare-improving contracts
in regulated markets (mandated fixed-price electricity tariffs, low-copay insurance), where the
failure is demand-side skepticism, not information held by the firm. Guaranteeing "best in
hindsight" prices removes that barrier without giving up incentives.

---

# 14. Gatekeepers and Self-Preferencing: Incentives and Welfare Trade-offs in Two-sided Markets (Francesco Decarolis, Muxin Li; Bocconi)

**Question.** When a dominant platform favors its own ancillary service in an adjacent market, when
does that hurt welfare? And why did the French remedy against Google adtech seem to backfire?

**Data/method.** A two-sided model: buyers (advertisers) and sellers (publishers) with
heterogeneous outside options, a monopolized primary product (publisher ad server), and a
competitive ancillary service (SSP/exchange). Sellers choose and pay for the ancillary service, but
buyers also have preferences over it. The model is extended to network effects and one- vs.
two-sided pricing. Empirically, a synthetic-control analysis of French display advertising around
the June 2022 deadline of the FCA's 2021 commitment (Google sharing auction data with rival SSPs)
is followed by structural estimation and counterfactual behavioral and structural remedies.

**Findings.** (1) Self-preferencing is profitable even when the gatekeeper's ancillary service is
lower quality (unless it is much worse), which contradicts the Chicago single-monopoly-profit
logic. Network effects strengthen the incentive. (2) With seller-only pricing, self-preferencing
can benefit sellers (the platform cuts the primary price to attract them) but hurts buyers who
prefer rival services. With two-sided pricing either side can lose. (3) After the FCA remedy,
French publisher revenue and advertiser participation fell compared with synthetic controls. The
estimates show French advertisers value Google-adtech publishers much more. A publisher-side-only
remedy pushed publishers toward technology advertisers avoided, so participation shrank on both
sides and total welfare fell. (4) A modest advertiser-side improvement in rivals' relative value
would have offset the loss. Structural separation beats behavioral remedies only if it raises rival
quality for *both* sides. (5) Gatekeepers re-optimize after regulation, as in Apple's new fees after
the EC ruling.

**Why it matters.** It is timely for the US v. Google adtech remedies phase, the DMA's ban on
self-preferencing, and the EC's draft Article 102 guidelines.

**Market-failures & public-policy link:** leveraging market power across complementary markets on
a two-sided platform. The main policy lesson is about how remedies can fail: one-sided
interventions can misalign cross-side incentives and lower welfare, so antitrust remedies must be
designed for both sides together.
