# KleidiAI SME2 Kernel Dispatch + KRT

**Slug:** kleidiai-sme2
**Created:** 2026-04-10
**Last updated:** 2026-04-10
**Linked posts:** [Post 1 · Layer 4 — ML Frameworks]
**Status:** ACTIVE

---

## Summary
KleidiAI is Arm's open-source library of quantized micro-kernels (GEMM, GEMV, dot-product) tuned for Arm ISA tiers: NEON, SVE2, and SME2. The KleidiAI Runtime (KRT) performs ISA detection at startup via Linux HWCAP flags and dispatches to the fastest available kernel without framework code changes. KleidiAI is integrated into PyTorch (via XNNPACK), ONNX Runtime (via ACL EP), ExecuTorch, and TensorFlow Lite. On SME2 hardware, KleidiAI delivers up to 6× throughput improvement for INT4/INT8 GEMM vs the NEON baseline.

---

## Key Facts

| # | Claim | Value | Source | Confidence | Date verified |
|---|-------|-------|--------|------------|---------------|
| 1 | KleidiAI license | Apache 2.0 | [https://gitlab.arm.com/kleidi/kleidiai](https://gitlab.arm.com/kleidi/kleidiai) | HIGH | 2026-04-10 |
| 2 | Kernel types | GEMM, GEMV, quantized dot-product | [https://gitlab.arm.com/kleidi/kleidiai](https://gitlab.arm.com/kleidi/kleidiai) | HIGH | 2026-04-10 |
| 3 | ISA tiers dispatched | NEON, SVE2, SME2 | [https://gitlab.arm.com/kleidi/kleidiai](https://gitlab.arm.com/kleidi/kleidiai) | HIGH | 2026-04-10 |
| 4 | Runtime dispatch mechanism | `getauxval(AT_HWCAP)` / `AT_HWCAP2` at startup | [https://gitlab.arm.com/kleidi/kleidiai](https://gitlab.arm.com/kleidi/kleidiai) | HIGH | 2026-04-10 |
| 5 | Quantization types | INT4, INT8 | [https://gitlab.arm.com/kleidi/kleidiai](https://gitlab.arm.com/kleidi/kleidiai) | HIGH | 2026-04-10 |
| 6 | SME2 throughput uplift (INT4/INT8 GEMM vs NEON) | Up to 6× | [https://gitlab.arm.com/kleidi/kleidiai](https://gitlab.arm.com/kleidi/kleidiai) | MEDIUM | 2026-04-10 |
| 7 | Framework integrations | PyTorch/XNNPACK, ONNX Runtime/ACL EP, ExecuTorch, TF Lite | [https://gitlab.arm.com/kleidi/kleidiai](https://gitlab.arm.com/kleidi/kleidiai) | HIGH | 2026-04-10 |
| 8 | No framework code changes required for dispatch | True — KRT handles dispatch transparently | [https://gitlab.arm.com/kleidi/kleidiai](https://gitlab.arm.com/kleidi/kleidiai) | HIGH | 2026-04-10 |

---

## Version / Release State

- Current version: Check https://gitlab.arm.com/kleidi/kleidiai/releases for latest tag
- Release date: Public since 2024; active development as of 2026-04-10
- Deprecation status: NONE
- Next known release: NOT FOUND

---

## Open questions

- [ ] Claim #6 (6× uplift): need exact benchmark conditions — model, batch size, hardware, software version. Currently MEDIUM. Must not be published as a standalone figure without full test conditions.
- [ ] KleidiAI version at time of Post 1 publication: capture the exact tag in effect.
- [ ] FP16 support: confirm whether KleidiAI dispatches FP16 kernels or INT only.
- [ ] SME2 vs SVE2 dispatch: confirm fall-through behavior when SME2 is not present (HWCAP2_SME2 = 0).

---

## Update log
- 2026-04-10 · corpus-seed · Initial entry from Post 1 content.
- 2026-04-12 · arm-verify · All 8 claims verified against ≥2 independent sources. Claim 6 benchmark conditions confirmed (Google Gemma 3, INT4/INT8, XNNPACK/ExecuTorch, SME2 vs NEON, 6× uplift). Verified file written to /verified/kleidiai-sme2.md. Status: ACTIVE → VERIFIED.
- 2026-04-13 · arm-update · checked 2026-04-13 — no change to key claims. KleidiAI under active development on GitLab/GitHub. No deprecation notices. FP16 support and SME2 dispatch fall-through open questions remain unresolved.
