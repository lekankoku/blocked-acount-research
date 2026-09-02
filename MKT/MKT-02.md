## Operational TAM, SAM, and SOM Definitions

* **Total Addressable Market (TAM)**: The total annual volume of non-EU national visa/residence-title opportunities requiring statutory proof of financial resources under German immigration law (§2 Abs. 3 AufenthG)[cite: 2, 7]. The primary counting unit is **annual customer account opportunities** (counts of accounts per year)[cite: 2]. Deposits are derived secondarily as $\text{Deposit Volume} = \text{Accounts} \times \text{Statutory Amount}$[cite: 2].
* **Serviceable Addressable Market (SAM)**: The portion of TAM addressable after applying legal, geographic, regulatory, proof-of-funds alternative, and payment/KYC friction filters[cite: 2, 5]. Formally:
  $$SAM = TAM \times \prod_{k \in K} (1 - f_{k})$$
  where $f_k \in [0, 1]$ represents non-overlapping exclusion factors applied exactly once at the TAM$\rightarrow$SAM transition[cite: 2, 5].
* **Serviceable Obtainable Market (SOM)**: The fraction of SAM captured in Years 1–3 given competitive dynamics, channel distribution reach, brand equity, and operational capacity[cite: 2, 7]. Formally:
  $$SOM = SAM \times f_{\text{capture}}$$
  where $f_{\text{capture}} \in [0, 1]$ represents the achievable market adoption rate[cite: 2, 7].

---

## Evidence-Quality Summary & Classification

* **Confirmed Facts**:
  * Published FFO 2025 national visa workload totals: 99,388 for study/prep (BA-01/02 shared)[cite: 1] and 11,157 for language/school (BA-05/08 shared)[cite: 1].
  * FFO 2025 Opportunity Card visa workload total: $\approx 17,500$[cite: 1].
  * Historical domestic proxies: 19,910 first-time §16a residence-title grants (2024)[cite: 1] and 4,930 §16d recognition entrant persons (2023)[cite: 1].
  * Statutory monthly blocked deposit rates for 2025/2026: €992/mo (§16b study = €11,904/yr)[cite: 6], €1,091/mo (§17 study search = €13,092/yr)[cite: 6], €1,091.20/mo (§16f language = €13,094.40/yr)[cite: 6], and €1,091/mo (§20a Opportunity Card = €13,092/yr)[cite: 6].
  * Exclusions by design: EU/EEA nationals require no visa/blocked account[cite: 5]; Au Pairs and BFD/FSJ volunteers receive contracts/pocket money satisfying livelihood rules without blocked accounts[cite: 4, 5, 6].
* **Evidence-Backed Estimates**:
  * 2025 visa-side partial gross ceiling of $\approx 128,045$ consular administrative episodes ($99,388 + 11,157 + 17,500$)[cite: 1].
  * Sanctions/FATCA geographic restriction filter ($f_{\text{sanctions}} \approx 3.0\%$)[cite: 5, 7].
  * Incumbent market share ceilings: market leaders (Fintiba, Expatrio) process 35,000–60,000 accounts/year each, representing 25%–40% mature SAM capture[cite: 7].
* **Assumptions**:
  * Proof-of-funds leakage rate ($f_{\text{alt\_proof}} = f_{\text{scholarship}} + f_{\text{guarantor}}$) across Base (18%), Conservative (25%), and Upside (12%) scenarios[cite: 7].
  * KYC and FX cross-border drop-off rates ($f_{\text{kyc/fx}}$) across Base (7%), Conservative (12%), and Upside (4%) scenarios[cite: 7].
  * New-entrant Year 1–3 SOM adoption capture rates ($f_{\text{capture}}$): Study (Cons 2.5% / Base 7.5% / Upside 15.0%)[cite: 7]; Opportunity Card (Cons 2.0% / Base 6.0% / Upside 12.5%)[cite: 7]; Language/School (Cons 1.0% / Base 3.5% / Upside 8.0%)[cite: 7].
  * "At most one potential account opportunity per eligible administrative episode" convention[cite: 1, 2].
* **Hypotheses**:
  * Additional addressable demand existing in unmeasured pathways (BA-04, BA-09, BA-10, BA-11, BA-12)[cite: 1].
  * Potential displacement capture from legacy banking exits (Deutsche Bank, ICICI Bank UK Germany branch)[cite: 7].
