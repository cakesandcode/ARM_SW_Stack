# Slurm Configuration on Neoverse N3/V3 Clusters

**Slug:** slurm-neoverse
**Created:** 2026-04-10
**Last updated:** 2026-04-10
**Linked posts:** [Post 2 · Building Your Arm HPC Stack: Compilers, Math Libraries, and Cluster Tools]
**Status:** ACTIVE

---

## Summary

Slurm (Simple Linux Utility for Resource Management) on Arm Neoverse-based clusters requires careful configuration of CPU affinity, NUMA topology binding, and task plugins to achieve performance comparable to x86 HPC systems. This topic covers Slurm 25.x deployment on Neoverse N3/V3 clusters, including TaskPlugin selection, optimal `--cpu-bind` and `--mem-bind` flag usage, integration with Arm compilers (ACfL, ArmPL), and MPI launcher configuration (OpenMPI 5.x with PMIx). Key differences from x86 deployments include explicit NUMA-aware binding on multi-socket Neoverse V3 designs, environment module setup for Arm-compiled libraries, and testing of job submission scripts on first deployment.

---

## Key Facts

| # | Claim | Value | Source | Confidence | Date verified |
|---|-------|-------|--------|------------|---------------|
| 1 | Current Slurm stable version | 25.11 | [https://slurm.schedmd.com/release_notes.html](https://slurm.schedmd.com/release_notes.html) | HIGH | 2026-04-10 |
| 2 | Slurm no Arm-specific patches required in 25.x | Neoverse N/V cores supported natively via CPU features (neoverse_n1, neoverse_v2 constraints available) | [https://slurm.schedmd.com/documentation.html](https://slurm.schedmd.com/documentation.html) | MEDIUM | 2026-04-10 |
| 3 | Recommended TaskPlugin config | TaskPlugin=task/affinity,task/cgroup (with cgroup/v2) | [https://slurm.schedmd.com/cpu_management.html](https://slurm.schedmd.com/cpu_management.html) | HIGH | 2026-04-10 |
| 4 | Deprecated TaskPlugin | cgroup/v1 — migration to cgroup/v2 recommended | [https://slurm.schedmd.com/cgroups.html](https://slurm.schedmd.com/cgroups.html) | HIGH | 2026-04-10 |
| 5 | Neoverse V3 CSS max cores per socket | 128 cores (dual 64-core clusters on single socket) | [https://www.arm.com/products/neoverse-compute-subsystems/css-v3](https://www.arm.com/products/neoverse-compute-subsystems/css-v3) | HIGH | 2026-04-10 |
| 6 | Neoverse N3 CSS cores per cluster | 32 cores per compute subsystem (configurable 8–32) | [https://www.arm.com/products/silicon-ip-cpu/neoverse/neoverse-n3](https://www.arm.com/products/silicon-ip-cpu/neoverse/neoverse-n3) | HIGH | 2026-04-10 |
| 7 | NUMA topology: Neoverse V2 Grace CPU | 2 NUMA nodes (connected via NVLink C2C) with up to 144 cores total | [https://docs.nvidia.com/dccpu/grace-perf-tuning-guide/index.html](https://docs.nvidia.com/dccpu/grace-perf-tuning-guide/index.html) | HIGH | 2026-04-10 |
| 8 | Optimal binding pattern for NUMA | `--cpu-bind=mask_cpu` or `--cpu-bind=map_cpu` + `--mem-bind=local` to keep tasks and memory on same NUMA node | [https://slurm.schedmd.com/resource_binding.html](https://slurm.schedmd.com/resource_binding.html) | HIGH | 2026-04-10 |
| 9 | NUMA performance drop threshold | When thread count exceeds cores in one NUMA node, significant cross-NUMA latency observed | [https://developer.arm.com/community/arm-community-blogs/b/ai-blog/posts/introduce-the-cross-numa-problem-and-optimization-in-llama-cpp-with-llama3-model-running-in-neoverse-n2](https://developer.arm.com/community/arm-community-blogs/b/ai-blog/posts/introduce-the-cross-numa-problem-and-optimization-in-llama-cpp-with-llama3-model-running-in-neoverse-n2) | HIGH | 2026-04-10 |
| 10 | AWS Graviton4 NUMA config | Dual-socket NUMA (first Graviton generation with 2-socket support) | [https://aws.github.io/graviton/](https://aws.github.io/graviton/) | HIGH | 2026-04-10 |
| 11 | AWS Graviton3E (HPC7g) NUMA config | Single NUMA domain (all 64 cores in one node) | [https://aws.amazon.com/ec2/instance-types/hpc7g/](https://aws.amazon.com/ec2/instance-types/hpc7g/) | HIGH | 2026-04-10 |
| 12 | Azure Cobalt 100 architecture | 128 Neoverse N2 cores, dual-socket, 12×DDR5 channels, 3.4 GHz | [https://learn.microsoft.com/en-us/azure/virtual-machines/sizes/cobalt-overview](https://learn.microsoft.com/en-us/azure/virtual-machines/sizes/cobalt-overview) | HIGH | 2026-04-10 |
| 13 | OpenMPI 5.0.x with Slurm requirement | Slurm 22.05+ required for PMIx support (v2.x–v5.x compatible) | [https://docs.open-mpi.org/en/v5.0.x/launching-apps/slurm.html](https://docs.open-mpi.org/en/v5.0.x/launching-apps/slurm.html) | HIGH | 2026-04-10 |
| 14 | OpenMPI 5.0+ launch method | mpirun recommended over direct srun launch; PMI-2 not supported | [https://docs.open-mpi.org/en/v5.0.x/launching-apps/pmix-and-prrte.html](https://docs.open-mpi.org/en/v5.0.x/launching-apps/pmix-and-prrte.html) | HIGH | 2026-04-10 |
| 15 | ACfL environment module setup | Load modules in sbatch script, not ~/.bashrc; path format: `/opt/arm/modulefiles` | [https://learn.arm.com/install-guides/acfl/](https://learn.arm.com/install-guides/acfl/) | HIGH | 2026-04-10 |
| 16 | ACfL + OpenMPI integration | Must recompile OpenMPI with ACfL if using libfabric-aws; update PATH and LD_LIBRARY_PATH in job script | [https://aws.amazon.com/blogs/hpc/best-practices-for-running-molecular-dynamics-simulations-on-aws-graviton3e/](https://aws.amazon.com/blogs/hpc/best-practices-for-running-molecular-dynamics-simulations-on-aws-graviton3e/) | MEDIUM | 2026-04-10 |
| 17 | MpiDefault config in slurm.conf | Set `MpiDefault=pmix` for modern Arm clusters (enables PMIx plugin, required for OpenMPI 5.x) | [https://slurm.schedmd.com/mpi_guide.html](https://slurm.schedmd.com/mpi_guide.html) | HIGH | 2026-04-10 |
| 18 | CPU affinity verbose testing | Use `--cpu-bind=verbose,none --mem-bind=verbose,none` with srun to test binding without enforcing | [https://docs.lumi-supercomputer.eu/runjobs/scheduled-jobs/distribution-binding/](https://docs.lumi-supercomputer.eu/runjobs/scheduled-jobs/distribution-binding/) | MEDIUM | 2026-04-10 |
| 19 | AWS ParallelCluster Slurm on Arm | Supported; migration effort mostly compiler recompilation for Arm; EFA (200Gbps peak) available on c7gn/hpc7g | [https://aws.amazon.com/blogs/compute/deploying-a-burstable-and-event-driven-hpc-cluster-on-aws-using-slurm-part-1/](https://aws.amazon.com/blogs/compute/deploying-a-burstable-and-event-driven-hpc-cluster-on-aws-using-slurm-part-1/) | MEDIUM | 2026-04-10 |
| 20 | Slurm security updates 2024–2025 | Versions 24.11.5, 24.05.8, 23.11.11, 25.05.2 include security fixes; CPU affinity features continue to evolve | [https://docs.aws.amazon.com/pcs/latest/userguide/slurm-versions.html](https://docs.aws.amazon.com/pcs/latest/userguide/slurm-versions.html) | MEDIUM | 2026-04-10 |

---

## Version / Release State

- **Current version:** 25.11 (latest stable)
- **Release date:** 2025 (6-month release cycle since 2024)
- **Deprecation status:** NONE (cgroup/v1 plugins deprecated; cgroup/v2 recommended)
- **Next known release:** 25.05.x series; 6-month cadence
- **Arm-specific notes:** No Arm-specific patches required; standard Slurm 25.x compiles natively on Arm with GCC or ACfL

---

## Open questions

- [ ] **Neoverse N3 NUMA domains per socket** — Arm documentation does not explicitly specify NUMA node count per N3 socket. CSS N3 supports 8–32 cores, but NUMA topology (1 node per 8 cores? 1 node per socket?) is NOT FOUND.
- [ ] **Neoverse V3 CSS NUMA topology** — V3 supports up to 128 cores per socket (2×64-core clusters), but whether these two clusters map to 2 separate NUMA nodes or 1 unified node is NOT FOUND. Critical for Slurm configuration.
- [ ] **ACfL/ArmPL + Slurm known issues** — No documented incompatibilities found, but integration patterns (especially for libfabric-aws) are sparse. Requires verification in production deployments.
- [ ] **Slurm task plugin performance on Neoverse** — task/affinity vs task/cgroup benchmarks on Arm HPC workloads are NOT FOUND. Recommendation is generic (both plugins together) rather than Arm-specific.
- [ ] **sbatch MPI example annotated for Neoverse** — Generic examples found (LUMI, JURECA, NERSC); Neoverse-specific annotated sbatch script with ACfL + OpenMPI + PMIx is NOT FOUND in official docs.

---

## Update log

- **2026-04-10 · arm-research agent · initial research and topic creation**
  - Conducted 11 independent web searches per protocol
  - Focused on Slurm 25.x, Neoverse N3/V3 specs, AWS Graviton4, Azure Cobalt 100
  - Identified 20 key facts with HIGH/MEDIUM confidence
  - Flagged 5 open questions requiring follow-up research

## Update — 2026-04-13 (arm-update)
**Trigger:** Patch releases for Slurm 25.11 published since Last updated date.
**Change:** Slurm 25.11.4 is now the current stable patch (released 2026-03-12), superseding 25.11.0. Patch releases 25.11.2 (2026-01-15), 25.11.3 (2026-02-19), and 25.11.4 (2026-03-12) issued — all are bug/security fixes with no functional change to Arm-relevant configuration claims. Slurm 26.05 is planned (v0.0.41 API endpoint removal announced for 26.05).
**Affected claims:** #1 (current stable version — was 25.11, now 25.11.4 patch; no claim is wrong)
**Action taken:** Update block appended; INFO alert raised. No Post 2 claim requires correction. Claim #1 should note 25.11.4 as current patch when revised.
**Source:** [SchedMD Release Announcements](https://www.schedmd.com/slurm-support/release-announcements/) accessed 2026-04-13
