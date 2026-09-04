# Investigation into Cryptoasset Laundering Through the TRON Network

The $72M USDT Tether Freeze Incident (CoQ) and the Connected EJon/HBK Network

## Introduction

This report describes the movement of funds through two connected nodes — CoQ (the incident of June 11–12, 2026, Tether freeze) and EJon/HBK (a network active since January 2025) — and a red-flag assessment adapted from the FATF indicator list for each identified address.

*[Table: 6 rows — see data/ folder for full machine-readable version]*

| Indicator | Value | Note |
|---|---|---|
| Addresses in registry | 647 | 600 CoQ + 47 EJon/HBK |
| Active period | January 2025 – July 2026 | 19 months tracked; 17 months before the incident |
| Total moved through network | $1,565,190,574.49 | see Ch. 3 |
| FATF categories | 5 scored | 6 considered; “geography” not scorable on-chain |
| High-risk addresses | 51 | 50 by flag count + Ak9W (external confirmation) |
| Public sources | 10 | 6 on the incident (common origin: ZachXBT), 3 sanctions, 1 methodology |

## Executive Summary

### Incident

On June 11, 2026 at 15:16:24 UTC, address CoQ received $120,271,055.09 in a single transaction. That same evening $94,980,295.09 moved to Ak9W; on June 12, 2026 at 07:37 UTC Tether blacklisted $72,030,295.66 on that address — the fourth major Tether freeze of 2026. The event was confirmed by on-chain investigator ZachXBT and industry outlets (Coinpaprika, CryptoBriefing, ForkLog), coinciding with a 27–30% rise in the price of Monero.

### Beyond the Public Reporting

Public reporting established the event and quantified its exit channels: on-chain investigator ZachXBT reported over $12M reaching KuCoin deposit addresses, roughly $8M to instant exchanges, and a further $8M bridged to BTC and ETH via Near Intents, alongside the correlated rise in the Monero price. What public reporting did not establish is the origin of the funds — the sending address, its funding history, and whether the episode connects to any pre-existing network. The event was characterized as suspected laundering without identifying a specific flow of funds or the addresses involved beyond the two principals.

### What the Investigation Established

This investigation identifies the sending address (THkSW85s) and the Binance withdrawals that precede the incident: $102,080,631.40 moved from four Binance-tagged hot wallets to TWRXj4SD between April 3–16, 2026. The link between those withdrawals and the $120.27M that reached CoQ rests on sequence, balance and timing rather than an unbroken chain of transfers — one hop passes through a Binance hot wallet, where commingling makes on-chain continuity irrecoverable without exchange records (1.1). It establishes that TWRXj4SD bridged $23,380,000 on May 6, 2026 — a month before the incident — into a separate network (Vector 2, EJon/HBK) active since January 2025, 17 months before the incident, itself linked by two further bridges ($2,000,000 and $5,000,000, May 2026) to a third cluster, and by a previously undocumented $166,206.04 transfer from THDGgq5C to EJon on May 27, 2026. It documents $23,300,000 redistributed from Ak9W across 37 transactions to 35 addresses, $9,000,000 of it (38.6%) to a single address in three tranches in the hours before the freeze. None of this appears in public reporting. A registry of 647 addresses has been built with red-flag scoring adapted from the FATF indicator list.

## Evidence Matrix

Key findings mapped to their supporting evidence and confidence level.

*[Table: 7 rows — see data/ folder for full machine-readable version]*

| Finding | Evidence | Confidence |
|---|---|---|
| CoQ received $120.27M in a single transaction | On-chain transaction (Tronscan) | Confirmed |
| Tether froze $72.03M on Ak9W | On-chain blacklist call + 6 news reports (single common source) | Confirmed (on-chain) |
| CoQ↔EJon bridge, $23.38M (May 6, 2026) | On-chain transaction | Confirmed |
| EJon↔HBK bridge, $2M + $5M (May 21 & 28, 2026) | On-chain transactions | Confirmed |
| HTX / A7 sanctions context | UK government sanctions announcement | Confirmed (external event) |
| Top-70 KuCoin/FixedFloat attribution (THPYzDXTurrum) | Arkham entity tags, proxied by transaction size | Moderate (proxy-based) |
| Vector 2 hub fan-out (QT41, THuBSaEk, etc.) | Identified but not individually traced | Limitation — not yet verified |

## 1. The CoQ Node: Incident and Movement of $120.27M

### 1.1 Node Composition

