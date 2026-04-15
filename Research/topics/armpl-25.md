# ArmPL 25.x — Scope and Platform Support

**Slug:** armpl-25
**Created:** 2026-04-10
**Last updated:** 2026-04-10
**Linked posts:** [Post 1 · Layer 2 — HPC Math Libraries, Post 2 · HPC Compilers + Cluster]
**Status:** ACTIVE

---

## Summary
Arm Performance Libraries (ArmPL) 25.x is Arm's free, optimized BLAS/LAPACK/FFT/sparse library suite for Arm CPUs. It targets HPC workloads on Neoverse platforms and supports Linux, macOS (Apple Silicon), and Windows on Arm. ArmPL is a direct replacement for MKL on x86 HPC clusters migrating to Arm. It is a free download; no license fee.

---

## Key Facts

| # | Claim | Value | Source | Confidence | Date verified |
|---|-------|-------|--------|------------|---------------|
| 1 | Product name | Arm Performance Libraries (ArmPL) | [https://developer.arm.com/Tools%20and%20Software/Arm%20Performance%20Libraries](https://developer.arm.com/Tools%20and%20Software/Arm%20Performance%20Libraries) | HIGH | 2026-04-10 |
| 2 | Current major version | 25.x | [https://developer.arm.com/Tools%20and%20Software/Arm%20Performance%20Libraries](https://developer.arm.com/Tools%20and%20Software/Arm%20Performance%20Libraries) | MEDIUM | 2026-04-10 |
| 3 | License | Free download, no license fee | [https://developer.arm.com/Tools%20and%20Software/Arm%20Performance%20Libraries](https://developer.arm.com/Tools%20and%20Software/Arm%20Performance%20Libraries) | HIGH | 2026-04-10 |
| 4 | Included components | BLAS, LAPACK, FFT, sparse solvers | [https://developer.arm.com/Tools%20and%20Software/Arm%20Performance%20Libraries](https://developer.arm.com/Tools%20and%20Software/Arm%20Performance%20Libraries) | HIGH | 2026-04-10 |
| 5 | Supported OS | Linux (Neoverse), macOS (Apple Silicon), Windows on Arm | [https://developer.arm.com/Tools%20and%20Software/Arm%20Performance%20Libraries](https://developer.arm.com/Tools%20and%20Software/Arm%20Performance%20Libraries) | HIGH | 2026-04-10 |
| 6 | SME2 BLAS optimization approach | ArmPL relies on compiler vectorization + SVE/SVE2 microkernels; SME2 explicit kernels in development via KleidiAI/XNNPACK for AI, not yet in core BLAS | [https://developer.arm.com/community/arm-community-blogs/b/ai-blog/posts/executorch-1-0-is-here-and-with-sme2-optimizations-through-kleidiai](https://developer.arm.com/community/arm-community-blogs/b/ai-blog/posts/executorch-1-0-is-here-with-sme2-optimizations-through-kleidiai), [https://arxiv.org/pdf/2512.21473](https://arxiv.org/pdf/2512.21473) | MEDIUM | 2026-04-10 |
| 7 | Performance vs MKL on Neoverse | ArmPL DGEMM: 95% peak single-core, 90% peak parallel on ThunderX2 (v19.0); Pardiso sparse 5x faster than MKL on Neoverse V1; no Neoverse V3 head-to-head benchmark found | [https://developer.arm.com/community/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/pardiso-sparse-linear-solver-on-arm](https://developer.arm.com/community/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/pardiso-sparse-linear-solver-on-arm) | MEDIUM | 2026-04-10 |
| 8 | ArmPL 25.x minor version | 25.04.1 (June 17, 2025) and 25.07 available by Sept 2025 | [https://community.arm.com/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/arm-performance-libraries-25-04-and-arm-toolchain-for-linux-20-release](https://community.arm.com/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/arm-performance-libraries-25-04-and-arm-toolchain-for-linux-20-release), [https://medium.com/@tltyavuz/setting-up-arm-performance-libraries-armpl-in-a-petalinux-environment-from-scratch-to-execution-09c07d9eea60](https://medium.com/@tltyavuz/setting-up-arm-performance-libraries-armpl-in-a-petalinux-environment-from-scratch-to-execution-09c07d9eea60) | HIGH | 2026-04-10 |
| 9 | OpenMP threading model | ArmPL built with OpenMP; uses system OpenMP runtime (GCC libgomp / LLVM libomp); offers -seq and -omp variants; adaptive thread usage (1 thread for small matrices) | [https://developer.arm.com/documentation/102580/latest/Set-the-number-of-OpenMP-threads](https://developer.arm.com/documentation/102580/latest/Set-the-number-of-OpenMP-threads), [https://learn.arm.com/install-guides/armpl/](https://learn.arm.com/install-guides/armpl/) | HIGH | 2026-04-10 |
| 10 | LAPACK/FFT coverage | LAPACK 3.12.0 (as of 25.x); full FFTW API support for in/out-of-place real and complex FFTs; detailed routine index in reference manual | [https://developer.arm.com/documentation/101004/latest/](https://developer.arm.com/documentation/101004/latest/) | MEDIUM | 2026-04-10 |

---

## Version / Release State

- Current version: 25.04.1 (June 17, 2025); 25.07 available by Sept 2025
- Release date: 25.04 released June 17, 2025 (per Arm Community blog); 25.07 release date NOT FOUND
- Deprecation status: NONE
- Next known release: Unknown (no 25.10 or 26.x announced)

---

## Open questions

- [x] Claim #6: **RESOLVED** — ArmPL 25.x BLAS relies on compiler vectorization + hand-tuned SVE/SVE2 microkernels. SME2 explicit optimization is in development (via KleidiAI/XNNPACK for AI frameworks) but not yet in core BLAS routines. Sources: ExecuTorch blog post, arxiv paper on SME GEMM optimization.
- [x] Claim #7: **PARTIALLY RESOLVED** — Found historical benchmark: Pardiso (sparse solver) 5x faster than MKL on Neoverse V1. No Neoverse V3 head-to-head ArmPL vs MKL benchmark found in HPCwire, Moor Insights, or analyst reports. Requires further search or direct contact with Arm.
- [x] Claim #8: **RESOLVED** — ArmPL 25.04.1 released June 17, 2025; version 25.07 available by Sept 2025 (exact release date NOT FOUND).
- [x] Claim #9: **RESOLVED** — ArmPL uses system OpenMP runtime (GCC libgomp or LLVM libomp). Library variants: -seq (sequential) and -omp (OpenMP multi-threaded). Adaptive threading: uses 1 thread for small matrices.
- [ ] **NOT FOUND**: Exact release date for ArmPL 25.07 — requires verification from Arm developer website or release notes.

---

## Update log
- 2026-04-10 · corpus-seed · Initial entry. Claims #6 and #7 LOW — no benchmarks found yet.
- 2026-04-10 · arm-research · Filled open questions via 8 independent web searches. Resolved version (25.04.1 June 2025, 25.07 by Sept), OpenMP model (system runtime), SME2 approach (compiler vectorization + SVE/SVE2 kernels for BLAS; SME2 in KleidiAI for AI frameworks). Found partial benchmark (Pardiso 5x vs MKL on V1, no V3 data). LAPACK 3.12, full FFTW support confirmed. Sources: Arm blogs, arxiv papers, GitHub, learn.arm.com. Egress blocks prevented access to official release notes PDFs.

## Update — 2026-04-13 (arm-update)
**Trigger:** New release — ArmPL 26.01 confirmed available as of April 2026.
**Change:** ArmPL 26.01 is now the current major version, superseding 25.04.1 and 25.07. Version 26.01 is available as a Debian package and confirmed compatible with macOS (macOS >= 10.15). Build tested with GCC 14, LLVM 21.1, and NVHPC 25.11.
**Affected claims:** #2 (current major version — was 25.x, now 26.x), #8 (minor version — 25.04.1/25.07 superseded by 26.01)
**Action taken:** Update block appended; MODERATE alert raised. Post 2 cites ArmPL 25.x as the current version; 26.01 is now available and should be noted. Existing technical claims about library components (BLAS, LAPACK, FFT, sparse), OpenMP model, and SME2 approach are not contradicted by this release.
**Source:** [Arm Performance Libraries Downloads](https://developer.arm.com/tools-and-software/server-and-hpc/downloads/arm-performance-libraries) accessed 2026-04-13; Homebrew Formulae arm-performance-libraries (version 26.01 confirmed) accessed 2026-04-13