* **Unknowns**:
  * Exact segment-level splits within shared FFO baskets (BA-01 vs BA-02; BA-05 vs BA-08)[cite: 1].
  * Total domestic in-country Opportunity Card initial issuances[cite: 1, 8].
  * Empirical conversion rate from approved national visa to actual commercial account opening[cite: 1, 2].
* **Contradictory Evidence**:
  * Consular visa terminology ambiguity: FFO detailed tables state "processed national visas" (480,864 total), while high-level web pages refer to "issued national visas" or "processed applications"[cite: 1].
  * Primary BAMF source labels BA-03 as "first-time residence-title grants" while federal newsletter secondary wording calls them "visas"[cite: 1].

---

## Segment-Level Account-Volume Baseline & Overlap Model

| segment_id | pathway_description | baseline_record_id | gross_volume | metric_type & vintage | overlap_deduplication_treatment | baseline_tam_accounts |
|---|---|---|---:|---|---|---:|
| **BA-01 / BA-02** | Higher-education study (§16b) & study-place search (§17) | `MKT01-POP-2025-FFO-STUDY` | 99,388 | Consular cases (2025)[cite: 1] | Combined FFO basket loaded **once**. No standalone split allocated[cite: 1]. | 99,388 |
| **BA-03** | Vocational training (§16a) | `MKT01-POP-2024-BAMF-16A-FIRST` | 19,910 | Residence titles (2024)[cite: 1] | Separated in-country proxy layer; non-additive to 2025 consular total[cite: 1]. | *19,910 (Proxy)* |
| **BA-04** | Training-place search (§17(1)) | null | null | Unobserved[cite: 1] | Kept null; zero synthetic residual[cite: 1]. | null |
| **BA-05 / BA-08** | Standalone language course (§16f) & school exchange | `MKT01-POP-2025-FFO-LANG-SCHOOL` | 11,157 | Consular cases (2025)[cite: 1] | Combined FFO basket loaded **once**. No standalone split allocated[cite: 1]. | 11,157 |
| **BA-06** | Qualification recognition (§16d) | `MKT01-POP-2022-BAMF-RECOG-ENTRY` | 4,930 | Entrant persons (2023)[cite: 1] | Separated historical proxy layer (2023 preferred over 2022)[cite: 1]. | *4,930 (Proxy)* |
| **BA-07** | Opportunity Card (§20a/§20b) | `MKT01-POP-2025-FFO-OPPCARD` | ≈17,500 | Consular cases (2025)[cite: 1] | Visa-side gross ceiling; in-country issuance unknown[cite: 1, 8]. | 17,500 |
| **BA-09 to BA-12** | Internships, Working Holiday, Researchers, Volunteers | null | null | Unobserved[cite: 1] | Kept null; Au Pairs / Volunteers excluded by program design[cite: 1, 5]. | null |
| **Primary 2025 Consular Gross Ceiling** | **Active 2025 Overseas Visa Scope** | **Combined 2025 FFO** | **128,045** | **Consular Cases (2025)**[cite: 1] | **Sum of distinct 2025 consular records ($99,388 + 11,157 + 17,500$)[cite: 1].** | **128,045** |

---

## Market-Sizing Results: Scenarios & Derived Deposit Volumes

### Account-Volume Model (Primary Metric)