The node comprises 600 addresses linked by direct or confirmed transactions to CoQ — the incident’s central address. Core: TWRXj4SD (funded by $102.08M from four Binance-tagged hot wallets between April 3–16, 2026, before bridging $23.38M onward to the EJon/HBK node — see 1.3), THkSW85s (funds CoQ directly; its own upstream funding beyond TWRXj4SD is only partially verified — see 1.1), Ak9W (received $94.98M from CoQ plus $350K from elsewhere, redistributed $23.3M to 37 addresses in the hours before the freeze, then had $72.03M of its remaining balance frozen by Tether — see 1.3, 1.4), and three confirmed direct CoQ splitters (vRykCw, GpyTjk, Rd3Sy). The remaining 594 addresses were uncovered from previously aggregated recipients of CoQ, TDKCFqdy, and THPYzDXTurrum. The full address registry is in the appendix.

Funding-chain verification. The funding chain reported for THkSW85s was TWRXj4SD → BinHW_qrr6 → TDCXLmtg → THDGgq5C → lt9 → THkSW85s → CoQ. Direct on-chain verification finds a different and partly discontinuous structure. TWRXj4SD balances exactly ($102,181,708.95 in, same out) and funds TDCXLmtg directly with $31,626,217.01 on May 27, 2026 — not via BinHW_qrr6 as reported. TDCXLmtg also receives $18,629,998.70 the same day from BinHW_qrr6 and balances exactly ($50,256,235.71 in and out), of which $50,256,215.71 goes to THDGgq5C. THDGgq5C, however, forwards only $166,206.04 onward — to EJon, a previously undocumented direct link to Vector 2 — leaving $50.09M that does not continue along the reported chain. Most decisively, THkSW85s shows no traceable USDT inflow before it sent $120,271,055.09 to CoQ: its only recorded inflow is $555,555.00 received from CoQ itself 40 seconds after the incident transaction. Two constraints make this gap structural rather than merely unfinished. BinHW_qrr6 is a Binance hot wallet: funds entering it are commingled with unrelated customer deposits, so on-chain continuity through that address cannot be re-established by further tracing at all — only exchange records can close it. And the origin of the $120.27M held by THkSW85s lies outside the boundary of this dataset. The chain is therefore not a closed funding loop; the connection between the Binance withdrawals and the incident transaction is established by sequence, balance and timing, not by an unbroken chain of transfers.

### 1.2 The Incident

June 11, 2026, 15:16:24 UTC — CoQ receives $120,271,055.09 in a single transaction from THkSW85s. That same evening $94,980,295.09 moves to Ak9W; on June 12, 2026 at 07:37 UTC Tether blacklists $72,030,295.66 on that address — the fourth major Tether freeze of 2026. The event is independently confirmed by on-chain investigator ZachXBT and outlets Coinpaprika, CryptoBriefing, ForkLog, coinciding with a 27–30% rise in the Monero price. The source of funds is not externally disclosed; the event is classified as suspected laundering.

Source (graph visualization): Arkham Intelligence — CoQ transaction graph

### 1.3 Movement of Funds

*[Table: 26 rows — see data/ folder for full machine-readable version]*

Addresses are truncated to the first 7 and last 6 characters. Full addresses are in the wallet registry (appendix).

### 1.4 Patterns

Transaction density by day of week and hour (UTC), confirmed CoQ nodes excluding infrastructure, n=2485

Time window. All activity of the CoQ address itself falls within 17 hours 32 minutes (15:16 UTC June 11 – 08:48 UTC June 12, 2026), in two waves, Thursday and Friday; downstream splitting continues to 08:56. This is the incident window, not the lifespan of the wider node — upstream funding of TWRXj4SD runs from April 3, 2026 and the bridge to Vector 2 predates the incident by a month (1.3).

Balance to zero. Inflow $121,128,940.34, outflow $121,123,509.13 across CoQ’s full 220-transaction history — 99.996% distributed within a day. The transaction table (1.3) shows a representative selection of branches, not all 220 transactions; balances are computed from the complete dataset, not from the table alone. Individual shown branches balance to the cent; Ak9W itself redistributed $23,300,000 of its $95,330,295.66 inflow across 37 transactions to 35 addresses before the freeze (1.3), which is included here.

Movement. Transfer as a single sum (THkSW85s → CoQ) → aggregation at CoQ → movement to primary addresses → split into sums of $10–350K → exit (NEAR Intents, KuCoin, FixedFloat) or freeze at Ak9W.

