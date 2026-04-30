# Taiwan Daily Life Reference Split Plan

> **Status:** Complete
> **Completed:** 2026-05-01
> **Walkthrough:** `2605010502-taiwan-daily-life-reference-split-walkthrough.md`
> **Created:** 2026-05-01
> **Author:** Codex
> **Source:** Direct request
> **Related Projex:** `2604302239-taiwan-daily-life-scenario-workflows-revision-plan.md`, `2604302239-taiwan-daily-life-scenario-workflows-revision-walkthrough.md`, `2604302342-taiwan-daily-life-correctness-fix-patch.md`, `2604302355-taiwan-daily-life-links-numbers-reference-fix-patch.md`
> **Worktree:** Yes

---

## Summary

Split `SKILL.md` from monolithic routing database into operating playbook + per-domain references. `SKILL.md` keeps universal answer behavior, source-truth rules, status variables, common need patterns, scenario/action playbooks, cross-domain routing rules, emergency-first data, and a complete domain lookup map. Detailed domain tables, URLs, hotlines, Chinese search terms, and domain edge cases move into `references/`.

**Scope:** `taiwan-daily-life` skill docs only: `SKILL.md`, `README.md`, new domain `references/*.md`.
**Estimated Changes:** 19 files: 1 rewrite, 1 README update, 17 new reference files.

---

## Objective

### Problem / Gap / Need

Current `SKILL.md` is ~690 lines and packs all routing data into the runtime loader. Activation should still provide enough behavior/playbook context to answer well, but agents should not scan every detailed domain table before knowing the applicable domain. The skill should load universal operating rules and playbooks first, then read only the relevant domain reference file(s).

### Success Criteria

- [ ] `SKILL.md` no longer contains the full detailed domain routing tables from current lines 116-634.
- [ ] `SKILL.md` keeps universal behavior: `Language Policy`, `Answering Workflow`, `Agent Output Policy`, `Source Truth Levels`, `Status Variables`, `Common User Need Patterns`, `Scenario Playbooks`, `Cross-Domain Routing Rules`, and `What This Skill Does NOT Cover`.
- [ ] `SKILL.md` keeps emergency immediate-action numbers inline: `110`, `119`, `112`, `113`, `165`, `1925`, `1955`.
- [ ] Every current detailed domain section exists in a dedicated `references/*.md` file with no intentional loss of routing rows, URLs, hotlines, Chinese search terms, or key notes.
- [ ] Reference files preserve current corrected source details from latest patches: RIS `/app/portal/20`, NPA police certificate `/E7WebO/`, NHIA enrollment route, eTax alien route, NCC complaint routes, and scoped `1955`.
- [ ] README documents new ownership: `SKILL.md` is operating playbook + lookup map; `references/` contains detailed domain routes.

### Out of Scope

- No source freshness audit or new Taiwan policy research.
- No correctness rewrites beyond mechanical relocation and minor wording needed for loader/reference boundaries.
- No new domains unless required to house existing content.
- No automated reference-loader tooling.

---

## Context

### Current State

`SKILL.md` currently contains:

- Frontmatter + title/freshness timestamp: lines 1-19.
- Universal rules: `Core Principle`, `Language Policy`, `Answering Workflow`, `Agent Output Policy`, `Source Truth Levels`: lines 21-65.
- Classifiers/playbooks: `Common User Need Patterns`, `Status Variables`, `Scenario Playbooks`: lines 67-112.
- 17 detailed domain sections: lines 116-634.
- `Cross-Domain Routing Rules`: lines 638-680.
- `What This Skill Does NOT Cover`: lines 684-689.

Keep all non-domain policy/playbook/cross-domain sections in `SKILL.md`. Split only current detailed domain sections.

### Key Files

