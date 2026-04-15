# Verified Claims — Slurm Configuration on Neoverse N3/V3 Clusters

**Last verified:** 2026-04-10

| Claim | Value | Source 1 | Source 2 | Verified by | Date |
|-------|-------|----------|----------|-------------|------|
| Current Slurm stable version | 25.11 (latest: 25.11.2) | [SchedMD Release Announcements](https://www.schedmd.com/slurm-version-25-11-1-is-now-available/) | [AWS PCS - Slurm Versions](https://docs.aws.amazon.com/pcs/latest/userguide/slurm-versions.html) | arm-verify | 2026-04-10 |
| Recommended TaskPlugin config | task/affinity,task/cgroup (with cgroup/v2) | [Slurm CPU Management Guide](https://slurm.schedmd.com/cpu_management.html) | [CoreWeave - Task Plugins](https://docs.coreweave.com/docs/products/sunk/development-on-slurm/task-plugins) | arm-verify | 2026-04-10 |
| Cgroup v1 deprecation status | DEPRECATED; migration to cgroup/v2 recommended | [Slurm Cgroups Guide](https://slurm.schedmd.com/cgroups.html) | [Slurm Cgroup v2 Plugin Documentation](https://slurm.schedmd.com/cgroup_v2.html) | arm-verify | 2026-04-10 |
| Neoverse V3 CSS max cores per socket | 128 cores (dual 64-core clusters per socket) | [TechRadar - Neoverse V3 Analysis](https://www.techradar.com/pro/arms-new-super-powerful-neoverse-v3-cpu-core-obliterates-previous-generation-and-should-get-intel-and-amd-worried-hbm-and-cxl-support-128-cores-per-socket-hyperscalers-will-be-salivating) | [Tom's Hardware - Neoverse V3 Review](https://www.tomshardware.com/pc-components/cpus/arm-unveils-next-gen-neoverse-cpu-cores-and-compute-subsystems-hoping-to-entice-more-custom-silicon-customers) | arm-verify | 2026-04-10 |
| Neoverse N3 CSS cores per cluster | 32 cores per compute subsystem (configurable 8–32) | [Arm Product Page - Neoverse N3](https://www.arm.com/products/silicon-ip-cpu/neoverse/neoverse-n3) | [AnandTech - Neoverse V3 and N3 Announcement](https://www.anandtech.com/show/21270/arm-announces-neoverse-v3-and-n3-cpu-cores) | arm-verify | 2026-04-10 |
| NUMA topology: Azure Cobalt 100 | 128 Neoverse N2 cores, dual-socket, 12×DDR5 channels, 3.4 GHz | [servethehome - Azure Cobalt 100 Launch](https://www.servethehome.com/microsoft-azure-cobalt-100-128-core-arm-neoverse-n2-cpu-launched/) | [Microsoft Learn - Cobalt Overview](https://learn.microsoft.com/en-us/azure/virtual-machines/sizes/cobalt-overview) | arm-verify | 2026-04-10 |
| AWS Graviton4 NUMA config | Dual-socket NUMA (192 cores at 2.8 GHz) | [Arm Community Blog - Graviton4 HPC Performance](https://developer.arm.com/community/arm-community-blogs/b/servers-and-cloud-computing-blog/posts/leading-hpc-performance-with-graviton4) | [Chips and Cheese - Neoverse V2 in Graviton4](https://chipsandcheese.com/p/arms-neoverse-v2-in-awss-graviton-4) | arm-verify | 2026-04-10 |
| AWS Graviton3E (HPC7g) NUMA config | Single NUMA domain (64 cores) | [AWS Blog - Graviton3E HPC Instances](https://aws.amazon.com/blogs/hpc/application-deep-dive-into-the-graviton3e-based-amazon-ec2-hpc7g-instance/) | [AWS EC2 Instance Types - HPC7g](https://aws.amazon.com/ec2/instance-types/hpc7g/) | arm-verify | 2026-04-10 |
| NVIDIA Grace CPU NUMA topology | 2 NUMA nodes (connected via NVLink C2C) with 144 cores total | [NVIDIA Grace Performance Tuning Guide](https://docs.nvidia.com/dccpu/grace-perf-tuning-guide/index.html) | [NVIDIA Technical Blog - Grace CPU Architecture](https://developer.nvidia.com/blog/nvidia-grace-cpu-superchip-architecture-in-depth/) | arm-verify | 2026-04-10 |
| Optimal NUMA binding pattern | `--cpu-bind=mask_cpu` or `--cpu-bind=map_cpu` + `--mem-bind=local` | [Slurm Resource Binding Guide](https://slurm.schedmd.com/resource_binding.html) | [LUMI Documentation - Distribution and Binding](https://docs.lumi-supercomputer.eu/runjobs/scheduled-jobs/distribution-binding/) | arm-verify | 2026-04-10 |
| OpenMPI 5.0.x with Slurm requirement | Slurm 22.05+ required for PMIx v2.x–v5.x support | [Open MPI 5.0.x Launching with Slurm](https://docs.open-mpi.org/en/v5.0.x/launching-apps/slurm.html) | [Slurm MPI Users Guide](https://slurm.schedmd.com/mpi_guide.html) | arm-verify | 2026-04-10 |
| OpenMPI 5.0+ launch recommendation | mpirun recommended over direct srun launch; PMI-2 not supported | [Open MPI 5.0.x PMIx Documentation](https://docs.open-mpi.org/en/v5.0.x/launching-apps/pmix-and-prrte.html) | [Slurm MPI Users Guide](https://slurm.schedmd.com/mpi_guide.html) | arm-verify | 2026-04-10 |
| MpiDefault config | `MpiDefault=pmix` for modern Arm clusters with OpenMPI 5.x | [Slurm MPI Guide](https://slurm.schedmd.com/mpi_guide.html) | [Open MPI Launching with Slurm](https://docs.open-mpi.org/en/v5.0.x/launching-apps/slurm.html) | arm-verify | 2026-04-10 |

---

## Notes

- LOW confidence claims (Neoverse N3 NUMA node topology per socket, Neoverse V3 unified vs. multi-node clusters, Slurm task plugin performance benchmarks on Arm) excluded per arm-verify protocol.
- NUMA topology claims verified across multiple Arm partners (AWS, Microsoft Azure, NVIDIA) with consistent architecture documentation.
- Slurm configuration guidance sourced from both primary SchedMD documentation and verified HPC cluster implementations (LUMI, NERSC).