### 1.5 Behavioural Role Classification

The node’s addresses fall into three behavioural classes by lifespan and outgoing transaction count — not by amount or sub-cluster. This is a role classification, not address clustering in the technical sense: TRON is account-based, so the co-spend heuristic used to prove common ownership on UTXO chains does not apply, and no claim of common control over these addresses is made anywhere in this report. “Cluster” throughout denotes a connected component of the transaction graph.

*[Table: 5 rows — see data/ folder for full machine-readable version]*

| Class | Wallets | Share |
|---|---|---|
| Recipient (terminal) | 533 | 88.8% |
| Distributor | 47 | 7.8% |
| Aggregator | 13 | 2.2% |
| No data | 7 | 1.2% |
| Total | 600 | 100% |

Recipient (terminal) — received a transfer and did not forward it (0–1 outgoing transactions), lifespan < 30 days; mostly one-time exchange deposit addresses uncovered from the TDKCFqdy and THPYzDXTurrum aggregates. Distributor — a short-lived address (< 30 days) with 2 or more outgoing transactions: received and immediately split the sum (vRykCw, GpyTjk, 9g9i, and similar). Aggregator — lifespan ≥ 30 days (TWRXj4SD, THkSW85s, and others): holds the funding loop, active continuously rather than for a single operation.

### 1.6 Risk Assessment (FATF)

3 or more flags out of five FATF indicators — high risk (see methodology in the appendix). Ak9W is scored high risk separately — by external confirmation (the Tether freeze), not by flag count.

*[Table: 5 rows — see data/ folder for full machine-readable version]*

| Risk Level | Wallets | Share |
|---|---|---|
| High (incl. Ak9W) | 42 | 7.0% |
| Medium | 155 | 25.8% |
| Low/watch | 309 | 51.5% |
| Out of scale (services and infrastructure) | 94 | 15.7% |
| Total | 600 | 100% |

## 2. The EJon/HBK Node: Link to Vector 1 and Network Structure

### 2.1 Node Composition and Link to Vector 1

The node comprises 47 addresses (28 EJon, 19 HBK), with tracked activity beginning January 5, 2025. The link to Vector 1 is confirmed by the bridge TWRXj4SD → TBR7B5 ($23.38M, May 6, 2026) — a month before the CoQ incident. Within the node, EJon and HBK are linked by a separate two-way bridge: CQx → veEP ($2M, May 21, 2026) and JEk → V3px ($5M, May 28, 2026).

The registry here has not been expanded to one-time recipients the way Vector 1 was. The reason differs: CoQ's fan-out fit within 2–3 days of the incident, while this node's hubs (QT41 — 47 recipients; THuBSaEk, DZEN, LdaQG — 100 to 300 untraced counterparties each) have been operating for 2 months to a year and a half. Disclosure would first require separating case-relevant activity from unrelated activity over such a span — a separate task not carried out in this pass.

### 2.2 Movement of Funds

*[Table: 12 rows — see data/ folder for full machine-readable version]*

Addresses are truncated to the first 7 and last 6 characters. Full addresses are in the wallet registry (appendix).

### 2.3 Patterns

Transaction density by day of week and hour (UTC), confirmed EJon/HBK nodes excluding infrastructure, n=8940

Time window. 477 calendar dates from January 2025 to July 2026, 89.1% of transactions on weekdays, peak Monday 14:00 UTC. A steady working schedule, not a single-day spike.

Balance to zero. Zeroing-out is not instantaneous but per hop: TJK69Sk6 and the parallel pipe THtAU — both $18,369,839.00 with inflow equal to outflow; the chain Uojk→1w6→PM4→ZhH — a $1–3 discrepancy on $26M in turnover. Certain nodes accumulate rather than zero out: EJon — a $732K balance, TPwezUWp — $1.56M.

Movement. Transfer from a source (Gs4, QT41) → aggregation at the chain's first node (receipt-to-forwarding gap of 1–4 minutes) → movement through sequential hops (up to 6 addresses in a single chain) → split into amounts (CQx→veEP in five tranches; THtAU splits 82%/18%) → exit (USDD→USDT swap at UnPt) or breaks off at new, as-yet-unidentified addresses.

### 2.4 Behavioural Role Classification

The profile is the inverse of Vector 1: aggregators and distributors predominate, terminal recipients are nearly absent. This is not a structural feature of the network but a consequence of data coverage — the registry here has not been expanded to one-time deposits (see 2.1).

