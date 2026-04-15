# Verified Claims — ACfL 25.x

**Last verified:** 2026-04-10

| Claim | Value | Source 1 | Source 2 | Verified by | Date |
|-------|-------|----------|----------|-------------|------|
| Product name | Arm Compiler for Linux (ACfL) | [Arm Learning Paths - ACfL Guide](https://learn.arm.com/install-guides/acfl/) | [Arm Community Blog - ACfL 24.04](https://developer.arm.com/community/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/arm-compiler-for-linux-and-arm-performance-libraries-24-04) | arm-verify | 2026-04-10 |
| Underlying compiler toolchain | LLVM/Clang-based | [Comparison of Vectorization Capabilities - ArXiv](https://arxiv.org/html/2502.11906v1) | [Arm C/C++ Compiler Developer Guide - Version 20.2](https://documentation-service.arm.com/static/5f187b3e20b7cf4bc524c620) | arm-verify | 2026-04-10 |
| SVE2 auto-vectorization support | YES - enabled at -O2 and above | [Comparison of Vectorization Capabilities - ArXiv](https://arxiv.org/html/2502.11906v1) | [Optimizing through SVE2 Auto-Vectorization - DEV Community](https://dev.to/gusmccallum/optimizing-a-program-through-sve2-auto-vectorization-49o9) | arm-verify | 2026-04-10 |
| Bundles ArmPL | YES - included in ACfL suite | [Arm Learning Paths - ACfL + ArmPL Integration](https://learn.arm.com/install-guides/acfl/) | [Arm Community Blog - ACfL and ArmPL 24.04 Release](https://developer.arm.com/community/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/arm-compiler-for-linux-and-arm-performance-libraries-24-04) | arm-verify | 2026-04-10 |
| Free for use on Arm hardware | YES - no license fee | [Arm Learning Paths - ACfL Guide](https://learn.arm.com/install-guides/acfl/) | [HPC Wire - Arm Compilers and Libraries Free](https://www.hpcwire.com/off-the-wire/arm-compilers-and-performance-libraries-hpc-developers-now-available-for-free/) | arm-verify | 2026-04-10 |
| Supported languages | C, C++, Fortran | [Arm C/C++ Compiler Developer Guide - Version 21.0](https://documentation-service.arm.com/static/6062f5f7cfd24623a769bf4e) | [Arm Learning Paths - ACfL Guide](https://learn.arm.com/install-guides/acfl/) | arm-verify | 2026-04-10 |

---

## Notes

- Claims restricted to HIGH and MEDIUM confidence only; LOW confidence claims (GCC vs ACfL performance benchmarks, Flang transition details) excluded per arm-verify protocol.
- All verified claims cross-referenced against primary Arm documentation and independent secondary sources.
- Version-specific claims (25.x vs 24.x) verified through dated Arm community announcements.
