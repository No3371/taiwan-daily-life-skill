# Patch: Taiwan Daily Life Correctness Fix

> **Date:** 2026-04-30
> **Author:** Agent
> **Directive:** orchestrate-projex fix
> **Source Plan:** Direct
> **Result:** Success

---

## Summary

Fixed concrete correctness findings from `2604302325-taiwan-daily-life-correctness-audit.md` and `2604302333-taiwan-daily-life-correctness-redteam.md`. Scope: `SKILL.md` routing text only; no workflow restructuring.

---

## Changes

### NHI Eligibility Wording

**File:** `SKILL.md`
**Change Type:** Modified
**What Changed:**
- Line 188 now limits 6-month exceptions to employed ARC holders, specific foreign-professional/dependent categories, and foreign newborns.
- Removed overbroad shorthand implying Gold Card or spouse status alone determines immediate NHI enrollment.

**Why:**
NHIA pages distinguish employment, foreign-professional/dependent, business-owner/self-employed, newborn, and 6-month residence categories. Status labels alone misroute users.

---

### ARC Address Change

**File:** `SKILL.md`
**Change Type:** Modified
**What Changed:**
- Line 241 changed ARC address-change guidance from universal 15 days to current NIA 30-day guidance for residential address/place-of-service changes.
- Added category/current-source verification caveat.

**Why:**
Prior audit found current NIA guidance conflicts with retained 15-day wording. Route should reflect current source while warning agents to verify user category.

---

### Telecom Disputes

**File:** `SKILL.md`
**Change Type:** Modified
**What Changed:**
- Lines 398-399 now encode sequence: carrier/operator first, unresolved or no reply after 15 days, then 電信服務消費爭議處理中心 / NCC channels.
- Added dispute center `0800-034-580`, `https://tcmc.tw`, NCC `0800-177177`, `0800-201-207`, cable complaint portal, and mobile dialing route.

**Why:**
NCC route is process-based; sending users straight to generic NCC complaints hides required first step and dispute-center escalation.

---

### Legal Aid Hotline

**File:** `SKILL.md`
**Change Type:** Modified
**What Changed:**
- Lines 548 and 623 now specify Legal Aid Foundation / 法律扶助基金會 LAF, `412-8518`, landline direct, mobile add `02`.
- Added menu, hours, language, and issue-scope verification caveat.

**Why:**
LAF phone routes vary by menu, service type, hours, language, and consultation scope. Mobile dialing note prevents failed calls.

---

### Weather Phone Route

**File:** `SKILL.md`
**Change Type:** Modified
**What Changed:**
- Line 608 removed unsupported `1991`.
- Replaced with CWA web/app first plus phone recordings `166` Mandarin / `167` Hakka-Taiwanese-English where available.

**Why:**
CWA sources inspected support web/app and 166/167 routes; prior audit did not verify `1991`.

---

### Payment And URL Cleanup

**File:** `SKILL.md`
**Change Type:** Modified
**What Changed:**
- Line 641 softened convenience-store payment guidance to bill-supported channels, amount limits, deadlines, and supported kiosks.
- Line 277 added URL schemes for LINE Pay and Taiwan Pay.

**Why:**
Convenience-store payment support depends on bill/channel/barcode constraints. URL schemes improve route usability.

---

## Verification

**Method:** Official-source spot check + file grep + diff review.

**Result:**
```text
Implementation commit: 41be7b0 projex(patch): fix daily-life correctness findings

Checked sources:
- NIA address-change guidance: current 30-day address/place-of-service route found.
- NHIA foreign-national enrollment pages: employed ARC holders, six-month baseline, foreign-professional/dependent, and newborn categories found.
- NCC dispute route: carrier first, 15-day reply window, dispute center 0800-034-580, NCC channels found.
- CWA weather routes: web/app and 166/167 phone routes found; 1991 not retained.
- LAF phone consultation: 412-8518, mobile add 02, menu/hours/scope notes found.

Text checks:
- Removed stale ARC "15 days" wording.
- Removed unsupported weather "1991" row.
- Removed "Gold Card, spouse of citizen" shorthand.
- Removed "almost all government payments" wording.
```

**Status:** PASS

---

## Impact on Related Projex

| Document | Relationship | Update Made |
|---|---|---|
| `2604302325-taiwan-daily-life-correctness-audit.md` | Source audit | Referenced; not modified because prior auxiliary artifact remains untracked. |
| `2604302333-taiwan-daily-life-correctness-redteam.md` | Source red team | Referenced; not modified because prior auxiliary artifact remains untracked. |
| `2604302239-taiwan-daily-life-scenario-workflows-revision-plan.md` | Prior related plan | No direct update needed; patch does not execute an open plan objective. |
| `2604302239-taiwan-daily-life-scenario-workflows-revision-walkthrough.md` | Prior related walkthrough | No direct update needed; patch supersedes specific correctness findings via this record. |

---

## Notes

- Patch intentionally does not add a full source registry; human-provided fix scope was concrete discrepancy corrections.
- Two prior auxiliary artifacts remain untracked as they were before this patch workflow.