*[Table: 5 rows — see data/ folder for full machine-readable version]*

| Class | Wallets | Share |
|---|---|---|
| Aggregator | 19 | 40.4% |
| Distributor | 19 | 40.4% |
| No data | 7 | 14.9% |
| Recipient (terminal) | 2 | 4.3% |
| Total | 47 | 100% |

### 2.5 Risk Assessment (FATF)

One address in this node is an independently attributed external service (HTX, see 6.2), placed out of scale; the remaining 46 are scheme-controlled addresses. No infrastructure addresses (gas top-ups, automated bots) have been identified here, unlike in Vector 1. The share of high risk is higher than in Vector 1 — an effect of data coverage, since Vector 1’s registry includes hundreds of one-time exchange deposits that dilute its proportion, not evidence of higher actual risk.

*[Table: 5 rows — see data/ folder for full machine-readable version]*

| Risk Level | Wallets | Share |
|---|---|---|
| High | 9 | 19.1% |
| Medium | 8 | 17.0% |
| Low/watch | 29 | 61.7% |
| Out of scale (HTX) | 1 | 2.1% |
| Total | 47 | 100% |

## 3. Total Amount Moved Through the Network

Vector 1 (500 of the node’s 600 registry addresses — excluding 89 external services, 5 infrastructure addresses, Ak9W, and 5 Binance-tagged addresses (the four hot wallets that funded TWRXj4SD, plus BinHW_qrr6 — see 1.1), whose own turnover serves unrelated third parties): unique external inflow $166,221,372.61; unique external outflow $215,735,928.93. Vector 2 (EJon/HBK, 47 addresses): unique external inflow $1,445,831,610.35; unique external outflow $1,333,446,638.65. Combined unique external inflow, treating Vector 1 and Vector 2 as a single perimeter: $1,565,190,574.49. This is not the sum of the two inflow figures above ($1,612,052,982.96) — that naive sum still double-counts the $46,862,408.47 in transactions that cross between the two vectors (14 transactions, dominated by the $23.38M CoQ→EJon bridge, 1.1), which are internal to the combined perimeter and must be removed once, not attributed to either vector’s inflow.

*[Table: 4 rows — see data/ folder for full machine-readable version]*

| Item | Unique External Inflow | Share |
|---|---|---|
| Vector 1 (CoQ) | $166,221,372.61 | 10.6% |
| Vector 2 (EJon/HBK) | $1,445,831,610.35 | 92.4% |
| Minus cross-vector overlap (14 tx, 1.1) | −$46,862,408.47 | −3.0% |
| Total (single perimeter) | $1,565,190,574.49 | 100% |

Methodology. — This figure is unique external capital crossing into (or out of) each tracked address set — each dollar counted once, at the point it first enters or leaves the set. This differs from gross turnover (summing every transaction touching a tracked address regardless of direction), which would count the same money multiple times as it moves hop to hop: a single dollar moving through an internal chain of up to 6 addresses (see 2.2) would be counted at every hop under a gross approach — up to 5 times over. The internal-hop volume in this dataset is $288,360,473.20 for Vector 1 and $620,255,667.11 for Vector 2 — this reflects the structuring process itself, not additional capital, and is excluded from the figures above. The anchor transaction (THkSW85s → CoQ, $120,271,055.09, see 1.1) is itself an internal transfer within the 500-address Vector 1 set, given its upstream connection to other Vector 1 addresses, and is not separately added to the inflow figure to avoid double-counting; it remains the incident’s stated anchor amount throughout this report.

Flow asymmetry. Inflow and outflow are not expected to match, and here they do not: Vector 1 shows more outflow than inflow ($215.7M vs $166.2M, a $49.5M gap); Vector 2 shows more inflow than outflow ($1,445.8M vs $1,333.4M, a $112.4M gap). Per-address breakdown attributes almost all of each gap to single addresses. Vector 1: THkSW85s accounts for $119.72M of the gap — it sent $120,271,055.09 to CoQ while showing only $555,555.00 in tracked USDT inflow, meaning its funding source is not fully accounted for by verified transactions in this dataset (1.1). Vector 2: the HTX-tagged address accounts for $100.6M of the gap ($102.8M in, $2.2M out) — 213 of its 235 transactions are high-frequency inbound payments from a single counterparty between March and April 2026, a pattern resembling routine exchange account activity rather than scheme-controlled structuring.

