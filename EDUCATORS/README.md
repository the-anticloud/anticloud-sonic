# Educators — SONIC

**Project:** SONIC  
**Category:** SEARCH_ENGINES  
**Upstream:** https://github.com/valeriansaliou/sonic  
**Pinned commit:** `f7a75d25eb07d0e16456cb0a4098496dd8674c0e`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `ef2f6a083edb56a883245179fb9ba609c63304297e58785cd59b81ee9fb9459c`  
**Date:** October 2026

## Teaching with SONIC

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `ef2f6a083edb56a883245179fb9ba609c63304297e58785cd59b81ee9fb9459c` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
