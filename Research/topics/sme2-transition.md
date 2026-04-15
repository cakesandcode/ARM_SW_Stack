# SVE2 → SME2 Transition (3 Levels)

**Slug:** sme2-transition
**Created:** 2026-04-10
**Last updated:** 2026-04-10
**Linked posts:** [Post 1 · Layer 1 — Silicon (preview), Layer 4 — ML Frameworks (full)]
**Status:** ACTIVE

---

## Summary
SME2 (Scalable Matrix Extension 2) is the hardware acceleration tier above SVE2 on Arm v9.2-a+. It adds a tile register file (ZA) and streaming SVE mode, enabling efficient matrix multiply and transformer operations directly in the CPU. The transition from SVE2 to SME2 follows three distinct levels of developer involvement: (1) do nothing — existing SVE2 code runs unchanged in non-streaming mode; (2) KleidiAI-integrated frameworks dispatch to SME2 automatically via HWCAP; (3) explicit programming with streaming mode, ZA tile management, and SME2 intrinsics.

---

## Key Facts

| # | Claim | Value | Source | Confidence | Date verified |
|---|-------|-------|--------|------------|---------------|
| 1 | SME2 ISA introduced in | Armv9.2-a | [https://developer.arm.com/documentation/ddi0616/latest](https://developer.arm.com/documentation/ddi0616/latest) | HIGH | 2026-04-10 |
| 2 | SME2 compile flag | `-march=armv9.2-a+sme2` | [https://developer.arm.com/documentation/101754/latest](https://developer.arm.com/documentation/101754/latest) | HIGH | 2026-04-10 |
| 3 | SME2 HWCAP detection | `getauxval(AT_HWCAP2) & HWCAP2_SME2` | [https://developer.arm.com/documentation/101754/latest](https://developer.arm.com/documentation/101754/latest) | HIGH | 2026-04-10 |
| 4 | Streaming mode entry | `smstart` instruction / `__arm_streaming` ACLE attribute | [https://developer.arm.com/documentation/ddi0616/latest](https://developer.arm.com/documentation/ddi0616/latest) | HIGH | 2026-04-10 |
| 5 | ZA tile register file | 2D tile registers shared across all lanes | [https://developer.arm.com/documentation/ddi0616/latest](https://developer.arm.com/documentation/ddi0616/latest) | HIGH | 2026-04-10 |
| 6 | Level 1: existing SVE2 code | Runs unchanged; no SME2 gain unless code targets streaming mode | [https://developer.arm.com/documentation/101754/latest](https://developer.arm.com/documentation/101754/latest) | HIGH | 2026-04-10 |
| 7 | Level 2: KleidiAI auto-dispatch | Framework calls KleidiAI → KRT detects HWCAP2_SME2 → dispatches SME2 kernel | [https://gitlab.arm.com/kleidi/kleidiai](https://gitlab.arm.com/kleidi/kleidiai) | HIGH | 2026-04-10 |
| 8 | Level 2 coverage | ~95% of production ML inference workloads | [https://gitlab.arm.com/kleidi/kleidiai](https://gitlab.arm.com/kleidi/kleidiai) | LOW | 2026-04-10 |
| 9 | Level 3: explicit SME2 programming | Requires streaming mode management, ZA setup, SME2 intrinsics | [https://developer.arm.com/documentation/101754/latest](https://developer.arm.com/documentation/101754/latest) | HIGH | 2026-04-10 |

---

## Version / Release State

- Current version: SME2 in Armv9.2-a; SME2+ planned in future ISA revision
- Release date: Armv9.2-a — 2023; first silicon shipping in Neoverse V3/N3 platforms
- Deprecation status: NONE (SVE2 not deprecated; remains valid non-streaming path)
- Next known release: SME2+ (NOT FOUND — no announced date as of 2026-04-10)

---

## Open questions

- [ ] Claim #8 (~95% coverage): this figure needs a primary source. Likely from a KleidiAI README or Arm Developer blog. Mark LOW until found.
- [ ] SVE2 vs streaming-SVE2: clarify whether SVE2 instructions are valid inside streaming mode without modification, or if they require re-compilation.
- [ ] ZA tile dimensions: confirm whether tile size scales with SVL (Streaming Vector Length) and what the default SVL is on Neoverse V3.
- [ ] `__arm_streaming` ACLE attribute: confirm supported GCC and LLVM/Clang versions.

---

## Update log
- 2026-04-10 · corpus-seed · Initial entry from Post 1 content. Level descriptions drawn from Arm developer documentation and KleidiAI repo.
- 2026-04-12 · arm-verify · Claims 1-7 and 9 verified against ≥2 independent sources; Claim #8 remains LOW (not promoted). Verified file written to verified/sme2-transition.md.
- 2026-04-13 · arm-update · checked 2026-04-13 — no change. SME2 in Armv9.2-a; no new ISA revision announced. Claim #8 (~95%) still unverified — no primary source found. SVE2 deprecation: NONE confirmed.