| market_layer | segment_scope | conservative_scenario | base_scenario | upside_scenario | key_filtering_parameters |
|---|---|---:|---:|---:|---|
| **TAM** | Primary 2025 Consular Scope | **128,045** | **128,045** | **128,045** | Gross annual consular visa opportunities[cite: 1]. |
| **SAM** | Study / Prep (BA-01/02) | 63,614 | 73,522 | 81,438 | Cons: $f_{\text{alt}}=25\%, f_{\text{kyc}}=12\%$; Base: $18\%, 7\%$; Upside: $12\%, 4\%$[cite: 7]. |
| **SAM** | Opportunity Card (BA-07) | 11,195 | 12,940 | 14,330 | Cons: $f_{\text{alt}}=25\%, f_{\text{kyc}}=12\%$; Base: $18\%, 7\%$; Upside: $12\%, 4\%$[cite: 7]. |
| **SAM** | Language / School (BA-05/08) | 7,137 | 8,252 | 9,139 | Cons: $f_{\text{alt}}=25\%, f_{\text{kyc}}=12\%$; Base: $18\%, 7\%$; Upside: $12\%, 4\%$[cite: 7]. |
| **SAM Total** | **Serviceable Addressable Market** | **81,946** | **94,714** | **104,907** | **Combined SAM account opportunity range[cite: 2, 5, 7].** |
| **SOM** | Study / Prep (BA-01/02) | 1,590 | 5,514 | 12,216 | $f_{\text{capture}, 1}$: Cons 2.5%, Base 7.5%, Upside 15.0%[cite: 7]. |
| **SOM** | Opportunity Card (BA-07) | 224 | 776 | 1,791 | $f_{\text{capture}, 3}$: Cons 2.0%, Base 6.0%, Upside 12.5%[cite: 7]. |
| **SOM** | Language / School (BA-05/08) | 71 | 289 | 731 | $f_{\text{capture}, 4}$: Cons 1.0%, Base 3.5%, Upside 8.0%[cite: 7]. |
| **SOM Total** | **Serviceable Obtainable Market** | **1,885** | **6,579** | **14,738** | **Net Year 1–3 obtainable commercial account openings[cite: 2, 7].** |

### Derived Deposit-Volume Model (Secondary Metric)

$$V_{\text{deposit}} = \sum_{i} \left( N_{\text{accounts}, i} \times D_{\text{req}, i} \right)$$

*Statutory Rates Used*: Study = €11,904/yr[cite: 6]; Opportunity Card = €13,092/yr[cite: 6]; Language/School = €13,094.40/yr[cite: 6].

| market_layer | segment_scope | conservative_deposit_vol | base_deposit_vol | upside_deposit_vol |
|---|---|---:|---:|---:|
| **TAM** | Primary 2025 Consular Scope | **€1,558,318,973** | **€1,558,318,973** | **€1,558,318,973** |
| **SAM** | Study / Prep (BA-01/02) | €757,261,056 | €875,205,888 | €969,438,048 |
| **SAM** | Opportunity Card (BA-07) | €146,564,940 | €169,410,480 | €187,608,360 |
| **SAM** | Language / School (BA-05/08) | €93,454,723 | €108,054,989 | €119,670,082 |
| **SAM Total** | **Serviceable Addressable Market** | **€997,280,719** | **€1,152,671,357** | **€1,276,716,490** |
| **SOM** | Study / Prep (BA-01/02) | €18,927,360 | €65,638,656 | €145,419,264 |
| **SOM** | Opportunity Card (BA-07) | €2,932,608 | €10,159,392 | €23,447,772 |
| **SOM** | Language / School (BA-05/08) | €929,702 | €3,784,282 | €9,572,006 |
| **SOM Total** | **Serviceable Obtainable Market** | **€22,789,670** | **€79,582,330** | **€178,439,042** |

---

## Proof-of-Funds Reduction Mechanisms

| pathway / segment | proof_mechanism | observed_or_assumed | model_treatment | evidence_source |
|---|---|---|---|---|
| **Au Pair & BFD/FSJ Voluntary** | Host contract, room/board, pocket money | **Observed / Documented** | **Full Exclusion (100%)**: Blocked accounts not legally required. Removed from TAM[cite: 4, 5, 6]. | Embassy visa leaflets & AufenthG specifications[cite: 4, 6]. |
| **Vocational Training (§16a)** | Company apprenticeship salary | **Observed / Documented** | **Excluded when salary $\ge$ threshold**: Blocked account required only for shortfalls[cite: 4, 5, 6]. | BAMF & *Make it in Germany* guidance[cite: 4, 5]. |
| **Higher Ed Study (§16b)** | Institutional scholarships (DAAD) | **Assumed (Usage %)** | **SAM Reduction Factor**: Part of $f_{\text{alt\_proof}}$ (12%–25% range)[cite: 4, 5, 7]. | DAAD statistics & consular checklists[cite: 4, 5, 7]. |
| **All Student / Search Categories** | *Verpflichtungserklärung* (Sponsor) | **Assumed (Usage %)** | **SAM Reduction Factor**: Part of $f_{\text{alt\_proof}}$ (12%–25% range)[cite: 4, 5, 7]. | Foreign Office legal directives (§68 AufenthG)[cite: 4, 5, 7]. |
| **Chancenkarte (§20a)** | Part-time German job ($\ge €1,091$/mo net) | **Assumed (Usage %)** | **SAM Reduction Factor**: Part of $f_{\text{alt\_proof}}$ (12%–25% range)[cite: 4, 5, 7]. | *Make it in Germany* Q&A portal[cite: 4, 5]. |

