# Verified Claims — Neoverse CSS V3 and N3 Specifications

**Last verified:** 2026-04-12

| Claim | Value | Source 1 | Source 2 | Verified by | Date |
|-------|-------|----------|----------|-------------|------|
| V3 core count (CSS reference config) | 128 cores per socket | [TechRadar: Neoverse V3 128 cores](https://www.techradar.com/pro/arms-new-super-powerful-neoverse-v3-cpu-core-obliterates-previous-generation-and-should-get-intel-and-amd-worried-hbm-and-cxl-support-128-cores-per-socket-hyperscalers-will-be-salivating) | [Arm.com: CSS V3](https://www.arm.com/products/neoverse-compute-subsystems/css-v3) | arm-verify | 2026-04-12 |
| V3 ISA extensions | SME2, SVE2 (ARMv9.2) | [Tom's Hardware: Neoverse V3](https://www.tomshardware.com/pc-components/cpus/arm-unveils-next-gen-neoverse-cpu-cores-and-compute-subsystems-hoping-to-entice-more-custom-silicon-customers) | [Arm Newsroom: Neoverse V3 Overview](https://newsroom.arm.com/blog/microsoft-azure-cobalt-200-arm-neoverse-css-v3) | arm-verify | 2026-04-12 |
| V3 interconnect support | PCIe Gen5, CXL 3.0 | [TechRadar: V3 PCIe Gen5 CXL](https://www.techradar.com/pro/arms-new-super-powerful-neoverse-v3-cpu-core-obliterates-previous-generation-and-should-get-intel-and-amd-worried-hbm-and-cxl-support-128-cores-per-socket-hyperscalers-will-be-salivating) | [Arm.com: Neoverse V3 Product Page](https://www.arm.com/products/silicon-ip-cpu/neoverse/neoverse-v3) | arm-verify | 2026-04-12 |
| V3 memory support | HBM3, DDR5, LPDDR5 | [ServeTheHome: CSS V3 specs](https://www.servethehome.com/microsoft-azure-cobalt-200-launched-with-132-arm-neoverse-v3-cores/) | [TechRadar: HBM3 support](https://www.techradar.com/pro/arms-new-super-powerful-neoverse-v3-cpu-core-obliterates-previous-generation-and-should-get-intel-and-amd-worried-hbm-and-cxl-support-128-cores-per-socket-hyperscalers-will-be-salivating) | arm-verify | 2026-04-12 |
| V3 AI performance uplift vs V2 | 84% (AI data analytics workload) | [HotHardware: V3 AI uplift](https://hothardware.com/news/arm-next-gen-neoverse-ai-performance-lift) | [Arm.com: Neoverse V3 Product Page](https://www.arm.com/products/silicon-ip-cpu/neoverse/neoverse-v3) | arm-verify | 2026-04-12 |
| Cobalt 200 implementation | Neoverse CSS V3 (132 cores, TSMC 3nm) | [Phoronix: Cobalt 200 announcement](https://www.phoronix.com/news/Microsoft-Azure-Cobalt-200) | [Microsoft Tech Community: Cobalt 200](https://techcommunity.microsoft.com/blog/azureinfrastructureblog/announcing-cobalt-200-azure%E2%80%99s-next-cloud-native-cpu/4469807) | arm-verify | 2026-04-12 |
| N3 ML performance vs N2 | 3× improvement | [AnandTech: N3 3x ML perf](https://www.anandtech.com/show/21270/arm-announces-neoverse-v3-and-n3-cpu-cores) | [Arm.com: Neoverse N3 Product Page](https://www.arm.com/products/silicon-ip-cpu/neoverse/neoverse-n3) | arm-verify | 2026-04-12 |
| N3 performance-per-watt vs N2 | 20% improvement | [Arm Community Blog: N3 perf/W](https://community.arm.com/arm-community-blogs/b/infrastructure-solutions-blog/posts/arm-neoverse-css-n3-brings-industry-leading-performance-per-watt-to-custom-silicon) | [Tom's Hardware: N3 specs](https://www.tomshardware.com/pc-components/cpus/arm-unveils-next-gen-neoverse-cpu-cores-and-compute-subsystems-hoping-to-entice-more-custom-silicon-customers) | arm-verify | 2026-04-12 |
| N3 TDP (32-core CSS config) | 40 W | [ServeTheHome: CSS N3 specs](https://www.servethehome.com/arm-neoverse-n3-and-v3-with-css-launched/) | [Tom's Hardware: N3 announcement](https://www.tomshardware.com/pc-components/cpus/arm-unveils-next-gen-neoverse-cpu-cores-and-compute-subsystems-hoping-to-entice-more-custom-silicon-customers) | arm-verify | 2026-04-12 |
| N3 example products (CORRECTED) | Google Axion N4A (N3 cores only) | [Google Cloud Blog: Axion N4A](https://cloud.google.com/blog/products/compute/axion-based-n4a-vms-now-in-preview) | [Phoronix: Google Cloud N4A review](https://www.phoronix.com/review/google-cloud-n4a-axion) | arm-verify | 2026-04-12 |
| Graviton4 architecture (CORRECTED) | Neoverse V2 (NOT N3 or V3) | [Chips and Cheese: Graviton4 V2](https://chipsandcheese.com/p/arms-neoverse-v2-in-awss-graviton-4) | [Arm Newsroom: Graviton4 V2](https://newsroom.arm.com/blog/arm-aws-reinvent-2024) | arm-verify | 2026-04-12 |

---

## Notes

### Cobalt 100 (Neoverse N2) vs Cobalt 200 (Neoverse V3) Disambiguation

The topic file previously conflated two distinct products:

- **Azure Cobalt 100**: 128-core Neoverse N2 processor, TSMC 5nm, GA since October 2024. Uses Arm Neoverse Compute Subsystems N2 template.
- **Azure Cobalt 200**: 132-core Neoverse V3 processor, TSMC 3nm, announced 2025/2026. Uses Arm Neoverse Compute Subsystems V3 (CSS V3) with two 66-core chiplets.

Sources: [Microsoft Tech Community Cobalt 200](https://techcommunity.microsoft.com/blog/azureinfrastructureblog/announcing-cobalt-200-azure%E2%80%99s-next-cloud-native-cpu/4469807), [ServeTheHome Cobalt 100](https://www.servethehome.com/microsoft-azure-cobalt-100-128-core-arm-neoverse-n2-cpu-launched/)

### V3 CSS Reference Config (128 cores) vs Cobalt 200 Actual (132 active cores)

The Arm CSS V3 reference configuration specifies 128 cores per socket as the standard design point. However, Microsoft's Cobalt 200 implementation deviates: it features two 66-core chiplets for a total of 132 active cores instead of the reference 128. This is a product-specific optimization by Microsoft and does not invalidate the reference specification published by Arm.

Sources: [Arm CSS V3 spec](https://www.arm.com/products/neoverse-compute-subsystems/css-v3), [Phoronix Cobalt 200](https://www.phoronix.com/news/Microsoft-Azure-Cobalt-200)

### Claim 10 Correction: Graviton4 is Neoverse V2, Not N3

**Error in original topic file:** Claim 10 listed "AWS Graviton4" as an N3 example product. This is incorrect.

**Correction:** AWS Graviton4 uses **Neoverse V2 cores** (96 cores), not N3 or V3. For N3 example products, only **Google Axion N4A** is a confirmed production system using Neoverse N3 cores. Google's earlier Axion C4A uses Neoverse V2.

Sources: [Chips and Cheese: Graviton4 uses V2](https://chipsandcheese.com/p/arms-neoverse-v2-in-awss-graviton-4), [Arm Newsroom: Graviton4 announcement](https://newsroom.arm.com/blog/arm-aws-reinvent-2024), [Google Cloud Blog: N4A Axion](https://cloud.google.com/blog/products/compute/axion-based-n4a-vms-now-in-preview)

---

**Verification methodology:** Each claim verified against ≥2 independent sources (Arm official pages, major tech press, product announcements). Performance claims (Claims 5, 7, 8) retain MEDIUM confidence per schema: workload specifics and benchmark methodology not publicly disclosed by Arm in detail. See topic file open questions for further investigation requirements.
