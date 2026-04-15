# Research Corpus Schema
# Arm SW Stack Series — Aruna Kumar
# Every agent reads this before writing to the corpus.

---

## Guiding principles

1. Every claim has a source URL and an access date. No exceptions.
2. Confidence is assigned per claim, not per document.
3. Updates are appended, never overwritten. Old data stays visible.
4. Uncertainty is explicit. "NOT FOUND" is a valid and required answer.
5. Code lives in Research/code/. Documents live in Research/documents/. Never mix.

---

## Confidence levels

| Level  | Meaning                                              |
|--------|------------------------------------------------------|
| HIGH   | Primary source (official docs, release notes, paper) |
| MEDIUM | Reputable secondary source (major tech press, analyst report) |
| LOW    | Single source, unverified, or inferred               |

LOW-confidence claims must not appear in published posts without upgrade to HIGH or MEDIUM.

---

## Topic file format  →  Research/topics/{slug}.md

```markdown
# {Topic Name}

**Slug:** {slug}
**Created:** YYYY-MM-DD
**Last updated:** YYYY-MM-DD
**Linked posts:** [Post 1 · Layer N], [Post 2 · Layer N]
**Status:** ACTIVE | OUTDATED | SUPERSEDED

---

## Summary
One paragraph. What this topic is and why it matters to the series.

---

## Key Facts

| # | Claim | Value | Source | Confidence | Date verified |
|---|-------|-------|--------|------------|---------------|
| 1 | ...   | ...   | [URL]  | HIGH       | YYYY-MM-DD    |

---

## Version / Release State

- Current version:
- Release date:
- Deprecation status: NONE | DEPRECATED (date) | SUPERSEDED BY (what)
- Next known release:

---

## Open questions
Things not found or conflicting across sources. Requires follow-up.

- [ ] ...

---

## Update log
- YYYY-MM-DD · agent/human · description of change
```

---

## Verified claim format  →  Research/verified/{slug}.md

Only claims that have been checked against ≥2 independent sources.
Used by the draft agent as the only citable fact pool.

```markdown
# Verified Claims — {Topic}

**Last verified:** YYYY-MM-DD

| Claim | Value | Source 1 | Source 2 | Verified by | Date |
|-------|-------|----------|----------|-------------|------|
| ...   | ...   | [URL]    | [URL]    | arm-verify  | ...  |
```

---

## Source file format  →  Research/sources/{slug}/

Each topic slug gets a folder. Inside:
- `urls.md`  — list of URLs with one-line description and access date
- `notes.md` — raw extracted quotes and data before structuring
- Any downloaded PDFs, screenshots (named clearly)

```markdown
# Sources — {slug}

| URL | Description | Accessed | Status |
|-----|-------------|----------|--------|
| https://... | Official Arm KleidiAI overview | 2026-04-10 | LIVE |
```

---

## Draft file format  →  Research/drafts/{slug}-{format}.md

```markdown
# Draft — {Title}
**Format:** substack-post | linkedin | docx | slide-notes
**Target post:** Post N — {title}
**Corpus sources used:** [list topic slugs]
**Status:** RAW | REVIEWED | APPROVED | PUBLISHED

---

{content}

---
## Claims requiring verification
- [ ] Claim text — [NEEDS RESEARCH]
```

---

## Code file conventions  →  Research/code/

- One script per purpose. Named descriptively: `scrape_arm_releases.py`, `verify_claims.py`
- Every script has a docstring: what it does, inputs, outputs, dependencies
- Test scripts named `test_{script_name}.py`
- No notebooks in code/. If analysis requires a notebook, save to documents/

---

## _ALERTS.md  →  Research/_ALERTS.md

Breaking changes, deprecations, or major announcements that affect published posts.
Written by arm-update. Reviewed by human before acting.

```markdown
## ALERT — YYYY-MM-DD
**Topic affected:** {slug}
**Change:** Description
**Posts affected:** Post N
**Action required:** Update live post | Note only | Urgent correction
```
