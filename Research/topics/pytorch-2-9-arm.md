# PyTorch 2.9 SVE2/SME2 Improvements

**Slug:** pytorch-2-9-arm
**Created:** 2026-04-10
**Last updated:** 2026-04-10
**Linked posts:** [Post 1 · Layer 4 — ML Frameworks]
**Status:** ACTIVE

---

## Summary
PyTorch 2.9 includes significant Arm-specific improvements: TorchInductor now generates SVE2 and SME2 vectorized code via LLVM, and XNNPACK is updated with KleidiAI SME2 kernels for INT4/INT8 inference. The combination means that existing PyTorch models running on Neoverse V3 or N3 hardware get automatic SME2 throughput improvements without model-level code changes.

---

## Key Facts

| # | Claim | Value | Source | Confidence | Date verified |
|---|-------|-------|--------|------------|---------------|
| 1 | PyTorch version | 2.9 | [https://pytorch.org/blog/](https://pytorch.org/blog/) | MEDIUM | 2026-04-10 |
| 2 | TorchInductor SVE2/SME2 codegen | YES — via LLVM backend | [https://pytorch.org/blog/](https://pytorch.org/blog/) | MEDIUM | 2026-04-10 |
| 3 | XNNPACK + KleidiAI integration | YES — auto-dispatch INT4/INT8 on SME2 | [https://github.com/google/XNNPACK](https://github.com/google/XNNPACK) | HIGH | 2026-04-10 |
| 4 | No model code changes required | YES — dispatch is transparent via KRT | [https://gitlab.arm.com/kleidi/kleidiai](https://gitlab.arm.com/kleidi/kleidiai) | HIGH | 2026-04-10 |
| 5 | PyTorch 2.9 release date | NOT FOUND — verify against pytorch.org/blog | — | LOW | 2026-04-10 |

---

## Version / Release State

- Current version: PyTorch 2.9 (confirm release vs RC status)
- Release date: NOT FOUND — requires verification
- Deprecation status: NONE
- Next known release: NOT FOUND

---

## Open questions

- [ ] Claim #1/#5: Confirm PyTorch 2.9 has been released (not RC). If still RC, adjust claims accordingly.
- [ ] TorchInductor SME2 codegen: confirm LLVM minimum version required and whether this is enabled by default or requires a build flag.
- [ ] XNNPACK KleidiAI SME2 kernels: confirm minimum XNNPACK version and whether this ships in the default PyTorch 2.9 wheel.
- [ ] Performance benchmark: need an official figure for SME2 vs NEON baseline for a representative model (e.g., Llama-7B token/s, ResNet-50 images/s).

---

## Update log
- 2026-04-10 · corpus-seed · Initial entry. Version number MEDIUM confidence — needs confirmation against official pytorch.org release notes.
- 2026-04-12 · arm-verify · All 5 claims verified against ≥2 independent sources. Claims 1 and 5 upgraded from LOW/MEDIUM to HIGH confidence. Verified file created at verified/pytorch-2-9-arm.md. Confirmed: PyTorch 2.9.0 released 2025-10-15; TorchInductor SVE2/SME2 codegen via LLVM + KleidiAI auto-dispatch; zero code changes required; all features enabled by default in standard PyTorch wheel and ExecuTorch 0.7+.

## Update — 2026-04-13 (arm-update)
**Trigger:** New releases — PyTorch 2.10 and 2.11 published after topic Last updated date.
**Change:** PyTorch 2.10 was released 2026-01-21; PyTorch 2.11 GA has also been released as of April 2026, making PyTorch 2.9 no longer the current version.
**Affected claims:** #1 (version), #5 (release date context)
**Action taken:** Update block appended; MODERATE alert raised. Existing claims about PyTorch 2.9 features remain factually accurate but the version is outdated. Claim #1 version value should be qualified as "2.9 (at time of Post 1 publication; current as of April 2026: 2.11)".
**Source:** [PyTorch 2.10 Release Blog](https://pytorch.org/blog/pytorch-2-10-release-blog/) accessed 2026-04-13; [PyTorch 2.11.0 GA](https://dev-discuss.pytorch.org/t/pytorch-2-11-0-general-availability/3328) accessed 2026-04-13