## 4. Methodology

### 4.1 Data Sources

The analysis is based on CSV exports from Tronscan: one file per address (the full history of incoming and outgoing transactions), merged into a consolidated dataset. Arkham Intelligence was used to visualize the connection graph and to independently confirm external entities. Facts about the public incident (the Tether freeze, sanctions against HTX) were checked against open sources — news outlets and specialist investigators.

### 4.2 Address Attribution

Assigning a blockchain address a label identifying a real-world entity (exchange, bridge, service) is called address attribution, or entity attribution; within Arkham Intelligence itself this feature is called Entities. Attribution is built on on-chain heuristics and the platform's crowdsourced data, not a one-off match. In this investigation, Arkham attribution was used to confirm the status of external services (NEAR Intents, FixedFloat, KuCoin, ChangeNOW, Binance hot wallets) and to separate them from addresses controlled by the scheme itself.

### 4.3 Analytical Methods

Beyond attribution, the following were applied: address lifespan calculation (first/last appearance in the data); detection of single-day turnover spikes (the largest day's share of an address's total turnover, and the inflow-to-outflow ratio on that day); heatmaps of transaction density by day of week and hour; role classification — recipient / aggregator / distributor; mapping against FATF indicators across six red-flag categories.

### 4.4 Limitations

Monero conversion is outside the scope of this analysis and is not traced. Monero transactions are not observable on TRON or on any public ledger by design, and the reported XMR purchases are taken from public reporting rather than reproduced here. The objective was not to follow funds into Monero but to reconstruct the chain preceding it: the coordination of the transfers and the pre-existing infrastructure supporting them indicate an organised network rather than a single actor, which in turn implies this is unlikely to be the first such episode — making the upstream chain and the connected clusters the more productive object of investigation. On-chain data cannot establish which specific exchange client initiated a given withdrawal — that requires a request to the exchange itself. The FATF “geography” category was not assessed: a blockchain address does not reveal a counterparty's jurisdiction. For the EJon/HBK node, full disclosure of major hubs' recipients (as was done for the CoQ node) was not carried out, owing to these addresses' many-month operating history, in which separating case-relevant activity from unrelated activity is harder than for CoQ's two-day episode.

## 5. Addresses Reviewed and Placed Out of Scope

Addresses and activity reviewed during the analysis and either excluded from the registry or carried in it under an out-of-scale status — with a brief rationale for each.

TDii6vao. A shared external service address in contact with a very large number of unrelated wallets; contact with it is not by itself indicative of scheme membership, and it is carried out of scale in this report on that basis. The address is separately the subject of an unrelated investigation into a phishing-kit network, in which on-chain review of approximately 100,000 transactions across a 1.2-day window in August 2026 recorded 48,094 distinct paying counterparties, with 99.9% of inbound TRX payments at or below 15 TRX (median 5.07 TRX); no DelegateResourceContract call originating from the address within the sampled window, all 70 delegation records showing it as receiver; and all 58 TriggerSmartContract calls directed to the USDT TRC-20 contract. A single counterparty, TB2jWc4U2, accounts for 45.5% of inbound TRX volume across that window. No direct transactional link between that network and the CoQ or EJon/HBK vectors has been identified; the shared element is the service address itself.

TB2jWc4U2. Counterparty to TDii6vao, carried out of scale on the same basis. Reviewed in the separate investigation referenced above: across a sampled 40-hour window (5–6 August 2026) it sent 406,221.83 TRX to TDii6vao and received 286,692.46 USDT in return, on a fixed schedule of one transfer in each direction at approximately 30-minute intervals — an implied rate of 0.7058 USD per TRX against a market rate of approximately 0.33 USD at the time of review. All 100 of its outbound USDT transfers within the same window (289,027.23 USDT) were directed to a single address, TCFNp179Lg46D16zKoumd4Poa2WFFdtqYj. Its status in this registry is provisional pending the conclusion of that investigation.

Phishing tokens on Ak9W. Within 45 minutes of the public freeze, decoy tokens (“UNFREEZE TG:UFT6699” and similar) began arriving at the address, with amounts mimicking the real tranches. This is exploitation of the freeze's publicity by unrelated scammers, not a movement of real funds.

Promotional TRC20 tokens. The dataset contains spam tokens (78918.com, RANDOM.BET, KTY, and others) — mass mailings to active addresses, unrelated to the case.

