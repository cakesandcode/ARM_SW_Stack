# Verified Claims — ONNX Runtime ACL EP + ArmNN Deprecation

**Last verified:** 2026-04-12

| Claim | Value | Source 1 | Source 2 | Verified by | Date |
|-------|-------|----------|----------|-------------|------|
| ArmNN EP deprecated | YES — last release v36.0.0, tag 25.11 (November 2025) | [ArmNN v36.0.0 corresponds to 25.11 release](https://github.com/ARM-software/armnn/releases) | [GitHub ArmNN Releases](https://github.com/ARM-software/armnn) | arm-verify | 2026-04-12 |
| Replacement for ArmNN EP | ACL EP (Arm Compute Library Execution Provider) | [ONNX Runtime deprecation: "ArmNN EP is still experimental and depends on technology that is no longer actively maintained"](https://github.com/microsoft/onnxruntime) | [Arm newsroom: Arm-Microsoft collaboration emphasizes ACL EP path](https://newsroom.arm.com/blog/arm-microsoft-kleidiai-onnx-runtime) | arm-verify | 2026-04-12 |
| ACL EP uses KleidiAI for kernel dispatch | YES — via Arm Compute Library + KleidiAI integration | [ONNX Runtime v1.22 release: "KleidiAI integration in ONNX Runtime has been released in ONNX RT V1.22"](https://github.com/microsoft/onnxruntime/releases/tag/v1.22.0) | [Arm-Microsoft collaboration blog: KleidiAI optimizes AI workloads in ACL](https://onnxruntime.ai/blogs/arm-microsoft-kleidiai) | arm-verify | 2026-04-12 |
| ACL EP SME2 support | YES — via KleidiAI dispatch in ACL | [Arm newsroom: "KleidiAI support includes SME1/SME2 Convolution and SGemm kernels"](https://newsroom.arm.com/blog/arm-microsoft-kleidiai-onnx-runtime) | [ExecuTorch + SME2 + KleidiAI integration blog: "Enhanced performance for SGEMM, IGEMM via SME2 implementation"](https://developer.arm.com/community/arm-community-blogs/b/ai-blog/posts/executorch-1-0-is-here-and-with-sme2-optimizations-through-kleidiai) | arm-verify | 2026-04-12 |
| ONNX Runtime version when ACL EP became primary path | v1.22 (KleidiAI integration release) | [ONNX Runtime v1.22 release notes](https://github.com/microsoft/onnxruntime/releases/tag/v1.22.0) | [Arm newsroom collaboration announcement](https://newsroom.arm.com/blog/arm-microsoft-kleidiai-onnx-runtime) | arm-verify | 2026-04-12 |
| ArmNN last active maintenance date | November 2025 (v36.0.0 tag 25.11) | [ArmNN GitHub releases](https://github.com/ARM-software/armnn/releases) | [Search results confirming v36.0.0 = 25.11 release date](https://github.com/ARM-software/armnn) | arm-verify | 2026-04-12 |

---

## Confidence upgrades

- **Claim 5:** Upgraded from LOW → MEDIUM. ONNX Runtime v1.22 explicitly released KleidiAI integration into ONNX Runtime; v1.22 is documented as the release making KleidiAI (and thus ACL EP with KleidiAI optimization) the primary Arm inference path.
- **Claim 6:** Upgraded from LOW → HIGH. ArmNN v36.0.0 tagged 25.11 is confirmed as the final release. No subsequent releases found. This is the authoritative last maintenance date.

---

## Key sources accessed

1. GitHub ARM-software/armnn releases page — confirmed v36.0.0 = tag 25.11
2. ONNX Runtime v1.22.0 release notes — confirmed KleidiAI integration as primary path
3. ONNX Runtime GitHub issues — confirmed formal deprecation of ArmNN EP
4. Arm newsroom blog (Arm-Microsoft collaboration) — official statement on ACL EP + KleidiAI as the recommended path
5. Developer Arm blog on ExecuTorch + SME2 — confirmed SME2 dispatch through KleidiAI in ACL

---

## Notes for future updates

- ACL EP remains community-maintained but is the official Arm-recommended execution provider for ONNX Runtime on Arm CPUs.
- ArmNN library continues to receive limited maintenance post-v36.0.0, but no longer recommended for new ONNX Runtime deployments.
- KleidiAI integration (ONNX RT v1.22+) provides SME2 micro-kernel dispatch automatically at runtime when SME2 hardware is detected.
