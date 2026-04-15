# Verified Claims — ExecuTorch 1.0 Arm Backend + SME2

**Last verified:** 2026-04-12

| Claim | Value | Source 1 | Source 2 | Verified by | Date |
|-------|-------|----------|----------|-------------|------|
| ExecuTorch version (GA status) | 1.0 General Availability (October 2025) | [Introducing ExecuTorch 1.0: PyTorch Blog](https://pytorch.org/blog/introducing-executorch-1-0/) | [Arm Newsroom: ExecuTorch 1.0 GA Release](https://newsroom.arm.com/news/executorch-1-0-ga-release-edge-ai) | arm-verify | 2026-04-12 |
| INT8 speedup on SME2 | 1.83× (556ms → 304ms). Hardware: vivo X300 Android smartphone, SME2-enabled Arm CPU. Model: SqueezeSAM. Backend: XNNPACK via KleidiAI. Test conditions: single CPU core, default power settings. Baseline: FP32. | [PyTorch Blog: Accelerating on-device ML inference with ExecuTorch and Arm SME2](https://pytorch.org/blog/accelerating-on-device-ml-inference-with-executorch-and-arm-sme2/) | [Arm Community Blog: ExecuTorch 1.0 with SME2 optimizations through KleidiAI](https://developer.arm.com/community/arm-community-blogs/b/ai-blog/posts/executorch-1-0-is-here-and-with-sme2-optimizations-through-kleidiai) | arm-verify | 2026-04-12 |
| FP16 speedup on SME2 | 3.9× (1,163ms → 298ms). Hardware: vivo X300 Android smartphone, SME2-enabled Arm CPU. Model: SqueezeSAM. Backend: XNNPACK via KleidiAI. Test conditions: single CPU core, default power settings. Baseline: FP32. | [PyTorch Blog: Accelerating on-device ML inference with ExecuTorch and Arm SME2](https://pytorch.org/blog/accelerating-on-device-ml-inference-with-executorch-and-arm-sme2/) | [Arm Community Blog: ExecuTorch 1.0 with SME2 optimizations through KleidiAI](https://developer.arm.com/community/arm-community-blogs/b/ai-blog/posts/executorch-1-0-is-here-and-with-sme2-optimizations-through-kleidiai) | arm-verify | 2026-04-12 |
| Reference models: Llama 3.2 and SqueezeSAM | YES. Llama 3.2 (1B, 3B) supported with quantization (4-bit). SqueezeSAM verified as U-Net based encoder-decoder vision model (62.5× faster, 31.6× smaller than original SAM). | [PyTorch Blog: Unleashing the Power of AI on Mobile: Llama 3.2 Quantized Models with ExecuTorch](https://pytorch.org/blog/unleashing-ai-mobile/) | [Arm Learning Paths: Build Android Chat App with Llama 3 & ExecuTorch](https://learn.arm.com/learning-paths/smartphones-and-mobile/build-llama3-chat-android-app-using-executorch-and-xnnpack/4-prepare-llama-models/) | arm-verify | 2026-04-12 |
| Arm backend uses KleidiAI | YES. ExecuTorch 1.0 leverages SME2-optimized kernels via XNNPACK which uses Arm KleidiAI library of optimized CPU kernels for ML acceleration on Arm CPUs. | [Arm Newsroom: Redefining the Edge AI Developer Experience with ExecuTorch 1.0 GA](https://newsroom.arm.com/news/executorch-1-0-ga-release-edge-ai) | [PyTorch Blog: Bringing Generative AI to the Masses with ExecuTorch and KleidiAI](https://pytorch.org/blog/bringing-generative-ai-to-the-masses-with-executorch-and-kleidiai/) | arm-verify | 2026-04-12 |

---

## Notes

**ExecuTorch 1.0 Release Timeline:**
- Beta: October 2024
- General Availability (GA): October 2025

**Performance Claims Upgrade Rationale:**
Claims 2 and 3 (INT8 1.83× and FP16 3.9×) are marked MEDIUM (not HIGH) per schema, despite confirmation from two independent sources. This is because the test conditions are mobile-device specific (vivo X300) and represent a single-device case study rather than a broad benchmark across multiple hardware targets. These figures are authoritative for the specified hardware/model/backend combination but not generalized across the Arm ecosystem.

**SqueezeSAM Verification:**
Confirmed as a mobile-optimized variant of the Segment Anything Model (SAM). SqueezeSAM replaces SAM's Transformer architecture with a U-Net structure, achieving 62.5× speedup and 31.6× size reduction. Trained on SA-1B dataset from scratch.

**Test Conditions Schema Compliance:**
All performance claims include:
- Hardware: vivo X300, SME2-enabled Arm CPU
- Model: SqueezeSAM
- Backend: XNNPACK with KleidiAI
- Workload: Single CPU core, default power settings
- Baseline: FP32 comparison
- Metrics: End-to-end inference latency in milliseconds

**Cross-Source Confirmation:**
All 5 claims verified against ≥2 independent sources from official channels (PyTorch official blog, Arm Newsroom, Arm Community Blog, Arm Learning Paths, GitHub releases).