| File | Role | Change Summary |
|------|------|----------------|
| `SKILL.md` | Runtime operating playbook + lookup map | Keep universal behavior, need patterns, scenario playbooks, cross-domain rules, emergency immediate numbers, and domain lookup map; remove detailed domain tables. |
| `README.md` | Human overview | Document split ownership and maintenance rules. |
| `references/government-identity.md` | Domain ref | Move current domain 1. |
| `references/nhi-healthcare.md` | Domain ref | Move current domain 2. |
| `references/taxation.md` | Domain ref | Move current domain 3. |
| `references/housing-utilities-neighborhood.md` | Domain ref | Move current domain 4. |
| `references/banking-fraud-insurance.md` | Domain ref | Move current domain 5. |
| `references/education-childcare-family.md` | Domain ref | Move current domain 6. |
| `references/work-labor-rights.md` | Domain ref | Move current domain 7. |
| `references/transportation-vehicles.md` | Domain ref | Move current domain 8. |
| `references/telecom-digital-life.md` | Domain ref | Move current domain 9. |
| `references/mail-parcels-consumer-life.md` | Domain ref | Move current domain 10. |
| `references/family-pets-life-events.md` | Domain ref | Move current domain 11. |
| `references/elder-care-disability-social-welfare.md` | Domain ref | Move current domain 12. |
| `references/environment-public-health.md` | Domain ref | Move current domain 13. |
| `references/weather-earthquakes-holidays-closures.md` | Domain ref | Move current domain 14. |
| `references/legal-process-mediation.md` | Domain ref | Move current domain 15. |
| `references/civil-defense-alerts-wartime.md` | Domain ref | Move current domain 16. |
| `references/emergency-safety.md` | Domain ref | Move current domain 17 details; `SKILL.md` keeps immediate numbers inline. |

### Dependencies

- **Requires:** Existing corrected `SKILL.md` baseline on `main`.
- **Blocks:** Future smaller correctness audits by reference file.

### Constraints

- `SKILL.md` must remain useful without reading references for universal answer behavior and scenario/action sequencing.
- `SKILL.md` must remain enough for an agent to choose domain files without opening all references.
- Emergency user flow must not require reference lookup before showing `110`, `119`, `113`, `165`, `1925`, or `1955` where relevant.
- Reference links must be relative and simple: `references/<name>.md`.
- Do not introduce stale exact figures; preserve current "verify before quoting" rules.
- Use ASCII file names for portability; keep Chinese terms inside Markdown content.

### Assumptions

- Runtime agents can read relative domain files referenced from `SKILL.md`.
- `references/` at skill root is acceptable; no existing folder conflicts.
- Mechanical split may reuse current domain content verbatim inside references, with only headings adjusted.
- `Last updated` can be changed to execution timestamp only if executor performs the split then verifies content placement.

### Impact Analysis

- **Direct:** Skill activation keeps operating guidance but detailed domain routing moves to references.
- **Adjacent:** README maintenance docs and future route fixes must target reference files for domain details.
- **Downstream:** Agents can still use `SKILL.md` for behavior/playbooks; source routes and domain-specific details require relevant references.

---

## Implementation

### Overview

Create `references/` and move each current detailed domain section into a separate file. Rewrite `SKILL.md` as operating playbook + domain router: keep universal rules, status variables, common need patterns, scenario playbooks, cross-domain rules, emergency numbers, and lookup matrix with trigger cues. Remove only the detailed domain tables from `SKILL.md`.

### Step 1: Move Each Domain Section To Its Own Reference

**Objective:** Create one reference file per current detailed domain section.
**Confidence:** High
**Depends on:** None

**Files:**
- `references/government-identity.md`
- `references/nhi-healthcare.md`
- `references/taxation.md`
- `references/housing-utilities-neighborhood.md`
- `references/banking-fraud-insurance.md`
- `references/education-childcare-family.md`
- `references/work-labor-rights.md`
- `references/transportation-vehicles.md`
- `references/telecom-digital-life.md`
- `references/mail-parcels-consumer-life.md`
- `references/family-pets-life-events.md`
- `references/elder-care-disability-social-welfare.md`
- `references/environment-public-health.md`
- `references/weather-earthquakes-holidays-closures.md`
- `references/legal-process-mediation.md`
- `references/civil-defense-alerts-wartime.md`
- `references/emergency-safety.md`

**Changes:**

For each current domain:

