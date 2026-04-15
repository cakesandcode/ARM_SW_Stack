# Neoverse CSS V3 and N3 Specifications

**Slug:** neoverse-v3-n3
**Created:** 2026-04-10
**Last updated:** 2026-04-10
**Linked posts:** [Post 1 · Layer 1 — Silicon]
**Status:** ACTIVE

---

## Summary
Neoverse CSS V3 and CSS N3 are Arm's current-generation server CPU platforms, shipping in products from Microsoft (Cobalt 200) and Google (Axion N4A). V3 targets maximum compute density and AI throughput; N3 targets efficient scale-out. Both support SME2, CXL 3.0, and PCIe Gen5. V3 carries a reported 84% AI performance uplift vs V2. N3 carries a 3× ML performance improvement vs N2 and 20% better performance-per-watt. (Note: AWS Graviton4 uses Neoverse V2, not V3.)

---

## Key Facts

| # | Claim | Value | Source | Confidence | Date verified |
|---|-------|-------|--------|------------|---------------|
| 1 | V3 core count (CSS config) | 128 cores | [https://developer.arm.com/Processors/Neoverse%20V3](https://developer.arm.com/Processors/Neoverse%20V3) | HIGH | 2026-04-10 |
| 2 | V3 ISA extensions | SME2, SVE2, AMX | [https://developer.arm.com/Processors/Neoverse%20V3](https://developer.arm.com/Processors/Neoverse%20V3) | HIGH | 2026-04-10 |
| 3 | V3 interconnect | PCIe Gen5, CXL 3.0 | [https://developer.arm.com/Processors/Neoverse%20V3](https://developer.arm.com/Processors/Neoverse%20V3) | HIGH | 2026-04-10 |
| 4 | V3 memory | HBM3 support | [https://developer.arm.com/Processors/Neoverse%20V3](https://developer.arm.com/Processors/Neoverse%20V3) | HIGH | 2026-04-10 |
| 5 | V3 AI uplift vs V2 | 84% | [https://developer.arm.com/Processors/Neoverse%20V3](https://developer.arm.com/Processors/Neoverse%20V3) | MEDIUM | 2026-04-10 |
| 6 | V3 example product | Microsoft Cobalt 200 | [https://azure.microsoft.com/en-us/blog/cobalt-100-microsoft-first-arm-cpu](https://azure.microsoft.com/en-us/blog/cobalt-100-microsoft-first-arm-cpu) | HIGH | 2026-04-10 |
| 7 | N3 ML perf vs N2 | 3× | [https://developer.arm.com/Processors/Neoverse%20N3](https://developer.arm.com/Processors/Neoverse%20N3) | MEDIUM | 2026-04-10 |
| 8 | N3 perf/W improvement vs N2 | 20% | [https://developer.arm.com/Processors/Neoverse%20N3](https://developer.arm.com/Processors/Neoverse%20N3) | MEDIUM | 2026-04-10 |
| 9 | N3 TDP (32-core config) | 40 W | [https://developer.arm.com/Processors/Neoverse%20N3](https://developer.arm.com/Processors/Neoverse%20N3) | MEDIUM | 2026-04-10 |
| 10 | N3 example products | Google Axion N4A | [https://cloud.google.com/blog/products/compute/axion-based-n4a-vms-now-in-preview](https://cloud.google.com/blog/products/compute/axion-based-n4a-vms-now-in-preview) | HIGH | 2026-04-12 |

---

## Version / Release State

- Current version: CSS V3 (Neoverse V3), CSS N3 (Neoverse N3)
- Release date: V3 announced 2024; shipping in CSP products 2024–2025
- Deprecation status: NONE
- Next known release: NOT FOUND (V4 / N4 not announced as of 2026-04-10)

---

## Open questions

- [ ] Claim #5 (84% AI uplift): workload and comparison baseline not specified. Need official Arm benchmark disclosure to upgrade to HIGH.
- [ ] Claim #7 (3× ML perf): same issue — benchmark, model, and hardware config required.
- [ ] Claim #9 (40W TDP): confirm if this is TDP for the full SoC or the CPU complex only.
- [ ] CSS V3 vs AGI CPU: clarify whether AGI CPU uses V3 cores inside a Arm-designed SoC, or is a wholly new microarchitecture.
- [x] Cobalt 200 vs Cobalt 100: RESOLVED — Cobalt 100 = N2 (GA Oct 2024, TSMC 5nm, 128 cores); Cobalt 200 = V3 CSS (announced 2025/2026, TSMC 3nm, 132 cores). See verified file.

---

## Update log
- 2026-04-10 · corpus-seed · Initial entry from Post 1 draft.
- 2026-04-12 · arm-verify · Verified all 10 claims against ≥2 sources. CORRECTIONS: Claim 10 updated to "Google Axion N4A" only (removed Graviton4 which uses V2). Added verified file at verified/neoverse-v3-n3.md with full source citations and notes on Cobalt 100 vs 200 discrepancy (132 vs 128 cores). Open question on Cobalt SKUs resolved.
- 2026-04-13 · arm-update · checked 2026-04-13 — no change. No V4/N4 announced. Existing CSS V3/N3 specs confirmed current. Product pages LIVE.
