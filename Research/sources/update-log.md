# Update Log — Arm SW Stack Research Corpus

Appended by arm-update agent on each weekly run. Append only.

---

## Run — 2026-04-13
Slugs checked: 11
Changes found: 6 (3 MODERATE, 3 INFO)
Alerts raised: 6
Slugs unchanged: 5

### Changed slugs
| Slug | Finding | Severity |
|------|---------|----------|
| pytorch-2-9-arm | PyTorch 2.10 (2026-01-21) and 2.11 (GA April 2026) released; topic cites 2.9 as current | MODERATE |
| executorch-1-0 | ExecuTorch 1.2.0 released; topic cites 1.0 as current | MODERATE |
| armpl-25 | ArmPL 26.01 released; topic cites 25.x as current | MODERATE |
| arm-agi-cpu | Commercial OEM systems (ASRockRack, Lenovo, Supermicro) now orderable; volume H2 2026 unchanged | INFO |
| onnxruntime-acl-ep | ONNX Runtime 1.24 released Jan 2026; ACL EP path confirmed active | INFO |
| slurm-neoverse | Slurm 25.11.4 is current patch (2026-03-12); no functional change to Arm config claims | INFO |

### Unchanged slugs
| Slug | Note |
|------|------|
| neoverse-v3-n3 | No V4/N4 announced; existing specs confirmed current |
| sme2-transition | No ISA changes; Claim #8 (~95%) still unverified LOW |
| kleidiai-sme2 | Active development; no deprecation; version bump not captured |
| arm-forge-map | Linaro Forge 25.1.2 confirmed current; no 25.2 release found |
| acfl-25 | No confirmed new release; ArmPL 26.01 implies possible ACfL update — manual check needed |

### Source URL status
- All primary domain URLs (developer.arm.com, pytorch.org, schedmd.com, github.com, linaroforge.com) confirmed LIVE via search return.
- Egress-blocked URLs in armpl-25/urls.md and acfl-25/urls.md remain BLOCKED_BY_PROXY — status unchanged from 2026-04-10 assessment.
- No dead URLs identified this run.

### Searches executed
- 12 web searches across 6 domain targets (arm.com, pytorch.org, github.com/pytorch, github.com/microsoft/onnxruntime, schedmd.com, linaroforge.com)
- All searches returned results; no search failed.
