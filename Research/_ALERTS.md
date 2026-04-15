# Alerts — Arm SW Stack Series Research Corpus

Breaking changes, deprecations, or announcements that affect published content.
Written by arm-update agent. Reviewed by human before acting on.

---

## ALERT — 2026-04-13
**Severity:** MODERATE
**Topic slug:** pytorch-2-9-arm
**Change:** PyTorch 2.9 is no longer the current release; PyTorch 2.10 (released 2026-01-21) and PyTorch 2.11 (GA, April 2026) have been published. Post 1 refers to PyTorch 2.9 SVE2/SME2 improvements as current.
**Posts affected:** Post 1 (Layer 1 — Silicon; section citing PyTorch 2.9 with TorchInductor SVE2/SME2 codegen and XNNPACK+KleidiAI)
**Action required:**
  - [ ] Update live Substack post — add note that PyTorch 2.9 was current at publication; latest is 2.11
  - [ ] Update Research/topics/pytorch-2-9-arm.md — done (update block appended)
  - [ ] Flag Claim #1 (version) in Research/verified/pytorch-2-9-arm.md as OUTDATED
  - [ ] Check PyTorch 2.10/2.11 release notes for any Arm-specific changes that affect claims
**Source:** [PyTorch 2.10 Release Blog](https://pytorch.org/blog/pytorch-2-10-release-blog/) accessed 2026-04-13; [PyTorch 2.11.0 GA](https://dev-discuss.pytorch.org/t/pytorch-2-11-0-general-availability/3328) accessed 2026-04-13

---

## ALERT — 2026-04-13
**Severity:** MODERATE
**Topic slug:** executorch-1-0
**Change:** ExecuTorch 1.2.0 is now the current release; it adds Voxtral Realtime, Cortex-M first-class target, Metal backend improvements. ExecuTorch 1.0 is two minor versions behind. Post 1 cites ExecuTorch 1.0 as the current version.
**Posts affected:** Post 1 (Layer 4 — ML Frameworks; ExecuTorch 1.0 Arm backend + SME2 section)
**Action required:**
  - [ ] Update live Substack post — note ExecuTorch 1.0 was current at publication; 1.2.0 is now latest
  - [ ] Update Research/topics/executorch-1-0.md — done (update block appended)
  - [ ] Flag Claim #1 (version) in Research/verified/executorch-1-0.md as OUTDATED
  - [ ] Note only for Claims #2–#6 — speedup figures and reference models remain valid for 1.0; verify if 1.2.0 changes these benchmarks
**Source:** [ExecuTorch Releases — GitHub](https://github.com/pytorch/executorch/releases) accessed 2026-04-13

---

## ALERT — 2026-04-13
**Severity:** MODERATE
**Topic slug:** armpl-25
**Change:** ArmPL 26.01 is now the current major version; Post 2 references ArmPL 25.x as the current release. The jump from 25.x to 26.01 represents a new calendar-year major version. Technical library capabilities (BLAS, LAPACK, FFT, sparse) and licensing (free) are not known to have changed.
**Posts affected:** Post 2 (HPC Compilers + Cluster; ArmPL version cited)
**Action required:**
  - [ ] Update live Substack post — note ArmPL 25.x was current at publication; 26.01 is now available
  - [ ] Update Research/topics/armpl-25.md — done (update block appended)
  - [ ] Flag Claims #2 and #8 in Research/verified/armpl-25.md as OUTDATED (version numbers)
  - [ ] Check ArmPL 26.01 release notes for any new BLAS/LAPACK/SME2 features before revising
**Source:** [Arm Performance Libraries Downloads](https://developer.arm.com/tools-and-software/server-and-hpc/downloads/arm-performance-libraries) accessed 2026-04-13

---

## ALERT — 2026-04-13
**Severity:** INFO
**Topic slug:** arm-agi-cpu
**Change:** Commercial Arm AGI CPU servers are now available for order from ASRockRack, Lenovo, and Supermicro. A liquid-cooled 200kW Supermicro design (336 CPUs, ~45,000 cores) was announced. Volume production timeline (H2 2026) unchanged.
**Posts affected:** Post 1 (Layer 1 — Silicon; Arm AGI CPU availability section)
**Action required:**
  - [ ] Note only — no post edit needed for factual accuracy; existing claims are not wrong
  - [ ] Optional: add footnote that early OEM systems are now orderable while volume ramp remains H2 2026
**Source:** [ServeTheHome — Arm AGI CPU Launch](https://www.servethehome.com/arm-agi-cpu-launched-establishing-arm-as-a-silicon-provider/) accessed 2026-04-13

---

## ALERT — 2026-04-13
**Severity:** INFO
**Topic slug:** onnxruntime-acl-ep
**Change:** ONNX Runtime 1.24 released January 2026 (1.23.2 in October 2025); ACL EP confirmed active; KleidiAI enhancements on roadmap. ArmNN EP deprecation status unchanged.
**Posts affected:** Post 1 (Layer 4 — ML Frameworks; ONNX Runtime ACL EP section)
**Action required:**
  - [ ] Note only — no post edit needed; Claim #5 accurately identifies v1.22 as the inflection point
  - [ ] Optional: update footnote to note current ORT version is 1.24 if post cites a specific version number
**Source:** [ONNX Runtime Releases — GitHub](https://github.com/microsoft/onnxruntime/releases) accessed 2026-04-13

---

## ALERT — 2026-04-13
**Severity:** INFO
**Topic slug:** slurm-neoverse
**Change:** Slurm 25.11.4 is now the current patch release (2026-03-12); prior patches 25.11.2 and 25.11.3 were also issued. No functional change to Arm-specific configuration claims. Slurm 26.05 is planned (v0.0.41 API endpoint removal announced).
**Posts affected:** Post 2 (HPC Compilers + Cluster; Slurm version cited)
**Action required:**
  - [ ] Note only — no post edit needed; "Slurm 25.11" is accurate; patch suffix 25.11.4 is a minor version note
**Source:** [SchedMD Release Announcements](https://www.schedmd.com/slurm-support/release-announcements/) accessed 2026-04-13

---

## Alert format (for arm-update agent)

```
## ALERT — YYYY-MM-DD
**Severity:** URGENT | MODERATE | INFO
**Topic slug:** {slug}
**Change:** One sentence describing what changed.
**Posts affected:** Post N (section: ...)
**Action required:**
  - [ ] Update live Substack post
  - [ ] Update Research/topics/{slug}.md
  - [ ] Flag claims in Research/verified/{slug}.md as OUTDATED
  - [ ] Note only — no post edit needed
**Source:** [URL] accessed YYYY-MM-DD
```
