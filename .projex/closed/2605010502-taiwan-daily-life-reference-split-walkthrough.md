# Walkthrough: Taiwan Daily Life Reference Split

> **Execution Date:** 2026-05-01
> **Completed By:** Codex
> **Source Plan:** `2605010007-taiwan-daily-life-reference-split-plan.md`
> **Execution Log:** `2605010007-taiwan-daily-life-reference-split-log.md`
> **Audit:** `2605010502-taiwan-daily-life-reference-split-audit.md`
> **Result:** Success

---

## Summary

`SKILL.md` was split from monolithic domain routing database into compact operating playbook + lookup map. Seventeen domain reference files now hold detailed routes, URLs, hotlines, search terms, and domain edge cases. Audit found and fixed generic reference-fit guidance plus malformed execution-log artifacts before close.

---

## Objectives Completion

| Objective | Status | Notes |
|---|---|---|
| Move each detailed domain section to a dedicated reference file | Complete | 17 `references/*.md` files created with primary routing and key notes preserved. |
| Rewrite `SKILL.md` as operating playbook and lookup map | Complete | Universal behavior, scenario playbooks, cross-domain rules, and emergency-first numbers retained; detailed domain tables removed. |
| Update README for split ownership | Complete | README now documents `SKILL.md` vs `references/` maintenance responsibilities. |
| Content preservation audit | Complete | Route/hotline checks passed; audit strengthened candidate-scanning blocks and cleaned execution log. |

---

## Execution Detail

### Step 1: Move Each Domain Section To Reference

**Planned:** Create one reference file per current detailed domain section.

**Actual:** Created 17 `references/*.md` files and moved the former detailed domain routing bodies into them. Added `Reference Fit`, adjacent-reference, and disambiguator blocks.

**Deviation:** Audit found the first fit blocks were too generic. Commit `56f2f19` rewrote all 17 fit blocks with domain-specific triggers, boundaries, adjacent references, and disambiguators.

**Verification:** `rg -n "^# " references` found 17 top-level headings; `rg -n "Reference Fit|Do not use this file as the main route|Adjacent references|Fast disambiguators" references` found required sections in every reference.

### Step 2: Rewrite `SKILL.md`

**Planned:** Keep universal rules/playbooks and replace detailed domain tables with lookup rows.

**Actual:** `SKILL.md` now contains Core Principle, Language Policy, Answering Workflow, Agent Output Policy, Source Truth Levels, Common User Need Patterns, Status Variables, Scenario Playbooks, Emergency First, Domain Reference Lookup, Cross-Domain Routing Rules, and scope exclusions.

**Deviation:** None.

**Verification:** Detailed table marker grep returned no matches in `SKILL.md`; retained-section grep found all required operating sections.

### Step 3: Update README

**Planned:** Document split ownership and maintenance rules.

**Actual:** README Files and Maintenance Rules sections now explain that `SKILL.md` owns operational behavior/lookup and `references/` owns domain detail.

**Deviation:** None.

**Verification:** `rg -n "references/|lookup map|operating playbook|cross-domain" README.md` found expected ownership text.

### Step 4: Content Preservation + Audit Fixes

**Planned:** Prove important routes and emergency numbers were preserved.

**Actual:** Corrected source details remain in references; emergency immediate numbers remain in both `SKILL.md` and `references/emergency-safety.md`. Audit report `2605010502-taiwan-daily-life-reference-split-audit.md` records fixes.

**Deviation:** Audit added one extra commit after execution completion: `56f2f19 projex: audit reference split fixes`.

**Verification:** Corrected-route grep found RIS `/app/portal/20`, NPA `/E7WebO/`, NHIA enrollment, eTax alien route, and NCC complaint route. `git diff --check` reported only expected line-ending warnings, no whitespace errors.

---

## Complete Change Log

**Derived from:** `git diff --stat main..HEAD`

### Files Created

| File | Purpose | In Plan? |
|---|---|---|
| `references/*.md` (17 files) | Detailed domain routing refs | Yes |
| `.projex/2605010007-taiwan-daily-life-reference-split-log.md` | Execution record | Workflow artifact |
| `.projex/2605010502-taiwan-daily-life-reference-split-audit.md` | Audit report and fix record | Audit artifact |
| `.projex/closed/2605010502-taiwan-daily-life-reference-split-walkthrough.md` | Close walkthrough | Close artifact |

### Files Modified

| File | Changes | In Plan? |
|---|---|---|
| `SKILL.md` | Removed detailed domain tables; added Emergency First + Domain Reference Lookup | Yes |
| `README.md` | Updated file ownership and maintenance rules | Yes |
| `.projex/2605010007-taiwan-daily-life-reference-split-plan.md` | Marked complete and linked walkthrough | Close artifact |
| `references/*.md` | Audit tightened `Reference Fit` blocks | Audit fix |

---

## Success Criteria Verification

| Criterion | Method | Result |
|---|---|---|
| Monolithic domain tables removed from `SKILL.md` | `rg -n "Primary routing|Key routing notes|\\| Question type \\| Go to \\|" SKILL.md` | Pass |
| Universal behavior/playbooks retained | retained-heading `rg` in `SKILL.md` | Pass |
| Emergency numbers inline | `rg -n "110|119|112|113|165|1925|1955" SKILL.md references/emergency-safety.md` | Pass |
| Every domain exists in `references/` | `rg -n "^# " references` | Pass |
| Corrected routes preserved | targeted corrected-route `rg` | Pass |
| README updated | README ownership `rg` | Pass |

**Overall:** 6/6 criteria passed.

---

## Deviations from Plan

- Audit strengthened `Reference Fit` blocks after finding the initial blocks were boilerplate. Impact positive; no route content changed intentionally.
- Audit cleaned malformed escape artifacts in the execution log. Impact positive; documentation now readable.

---

## Issues Encountered

- Initial execution generator attempt failed before commit due quoting/helper-name errors; log records restore/regeneration.
- Audit discovered generic fit blocks and emergency self-reference ambiguity; fixed in commit `56f2f19`.

---

## Key Insights

- Mechanical content splits need a second pass on per-file entry guidance; otherwise references exist but are weaker as routing decision aids.
- Emergency reference files need different boundary wording than ordinary domains: immediate action first, references only after danger handling.

---

## Recommendations

No immediate follow-up required. Future correctness/source-freshness audits should target individual `references/*.md` files instead of the whole skill.