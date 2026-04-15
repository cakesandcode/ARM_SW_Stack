# Verified Claims — SVE2 → SME2 Transition

**Last verified:** 2026-04-12

| Claim | Value | Source 1 | Source 2 | Verified by | Date |
|-------|-------|----------|----------|-------------|------|
| 1. SME2 ISA introduced in | Armv9.2-a | [Arm Architecture Reference Manual ddi0616](https://developer.arm.com/documentation/ddi0616/latest/) | [Arm Newsroom: Scalable Matrix Extension for Armv9](https://newsroom.arm.com/blog/scalable-matrix-extension) | arm-verify | 2026-04-12 |
| 2. SME2 compile flag | `-march=armv9.2-a+sme2` | [Arm Compiler Reference 101754: -march option](https://developer.arm.com/documentation/101754/latest/) | [LLVM Review D109517: Armv9.2-A support](https://reviews.llvm.org/D109517) | arm-verify | 2026-04-12 |
| 3. SME2 HWCAP detection | `getauxval(AT_HWCAP2) & HWCAP2_SME2` | [ARM64 ELF hwcaps: Linux Kernel docs](https://docs.kernel.org/arch/arm64/elf_hwcaps.html) | [getauxval(3) Linux manual page](https://man7.org/linux/man-pages/man3/getauxval.3.html) | arm-verify | 2026-04-12 |
| 4. Streaming mode entry | `smstart` instruction / `__arm_streaming` ACLE attribute | [Arm Architecture Reference ddi0602: SMSTART instruction](https://developer.arm.com/documentation/ddi0602/latest/Base-Instructions/SMSTART--Enables-access-to-Streaming-SVE-mode-and-SME-architectural-state--an-alias-of-MSR--immediate--/) | [LLVM AArch64 SME Documentation: Streaming Mode](https://llvm.org/docs/AArch64SME.html) | arm-verify | 2026-04-12 |
| 5. ZA tile register file | 2D tile registers (SVL × SVL bytes) shared across all lanes | [Arm SME Overview: ZA array vector access](https://developer.arm.com/documentation/109246/latest/SME-Overview/SME-ZA-storage/ZA-array-vector-access-and-ZA-tile-mapping) | [SME Programmer's Guide v1.0 Non-Confidential](https://documentation-service.arm.com/static/664f013638084307512bb30c) | arm-verify | 2026-04-12 |
| 6. Level 1: existing SVE2 code | Runs unchanged in non-streaming mode; no SME2 gain unless code targets streaming mode | [Arm Community Blog: SME Introduction](https://developer.arm.com/community/arm-community-blogs/b/architectures-and-processors-blog/posts/arm-scalable-matrix-extension-introduction) | [LLVM Issue #86743: SVE code generation in SME](https://github.com/llvm/llvm-project/issues/86743) | arm-verify | 2026-04-12 |
| 7. Level 2: KleidiAI auto-dispatch | Framework calls KleidiAI → KRT detects HWCAP2_SME2 → dispatches SME2 kernel | [KleidiAI GitHub: README and auto-dispatch behavior](https://github.com/ARM-software/kleidiai) | [Arm Developer Blog: ExecutorTorch 1.0 with SME2 optimizations](https://developer.arm.com/community/arm-community-blogs/b/ai-blog/posts/executorch-1-0-is-here-and-with-sme2-optimizations-through-kleidiai) | arm-verify | 2026-04-12 |
| 9. Level 3: explicit SME2 programming | Requires streaming mode management, ZA setup, SME2 intrinsics | [Arm Learning Path: Streaming mode and ZA state](https://learn.arm.com/learning-paths/cross-platform/multiplying-matrices-with-sme2/3-streaming-mode/) | [Arm ACLE: SME2 intrinsics and __arm_streaming attributes](https://arm-software.github.io/acle/main/acle.html) | arm-verify | 2026-04-12 |

---

## Notes

**Claim #8** (~95% coverage of production ML inference workloads) remains **LOW confidence** — no primary source found. Searched multiple KleidiAI documentation sources and Arm blogs; this claim appears to be marketing-level assertion without backing in public technical documentation. **NOT INDEPENDENTLY VERIFIED**. Remains in topic file as LOW confidence only.

All HIGH-confidence claims (1-7, 9) verified against ≥2 independent primary sources: official Arm architecture manuals (ddi0616, ddi0602), compiler documentation (101754), LLVM/GCC toolchain reviews, Linux kernel ELF hwcaps documentation, and official Arm learning paths and programmer guides.

---

## Verification methodology

- Claims sourced from official Arm Architecture Reference Manual (primary source)
- Cross-referenced with compiler toolchain documentation (GCC, LLVM/Clang)
- HWCAP detection verified against Linux kernel documentation and userspace API specs
- Streaming mode, ZA, and intrinsics verified via Arm learning paths and SME Programmer's Guide
- KleidiAI claims verified from official GitHub repository and Arm Developer blog posts
- Claim #8 not promoted: no peer-reviewed publication or official Arm claim found in public sources
