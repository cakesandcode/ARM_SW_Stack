# ExecuTorch 1.0 Arm Backend + SME2

**Slug:** executorch-1-0
**Created:** 2026-04-10
**Last updated:** 2026-04-10
**Linked posts:** [Post 1 · Layer 4 — ML Frameworks]
**Status:** ACTIVE

---

## Summary
ExecuTorch 1.0 is PyTorch's on-device inference runtime. The 1.0 release includes an Arm backend that targets SME2 via KleidiAI, delivering INT8 and FP16 speedups over the baseline. Reference models include Llama 3.2 and SqueezeSAM. ExecuTorch is the recommended path for deploying PyTorch models to Arm CPUs without the full PyTorch runtime dependency.

---

## Key Facts

| # | Claim | Value | Source | Confidence | Date verified |
|---|-------|-------|--------|------------|---------------|
| 1 | ExecuTorch version | 1.0 | [https://pytorch.org/executorch/](https://pytorch.org/executorch/) | HIGH | 2026-04-10 |
| 2 | INT8 speedup on SME2 | 1.83× | [https://pytorch.org/executorch/](https://pytorch.org/executorch/) | MEDIUM | 2026-04-10 |
| 3 | FP16 speedup on SME2 | 3.9× | [https://pytorch.org/executorch/](https://pytorch.org/executorch/) | MEDIUM | 2026-04-10 |
| 4 | Reference models | Llama 3.2, SqueezeSAM | [https://pytorch.org/executorch/](https://pytorch.org/executorch/) | HIGH | 2026-04-10 |
| 5 | Arm backend uses KleidiAI | YES | [https://pytorch.org/executorch/](https://pytorch.org/executorch/) | HIGH | 2026-04-10 |
| 6 | Baseline hardware for speedup figures | NOT FOUND — requires test conditions | — | LOW | 2026-04-10 |

---

## Version / Release State

- Current version: ExecuTorch 1.0
- Release date: NOT FOUND — check pytorch.org/executorch release notes
- Deprecation status: NONE
- Next known release: NOT FOUND

---

## Open questions

- [ ] Claims #2/#3 (1.83× INT8, 3.9× FP16): test conditions unknown. Need baseline hardware (which Arm CPU, which exact SKU), batch size, model, and comparison point (vs NEON baseline? vs CPU without SME2?).
- [ ] ExecuTorch 1.0 GA date: confirm release vs pre-release status.
- [ ] SqueezeSAM: confirm this is SAM (Segment Anything Model) compressed variant — verify model architecture and task.
- [ ] Llama 3.2 ExecuTorch benchmark: confirm token/s figures if published.

---

## Update log
- 2026-04-10 · corpus-seed · Initial entry. Speedup figures MEDIUM — test conditions not captured. Mark LOW until conditions confirmed.
- 2026-04-12 · arm-verify · All 6 claims verified against ≥2 independent sources. Claims 1, 4, 5 confirmed HIGH. Claims 2, 3, 6 confirmed MEDIUM (test conditions mobile-specific, not generalizable across Arm ecosystem). ExecuTorch 1.0 GA release: October 2025. Test conditions fully documented: vivo X300 + SME2 + SqueezeSAM + XNNPACK/KleidiAI + single core + FP32 baseline. Verified file: /Research/verified/executorch-1-0.md

## Update — 2026-04-13 (arm-update)
**Trigger:** New release — ExecuTorch 1.2.0 published after topic Last updated date.
**Change:** ExecuTorch 1.2.0 is now the current release; it adds Voxtral Realtime speech inference, Cortex-M as a first-class target with CMSIS-NN integration, Metal backend improvements, and additional model support (Qwen3.5, Parakeet, Silero VAD). ExecuTorch 1.0 is no longer the current version.
**Affected claims:** #1 (version — now outdated), #4 (reference models — expanded in 1.2.0)
**Action taken:** Update block appended; MODERATE alert raised. Existing claims about ExecuTorch 1.0 features (Arm backend, KleidiAI integration, speedup figures) remain factually accurate but the version cited in Post 1 is behind by two minor releases.
**Source:** [ExecuTorch Releases — GitHub](https://github.com/pytorch/executorch/releases) accessed 2026-04-13
