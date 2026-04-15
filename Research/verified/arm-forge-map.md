# Verified Claims — Arm Forge MAP

**Last verified:** 2026-04-10

| Claim | Value | Source 1 | Source 2 | Verified by | Date |
|-------|-------|----------|----------|-------------|------|
| Linaro acquisition date | January 30, 2023 | [Linaro Newsroom - Arm Forge Acquisition](https://www.linaro.org/news/linaro-to-acquire-arm-forge-software-tools-business/) | [HPCwire - Linaro Acquires Arm Forge](https://www.hpcwire.com/off-the-wire/linaro-to-acquire-arm-forge-software-tools-business/) | arm-verify | 2026-04-10 |
| Arm acquisition of Allinea | December 2016 | [Design & Reuse News - Arm Allinea Acquisition](https://www.design-reuse.com/news/41116/arm-allinea-software-acquisition.html) | [BusinessWire - ARM Extends HPC with Allinea Acquisition](https://www.businesswire.com/news/home/20161215006575/en/ARM-Extends-HPC-Offering-with-Acquisition-of-Software-Tools-Provider-Allinea-Software) | arm-verify | 2026-04-10 |
| Current version (April 2026) | Linaro Forge 25.1.2 | [Linaro Forge 25.1.2 Documentation](https://docs.linaroforge.com/25.1.2/html/forge/forge/introduction_to_forge/map.html) | [Linaro Forge Blog - What's New in 25.1](https://www.linaro.org/blog/whats-new-in-linaro-forge-25-1/) | arm-verify | 2026-04-10 |
| Sampling profiler technology | Adaptive sampling with typical 5% runtime overhead | [Linaro MAP Overview](https://www.linaroforge.com/linaro-map/) | [Linaro Forge 25.1 Documentation - Performance Impact](https://docs.linaroforge.com/25.1.1/html/forge/map/cuda_profiling/performance_impact.html) | arm-verify | 2026-04-10 |
| Metrics captured | CPU time, MPI time, I/O time, thread activity, memory usage | [NERSC MAP Documentation](https://docs.nersc.gov/tools/performance/map/) | [Linaro MAP Overview - Capabilities](https://www.linaroforge.com/linaro-map/) | arm-verify | 2026-04-10 |
| Output file format | .map binary (appname_#p_YYYY-MM-DD_HH-MM.map) | [Linaro Forge 25.0 Documentation - Profile Output](https://docs.linaroforge.com/25.0.2/html/forge/map/get_started_map/profile_a_program.html) | [Linaro Forge 25.1.2 Documentation - Output Files](https://docs.linaroforge.com/25.1.2/html/forge/forge/map/get_started_map/profile_a_program.html) | arm-verify | 2026-04-10 |
| Slurm integration | MAP integrates via srun with map --profile wrapper | [Iowa State HPC Guides - Slurm and MAP](https://www.hpc.iastate.edu/guides/using-ddt-parallel-debugger--map-profiler-and-performance-reports) | [LUMI Documentation - Slurm Distribution and Binding](https://docs.lumi-supercomputer.eu/runjobs/scheduled-jobs/distribution-binding/) | arm-verify | 2026-04-10 |
| MPI rank capacity | Up to 2048 MPI tasks profiled | [Linaro Forge 25.1 Documentation - MPI Preparation](https://docs.linaroforge.com/25.1/html/forge/map/get_started_map/prepare_a_program_for_profiling.html) | [NERSC MAP Documentation - MPI Support](https://docs.nersc.gov/tools/performance/map/) | arm-verify | 2026-04-10 |
| Licensing model | Commercial; 2-week free trial available | [Linaro Forge Store](https://www.linaroforge.com/linaro-map/) | [Iowa State HPC Guides - Licensing](https://www.hpc.iastate.edu/guides/using-ddt-parallel-debugger--map-profiler-and-performance-reports) | arm-verify | 2026-04-10 |

---

## Notes

- LOW confidence claims (Neoverse V3/N3 SPE support status, GPU memory profiling accuracy, academic licensing options) excluded per arm-verify protocol.
- Licensing transition from commercial (Allinea/Arm era) to Linaro management confirmed via two independent news sources.
- Versions 25.1.1, 25.0.4 confirmed as current alongside 25.1.2.