```markdown
# <Domain Title>

## Reference Fit

Use this file when the user need involves:
- <specific issues owned by this domain>
- <common Chinese/local terms that indicate this domain>
- <admin status/context that changes this domain's routing>

Do not use this file as the main route when:
- <nearby issue that belongs to another reference>
- <emergency/safety path that must be handled before this domain>

Adjacent references:
- `<references/nearby-domain.md>` for <boundary condition>
- `<references/another-domain.md>` for <boundary condition>

Fast disambiguators:
- Ask/verify <one detail that determines whether this reference applies>.
- Ask/verify <one detail that determines which adjacent reference applies>.

## Primary Routing
<current table>

## Key Routing Notes
<current bullets>
```

Move current line ranges:

| Current Section | Target |
|---|---|
| lines 116-152 | `references/government-identity.md` |
| lines 156-195 | `references/nhi-healthcare.md` |
| lines 199-224 | `references/taxation.md` |
| lines 227-266 | `references/housing-utilities-neighborhood.md` |
| lines 269-295 | `references/banking-fraud-insurance.md` |
| lines 299-323 | `references/education-childcare-family.md` |
| lines 327-355 | `references/work-labor-rights.md` |
| lines 359-387 | `references/transportation-vehicles.md` |
| lines 391-414 | `references/telecom-digital-life.md` |
| lines 418-439 | `references/mail-parcels-consumer-life.md` |
| lines 443-463 | `references/family-pets-life-events.md` |
| lines 467-492 | `references/elder-care-disability-social-welfare.md` |
| lines 496-511 | `references/environment-public-health.md` |
| lines 515-539 | `references/weather-earthquakes-holidays-closures.md` |
| lines 543-564 | `references/legal-process-mediation.md` |
| lines 568-584 | `references/civil-defense-alerts-wartime.md` |
| lines 588-634 | `references/emergency-safety.md` |

Do not move current universal policy/playbook sections:

- `Language Policy`
- `Answering Workflow`
- `Agent Output Policy`
- `Source Truth Levels`
- `Common User Need Patterns`
- `Status Variables To Check Only When Relevant`
- `Scenario Playbooks`
- `Cross-Domain Routing Rules`
- `What This Skill Does NOT Cover`

`Reference Fit` should not duplicate the full `SKILL.md` lookup row. It should help an agent already reading the file decide whether to use it, switch to an adjacent file, or combine references.

**Rationale:** One file per domain gives agents precise lookup targets and makes future audits smaller. The fit block makes each reference useful during candidate scanning, not just after a perfect lookup. Keeping operating/playbook content in `SKILL.md` preserves the skill's core behavior without requiring a second read for every answer.

**Verification:**

```powershell
rg -n "ris.gov.tw/app/portal/20|eli.npa.gov.tw/E7WebO|nhi.gov.tw/en/np-5-2|etax.nat.gov.tw/etwmain/alien-tax-service|cabletvweb.ncc.gov.tw/pop30|1955" references
rg -n "^# " references
rg -n "Reference Fit|Do not use this file as the main route|Adjacent references|Fast disambiguators" references
```

Expected: corrected routes present; 17 reference files have top-level headings and fit blocks.

**If this fails:** Compare target file against source line range and restore missing rows before editing `SKILL.md`.

---

### Step 2: Rewrite SKILL.md As Operating Playbook And Domain Lookup Map

**Objective:** Keep universal behavior/playbooks in `SKILL.md`; replace detailed domain database with reference lookup.
**Confidence:** Medium
**Depends on:** Step 1

**Files:**
- `SKILL.md`

**Changes:**

Keep frontmatter description materially unchanged. Replace body after title/timestamp with this structure:

