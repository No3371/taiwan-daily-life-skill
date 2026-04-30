# Patch: Taiwan Daily Life Reference Integrity Fix

> **Date:** 2026-05-01
> **Author:** Codex
> **Directive:** Fix the reference-integrity problems identified by `2605010513-taiwan-daily-life-reference-integrity-redteam.md`: wrong/stale numbers, broken links, bad URLs, weak references, and missing source anchors/update dates. Prioritize LINE Pay URL, conscription agency URL/name, land transcript ownership check URL, NIA e-service route/address-change source, advisory hotline source anchors/update dates, and high-risk generic homepage routes for admin claims.
> **Source Plan:** Direct; context from `2605010513-taiwan-daily-life-reference-integrity-redteam.md`
> **Result:** Success

---

## Summary

Replaced reported dead/stale routes with current official anchors. Added dated hotline source anchors and README maintenance rule so future exact admin/hotline claims do not rest on generic homepages.

---

## Changes

### Broken URL Fixes

**Files:** `references/banking-fraud-insurance.md`, `references/government-identity.md`, `references/housing-utilities-neighborhood.md`
**Change Type:** Modified
**What Changed:**
- `references/banking-fraud-insurance.md:29` replaces broken LINE Pay `/tw` route with `https://pay.line.me/portal/tw`.
- `references/government-identity.md:34-35` replaces `oa.immigration.gov.tw` with NIA `申辦服務` and specific address-change FAQ.
- `references/government-identity.md:47` updates military-service owner from obsolete `內政部役政署` / `nca.gov.tw` to `內政部役政司 Department of Conscription Administration` / `https://dca.moi.gov.tw/`.
- `references/housing-utilities-neighborhood.md:27-28` replaces dead land e-service host with 全國地政電子謄本系統, land gateway, and gov.tw validation anchor.

**Why:** Red-team found primary routes returning 404/DNS failure or obsolete agency identity.

---

### Source Anchors For High-Risk Claims

**Files:** `references/government-identity.md`, `references/housing-utilities-neighborhood.md`, `references/nhi-healthcare.md`, `references/weather-earthquakes-holidays-closures.md`
**Change Type:** Modified
**What Changed:**
- `references/government-identity.md:39,51` adds NIA 1990 source/language-hours anchor and address-change citation rule.
- `references/housing-utilities-neighborhood.md:30,35,50` replaces MOI homepage lease route with Administrative Yuan consumer standard-contract page and adds anti-scam e-transcript fallback guidance.
- `references/nhi-healthcare.md:26,40,43,45,53` adds canonical NHIA ARC enrollment, HPA pregnancy/adult preventive-care, and TFDA personal-medicine import pages.
- `references/weather-earthquakes-holidays-closures.md:31` adds MOL legal anchor for private-sector holiday/labor-day questions.

**Why:** Exact eligibility/deadline/admin claims need current official source pages, not homepage + search fallback only.

---

### Hotline Audit Metadata

**Files:** `references/emergency-safety.md`, `README.md`
**Change Type:** Modified
**What Changed:**
- `references/emergency-safety.md:50-67` adds `Hotline Source Anchors`, last checked `2026-05-01 +08:00`, official URLs, and scope/hour caveats for advisory and emergency-adjacent numbers.
- `README.md:50` adds maintenance rule requiring exact official URL, supported claim, and last-checked/update-date metadata for high-risk admin claims and advisory hotlines.

**Why:** Future agents/maintainers need per-number provenance before quoting advisory hours, language support, fees, or eligibility.

---

## Verification

**Method:** Official source opens + static audit.

**Evidence:**
```text
Official sources opened:
- LINE Pay Taiwan: https://pay.line.me/portal/tw
- DCA/役政司: https://dca.moi.gov.tw/
- gov.tw land e-transcript service: https://www.gov.tw/News_Content_2_379465
- NIA services + address FAQ: https://www.immigration.gov.tw/5385/7244/ and https://www.immigration.gov.tw/5385/12162/12197/371903/
- NIA 1990, MOHW hotline list, WDA 1955, CPC 1950, TFDA 1919, HPA, NHIA, MOL law pages

rg "pay\.line\.me/tw|www\.nca\.gov\.tw|eservices\.land\.moi\.gov\.tw|oa\.immigration\.gov\.tw"
=> no matches

rg "https://www\.moi\.gov\.tw|https://www\.fda\.gov\.tw/eng|https://www\.mol\.gov\.tw; search|https://www\.hpa\.gov\.tw;"
=> no matches

git diff --check
=> pass; only Git CRLF normalization warnings
```

**Status:** PASS

---

## Fix Audit

| Red-Team Issue | Audit Result |
|---|---|
| LINE Pay URL | Fixed; old URL absent; current portal route present. |
| Conscription agency URL/name | Fixed; obsolete agency/host absent; 役政司/DCA present. |
| Land transcript ownership check URL | Fixed; dead host absent; e-transcript + gov.tw validation anchor present. |
| NIA e-service route/address-change source | Fixed; dead host absent; NIA service route + FAQ source present. |
| Advisory hotline source anchors/update dates | Fixed; source-anchor table added with last-checked date and official source notes. |
| High-risk generic homepage routes | Fixed for reported routes: lease, NHI ARC enrollment, TFDA medicine import, MOL labor holiday, HPA pregnancy/adult preventive care. |

Residual risk: government deep links still require periodic link checks; README now documents source-anchor rule.

---

## Impact on Related Projex

| Document | Relationship | Update Made |
|---|---|---|
| `2605010513-taiwan-daily-life-reference-integrity-redteam.md` | Source context | Not modified; remains untracked per directive. |

---

## Notes

Patch stayed within owned files: `README.md`, `references/*.md`, `.projex/closed/*.md`.
