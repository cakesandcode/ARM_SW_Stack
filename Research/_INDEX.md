# Research Index — Arm SW Stack Series
# Last updated: 2026-04-13
# Maintained by: arm-update (weekly) + human edits

---

## Series map

| Post | Title | Status | Topics |
|------|-------|--------|--------|
| Post 1 | Silicon + Intro | PUBLISHED (draft HTML) | arm-agi-cpu, neoverse-v3-n3, sme2-transition, kleidiai-sme2, onnxruntime-acl-ep, pytorch-2-9-arm, executorch-1-0 |
| Post 2 | HPC Compilers + Cluster | PUBLISHED (draft HTML) | acfl-25, armpl-25, arm-forge-map, slurm-neoverse |
| Post 3 | ML Frameworks | PLANNED | pytorch-2-9-arm, tensorflow-arm, xnnpack-kleidiai |
| Post 4 | Edge + Full Picture | PLANNED | executorch-1-0, arm-model-zoo, arm-avh |

---

## Topic registry

### ACTIVE TOPICS

| Slug | Topic | Post | Confidence | Last updated | Verified |
|------|-------|------|------------|--------------|---------|
| arm-agi-cpu | Arm AGI CPU — first in-house silicon | Post 1 | MEDIUM | 2026-04-13 | YES |
| neoverse-v3-n3 | Neoverse CSS V3 and N3 specs | Post 1 | HIGH | 2026-04-13 | YES |
| sme2-transition | SVE2 → SME2 transition (3 levels) | Post 1 | HIGH | 2026-04-13 | PARTIAL |
| kleidiai-sme2 | KleidiAI SME2 kernel dispatch + KRT | Post 1 | HIGH | 2026-04-13 | YES |
| onnxruntime-acl-ep | ONNX Runtime ACL EP + ArmNN deprecation | Post 1 | HIGH | 2026-04-13 | YES |
| pytorch-2-9-arm | PyTorch 2.9 SVE2/SME2 improvements | Post 1 | MEDIUM | 2026-04-13 | YES |
| executorch-1-0 | ExecuTorch 1.0 Arm backend + SME2 | Post 1 | MEDIUM | 2026-04-13 | YES |
| armpl-25 | ArmPL 25.x — scope + platform support | Post 2 | MEDIUM | 2026-04-13 | YES |
| acfl-25 | ACfL 25.x — compiler features | Post 2 | HIGH | 2026-04-13 | YES |
| arm-forge-map | Linaro Forge MAP profiler on Neoverse | Post 2 | HIGH | 2026-04-13 | YES |
| slurm-neoverse | Slurm config on Neoverse N3/V3 clusters | Post 2 | HIGH | 2026-04-13 | YES |

### PLANNED TOPICS (Post 3+)

| Slug | Topic | Post | Priority |
|------|-------|------|----------|
| kubernetes-arm-nodes | K8s Arm-native node pools (Graviton4, Cobalt, Axion) | Post 3 | MEDIUM |
| xnnpack-kleidiai | XNNPACK + KleidiAI integration depth | Post 3 | HIGH |
| tensorflow-kleidiai | TF2 KleidiAI dispatch mechanism | Post 3 | MEDIUM |
| arm-model-zoo | Arm ML Model Zoo — formats + benchmarks | Post 4 | MEDIUM |
| arm-avh | Arm Virtual Hardware CI/CD integration | Post 4 | LOW |

---

## Alerts
**6 alerts raised 2026-04-13** (3 MODERATE, 3 INFO). See _ALERTS.md for full entries.
- MODERATE: pytorch-2-9-arm — PyTorch 2.11 now current; Post 1 cites 2.9
- MODERATE: executorch-1-0 — ExecuTorch 1.2.0 now current; Post 1 cites 1.0
- MODERATE: armpl-25 — ArmPL 26.01 now current; Post 2 cites 25.x
- INFO: arm-agi-cpu — OEM systems now orderable; no claim error
- INFO: onnxruntime-acl-ep — ORT 1.24 now current; inflection point claim unchanged
- INFO: slurm-neoverse — Slurm 25.11.4 is current patch; no claim error

---

## Changelog
- 2026-04-12 · arm-verify-post1 · Full arm-verify compliance run on all 7 Post 1 topics. 7 verified/ files created. 56/57 claims promoted (Claim #8 of sme2-transition withheld — no primary source for ~95% figure). arm-agi-cpu: PARTIAL→YES (13 claims, Claim 13 upgraded LOW→MEDIUM). sme2-transition: re-classified PARTIAL (8/9). Both posts corrected: Graviton4=V2 fix, ArmNN date fix, ExecuTorch benchmark conditions added, Cobalt 200 CSS label corrected, Linaro Forge MAP acquisition documented. Audit report delivered: ARM_Stack_Post_Audit_2026-04-12.docx.
- 2026-04-10 · post2-complete · Post 2 published (draft HTML). All 4 Post 2 topics researched and verified. 35 claims verified across acfl-25, armpl-25, arm-forge-map, slurm-neoverse. 4 lab notebooks delivered, 52/52 tests pass.
- 2026-04-10 · initial · corpus created, Post 1 topics seeded from published draft
- 2026-04-13 · arm-update (weekly) · Full sweep of 11 ACTIVE slugs. 6 alerts raised (3 MODERATE, 3 INFO). Version changes: PyTorch 2.11 > 2.9, ExecuTorch 1.2.0 > 1.0, ArmPL 26.01 > 25.x. Confidence downgraded: pytorch-2-9-arm, executorch-1-0, armpl-25 → MEDIUM. 5 slugs confirmed unchanged (neoverse-v3-n3, sme2-transition, kleidiai-sme2, arm-forge-map, acfl-25). All topic files updated with check log or update blocks.