---

## Overlap & Deduplication Rules

* **Single-Stage Counting**: Count individuals at their primary visa entry stage; exclude subsequent domestic residence permit conversions to prevent double counting[cite: 3].
* **Flow vs. Stock**: Primary TAM models annual **flows** (new incoming visa applicants). The installed student stock ($\approx 402,000$ enrolled international students) is strictly isolated and excluded from annual acquisition TAM[cite: 1, 3].
* **Shared Category Baskets**: FFO combined totals (`MKT01-POP-2025-FFO-STUDY` = 99,388[cite: 1]; `MKT01-POP-2025-FFO-LANG-SCHOOL` = 11,157[cite: 1]) are loaded exactly once at the aggregate level. Standalone sub-segment allocations remain null[cite: 1, 8].
* **Sequential Stage Deduplication**: Study visa applicants who become enrolled students are counted once under visa flow. Education-to-work status transitions ($\approx 46,000$ cases annually) are excluded from student acquisition models[cite: 3].

---

## Geographic Boundary & Scope Treatment

MKT-02 operates strictly at the destination macro level (`worldwide_german_network` = 128,045 consular cases[cite: 1, 8]; `germany_third_country_nationals` = 24,840 historical domestic proxies[cite: 1, 8]). 

Origin-country disaggregation is prohibited in MKT-02 to prevent quantitative distortion caused by applying university student origin profiles to non-academic pathways (e.g., Opportunity Card, vocational training)[cite: 8]. Country-level attributes are maintained as nullable interface stubs (`country_iso_alpha3`, `mkt03_tier_priority`, `sam_geo_eligible_flag`), fully delegating origin-country prioritization to MKT-03[cite: 8].

---

## Complete Assumption Register

| assumption_id | description | model_layer | value_or_range | source | evidence_quality | scenario | sensitivity | validation_required |
|---|---|---|---|---|---|---|---|---|
| **ASM-MKT-01** | Non-EU visa cases equal max account opportunities | TAM | $1.0\times$ scalar | MKT-02-01 | Medium (Consular proxy)[cite: 1] | All | High | Embassy conversion tracking |
| **ASM-MKT-02** | Excluded EU/EEA national visa share | TAM | 0.0% (in consular data) | MKT-02-05 | High (Statutory rule)[cite: 5] | All | Low | Consular post audits |
| **ASM-MKT-03** | Alternative Proof Leakage ($f_{\text{alt\_proof}}$) | SAM | 12.0% – 25.0% (Base: 18.0%) | MKT-02-05, MKT-02-07 | Medium (DAAD / Consular specs)[cite: 5, 7] | Cons / Base / Upside | High (Rank 2) | Visa application proof-type audits |
| **ASM-MKT-04** | Sanctions / FATCA Exclusions ($f_{\text{sanctions}}$) | SAM | 3.0% fixed | MKT-02-05 | High (Provider disclosures)[cite: 5, 7] | All | Low | BaFin / Partner bank policy |
| **ASM-MKT-05** | KYC / FX Transfer Friction ($f_{\text{kyc/fx}}$) | SAM | 4.0% – 12.0% (Base: 7.0%) | MKT-02-07 | Medium (User review logs)[cite: 7] | Cons / Base / Upside | Medium (Rank 5) | Banking rail drop-off metrics |
| **ASM-MKT-06** | Student Year 1–3 Capture ($f_{\text{capture}, 1}$) | SOM | 2.5% – 15.0% (Base: 7.5%) | MKT-02-07 | Medium (Incumbent benchmarks)[cite: 7] | Cons / Base / Upside | High (Rank 1) | GTM & University partner deals |
| **ASM-MKT-07** | Opportunity Card Capture ($f_{\text{capture}, 3}$) | SOM | 2.0% – 12.5% (Base: 6.0%) | MKT-02-07 | Low (Early adoption tracking)[cite: 7] | Cons / Base / Upside | High (Rank 4) | Embassy portal referral shares |
| **ASM-MKT-08** | Language/School Capture ($f_{\text{capture}, 4}$) | SOM | 1.0% – 8.0% (Base: 3.5%) | MKT-02-07 | Low (Language directory data)[cite: 7] | Cons / Base / Upside | Low | Sprachschule affiliate deals |