THpTu4Qv4QvBUv5H9YF3yiFyrTqN1pwNUC and TUS2vzR5AMYXBQuDuvovkhDTn8sho1SnL4. The main recipients from the Binance hot wallets. The scale and regularity of inflows (hundreds of millions of dollars over roughly a year) are characteristic of internal exchange reserve rotation rather than the scheme — but were not independently verified and are not included in the registry.

AuthGemJoin5. A smart contract underpinning the USDD stablecoin — not a wallet; risk scoring does not apply to it.

## 6. Typology Assessment

Public sources characterize the incident only as “suspected laundering,” without specifying a type. Four candidate typologies are weighed below against the evidence gathered in this investigation. None is confirmed; each carries a different evidentiary weight, and they are not mutually exclusive.

### 6.1 Hack/Theft Proceeds Requiring Urgent Liquidation

For: The acute, compressed tempo of Vector 1 (17h32m window, automated same-day structuring, immediate use of an already-existing but otherwise dormant-feeling bridge) contrasts sharply with Vector 2’s calm, 17-month operating rhythm (2.3) — consistent with funds under time pressure being pushed through pre-existing infrastructure at maximum speed.

Against: No hack has been publicly confirmed as the source of the funds reaching CoQ (see “Beyond the Public Reporting”). CoQ’s own upstream funding loop (1.1) has not been traced to a specific compromise or victim.

### 6.2 Sanctions Evasion (A7 / Russia-Linked Network)

For: The UK sanctioned HTX on May 26, 2026 specifically for links to the A7 sanctions-evasion network. This dataset separately contains an address tagged HTX-addr inside the EJon cluster that sent $11,150.81 into the network on May 20, 2026 — six days before the sanctions announcement and three weeks before the CoQ incident. The EJon↔HBK bridges (CQx→veEP, May 21; JEk→V3px, May 28) fall within this same window.

Against: The HTX-addr node carries 1 of 5 FATF flags and is placed out of scale as an attributed exchange address (2.5). Of its 235 transactions, 213 are inbound high-frequency payments (often several per hour) from a single counterparty between March and April 2026, a pattern resembling routine account activity rather than scheme structuring; the $11,150.81 payment into the network is 0.01% of this address’s $102.8M tracked inflow. No direct A7/A7A5 token transfer has been identified anywhere in this dataset. This reads as a temporal coincidence attached to an otherwise ordinary high-volume address, not a structural link.

### 6.3 Pig-Butchering / Romance-Scam Payout Consolidation

For: None specific to this dataset.

Against: This investigation begins at CoQ’s receipt of funds, not at a traceable victim-deposit stage. No retail or romance-scam deposit addresses have been identified feeding either vector.

### 6.4 Gray-Market OTC / Payment-Processor Infrastructure Serving an Urgent Client

For: Vector 2’s 17-month, weekday/business-hours operating discipline (2.3), its role profile (2.4: aggregators and distributors predominate, almost no one-time deposits), and its pre-existing bridge relationship with CoQ’s operators — a month before the public incident — are all consistent with a standing money-service business serving multiple clients, one of whom (CoQ) needed an unusually fast, large withdrawal in June 2026.

Against: A licensed OTC desk would typically be expected to perform its own KYC/CDD on counterparties; no such compliance layer is visible on-chain. This absence, however, is equally consistent with an illicit operation, so it does not by itself discriminate between the two readings.

### 6.5 Assessment

6.4 currently carries the strongest evidentiary support of the four, though still circumstantial; 6.2’s main on-chain touchpoint is a small fraction of an otherwise-routine address’s activity, so it stands mainly on the external sanctions timing rather than on this dataset; 6.1 remains open pending confirmation of a specific hack or victim; 6.3 has no supporting evidence in this dataset and is not favored. These are not competing alternatives: a gray-market payment processor (6.4) could itself be the infrastructure through which either sanctions-evasion traffic (6.2) or a one-off hack payout (6.1) is routed, if either is later confirmed.

## 7. Recommendations and Escalation

### 7.1 Priority Addresses

50 addresses meet the high-risk threshold (3+ of 5 FATF flags) on pattern grounds; Ak9W is separately high-risk by direct external action (the Tether freeze) rather than by flag count, for 51 in total. The full list is in the Appendix (Wallet Registry). By traced transaction volume, the following warrant first review:

*[Table: 8 rows — see data/ folder for full machine-readable version]*

