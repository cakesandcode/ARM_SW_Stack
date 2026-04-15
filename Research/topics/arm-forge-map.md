# Arm Forge MAP

**Slug:** arm-forge-map  
**Created:** 2026-04-10  
**Last updated:** 2026-04-10  
**Linked posts:** [Post 2 · Building Your Arm HPC Stack]  
**Status:** ACTIVE

---

## Summary

Arm MAP (Arm Performance Reports' sampling profiler) is a low-overhead profiler designed for HPC workloads on Arm processors. Originally shipped by Allinea (acquired by Arm in 2016), MAP is now maintained by Linaro (which acquired the Arm Forge business in January 2023). MAP uses statistical sampling to profile C, C++, Fortran, and Python applications with typical 5% runtime overhead. On Neoverse clusters, MAP reveals CPU time, MPI communication, I/O, and thread activity across thousands of MPI ranks. It integrates with standard job schedulers (Slurm, HPE Cray) and is essential for understanding bottlenecks in scalable HPC codes before deeper analysis.

---

## Key Facts

| # | Claim | Value | Source | Confidence | Date verified |
|---|-------|-------|--------|------------|---------------|
| 1 | Current version | Linaro Forge 25.1.2 (latest as of April 2026) | [Linaro Forge Release History](https://www.linaroforge.com/release-history) | HIGH | 2026-04-10 |
| 2 | MAP component version | Included in Linaro Forge; no separate version number | [Linaro Forge 25.1 Blog](https://www.linaro.org/blog/whats-new-in-linaro-forge-25-1/) | HIGH | 2026-04-10 |
| 3 | Licensing model pre-2023 | Allinea DDT/MAP required commercial license (workstation, evaluation, floating license) | [Allinea Arm Acquisition – TOP500](https://www.top500.org/news/arm-buys-hpc-software-toolmaker-allinea/) | HIGH | 2026-04-10 |
| 4 | Allinea acquisition date | Arm acquired Allinea Software in December 2016 | [Design & Reuse News](https://www.design-reuse.com/news/3275-arm-extends-hpc-offering-with-acquisition-of-software-tools-provider-allinea-software/) | HIGH | 2026-04-10 |
| 5 | Linaro acquisition date | Linaro acquired Arm Forge from Arm in January 2023, rebranding to Linaro Forge/Linaro MAP | [Allinea Documentation at University of Notre Dame](https://docs.crc.nd.edu/general_pages/a/arm.html) | HIGH | 2026-04-10 |
| 6 | Current licensing | Commercial: workstation, floating, evaluation licenses; 2-week free trial with 32 MPI rank limit | [Workstation and Evaluation Licenses – Arm Developer](https://developer.arm.com/documentation/101136/latest/Arm-Forge/Licensing/Workstation-and-evaluation-licenses) | HIGH | 2026-04-10 |
| 7 | Community edition status | NO free community edition exists; licensing required for production use | [Linaro Forge Store](https://developer.arm.com/tools-and-software/server-and-hpc/downloads/arm-forge) | HIGH | 2026-04-10 |
| 8 | Sampling technology | Adaptive sampling; typical overhead 5% even for large-scale jobs with 1000s of MPI processes | [Linaro MAP Overview](https://www.linaroforge.com/linaro-map/) | HIGH | 2026-04-10 |
| 9 | Metrics captured | CPU time (instruction breakdown on x86_64); MPI time (MPI_Send, MPI_Reduce, MPI_Barrier, etc.); I/O time; thread activity; memory usage | [NERSC MAP Documentation](https://docs.nersc.gov/tools/performance/map/) | HIGH | 2026-04-10 |
| 10 | Sampling interval | NOT FOUND — hardware-dependent; controlled via perf PMU events configurable per architecture | [HPC Wiki Runtime Profiling](https://hpc-wiki.info/hpc/Runtime_profiling) | LOW | 2026-04-10 |
| 11 | Launch command (serial/OpenMP) | `map --profile ./myapp` or `map --profile ./myapp arg1 arg2` | [NERSC MAP Documentation](https://docs.nersc.gov/tools/performance/map/) | HIGH | 2026-04-10 |
| 12 | Launch command (MPI, mpirun) | `map --profile mpirun -np 8 ./myapp` | [NEsi MPI Profiling Guide](https://nesi.github.io/perf-training/python-scatter/profiling-mpi-map) | HIGH | 2026-04-10 |
| 13 | Launch command (MPI, srun/Slurm) | `map --profile srun ./myapp` (map --profile precedes srun for MPI) | [Iowa State HPC Guides](https://www.hpc.iastate.edu/guides/using-ddt-parallel-debugger--map-profiler-and-performance-reports) | HIGH | 2026-04-10 |
| 14 | Report generation command | `perf-report myapp_1p_2026-04-10_14-30.map` generates txt/csv/html summary from .map file | [ARMPerfReports HPC Wiki](https://hpc-wiki.info/hpc/ARMPerfReports) | MEDIUM | 2026-04-10 |
| 15 | Performance Reports relationship | Arm Performance Reports (perf-report tool) uses same sampling backend as MAP; can summarize MAP .map files or run standalone | [Arm Developer – Summarizing MAP file](https://developer.arm.com/docs/101137/1912/summarizing-an-existing-map-file) | HIGH | 2026-04-10 |
| 16 | MAP vs perf difference | MAP: source-level line-by-line profiling, MPI/OpenMP awareness, 5% overhead, no instrumentation. Linux perf: system-wide sampling, limited MPI/OpenMP support, no source lines visible | [Red Hat perf vs gprof blog](https://www.redhat.com/en/blog/perf-vs-gprofng) + [HPC Wiki](https://hpc-wiki.info/hpc/Runtime_profiling) | HIGH | 2026-04-10 |
| 17 | MAP vs gprof difference | MAP: sampling, low overhead, OpenMP/MPI aware. gprof: instrumentation-based, high overhead on non-trivial apps, no thread/MPI support | [HPC Wiki Runtime Profiling](https://hpc-wiki.info/hpc/Runtime_profiling) | HIGH | 2026-04-10 |
| 18 | Neoverse V3 support | NOT CONFIRMED in release notes. Statistical Profiling Extension (SPE) available on Neoverse cores (V1, N1 confirmed); V3/N3 require explicit verification | [Linaro SPE Prerequisites 25.0](https://docs.linaroforge.com/25.0/html/forge/map/spe_profiling/prerequisites.html) | LOW | 2026-04-10 |
| 19 | Neoverse N3 support | NOT CONFIRMED in release notes. Tooling updates mentioned for N3 in Arm Dec 2025/Jan 2026 innovations; no explicit MAP/Forge N3 claim found | [Arm Newsroom – Innovations Dec 2025/Jan 2026](https://newsroom.arm.com/blog/arm-innovations-from-dec-2025-jan-2026) | LOW | 2026-04-10 |
| 20 | Slurm integration version | Slurm 2.6.3+ required for Performance Reports; MAP integrates via standard srun + map --profile wrapper | [Iowa State HPC Guides](https://www.hpc.iastate.edu/guides/using-ddt-parallel-debugger--map-profiler-and-performance-reports) | MEDIUM | 2026-04-10 |
| 21 | Slurm GUI template | Forge provides submission template at `/shared/hpc/arm/forge/templates/slurm.qtf` for GUI-based job submission | [Princeton RCI MAP Guide](https://researchcomputing.princeton.edu/support/knowledge-base/map) | MEDIUM | 2026-04-10 |
| 22 | Output file format | .map binary file (subscript: appname_#p_YYYY-MM-DD_HH-MM.map where #p = process count) | [Linaro Forge 25.0 Docs](https://docs.linaroforge.com/25.0.2/html/forge/map/get_started_map/profile_a_program.html) | HIGH | 2026-04-10 |
| 23 | GUI profiling interface | Arm Forge GUI (DDT/MAP frontend); Linaro Forge maintains GUI for visualization and deep analysis | [Linaro Forge Product Page](https://www.linaroforge.com/linaro-map/) | HIGH | 2026-04-10 |
| 24 | MPI rank limit warning | MAP can profile up to 2048 MPI tasks; PMPI wrapper conflicts may occur if app also uses PMPI profiling | [Linaro Forge 25.1 Documentation](https://docs.linaroforge.com/25.1/html/forge/map/get_started_map/prepare_a_program_for_profiling.html) | HIGH | 2026-04-10 |

---

## Version / Release State

- **Current version:** Linaro Forge 25.1.2 (April 2026)
- **Latest stable:** 25.1.1, 25.0.4 also current
- **MAP component:** Included in Linaro Forge; no separate versioning
- **Release date (25.1):** Early 2026
- **Deprecation status:** NONE (Allinea branding deprecated; renamed to Linaro Forge Jan 2023)
- **Key updates in 25.1:** Memory overhead reduction, AMD rocprofiler-sdk support, Slurm 25.05.4 support, Python 3.14 support, Linux kernel 6.18 PMU events
- **Next known release:** Linaro Forge 25.2 (anticipated late 2026)

---

## Open Questions

- [ ] Exact sampling interval (µs or cycles per sample) — not documented as user-configurable parameter; hardware PMU dependent
- [ ] Explicit Neoverse V3 SPE support — confirmed for V1/N1; V3/N3 support status NOT FOUND in public release notes
- [ ] Explicit Neoverse N3 SPE support — mentioned in tooling roadmap but no MAP-specific claim found
- [ ] GPU memory profiling accuracy on Arm GPUs — AMD GPU profiling added in 25.1 (rocprofiler-sdk); Arm GPU support unclear
- [ ] Free or reduced-cost licensing for academic research — only 2-week trial documented; no academic license tier confirmed
- [ ] MAP output file size for long-running jobs — "tens of megabytes" claimed; need empirical data for 72h+ runs at 10k+ ranks

---

## Update log

- 2026-04-10 · arm-research · Initial research and topic creation. Confirmed Linaro Forge 25.1.2 as current version; Neoverse V3/N3 support marked NOT FOUND pending release notes verification.
- 2026-04-13 · arm-update · checked 2026-04-13 — no change. Linaro Forge 25.1.2 confirmed as current version via docs.linaroforge.com. No 25.2 release found. Slurm 25.05.4 support and AMD rocprofiler-sdk in 25.1 confirmed. Neoverse V3/N3 explicit SPE support still NOT FOUND in public release notes.

---

## Notes for post author

1. **Version statement for Post 2:** As of April 2026, MAP is distributed as part of Linaro Forge 25.1. Do not refer to "Arm Forge" branding in new content—use "Linaro Forge MAP" or just "MAP" with attribution to Linaro.

2. **Licensing clarity:** The tool is NOT free. A 2-week eval is available, but production clusters require a license. Mention this early to set expectations for readers.

3. **Neoverse V3/N3 claim:** The research found no explicit confirmation of V3/N3 support in public Linaro Forge or Arm release notes as of April 2026. If the post asserts V3 support, cite the SPE documentation or file an update request with Linaro.

4. **MAP vs perf:** A key distinguishing factor for HPC audiences: MAP shows MPI call timing and thread imbalance; perf shows system-wide CPU events. Include this in the post's differentiation section.

5. **Command syntax:** The `map --profile` syntax is stable across Slurm/mpirun. Include a practical example with `srun` and show the generated .map file name format.

6. **Sampling overhead:** The 5% overhead claim is the headline for adoption; contrast with gprof's higher instrumentation overhead. Verify this holds on Neoverse V3 before publication.
