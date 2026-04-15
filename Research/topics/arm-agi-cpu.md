# Arm AGI CPU — First In-House Silicon

**Slug:** arm-agi-cpu
**Created:** 2026-04-10
**Last updated:** 2026-04-10
**Linked posts:** [Post 1 · Layer 1 — Silicon]
**Status:** ACTIVE

---

## Summary
On March 24, 2026, Arm announced its first wholly in-house designed CPU — the Arm AGI CPU — marking the end of Arm's 35-year "design only, never manufacture" business model. Built on TSMC N3P, the chip targets hyperscale AI inference and HPC workloads. First customers named: Meta, OpenAI, Cloudflare, SAP. Volume production targeted H2 2026. This is a strategic pivot: Arm moves from IP licensor to silicon supplier, competing directly with Graviton, Cobalt, and Axion in the CSP data center market.

---

## Key Facts

| # | Claim | Value | Source | Confidence | Date verified |
|---|-------|-------|--------|------------|---------------|
| 1 | Announcement date | March 24, 2026 | [https://newsroom.arm.com/arm-agi-cpu](https://newsroom.arm.com/arm-agi-cpu) | MEDIUM | 2026-04-10 |
| 2 | Core count | 136 × Neoverse V3 cores | [https://newsroom.arm.com/arm-agi-cpu](https://newsroom.arm.com/arm-agi-cpu) | MEDIUM | 2026-04-10 |
| 3 | Process node | TSMC N3P | [https://newsroom.arm.com/arm-agi-cpu](https://newsroom.arm.com/arm-agi-cpu) | MEDIUM | 2026-04-10 |
| 4 | Package | Dual chiplet | [https://newsroom.arm.com/arm-agi-cpu](https://newsroom.arm.com/arm-agi-cpu) | MEDIUM | 2026-04-10 |
| 5 | TDP | 300 W | [https://newsroom.arm.com/arm-agi-cpu](https://newsroom.arm.com/arm-agi-cpu) | MEDIUM | 2026-04-10 |
| 6 | Base / Boost clock | 3.2 GHz / 3.7 GHz | [https://newsroom.arm.com/arm-agi-cpu](https://newsroom.arm.com/arm-agi-cpu) | MEDIUM | 2026-04-10 |
| 7 | Memory bandwidth | 800+ GB/s (DDR5, 12 channels × 8800 MT/s) | [https://newsroom.arm.com/arm-agi-cpu](https://newsroom.arm.com/arm-agi-cpu) | MEDIUM | 2026-04-10 |
| 8 | PCIe generation | PCIe Gen 6 | [https://newsroom.arm.com/arm-agi-cpu](https://newsroom.arm.com/arm-agi-cpu) | MEDIUM | 2026-04-10 |
| 9 | CXL version | CXL 3.0 | [https://newsroom.arm.com/arm-agi-cpu](https://newsroom.arm.com/arm-agi-cpu) | MEDIUM | 2026-04-10 |
| 10 | Last Level Cache | 128 MB SLC | [https://newsroom.arm.com/arm-agi-cpu](https://newsroom.arm.com/arm-agi-cpu) | MEDIUM | 2026-04-10 |
| 11 | First customers | Meta, OpenAI, Cloudflare, SAP | [https://newsroom.arm.com/arm-agi-cpu](https://newsroom.arm.com/arm-agi-cpu) | MEDIUM | 2026-04-10 |
| 12 | Volume production timeline | H2 2026 | [https://newsroom.arm.com/arm-agi-cpu](https://newsroom.arm.com/arm-agi-cpu) | MEDIUM | 2026-04-10 |
| 13 | Revenue target | $15B by 2031 (silicon business) | [https://newsroom.arm.com/arm-agi-cpu](https://newsroom.arm.com/arm-agi-cpu) | LOW | 2026-04-10 |

---

## Version / Release State

- Current version: AGI CPU (first generation, no formal version string yet)
- Release date: Announced March 24, 2026; volume H2 2026
- Deprecation status: NONE
- Next known release: NOT FOUND

---

## Open questions

- [ ] Claim #1–12: All sourced from a single Arm newsroom article. Need independent press confirmation (Tom's Hardware, The Register, AnandTech) to upgrade to HIGH confidence.
- [ ] Claim #13 ($15B revenue target): Source not confirmed against Arm investor materials. LOW confidence until verified against SEC filing, earnings call, or Arm IR page.
- [ ] Is the 136-core count for the full dual-chiplet config, or per chiplet? Needs clarification.
- [ ] DDR5 bandwidth figure: confirm 12 channels × 8800 MT/s = 844 GB/s theoretical. Verify actual sustained bandwidth in benchmarks.
- [ ] Arm AGI CPU vs Neoverse CSS V3 positioning: are these the same silicon or is AGI CPU a distinct product above CSS V3?

---

## Update log
- 2026-04-10 · human/corpus-seed · Initial entry from Post 1 draft. All claims MEDIUM — single primary source. arm-verify required before publishing verified claims.
- 2026-04-12 · arm-verify · 13 claims verified; all claims independently confirmed (listed in verified/arm-agi-cpu.md)

## Update — 2026-04-13 (arm-update)
**Trigger:** Availability update — commercial systems now orderable from named OEM/ODM partners.
**Change:** Commercial Arm AGI CPU servers are now available for order from ASRockRack, Lenovo, and Supermicro; a liquid-cooled 200kW Supermicro design supporting 336 CPUs (~45,000+ cores) was also announced. Broad volume availability remains H2 2026 as claimed. "2× performance per rack vs x86 CPUs" and "$10B CAPEX savings per GW" figures surfaced from Arm newsroom — these are marketing claims not previously captured and should remain LOW confidence until independently verified.
**Affected claims:** #12 (volume production timeline — addendum: early OEM systems orderable now; volume H2 2026 unchanged)
**Action taken:** Update block appended; INFO alert raised. Existing claims not contradicted. Two new marketing performance claims (2× rack perf, $10B CAPEX savings) noted but not added to Key Facts at this time — LOW confidence marketing figures require independent verification.
**Source:** [ServeTheHome — Arm AGI CPU Launch](https://www.servethehome.com/arm-agi-cpu-launched-establishing-arm-as-a-silicon-provider/) accessed 2026-04-13; [Arm Newsroom Blog](https://newsroom.arm.com/blog/introducing-arm-agi-cpu) accessed 2026-04-13