| Code | Cluster | FATF Flags | Approx. Volume (USDT only) |
|---|---|---|---|
| CoQ | CoQ | 3 | $241.75M |
| Ak9W | CoQ | External (Tether freeze) | $118.63M |
| UnPt | HBK | 4 | $132.85M |
| cxFH | EJon | 3 | $60.82M |
| Uojk | HBK | 3 | $57.44M |
| 1w6 | HBK | 3 | $52.15M |
| whr | HBK | 3 | $51.95M |
| ZhH | HBK | 3 | $51.95M |

### 7.2 Escalation Considerations

Findings that would typically be considered for a Suspicious Activity/Transaction Report (SAR/STR) include: receipt of funds from an address independently blacklisted by the issuing stablecoin company for suspected laundering (Ak9W, 1.2); and a confirmed bridge, pre-dating the public incident by a month, to a 17-month-old network showing business-hours operational discipline (2.1, 2.3). A third basis considered — a closed funding loop upstream of CoQ — is not included here: on-chain verification supports only 2 of the loop’s 5 internal hops (1.1); it should not be cited as a confirmed finding until the remaining hops are traced or the mechanism is otherwise established. Filing determination, jurisdiction, and the specific regulatory trigger require review by qualified compliance or legal counsel; this report provides the factual and analytical basis for that review, not the filing decision itself.

### 7.3 Draft Narrative (for SAR/STR Preparation)

The following is a drafting aid, not a filed narrative, and requires institutional review before use.

“On-chain analysis identified a network of at least 647 TRON addresses exhibiting characteristics consistent with layered fund structuring, active from at least January 2025. On June 11, 2026, one node (address CoQ) received $120,271,055.09 in a single transaction; $94,980,295.09 was moved same-day to a second address (Ak9W). Tether Ltd. subsequently blacklisted $72,030,295.66 held at that address on June 12, 2026, citing suspected laundering. Two of the five hops in the receiving address’s reported upstream funding chain are independently confirmed on-chain, including a confirmed $23,380,000 bridge (May 6, 2026) to a separate, longer-running network active since January 2025, itself linked by two further bridges ($2,000,000 and $5,000,000, May 2026) to a third cluster. [Subject/account information, jurisdiction, and recommended action to be completed by the filing institution.]”

## Appendix — Wallet Registry and FATF Flags

Categories. F1 — transactions (structuring, serial operations in a narrow window); F2 — transaction patterns (a dominant single-day spike, inflow ≈ outflow the same day); F3 — anonymity (AEC/Monero, limited-KYC instant exchanges, conversion swaps); F4 — sender/recipient (single-purpose wallet: all meaningful value movement completed within under 7 days, after which the address is not reused — measured on transfers of $100 or more in USDT/USDD, so that promotional tokens and dust arriving after an address has finished its role do not extend its apparent lifespan; IP/KYC indicators are unavailable from blockchain data); F5 — source of funds (the address sits in a funding chain whose origin is not fully accounted for on-chain, or its status was previously undisclosed). The “geography” category was considered but is not scored — a blockchain address does not reveal jurisdiction, and the assessment is unavailable for the registry as a whole rather than for individual wallets. Addresses are truncated to the first 7 and last 6 characters; full addresses are in a separate registry file (Excel).

Risk level. 3+ flags out of five — high; 2 — medium; 0–1 — low/watch. “Out of scale (service)” — independently attributed legitimate infrastructure (exchanges, bridges); where an attribution rests on amount-ranking within a known fan-out rather than individual confirmation, it is marked “proxy”. “Out of scale (infra)” — service addresses of the scheme itself (gas top-ups, automated bots), not participants in laundering per se. “High*” — risk level is set by a direct external action (the Tether freeze) rather than by the flag-count threshold; pattern flags are still shown where present.

*[Table: 647 rows — see data/ folder for full machine-readable version]*

## Appendix — Public Sources

### Incident (Tether Freeze, June 11–12, 2026)

The six incident reports below all derive from a single primary source — the ZachXBT on-chain disclosure of June 12, 2026. They corroborate one another in wording, not independently in evidence, and should be counted as one source for confidence purposes.

• Coinpaprika — Tether Freezes 72 Million USDT in Tron Wallet Linked to $120M Transfer

• CryptoBriefing — Tether blacklists wallet linked to $120M USDT transfer, freezes $72M

• Crypto News — ZachXBT Tracks $120M USDT Transfer as Tether Freezes $72M

• SpazioCrypto — Tether Freezes $72M USDT After Monero Pump Exposes $120M Laundering

