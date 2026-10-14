# Students — SONIC

**Project:** SONIC  
**Category:** SEARCH_ENGINES  
**Upstream:** https://github.com/valeriansaliou/sonic  
**Pinned commit:** `f7a75d25eb07d0e16456cb0a4098496dd8674c0e`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `ef2f6a083edb56a883245179fb9ba609c63304297e58785cd59b81ee9fb9459c`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `f7a75d25eb07d0e16456cb0a4098496dd8674c0e`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `ef2f6a083edb56a883245179fb9ba609c63304297e58785cd59b81ee9fb9459c`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