---

## Sensitivity Ranking & Key Decision Drivers

1. **SOM Adoption Capture Rate ($f_{\text{capture}}$)**: Impact: $-50.0\%$ to $+100.0\%$ on SOM accounts ($-3,694$ to $+8,159$ accounts; $-€44.7\text{M}$ to $+€98.9\text{M}$ deposit volume in Base)[cite: 9]. Driven by distribution partner execution and digital onboarding friction[cite: 7, 9].
2. **Alternative Proof Leakage ($f_{\text{alt\_proof}}$)**: Impact: $-20.0\%$ to $+13.3\%$ on SAM ($-12,768$ to $+10,193$ Base SAM accounts; $-€155.4\text{M}$ to $+€124.0\text{M}$ SAM deposits)[cite: 9]. Driven by scholarship rates and regional sponsor usage[cite: 5, 7, 9].
3. **Visa-to-Enrollee Deduplication / Conversion**: Impact: $-16.7\%$ to $+5.6\%$ on TAM[cite: 9]. Driven by gap between processed consular applications and actual matriculation[cite: 3, 9].
4. **Opportunity Card (*Chancenkarte*) Volume Baseline**: Impact: $\pm9.4\%$ on total TAM/SAM ($\pm 15,000$ TAM accounts; $\pm €178.6\text{M}$ TAM deposits)[cite: 9]. Driven by policy adoption and embassy visa processing speeds[cite: 7, 9].
5. **Payment Rail / KYC Accessibility ($f_{\text{kyc/fx}}$)**: Impact: $-11.1\%$ to $+5.6\%$ on SAM[cite: 9]. Driven by local FX controls, SWIFT limitations, and manual PostIdent requirements[cite: 5, 7, 9].

---

## Contradictions, Unknowns, and Validation Items

* **Contradiction 1 (Consular Visa Terminology)**: FFO detailed tables report "processed national visas" while high-level web pages cite "issued national visas"[cite: 1]. *Resolution*: Retain `metric_type = national_visa_administrative_cases`; do not convert to approved visas without embassy conversion data[cite: 1].
* **Contradiction 2 (BA-03 Metric Labeling)**: Primary BAMF report classifies 19,910 as "first-time residence-title grants", whereas federal newsletters label them "visas"[cite: 1]. *Resolution*: Preserve BAMF classification; keep separate from consular visa flows[cite: 1].
* **Unknown 1 (Fintiba/Expatrio Retention & Conversion)**: Public competitor numbers do not disclose exact funnel drop-offs from account opening to funded deposit.
* **Unknown 2 (Opportunity Card In-Country Grants)**: Consular data captures overseas cases ($\approx 17,500$)[cite: 1], but domestic in-country conversions remain unobserved[cite: 1, 8].
* **Validation Priority 1**: Field audit of top 50 study-abroad agencies (India, Turkey, Vietnam) to validate alternative proof leakage and distribution commission elasticity[cite: 7].
* **Validation Priority 2**: Empirical 12-month track record monitoring of *Chancenkarte* visa approvals and blocked account conversion rates[cite: 9].

---

## Downstream Handoffs

### FIN-02 Handoff (Financial Planning & Modeling)
* **Account Opportunities Baseline**: TAM = 128,045[cite: 1]; SAM Base = 94,714[cite: 7]; SOM Base = 6,579 accounts (Range: 1,885 – 14,738)[cite: 7].
* **Derived Deposit Volumes**: SAM Base Deposit = €1.15 Billion[cite: 6, 7]; SOM Base Deposit = €79.58 Million (Cons: €22.79M / Upside: €178.44M)[cite: 6, 7].
* **Statutory Deposit Benchmarks**: Study = €11,904[cite: 6]; Opportunity Card / Language = €13,092[cite: 6].