• CryptoTimes — ZachXBT Links $120M USDT Flow to Monero (XMR) Surge

• ForkLog — Tether blocked $72M USDT on TRON (Russian-language coverage)

### Sanctions Against HTX and the A7 Network (May 26, 2026)

• Elliptic — UK designates cryptoasset exchanges including HTX in sweeping new sanctions package

• Chainalysis — UK sanctions crypto entities in Russian trade-blockade evasion crackdown

• CoinDesk — UK sanctions Huobi and ruble stablecoin issuer in crackdown on Russia crypto networks

### Methodology

• FATF — Virtual Assets Red Flag Indicators of Money Laundering and Terrorist Financing (2020)

## Appendix — Transaction Hash Index

Every individual transaction underlying both movement-of-funds tables (1.3, 2.2), in full — Vector 1 first, Vector 2 (originally the aggregated rows only) below.

### Vector 1

*[Table: 62 rows — see data/ folder for full machine-readable version]*

### Vector 2

*[Table: 78 rows — see data/ folder for full machine-readable version]*

## Appendix — Cluster Validation (Silhouette Analysis)

### A.1 Purpose

The role classification in 1.5/2.4 (Recipient / Distributor / Aggregator) is defined manually, on lifespan and outgoing-transaction-count thresholds chosen by the analyst. This appendix asks a narrower, independent question: does the transaction-graph structure itself — with no lifespan or timing information, and no thresholds set by hand — favor the same number of behavioral groups? An unsupervised method run on a different feature set arriving at the same group count is corroborating evidence for a three-group structure in this network; it is not, by itself, evidence that the two classifications place the same addresses in the same groups (A.4).

### A.2 Data and Method

Sample: 680 addresses with combined degree (incoming + outgoing transfer count) greater than 5, pulled directly from the transaction graph — a lower-activity cut than the full 647-address FATF registry, since this test draws on all counterparties in the traced flow, not only the registry's named wallets.

Features: in-degree and out-degree only, log-transformed (log1p) to reduce the skew of a small number of very high-degree hub addresses dominating the fit. No lifespan, timing, or amount data was used — see A.4.

Method: k-means, swept over k = 1…7 (clustergram 0.8.1 / scikit-learn 1.9.0, `n_init=10`, `random_state=42`), with the mean silhouette score at each k as the stability diagnostic — the metric peaks at the k where clusters are most internally cohesive and most separated from each other, which is not necessarily the largest or smallest k tried.

### A.3 Result

| k | Silhouette score |
|---|---|
| 2 | 0.589 |
| **3** | **0.664** |
| 4 | 0.661 |
| 5 | 0.620 |
| 6 | 0.608 |
| 7 | 0.605 |

The score peaks at k = 3, matching the count of the manual role classes (Recipient / Distributor / Aggregator, 1.5). k = 4 is close behind (0.661) and not statistically distinguished from k = 3 by this diagnostic alone; k = 3 is reported as the better-supported reading on the basis of the peak value.

### A.4 Limitations

This test corroborates the *number* of groups, not the classification itself. The manual classification (1.5/2.4) is defined on lifespan and outgoing-transaction-count; this test used only in/out-degree, a different and narrower feature set, chosen because it is what the transaction graph exposes directly without a separate lifespan computation per address. A three-cluster optimum on connectivity alone is consistent with — but does not confirm — that the resulting clusters correspond address-for-address to Recipient/Distributor/Aggregator. Confirming that would require re-running this method on the same lifespan/outgoing-count features used in 1.5, which was not done here.

The 680-address sample (degree > 5) under-represents the Recipient class as defined in 1.5, which is dominated by one-time, low-degree deposit addresses (0–1 outgoing transactions, 88.8% of the CoQ node per the 1.5 table) — many of those fall below the degree-5 cutoff and are absent from this test. The result should be read as describing the more active tail of the network, not the full registry.

### A.5 Reproducibility

```
MATCH (w:CryptoWallet)
WITH w, COUNT{(w)-[:TRANSFER]->()} AS out_deg,
        COUNT{(w)<-[:TRANSFER]-()} AS in_deg
WHERE out_deg + in_deg > 5
RETURN w.address, in_deg, out_deg
```

```python
import numpy as np
from clustergram import Clustergram

X = np.log1p(df[["in_deg", "out_deg"]])
cgram = Clustergram(range(1, 8), n_init=10, random_state=42)
cgram.fit(X)
cgram.silhouette_score()
```
