# Investigation into Cryptoasset Laundering Through the TRON Network

On-chain investigation into a $120.27M USDT movement on TRON (the "CoQ" incident, June 11–12, 2026,
Tether freeze of $72.03M) and its connection to a separate network active since January 2025
("EJon/HBK"). 647 addresses assessed, red-flag scoring adapted from the FATF Virtual Assets Red Flag
Indicators (2020).

## Status and disclaimer

This is independent analytical work product, not a regulatory, judicial, or law-enforcement finding.
"High risk" and similar labels reflect on-chain pattern indicators only; they are not accusations
against any person, and several were revised during review after independent verification changed
the underlying numbers (see `report/REPORT.md`, §4.4 Limitations, for what on-chain data can and
cannot establish). Do not use this repository as the sole basis for account or transaction decisions
affecting a real person or entity.

## Contents

| Path | What it is |
|---|---|
| `report/REPORT.md` | Full investigation report, readable directly on GitHub |
| `report/Investigation_into_Cryptoasset_Laundering_Through_the_TRON_Network.docx` | Same report, formatted for offline reading/printing |
| `data/wallet_registry_fatf.csv` | All 647 assessed addresses, FATF flags (F1–F5), risk tier |
| `data/transaction_hash_index.csv` | 140 individual transactions with full TXIDs, underlying the report's summary tables |
| `data/key_transactions_vector1.csv` / `_vector2.csv` | The curated transaction tables as shown in the report body |
| `data/master_transactions.csv` | Full underlying dataset — 60,096 transaction rows, 2022-02-06 to 2026-07-11, as exported from Tronscan |
| `MANIFEST.md` | Every file in this repo with size and SHA-256 checksum |
| `CHAIN_OF_CUSTODY.md` | Data snapshot date, source, and known limitations of the attribution data |

## Registry summary

647 addresses total: 600 in the CoQ node, 47 in EJon/HBK.

| Risk tier | Addresses |
|---|---|
| High (incl. 1 by external confirmation) | 51 |
| Medium | 163 |
| Low/watch | 338 |
| Out of scale (attributed exchange/service) | 90 |
| Out of scale (scheme infrastructure) | 5 |

"Out of scale" addresses are independently attributed exchange or service addresses (or the scheme's
own gas/energy infrastructure) and are not scored for risk — see `report/REPORT.md` §Appendix for the
FATF flag definitions and why the "geography" category is not scored at all.

## Methodology, in one paragraph

Transaction data was exported from Tronscan per address and consolidated into
`data/master_transactions.csv`. Entity attribution (exchange, bridge, service) uses Arkham
Intelligence's Entities feature, cross-checked against public reporting. Five FATF indicator
categories were scored on-chain (F1–F5); a sixth (geography) is not scorable from blockchain data
alone and is reported as such rather than guessed. Full methodology, including what was *not*
established and why, is in `report/REPORT.md` §4.

## Reproducing a claim

Every dollar figure and date in the report traces to a row in one of the `data/` files. To check any
transaction cited in the report: take the TXID from `data/transaction_hash_index.csv` (or the `Note`
column of the key-transaction tables) and look it up directly on
[Tronscan](https://tronscan.org/#/transaction/) — paste the TXID after the trailing slash.