```markdown
# 台灣生活導航 — Taiwan Daily Life Navigation Index

Last updated: <execution timestamp> +08:00 (Asia/Taipei)

## Core Principle
<keep current routing-index principle, revised to say detailed domain routes live in references/>

## Language Policy
<keep current section>

## Answering Workflow
<keep current section>

## Agent Output Policy
<keep current section>

## Source Truth Levels
<keep current section>

## Common User Need Patterns
<keep current section>

## Status Variables To Check Only When Relevant
<keep current section>

## Scenario Playbooks
<keep current section>

## Emergency First
| Need | Immediate route |
|---|---|
| Police danger/crime | 110 |
| Fire/ambulance/rescue | 119 |
| Mobile emergency routing when 110/119 cannot connect/no SIM | 112 -> 0 police / 9 fire-ambulance |
| Domestic violence/child/sexual assault | 113 |
| Fraud | 165 |
| Suicide/self-harm crisis | 1925; 119/110 if immediate danger |
| Migrant/foreign-worker labor rights/interpretation | 1955 |

Read `references/emergency-safety.md` after immediate action when details are needed.

## Domain Reference Lookup
| User need / trigger terms | Read |
|---|---|
| Household registration, National ID, 戶籍謄本, 戶政, ARC/APRC, NIA, Gold Card, work permit status, MyData, 自然人憑證/TW FidO, police certificate, notarization/authentication, voting, military service | `references/government-identity.md` |
| NHI, clinic/hospital, health records, NHI card, pharmacy, pregnancy, vaccines, CDC, TFDA, food safety, mental health, addiction | `references/nhi-healthcare.md` |
| Income tax, 183 days, withholding, tax ID, deductions, business tax, property/vehicle local taxes, fuel fee, e-invoice | `references/taxation.md` |
| Rentals, landlord, lease, deposit, electricity/water/gas, address change, property transcript, garbage, bulky waste, neighborhood nuisance, internet comparison | `references/housing-utilities-neighborhood.md` |
| Bank accounts, cards, fraud transfer, remittance, credit report, stocks, FSC/insurance disputes, labor insurance record, debt, invoice prize bank account | `references/banking-fraud-insurance.md` |
| Public school, school district, transfer, bilingual/international school, university, Mandarin, TOCFL, scholarships, daycare, childcare subsidy, special education | `references/education-childcare-family.md` |
| Wages, overtime, leave, termination, migrant worker support, work permit, workplace injury/safety/harassment, unpaid wages, unemployment, labor insurance/pension, mediation, freelancer admin | `references/work-labor-rights.md` |
| MRT/bus/TRA/THSR, disruption, EasyCard/iPASS, YouBike, license, vehicle inspection, traffic fines, taxes, parking, towing, road closure, taxi, lost item, airport, accident | `references/transportation-vehicles.md` |
| SIM/eSIM, mobile plan, telecom/broadband dispute, government digital identity, ARC/ID login, OTP, phone loss, portal outage, convenience-store digital tasks | `references/telecom-digital-life.md` |
| Post office, registered letter, parcel pickup, customs, consumer dispute, product/food safety, e-invoice, printing/scanning, marketplace/delivery dispute | `references/mail-parcels-consumer-life.md` |
| Marriage/divorce/birth/death, same-sex marriage, baby NHI, adoption, inheritance, pregnancy documents, pets, pet import, funeral/death of foreign national | `references/family-pets-life-events.md` |
| Long-term care, disability certificate, assistive devices, accessible transport, elder welfare, rent/social housing subsidy, low income, homeless shelter, caregiver stress, dementia, sign language, disability parking, accessibility complaint, foreign caregiver | `references/elder-care-disability-social-welfare.md` |
| AQI, tap water quality/outage, dengue/pests/sanitation, CDC city measures, heat/cold/typhoon/rain alerts, pollution/noise/odor complaints, beach/mountain/river safety | `references/environment-public-health.md` |
| Weather forecast, earthquake report, typhoon stop-work/school, office calendar, make-up workday, Labor Day, school/bank/post/clinic closure, transport disruption, road closure, system outage | `references/weather-earthquakes-holidays-closures.md` |
| Legal aid, mediation, police report, stalking/harassment, missing person, cybercrime, sexual harassment, small claim/court, protection order, POA/will/notarization | `references/legal-process-mediation.md` |
| Air-raid alert/shelter, Wan-An drill, disaster shelter, national phone alert, civil-defense rumor | `references/civil-defense-alerts-wartime.md` |

## Cross-Domain Routing Rules
<keep current section>

## What This Skill Does NOT Cover
<keep current section>
```

