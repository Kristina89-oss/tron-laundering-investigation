# Manifest

Every file in this repository, its size, and its SHA-256 checksum. Recompute and compare before
relying on a file if you did not download it directly from this repository's release/commit.

| File | Size (bytes) | SHA-256 |
|---|---|---|
| `README.md` | 3,378 | `7a709d88676337151b23730bd385dccbec355a26f4b2134ae872d6807f016683` |
| `LICENSE` | 888 | `8a3ed70e429d7a89f03efc82b779499a427f4a769faaf376475134afe2521e42` |
| `MANIFEST.md` | (this file) | — |
| `CHAIN_OF_CUSTODY.md` | 2,972 | `16a6986b993102e57254926ff00a18dfbd6ed652127dfc01c7147a9a0f42e060` |
| `report/REPORT.md` | 37,566 | `bbe500da365561e55eb4c8ae0a226d53ed81994cc185277435d6cdcde986e2d7` |
| `report/Investigation_into_Cryptoasset_Laundering_Through_the_TRON_Network.docx` | 454,460 | `a17e9cd44108f5a1a5fdf42b4037f3d02c55d9eb5a5ce7a4bb98d847bb68c9ee` |
| `data/wallet_registry_fatf.csv` | 35,340 | `822c8a71dec97ee5f7f1b50d804352a269e9d67ea729674b0c02fb868dc9054b` |
| `data/transaction_hash_index.csv` | 20,416 | `e562a55a47e1d02dd98bec5028d62b16a8c2c641525533fb406fa741e8dfff62` |
| `data/key_transactions_vector1.csv` | 2,966 | `911aa1d27076478a10c34b0ba670af1f8fbb2124309e4414018d199360c2591e` |
| `data/key_transactions_vector2.csv` | 1,596 | `611f1ee2a9fe690ea1f651b2a7d141f87996d50c11a7d02c3b0462733fd98fd5` |
| `data/master_transactions.csv` | 10,113,973 | `1b71c690b2a55273e5d4c7b45b7bf66d09fba3f9e99452253ab1aea5684c6201` |

## How to verify

```bash
# Linux / macOS
sha256sum -c <<'EOF'
822c8a71dec97ee5f7f1b50d804352a269e9d67ea729674b0c02fb868dc9054b  data/wallet_registry_fatf.csv
1b71c690b2a55273e5d4c7b45b7bf66d09fba3f9e99452253ab1aea5684c6201  data/master_transactions.csv
EOF
```

```powershell
# Windows (PowerShell)
Get-FileHash data\wallet_registry_fatf.csv -Algorithm SHA256
```

If a hash does not match, the file has been altered since this manifest was generated — do not treat
it as the verified version.

## Generated

This manifest and the checksums above were generated in the same working pass that produced
`report/REPORT.md` and the `data/` extracts, directly from the source report
(`report/*.docx`) and its underlying transaction dataset. See `CHAIN_OF_CUSTODY.md` for data
provenance.
