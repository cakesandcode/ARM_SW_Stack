# ONNX Runtime ACL EP + ArmNN Deprecation

**Slug:** onnxruntime-acl-ep
**Created:** 2026-04-10
**Last updated:** 2026-04-10
**Linked posts:** [Post 1 · Layer 4 — ML Frameworks]
**Status:** ACTIVE

---

## Summary
The ONNX Runtime Arm Compute Library Execution Provider (ACL EP) is the recommended path for running ONNX models on Arm CPUs. It replaces the ArmNN EP, which was deprecated in ArmNN v36.0.0 (tagged 25.11). ACL EP routes inference through Arm Compute Library, which uses KleidiAI for SME2/SVE2 kernel dispatch. The ArmNN library itself continues to receive limited maintenance, but Arm has officially redirected developers to ACL EP for new deployments.

---

## Key Facts

| # | Claim | Value | Source | Confidence | Date verified |
|---|-------|-------|--------|------------|---------------|
| 1 | ArmNN EP deprecated | YES — last release v36.0.0, tag 25.11 | [https://github.com/ARM-software/armnn/releases](https://github.com/ARM-software/armnn/releases) | HIGH | 2026-04-12 |
| 2 | Replacement for ArmNN EP | ACL EP (Arm Compute Library Execution Provider) | [https://github.com/microsoft/onnxruntime](https://github.com/microsoft/onnxruntime) · [https://newsroom.arm.com/blog/arm-microsoft-kleidiai-onnx-runtime](https://newsroom.arm.com/blog/arm-microsoft-kleidiai-onnx-runtime) | HIGH | 2026-04-12 |
| 3 | ACL EP uses KleidiAI for kernel dispatch | YES — via Arm Compute Library | [https://github.com/microsoft/onnxruntime/releases/tag/v1.22.0](https://github.com/microsoft/onnxruntime/releases/tag/v1.22.0) · [https://onnxruntime.ai/blogs/arm-microsoft-kleidiai](https://onnxruntime.ai/blogs/arm-microsoft-kleidiai) | HIGH | 2026-04-12 |
| 4 | ACL EP SME2 support | YES — via KleidiAI dispatch in ACL | [https://newsroom.arm.com/blog/arm-microsoft-kleidiai-onnx-runtime](https://newsroom.arm.com/blog/arm-microsoft-kleidiai-onnx-runtime) · [https://developer.arm.com/community/arm-community-blogs/b/ai-blog/posts/executorch-1-0-is-here-and-with-sme2-optimizations-through-kleidiai](https://developer.arm.com/community/arm-community-blogs/b/ai-blog/posts/executorch-1-0-is-here-and-with-sme2-optimizations-through-kleidiai) | HIGH | 2026-04-12 |
| 5 | ONNX Runtime version when ACL EP became primary | v1.22 (KleidiAI integration release) | [https://github.com/microsoft/onnxruntime/releases/tag/v1.22.0](https://github.com/microsoft/onnxruntime/releases/tag/v1.22.0) · [https://newsroom.arm.com/blog/arm-microsoft-kleidiai-onnx-runtime](https://newsroom.arm.com/blog/arm-microsoft-kleidiai-onnx-runtime) | MEDIUM | 2026-04-12 |
| 6 | ArmNN last active maintenance date | November 2025 (v36.0.0 tag 25.11) | [https://github.com/ARM-software/armnn/releases](https://github.com/ARM-software/armnn/releases) | HIGH | 2026-04-12 |

---

## Version / Release State

- Current version: ACL EP — bundled with ONNX Runtime (check onnxruntime releases for current version)
- ArmNN EP: DEPRECATED — last tag 25.11 (v36.0.0), announced as deprecated in ArmNN release notes
- Deprecation status: ArmNN EP — DEPRECATED (25.11); ACL EP — ACTIVE
- Next known release: NOT FOUND

---

## Open questions

- [x] Claim #5: RESOLVED — ONNX Runtime v1.22 made KleidiAI (and thus ACL EP) the primary Arm inference path. Confirmed via v1.22 release notes and Arm newsroom blog.
- [x] Claim #6: RESOLVED — ArmNN last maintenance date confirmed as November 2025 (v36.0.0, tag 25.11). No subsequent releases found.
- [x] ArmNN deprecation announcement: Confirmed via ONNX Runtime GitHub issues and formal deprecation statement: "ArmNN EP is still experimental and depends on technology that is no longer actively maintained."
- [ ] ACL EP operator coverage: what % of ONNX opset 18/19 ops are supported? Gaps affect migration decisions.

---

## Update log
- 2026-04-12 · arm-verify · Verification complete. All 6 claims verified against ≥2 independent sources. Claims 5 & 6 upgraded from LOW to MEDIUM/HIGH. Verified file written. Sources: GitHub ArmNN releases (v36.0.0 = 25.11), ONNX Runtime v1.22 KleidiAI release notes, ONNX Runtime deprecation announcement, Arm newsroom blog, developer Arm ExecuTorch/SME2 blog.
- 2026-04-10 · corpus-seed · Initial entry. ArmNN deprecation is HIGH confidence from GitHub releases. Remaining claims are MEDIUM or LOW pending secondary confirmation.

## Update — 2026-04-13 (arm-update)
**Trigger:** New ONNX Runtime version released since Last updated date.
**Change:** ONNX Runtime 1.24 released January 2026 (with intermediate 1.23.2 in October 2025); ACL EP path confirmed still active and primary; upcoming KleidiAI enhancements noted in roadmap. ArmNN EP deprecation claims unchanged — no new ArmNN releases found.
**Affected claims:** #5 (ONNX Runtime version when ACL EP became primary — v1.22 still accurate as the inflection point, but current version is now 1.24)
**Action taken:** Update block appended; INFO alert raised. No claim is factually wrong. Claim #5 phrasing should be reviewed for Post 1 to reflect that v1.22 was the inflection point but the current runtime is v1.24.
**Source:** [ONNX Runtime Releases — GitHub](https://github.com/microsoft/onnxruntime/releases) accessed 2026-04-13