Remove only the detailed domain sections. Do not create or reference `references/answering-policy.md` or `references/scenario-playbooks.md`.

**Rationale:** This keeps `SKILL.md` as the fast, behavior-rich router. Emergency numbers remain inline because emergency answers should not wait for file reads.

**Verification:**

```powershell
rg -n "Language Policy|Answering Workflow|Agent Output Policy|Source Truth Levels|Common User Need Patterns|Scenario Playbooks|Cross-Domain Routing Rules|What This Skill Does NOT Cover" SKILL.md
rg -n "Primary routing|Key routing notes|\\| Question type \\| Go to \\|" SKILL.md
rg -n "references/.+\\.md" SKILL.md
rg -n "references/answering-policy.md|references/scenario-playbooks.md" SKILL.md
```

Expected:

- First command finds retained policy/playbook sections.
- Second command returns no detailed domain-table markers in `SKILL.md`.
- Third command lists every domain reference file.
- Fourth command returns no matches.

**If this fails:** Reinsert missing retained sections or lookup cues; do not reinsert full domain tables.

---

### Step 3: Update README For Split Ownership

**Objective:** Make human maintenance docs match new structure.
**Confidence:** High
**Depends on:** Steps 1-2

**Files:**
- `README.md`

**Changes:**

Update `Files` section:

```markdown
- `SKILL.md` - operating playbook, emergency-first rules, cross-domain routing, and domain reference lookup map.
- `references/` - detailed routing references by domain. This is where domain source routes, hotlines, portals, search terms, and edge-case notes live.
- `README.md` - human-facing overview and maintenance notes.
```

Update maintenance rules:

