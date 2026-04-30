# Patch: Taiwan Daily Life Reference Integrity Conditions

> **Date:** 2026-05-01
> **Author:** Codex
> **Directive:** Patch residual conditions from `2605010525-taiwan-daily-life-reference-integrity-fix-audit.md`: add source/update metadata for residual advisory hotlines, fix MOL Article 37/39 anchor precision, and add tracked-doc link-check convention.
> **Source Plan:** Direct; audit input `2605010525-taiwan-daily-life-reference-integrity-fix-audit.md`; prior patch `2605010522-taiwan-daily-life-reference-integrity-fix-patch.md`
> **Result:** Success

---

## Summary

Addressed conditional audit findings after commits `43322db` and `e99d590`. Added source/update or last-checked metadata beside residual hotline rows, split MOL holiday/wage law anchors into exact Article 37 and Article 39 URLs, and documented a tracked-doc link-check convention.

---

## Changes

### Link-Check Convention

**File:** `README.md`  
**Change Type:** Modified  
**What Changed:**
- Added PowerShell link-check convention for tracked `README.md`, `SKILL.md`, and `references/*.md` docs at `README.md:52`.
- Added instruction to record known-bad or JS-only URLs with last-checked/manual-verification notes near affected rows.

**Why:** Audit condition required practical link-check artifact/convention scoped to tracked routing docs.

---

### Emergency And Advisory Hotline Metadata

**Files:** `references/emergency-safety.md`, `references/legal-process-mediation.md`, `references/telecom-digital-life.md`, `references/nhi-healthcare.md`, `references/taxation.md`, `references/elder-care-disability-social-welfare.md`, `SKILL.md`  
**Change Type:** Modified  
**What Changed:**
- Added CWA `166/167` source/update metadata at `references/emergency-safety.md:41` and source-anchor table row at `references/emergency-safety.md:68`.
- Added LAF `412-8518` source/update metadata in emergency and legal routes at `references/emergency-safety.md:69`, `references/emergency-safety.md:78`, and `references/legal-process-mediation.md:26`.
- Added NCC telecom/cable hotline source/last-checked metadata at `references/telecom-digital-life.md:28-29`.
- Added NHIA `0800-030-598` source/update metadata at `references/nhi-healthcare.md:47`.
- Added tax `0800-000-321` source/update metadata at `references/taxation.md:36`.
- Added MOHW dementia `0800-474-580` source metadata at `references/elder-care-disability-social-welfare.md:36`.
- Tightened `SKILL.md:121` to point agents to emergency reference source anchors when details/hours/scope matter.

**Why:** Audit found hotline provenance incomplete outside `references/emergency-safety.md`.

---

### MOL Labor Holiday Anchor Precision

**File:** `references/weather-earthquakes-holidays-closures.md`  
**Change Type:** Modified  
**What Changed:**
- Replaced imprecise "Article 37/39 via Article 39 URL" with separate direct anchors: Article 37 holiday/rest-day anchor and Article 39 wage-for-holiday-work anchor at `references/weather-earthquakes-holidays-closures.md:31`.
- Added MOL law-system data cutoff `2026-03-31` from the opened MOL law pages.

**Why:** Audit found old row claimed Article 37 support from a URL that landed on Article 39 only.

---

## Verification

**Method:** Local diff/grep plus official source spot-checks.

**Result:**
```text
rg residual targets:
- README.md:52 link-check convention present.
- SKILL.md:121 emergency details/hours/scope/source-anchor pointer present.
- references/emergency-safety.md:68 CWA 166/167 source row present.
- references/emergency-safety.md:69 LAF 412-8518 source row present.
- references/legal-process-mediation.md:26 LAF source/update present.
- references/telecom-digital-life.md:28-29 NCC hotline metadata present.
- references/nhi-healthcare.md:47 NHIA hotline metadata present.
- references/taxation.md:36 tax hotline metadata present.
- references/elder-care-disability-social-welfare.md:36 dementia hotline metadata present.
- references/weather-earthquakes-holidays-closures.md:31 direct Article 37 and Article 39 anchors present.

Local checks:
- `git diff --check` passed; Git reported only LF-to-CRLF working-tree warnings.
- README link-check URL inventory command shape extracted 87 unique tracked-doc URLs without parsing errors.

Official source opens:
- LAF `https://www.laf.org.tw/tel-ext`: hotline `412-8518`, update `2024-07-31`.
- NCC `https://cabletvweb.ncc.gov.tw/pop30/`: `0800-034-580`, `0800-177177`, `02-4128-177`.
- NHIA `https://www.nhi.gov.tw/ch/np-2335-1.html`: `0800-030-598`, update `2023-12-19`.
- NTBT `https://www.ntbt.gov.tw/English/htmlList/5d6b0b486ba04927b88722b6d16bc01b`: `0800-000-321`, update `2026-04-30`.
- MOHW `https://mohw.gov.tw/np-23-1.html`: `0800-474-580`.
- CWA South `https://south.cwa.gov.tw/contact/category/ziSx1649745822gkJu`: `166/167`, update `2022-04-12`.
- MOL Article 37 and 39 direct URLs opened; both show Labor Standards Act with law data cutoff `2026-03-31`.
```

**Status:** PASS

---

## Impact on Related Projex

| Document | Relationship | Update Made |
|---|---|---|
| `2605010525-taiwan-daily-life-reference-integrity-fix-audit.md` | Audit input | Conditions addressed; input left untracked/unmodified. |
| `2605010513-taiwan-daily-life-reference-integrity-redteam.md` | Red-team input | Preserved; no edit or staging. |
| `2605010522-taiwan-daily-life-reference-integrity-fix-patch.md` | Prior patch record | Referenced as prior patch; no edit required. |

---

## Notes

No full live link-check run committed. README now defines the exact tracked-doc link-check command and recording convention; this patch verified the newly added/resolved anchors by official page opens.
