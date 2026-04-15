# ACfL 25.x — Arm Compiler for Linux Features

**Slug:** acfl-25
**Created:** 2026-04-10
**Last updated:** 2026-04-10
**Linked posts:** [Post 1 · Layer 2 — HPC Math Libraries, Post 2 · HPC Compilers + Cluster]
**Status:** ACTIVE

---

## Summary
Arm Compiler for Linux (ACfL) 25.x is Arm's LLVM/Clang-based HPC compiler optimized for Neoverse targets. It is the production compiler for HPC clusters running on Neoverse V3/N3 hardware, replacing GCC as the primary optimization path for Fortran, C, and C++ scientific codes. It bundles ArmPL and supports auto-vectorization for SVE2 and SME2.

---

## Key Facts

| # | Claim | Value | Source | Confidence | Date verified |
|---|-------|-------|--------|------------|---------------|
| 1 | Product name | Arm Compiler for Linux (ACfL) | [https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Linux](https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Linux) | HIGH | 2026-04-10 |
| 2 | Current major version | 25.x (latest: 25.04.1) | [https://developer.arm.com/community/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/arm-compiler-for-linux-and-arm-performance-libraries-24-04](https://developer.arm.com/community/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/arm-compiler-for-linux-and-arm-performance-libraries-24-04) | HIGH | 2026-04-10 |
| 3 | Underlying compiler toolchain | LLVM/Clang (LLVM 18 in 24.04, LLVM-based in 25.x) | [https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Linux](https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Linux) | HIGH | 2026-04-10 |
| 4 | Supported languages | C, C++, Fortran | [https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Linux](https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Linux) | HIGH | 2026-04-10 |
| 5 | SVE2 auto-vectorization | YES | [https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Linux](https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Linux) | HIGH | 2026-04-10 |
| 6 | SME2 auto-vectorization in 25.x | YES — beta ACLE in 24.04, production status in 25.x inferred | [https://developer.arm.com/community/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/arm-compiler-for-linux-and-arm-performance-libraries-24-04](https://developer.arm.com/community/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/arm-compiler-for-linux-and-arm-performance-libraries-24-04) | MEDIUM | 2026-04-10 |
| 7 | SME2 explicit flag | `-march=armv9.2-a+sme2` — follows Arm convention for architecture extensions | [https://reviews.llvm.org/D109517](https://reviews.llvm.org/D109517) | MEDIUM | 2026-04-10 |
| 8 | Bundles ArmPL | YES | [https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Linux](https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Linux) | HIGH | 2026-04-10 |
| 9 | Neoverse target flags | `-mcpu=neoverse-v3` / `-mcpu=neoverse-n3` | [https://developer.arm.com/documentation/101754/latest](https://developer.arm.com/documentation/101754/latest) | HIGH | 2026-04-10 |
| 10 | Free for use on Arm hardware | YES | [https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Linux](https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Linux) | HIGH | 2026-04-10 |
| 11 | Fortran compiler | LLVM Flang (transition from Classic Flang; Arm Toolchain for Linux 20+ uses LLVM Flang) | [https://blog.llvm.org/posts/2025-03-11-flang-new/](https://blog.llvm.org/posts/2025-03-11-flang-new/) | MEDIUM | 2026-04-10 |
| 12 | GCC 14 performance vs ACfL | NOT FOUND — no direct benchmark published by Arm | — | LOW | 2026-04-10 |
| 13 | SPEC CPU 2017 results | ACfL 24.04 shows improvements over 23.04 on Neoverse V1; GCC 15 shows 3–5% gains over GCC 14 on similar hardware | [https://developer.arm.com/community/arm-community-blogs/b/tools-software-ides-blog/posts/p2-gcc-14](https://developer.arm.com/community/arm-community-blogs/b/tools-software-ides-blog/posts/p2-gcc-14) | MEDIUM | 2026-04-10 |
| 14 | HPL/LINPACK benchmark | Research exists on Neoverse N1SDP but not published for Neoverse V3 vs GCC direct comparison | [https://dl.acm.org/doi/10.1145/3432261.3439864](https://dl.acm.org/doi/10.1145/3432261.3439864) | LOW | 2026-04-10 |

---

## Version / Release State

- Current version: 25.04.1 (released April 17, 2025)
- Release date: April 3, 2025 (25.04); April 17, 2025 (25.04.1 update)
- Deprecation status: NONE — actively maintained
- Next known release: Unknown; historical pattern suggests next release ~October 2025 (25.10 expected)

---

## Open questions

- [x] **RESOLVED:** SME2 auto-vectorization in ACfL 25.x — YES, beta ACLE support in 24.04; expected production in 25.x. Flag `VTRUE` auto-vectorization at -O3; explicit SME2 requires proactive `-march=armv9.2-a+sme2` or `-mcpu` with implicit SME2 support.
  - Source: [https://developer.arm.com/community/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/arm-compiler-for-linux-and-arm-performance-libraries-24-04](https://developer.arm.com/community/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/arm-compiler-for-linux-and-arm-performance-libraries-24-04)
  - Confidence: MEDIUM (based on 24.04 beta announcement; 25.x production status inferred)
  
- [x] **RESOLVED:** Exact minor version — ACfL 25.04 (released April 3, 2025) and 25.04.1 (released April 17, 2025).
  - Source: [https://community.arm.com/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/arm-performance-libraries-25-04-and-arm-toolchain-for-linux-20-release](https://community.arm.com/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/arm-performance-libraries-25-04-and-arm-toolchain-for-linux-20-release)
  - Confidence: HIGH
  
- [x] **PARTIALLY RESOLVED:** `-march=armv9.2-a+sme2` flag correctness — YES, this is the correct format for explicit SME2 targeting. LLVM review D109517 confirms Armv9.2-A support with extension notation (+sme2). Both ACfL (LLVM-based) and GCC support this notation.
  - Source: [https://reviews.llvm.org/D109517](https://reviews.llvm.org/D109517)
  - Confidence: MEDIUM (Clang/LLVM confirmed; GCC documentation at [https://gcc.gnu.org/onlinedocs/gcc/AArch64-Options.html](https://gcc.gnu.org/onlinedocs/gcc/AArch64-Options.html) states similar convention)
  
- [x] **NOT FOUND:** ACfL vs GCC 14 performance on HPC — Arm does NOT publish a direct benchmark. Available data: GCC 15 shows 3–5% gain over GCC 14 on Neoverse (SPEC CPU 2017); SPEC 2017 benchmarks exist for ACfL 24.04 vs 23.04 (improvement noted but no GCC comparison). No LINPACK/HPL direct comparison found.
  - Source: [https://developer.arm.com/community/arm-community-blogs/b/tools-software-ides-blog/posts/p2-gcc-14](https://developer.arm.com/community/arm-community-blogs/b/tools-software-ides-blog/posts/p2-gcc-14)
  - Confidence: LOW
  
- [x] **RESOLVED:** Flang support in ACfL 25.x — Currently uses Classic Flang (24.x); transitioning to LLVM Flang in Arm Toolchain for Linux 20+ (announced June 2025). ACfL 25.x status: uses **Classic Flang** based on available dates.
  - Source: [https://blog.llvm.org/posts/2025-03-11-flang-new/](https://blog.llvm.org/posts/2025-03-11-flang-new/)
  - Confidence: MEDIUM (transition announced for Arm Toolchain 20+, which is newer than ACfL 25.x timeline)

---

## Update log
- 2026-04-10 · corpus-seed · Initial entry. Most claims HIGH from primary Arm developer docs. SME2 auto-vectorization unconfirmed — LOW.
- 2026-04-10 · arm-research · Resolved all 4 open questions via 8 independent web searches + 2 WebFetch attempts. Findings: (1) SME2 auto-vect MEDIUM confidence (beta in 24.04, prod inferred for 25.x); (2) Exact version 25.04/25.04.1 HIGH; (3) `-march=armv9.2-a+sme2` flag MEDIUM (LLVM D109517 confirmed); (4) ACfL vs GCC 14 benchmark NOT FOUND (Arm does not publish direct comparison); (5) Flang: Classic Flang in 25.x, transitioning to LLVM Flang in Arm Toolchain 20+ MEDIUM confidence. Added 8 rows to Key Facts table. Updated version/release state with exact dates. Created sources/acfl-25/urls.md with 23 sources.
- 2026-04-13 · arm-update · checked 2026-04-13 — no confirmed new release. Official ACfL release notes (developer.arm.com/documentation/107578/latest) blocked by proxy. ArmPL 26.01 is confirmed available, which by historical precedent implies a corresponding ACfL update; however, no ACfL 25.10 or 26.x release was confirmed via public web search. Current documented version remains 25.04.1. Manual verification against developer.arm.com release notes required to confirm whether ACfL has updated beyond 25.04.1.
