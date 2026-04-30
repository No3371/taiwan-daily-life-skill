# Patch: Taiwan Daily Life Links Numbers Reference Fix

> **Date:** 2026-04-30
> **Author:** Agent
> **Directive:** orchestrate-projex fix
> **Source Plan:** Direct; latest red-team source `2604302346-taiwan-daily-life-links-numbers-references-redteam.md`
> **Result:** Success

---

## Summary

Patched concrete latest red-team findings in `SKILL.md`: stale/weak tax, RIS, police certificate, telecom/NCC, NHI, and `1955` labor-scope routes. Kept change bounded to routing/reference text; no behavior beyond source selection and label precision.

---

## Changes

### Routing Reference Corrections

**File:** `SKILL.md`
**Change Type:** Modified
**What Changed:**
- `SKILL.md:19` updated freshness timestamp to `2026-04-30 23:55 +08:00`.
- `SKILL.md:135` replaced bare `https://eli.npa.gov.tw` with `https://eli.npa.gov.tw/E7WebO/`; added pickup/postal eligibility verification.
- `SKILL.md:151` replaced stale RIS `/app/portal/364` with RIS `戶政機關通訊錄` `/app/portal/20`.
- `SKILL.md:161` replaced vague NHIA English `"Foreigner" section` route with direct Enrollment page and ARC-holder section label.
- `SKILL.md:205-206` replaced unsupported `www.irs.gov.tw` / `Same:` tax route with eTax alien individual income tax and NTB search fallback.
- `SKILL.md:398-399` replaced `https://tcmc.tw` with NCC HTTPS process page and `https://cabletvweb.ncc.gov.tw/pop30`; kept `0800-034-580`.
- `SKILL.md:601`, `SKILL.md:625`, `SKILL.md:674` scoped `1955` to migrant/foreign-worker labor rights; routed other labor disputes to local labor bureau / Ministry of Labor.

**Why:**
Latest red-team found these exact links/labels credibility-attackable or too broad. Official/current routes exist and are more precise.

---

## Verification

**Method:** Official-source spot check + stale-string scan + focused diff review.

**Result:**
```text
Official search/open checks:
- RIS 戶政機關通訊錄 surfaced at https://www.ris.gov.tw/app/portal/20.
- NHIA English Enrollment surfaced at https://www.nhi.gov.tw/en/np-5-2.html and ARC page at /en/cp-49-fb4a6-24-2.html.
- 警察刑事紀錄證明 surfaced under https://eli.npa.gov.tw/E7WebO/.
- NCC complaint/process refs surfaced at https://www.ncc.gov.tw/Chinese/content.aspx?site_content_sn=3154 and https://cabletvweb.ncc.gov.tw/pop30.
- WDA/MOL 1955 pages frame hotline around foreign/migrant workers, complaint, consultation, protection, and interpretation.

Stale-string scans:
- No matches for `www.irs.gov.tw`.
- No matches for `ris.gov.tw/app/portal/364`.
- No matches for `tcmc.tw`.
- No matches for `Labor Exploitation`.
- No matches for `1955 (labor)`.
- No matches for `"Foreigner" section`.

Diff size:
- `git diff --numstat -- SKILL.md` → `11 11 SKILL.md`
```

**Status:** PASS

---

## Impact on Related Projex

| Document | Relationship | Update Made |
|---|---|---|
| `2604302346-taiwan-daily-life-links-numbers-references-redteam.md` | Latest finding source | No edit; findings addressed in `SKILL.md` and this patch record |
| `2604302342-taiwan-daily-life-correctness-fix-patch.md` | Prior related patch | No edit; this patch follows up post-patch red-team findings |
| `2604302325-taiwan-daily-life-correctness-audit.md` | Prior audit context | No edit; latest red-team superseded concrete fix list |
| `2604302333-taiwan-daily-life-correctness-redteam.md` | Prior red-team context | No edit; latest red-team superseded concrete fix list |

---

## Notes

Patch intentionally did not commit untracked auxiliary audit/red-team artifacts; they remain outside patch lifecycle unless human requests commit.
