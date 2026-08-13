# Chain of Custody

## Data source

- **Source:** Tronscan (per-address transaction export) and Arkham Intelligence (entity attribution,
  transaction graph visualization).
- **Extraction method:** Per-address CSV export from Tronscan, consolidated into a single dataset.
- **Consolidated dataset:** `data/master_transactions.csv`
- **Row count:** 60,096
- **Date range covered:** 2022-02-06 01:28:36 UTC to 2026-07-11 21:13:42 UTC
- **Unique sending addresses in dataset:** 21,230
- **Unique receiving addresses in dataset:** 9,173
- **Fields:** Txn Hash, Time (UTC), From, To, Token Symbol, Amount

No block height is recorded in the underlying export; times are as reported by Tronscan at the time
of collection.

## What entity attribution means here, and its limits

"Attributed" (e.g., an address marked as an exchange or bridge) means Arkham's Entities feature
displayed that label at the time of research. Arkham attribution is a mix of on-chain heuristics and
crowdsourced/reported data, and **is not static** — a label current today can be revised, added, or
removed later. An attribution cited in this report should be treated as accurate as of the research
period, not as a live, continuously-verified fact. Anyone re-checking a specific address should
re-query Arkham (or Tronscan's own tags) rather than assume the label in `data/wallet_registry_fatf.csv`
still holds.

A subset of "Out of scale (KuCoin, proxy)" / "Out of scale (FixedFloat, proxy)" labels (66 addresses)
are **not individually confirmed** — they are assigned by transaction-amount ranking within a larger,
partially-attributed fan-out (see `report/REPORT.md` §Appendix, "Categories"). This is disclosed in
the registry itself via the "proxy" marker and should not be read as equivalent to an individually
verified exchange-deposit attribution.

## Known limitations of this dataset (see report §4.4 for full discussion)

- On-chain data cannot identify which specific exchange customer initiated a given withdrawal.
- A funding chain reported for one address (THkSW85s) is not fully reconstructable on-chain: one hop
  passes through a Binance hot wallet, where commingling with unrelated customer funds makes further
  on-chain tracing structurally impossible without exchange records, not merely unfinished.
- Several large upstream hubs in the EJon/HBK network (QT41, THuBSaEk, DZEN, LdaQG) have not had their
  full counterparty fan-out individually traced; the reasoning is disclosed in the report rather than
  silently omitted.
- Monero conversion referenced in public reporting is not observable on TRON or any public ledger and
  is not independently traced in this dataset.

## Integrity verification

Every file's SHA-256 checksum is listed in `MANIFEST.md`. To verify a file has not been altered since
publication, recompute its hash and compare:

```
sha256sum data/master_transactions.csv
```

(On Windows, use `certutil -hashfile data\master_transactions.csv SHA256`.)