### MKT-05 Handoff (Initial Target Customer Definition & ICP)
* **Core Target Segment**: Non-EU Higher Education Students (§16b) represent 77.6% of TAM (99,388 cases)[cite: 1] and 83.8% of Base SOM (5,514 accounts)[cite: 7]. Low uncertainty, high adoption potential[cite: 7].
* **Secondary Growth Segment**: Opportunity Card (§20a) represents 13.7% of TAM (17,500 cases)[cite: 1] and 11.8% of Base SOM (776 accounts)[cite: 7]. High growth potential, medium uncertainty due to recent introduction[cite: 7, 9].
* **Deprioritized Segments**: Au Pairs, BFD Volunteers, and Dual Vocational Trainees with full salary (§16a) excluded from primary ICP due to zero/low blocked-account mandate[cite: 5, 6].

### MKT-03 Handoff (Country Prioritization & Selection)
* **Delegated Country Mechanics**: All origin-country disaggregations, ISO mappings, and corridor prioritization are deferred to MKT-03[cite: 8].
* **Interface Schema Ready**: Schema stubs (`country_iso_alpha3`, `mkt03_tier_priority`, `sam_geo_eligible_flag`) are embedded and set to NULL stubs[cite: 8].
* **Target Candidate Scope**: Evaluate top candidate corridors (India, China, Turkey, Pakistan, Nigeria, Vietnam, Uzbekistan) against FX/capital control friction and local distribution channels[cite: 7].

---

## Acceptance Criteria Checklist

| acceptance_criterion | status | documented_limitation_or_notes |
|---|---|---|
| Operational TAM/SAM/SOM definitions provided | **Satisfied** | Account volume primary; deposit volume secondary derived[cite: 2]. |
| Reproducible segment-level model | **Satisfied** | Traceable to MKT-01 baseline records[cite: 1]. |
| Overlap & deduplication treatment | **Satisfied** | Shared baskets loaded once; flow/stock separated[cite: 1, 3, 8]. |
| Proof-of-funds treatment (observed vs assumed) | **Satisfied** | Documented exclusions vs assumed leakage factors[cite: 5, 7]. |
| Statutory blocked amounts incorporated | **Satisfied** | 2025/2026 BAföG-pegged amounts applied per segment[cite: 6]. |
| Conservative, Base, Upside scenarios | **Satisfied** | Account and deposit volumes calculated across 3 scenarios[cite: 7]. |
| Complete assumption register | **Satisfied** | Documented with IDs, ranges, quality, and sensitivity[cite: 7]. |
| Decision sensitivity ranking | **Satisfied** | Ranked 1–5 using MKT-02-10 results[cite: 9]. |
| Evidence-quality summary & facts/unknowns separation | **Satisfied** | Categorized into 6 formal evidence tiers[cite: 1]. |
| Downstream handoffs (FIN-02, MKT-05, MKT-03) | **Satisfied** | Explicit structured handoffs produced[cite: 7, 8]. |
| Geography views boundary enforcement | **Satisfied** | Scope bounded at macro level; origin split deferred to MKT-03[cite: 8]. |
| Parent status logic evaluated | **Satisfied** | All sub-tasks (MKT-02-01 to 02-10) complete[cite: 1, 7, 8, 9]. |

---

## Market-Sizing Conclusion & Parent Status

The proposed German blocked-account platform addresses a defensible 2025 Consular TAM of **128,045 annual account opportunities** ($\approx \mathbf{\text{€}1.56\text{ Billion}}$ deposit volume)[cite: 1, 6], yielding a Base SAM of **94,714 accounts** ($\approx \mathbf{\text{€}1.15\text{ Billion}}$ deposit volume)[cite: 6, 7]. In Years 1–3, a new entrant can realistically target a Base SOM of **6,579 accounts** ($\approx \mathbf{\text{€}79.58\text{ Million}}$ deposit volume), bounded by a Conservative SOM of **1,885 accounts** ($\text{€}22.79\text{M}$) and an Upside SOM of **14,738 accounts** ($\text{€}178.44\text{M}$)[cite: 6, 7].

The most decision-sensitive parameters are the **SOM Adoption Capture Rate** ($f_{\text{capture}}$)[cite: 7, 9] and **Alternative Proof Leakage** ($f_{\text{alt\_proof}}$)[cite: 5, 7, 9]. Key limitations include the absence of origin-country splits in consular baselines (delegated to MKT-03)[cite: 8] and early policy tracking data for the *Chancenkarte* segment[cite: 7, 9].

All mandatory research outputs exist, the quantitative model is reproducible, and all remaining gaps are transparently bounded[cite: 1, 2, 7, 8, 9].

**Recommended Parent Status**: **Ready for Review**