```markdown
Keep `SKILL.md` concise but operational: universal answer behavior, need-pattern/action playbooks, cross-domain rules, emergency immediate-action numbers, and complete lookup cues.
When adding or moving domain reference content, update both the target `references/*.md` file and the `SKILL.md` lookup row so agents can find it.
Detailed domain route corrections belong in the relevant reference file; mirror only enough cue text in `SKILL.md` for lookup.
```

**Rationale:** Avoids future contributors putting the full domain database back into `SKILL.md` while protecting retained playbooks.

**Verification:** `rg -n "references/|lookup map|operating playbook|cross-domain" README.md`.

**If this fails:** Leave README with minimal `references/` mention; runtime behavior lives in `SKILL.md`.

---

### Step 4: Content Preservation Audit

**Objective:** Prove split did not drop important routes or accidentally move retained behavior.
**Confidence:** High
**Depends on:** Steps 1-3

**Files:**
- `SKILL.md`
- `references/*.md`
- `README.md`

**Changes:**

No content changes unless audit finds missing routes. Run checks:

```powershell
rg -n "ris.gov.tw|immigration.gov.tw|nhi.gov.tw|etax.nat.gov.tw|mol.gov.tw|mvdis.gov.tw|cwa.gov.tw|dgpa.gov.tw|laf.org.tw|prepare.mnd.gov.tw" references
rg -n "110|119|112|113|165|1925|1955|1990|1922|1966|1957|1950|1919|0800-870-870|0800-770-885|0800-507-272" references SKILL.md
rg -n "Language Policy|Answering Workflow|Agent Output Policy|Source Truth Levels|Common User Need Patterns|Scenario Playbooks|Cross-Domain Routing Rules|What This Skill Does NOT Cover" SKILL.md
rg -n "Primary routing|Key routing notes|\\| Question type \\| Go to \\|" SKILL.md
rg -n "references/answering-policy.md|references/scenario-playbooks.md" SKILL.md references
```

Expected:

- Official source domains appear under `references/`.
- Emergency/support hotlines appear in `references/`; emergency-first numbers also appear in `SKILL.md`.
- Universal behavior/playbook/cross-domain sections remain in `SKILL.md`.
- Detailed domain table markers do not remain in `SKILL.md`.
- No policy/playbook reference files are created or linked.

**Rationale:** Mechanical split is the main risk; validation should target route retention, retained behavior, and loader compactness.

**If this fails:** Restore missing row/section from original `SKILL.md` source or previous commit, then rerun audit.

---

## Verification Plan

### Automated Checks

- [ ] `rg -n "^# " references` shows 17 reference files with headings.
- [ ] `rg -n "Reference Fit|Do not use this file as the main route|Adjacent references|Fast disambiguators" references` confirms each reference has candidate-scanning guidance.
- [ ] `rg -n "Primary routing|Key routing notes|\\| Question type \\| Go to \\|" SKILL.md` returns no full domain-table markers.
- [ ] `rg -n "references/.+\\.md" SKILL.md` lists all domain reference files.
- [ ] `rg -n "Language Policy|Answering Workflow|Agent Output Policy|Source Truth Levels|Common User Need Patterns|Scenario Playbooks|Cross-Domain Routing Rules|What This Skill Does NOT Cover" SKILL.md` confirms universal behavior/playbooks stayed.
- [ ] `rg -n "references/answering-policy.md|references/scenario-playbooks.md" SKILL.md references` returns no matches.
- [ ] `rg -n "ris.gov.tw/app/portal/20|eli.npa.gov.tw/E7WebO|nhi.gov.tw/en/np-5-2|etax.nat.gov.tw/etwmain/alien-tax-service|cabletvweb.ncc.gov.tw/pop30" references` finds latest corrected routes.
- [ ] `rg -n "110|119|112|113|165|1925|1955" SKILL.md references/emergency-safety.md` confirms immediate numbers preserved.

### Manual Verification

- [ ] Read `SKILL.md` alone and confirm an agent can choose references for household registration, NHI, tax, rent dispute, scam, school enrollment, labor dispute, train disruption, SIM problem, parcel/customs, pet import, elder care, air quality, typhoon closure, legal aid, air-raid alert, and emergency.
- [ ] Confirm `SKILL.md` alone still gives answer behavior, output artifact expectations, source-truth levels, status-variable prompts, common need patterns, scenario playbooks, and cross-domain routing rules.
- [ ] Spot-check 3 moved domains against old line ranges: one early (`government-identity`), one middle (`transportation-vehicles`), one late (`emergency-safety`).
- [ ] Confirm `SKILL.md` does not force emergency users through reference lookup before numbers/actions.

### Acceptance Criteria Validation

| Criterion | How to Verify | Expected Result |
|-----------|---------------|-----------------|
| Monolithic domain tables removed | `rg` table markers in `SKILL.md` | No detailed domain table markers remain. |
| Universal behavior/playbooks retained | `rg` retained headings in `SKILL.md` | All policy/playbook/cross-domain sections remain. |
| Lookup cues complete | Manual read of `Domain Reference Lookup` | Every old major domain maps to a file; cross-domain patterns remain directly in `SKILL.md`. |
| Details preserved | Targeted `rg` for corrected URLs/hotlines and domain headings | All important domain routes live in `references/`. |
| README updated | `rg "references/|lookup map|operating playbook" README.md` | New layout and maintenance rule documented. |

---

## Rollback Plan

Per-step rollback is noted above. If full implementation must be abandoned:

1. Restore `SKILL.md` and `README.md` from pre-execution version.
2. Delete newly added `references/*.md`.
3. Rerun `rg -n "Domain Index|Cross-Domain Routing Rules|Emergency Numbers" SKILL.md` to confirm monolithic file is back.

---

## Notes

### Risks

- **Lost route during manual split:** Mitigate with source line-range mapping and targeted `rg` audit.
- **Loader too thin:** Mitigate by keeping universal behavior, playbooks, cross-domain rules, emergency numbers, and complete trigger vocabulary in `SKILL.md`.
- **Emergency regression:** Mitigate by keeping emergency immediate-action numbers inline in `SKILL.md`.
- **Future drift:** Mitigate with README rule requiring lookup-map updates whenever domain reference files change.

### Open Questions

- None.

