# Taiwan Daily Life Routing Index Scenario Workflow Revision

> **Status:** Blocked
> **Created:** 2026-04-30
> **Author:** Agent
> **Source:** Direct request: "plan-projex revision" after audit
> **Related Projex:** None
> **Worktree:** No

---

## Summary

Revise `taiwan-daily-life` from strong source-routing index → source-routing + agent-action playbook. Add scenario workflows, agent deliverables, status variables, clearer source-truth categories, and brand-neutral language; trim repeated recommendation boilerplate.

**Scope:** `taiwan-daily-life` routing-index docs only.
**Estimated Changes:** 2 files: `SKILL.md`, `README.md`.

**Blocker:** folder is not in a Git repo. Normal projex requirement "plan committed before execution" cannot be satisfied until folder is imported into a repo or Git lifecycle is waived.

---

## Objective

### Problem / Gap / Need

Current `SKILL.md` routes well to agencies, hotlines, portals, and Chinese search terms. It under-specifies what agents should produce for humans facing daily-life friction: checklists, scripts, notice parsing, evidence packets, deadline plans, and scenario sequences. It also contains product-brand wording in human docs; the artifact should be provider-neutral.

### Success Criteria

- [ ] `SKILL.md` keeps routing-index purpose; does not become encyclopedia.
- [ ] Answering workflow tells agents to produce concrete deliverables when useful: checklist | Chinese message/script | deadline/evidence plan | notice/bill interpretation | office-hours/current-status check.
- [ ] Add scenario playbooks for high-frequency daily-life events: moving, official notice, payment/bill, lost document/card/phone, apartment/building problem, failed ARC/ID login, care need, typhoon/earthquake disruption.
- [ ] Add status-variable checklist so agents ask minimal high-impact questions.
- [ ] Reduce repeated recommendation caveats into one reusable rule.
- [ ] `README.md` reflects new "routing + action playbooks" scope.
- [ ] `README.md` and revised `SKILL.md` avoid "Codex skill" or any AI-brand framing; use neutral terms: "routing index", "agent", "assistant", or "instruction set" as appropriate.
- [ ] No exact fees, fines, subsidy thresholds, fare amounts, or deadline claims added without live verification.

### Out of Scope

- No live source audit of every hotline/URL.
- No policy-number update.
- No city-specific schedule tables.
- No restaurant/shop/attraction recommendation database.
- No legal/medical diagnosis content beyond routing and evidence preservation.

---

## Context

### Current State

`SKILL.md` structure:

- `Answering Workflow`: urgency classification, current-info verification, locality/status questions, source preference.
- `Common User Need Patterns`: short list of common needs.
- `Domain Index`: 17 routing domains.
- `Cross-Domain Routing Rules`: reusable handling for bills/forms/office discovery/currentness/closures/disputes.
- `What This Skill Does NOT Cover`: recs, legal advice, medical diagnosis, live news/policy.

Strengths:

- Good high-risk triage: emergency, DV, fraud, labor, legal, weather/closure.
- Good Taiwan-specific routing: 戶政, NIA, NHIA, eTax, BLI, MVDIS, 1999, 里辦公處, 調解委員會.
- Good freshness rule: verify fees/eligibility/deadlines/schedules/current events.

Weaknesses:

- Agent output shape not explicit enough.
- Scenario sequences scattered across domains.
- "Recommendation/comparison" caveat repeated across domains.
- Mandatory provenance note in every response is noisy for ordinary user answers and over-emphasizes implementation mechanics.
- README currently says "Codex skill"; revision should make docs brand-neutral.
- Missing daily-life admin frictions: Minguo date conversion, address parsing, registered mail/admin notices, debt/collections, medical admin, pharmacy/OTC, freelancer/self-employed, rural/offshore constraints.

### Key Files

| File | Role | Change Summary |
|------|------|----------------|
| `SKILL.md` | Runtime routing instructions | Add agent deliverables, status variables, scenario playbooks, source-truth model; trim repeated caveats; neutralize meta wording where appropriate. |
| `README.md` | Human overview | Update scope from routing-only to routing + practical action workflows; remove product-brand wording. |

### Dependencies

- **Requires:** User approval to execute plan.
- **Blocks:** Future `execute-projex` revision.
- **Blocked by:** No Git repo in `taiwan-daily-life` folder for projex commit lifecycle.

### Constraints

- Preserve artifact as routing index, not encyclopedia.
- Prefer official sources; use maps/forums/blogs only as practical/non-authoritative.
- Keep emergency action-first behavior.
- Do not assume user is foreign.
- Maintain English/Chinese service-name policy.
- Avoid bloating `SKILL.md`; add compact playbooks, not long prose.

### Assumptions

- User wants routing-index content revised, not only an external critique.
- Current audit findings are accepted as source direction.
- A later executor may run without full conversation context, so this plan must be self-contained.

### Impact Analysis

- **Direct:** `SKILL.md`, `README.md`.
- **Adjacent:** Future answers using this routing index should become more concrete and less source-list-only.
- **Downstream:** No code/tests. Manual review checks content quality.

---

## Implementation

### Step 1: Revise Workflow Header

**Objective:** Teach agents to produce practical artifacts, not just routes.
**Confidence:** High
**Depends on:** None

**Files:**
- `SKILL.md`

**Changes:**

Insert after current freshness/source rules in `## Answering Workflow`:

```markdown
## Agent Output Policy
- Prefer actionable artifacts when the user's need is concrete: bring-this checklist, Chinese call/LINE script, form/search terms, evidence packet, deadline plan, current-status check, or step sequence.
- For confusing documents/notices/bills, parse what it is, identify sender/authority, extract deadline/amount/location/action, then route to official verification.
- For recurring admin tasks, give sequence first, then offices/links, then what to prepare.
- If online flow fails, provide counter-service fallback and the exact phrase to ask for.
```

Revise artifact-note requirement:

```markdown
- Include provenance/update note only for audits, meta questions about this routing index, or when freshness/currentness affects confidence. For emergencies, never delay life-safety action with metadata.
```

**Rationale:** User-facing daily-life help needs outputs: "what do I do/bring/say now?" Provenance-note-on-every-response creates noise.

**Verification:** `rg -n "Agent Output Policy|Include provenance/update note only" SKILL.md`.

**If this fails:** Revert added block; keep original workflow.

---

### Step 2: Add Status Variables

**Objective:** Give agents a compact checklist for routing questions without over-asking.
**Confidence:** High
**Depends on:** Step 1

**Files:**
- `SKILL.md`

**Changes:**

Add section after `## Common User Need Patterns`:

```markdown
## Status Variables To Check Only When Relevant
- Location: city/county, district, address, school district, route/station.
- Identity/admin: household registration, National ID, ARC/APRC, passport, NHI, natural person certificate/TW FidO.
- Life context: age, student/employer/self-employed status, dependent family, disability/care status, renter/owner/vehicle owner.
- Urgency: immediate danger, deadline, penalty/fine, service outage, travel date, appointment date.
- Evidence: notice/bill/photo, sender, case number, amount, due date, screenshots, LINE/email, receipts, contract.
```

**Rationale:** Current workflow names many variables, but executors need a reusable compact list.

**Verification:** Section exists; no instruction asks all questions every time.

**If this fails:** Move variables into `Answering Workflow` as a shorter bullet.

---

### Step 3: Add Source-Truth Model

**Objective:** Make official vs operational vs practical sources explicit.
**Confidence:** High
**Depends on:** Step 1

**Files:**
- `SKILL.md`

**Changes:**

Add compact section near workflow:

```markdown
## Source Truth Levels
- Official truth: law, eligibility, deadlines, fees, fines, permits, agency jurisdiction. Use government/operator primary sources.
- Operational truth: open today, branch practice, appointment slots, train/bus status, hospital clinic hours. Verify with the office/operator/institution that owns the service.
- Practical truth: recommendations, English friendliness, app quality, neighborhood convenience, repair-shop quality. Use maps/web/provider sites; label as non-authoritative.
```

Then remove or shorten repeated "Non-authoritative practical search" caveats in domain rows where redundancy is high:

- banks with English apps
- English-speaking doctors
- international/private school options
- ISP comparisons
- restaurants/shops/gyms/repair services

Keep domain-specific search terms.

**Rationale:** Reduces repetition while preserving safety.

**Verification:** `rg -n "Source Truth Levels|Non-authoritative practical search" SKILL.md`; repeated caveats reduced, not eliminated where domain-specific.

**If this fails:** Keep new section and leave repeated caveats; no behavior break.

---

### Step 4: Add Scenario Playbooks

**Objective:** Cover what happens in daily life as sequences.
**Confidence:** High
**Depends on:** Steps 1-3

**Files:**
- `SKILL.md`

**Changes:**

Add section before `## Domain Index`:

```markdown
## Scenario Playbooks

**Moved home / moving soon**
→ Ask city/district, renter/owner, citizen/ARC/APRC, move date. Sequence: address/household or ARC update → utilities/internet/gas transfer → garbage/bulky waste → mail/parcels → parking/vehicle address → rent subsidy/lease records → deposit evidence.

**Got official notice / registered letter**
→ Extract agency/sender, date received, deadline, case number, amount, required action. Route to issuing agency first; if dispute/deadline risk, preserve envelope/notice and verify appeal/payment deadline.

**Need to pay bill/fine/fee**
→ Identify bill type, due date, barcode/payment code, agency/operator. Prefer official portal or convenience-store kiosk route; verify late fee/penalty before quoting.

**Lost key document/card/phone**
→ Triage fraud/safety first. Then suspend card/SIM/account → police report if theft/loss affects insurance or ID → replacement agency → update OTP/bank/government logins.

**Apartment/building problem**
→ Danger? use 119/110/gas company. Otherwise preserve dated photos/videos/messages → notify landlord/building manager in writing → check lease/building rules → mediation/consumer/building office route.

**ARC/ID/phone rejected online**
→ Ask exact ID type/format, issue date, phone carrier/account name, browser/app. Try uppercase/no spaces/current UI; then official counter/service line fallback.

**Care need for child/elder/disabled person**
→ Ask age, city, household/ARC/NHI, certificate/status, urgency, living arrangement. Route to school/social welfare/1966/1957/health center as applicable; check subsidies locally.

**Typhoon/earthquake/holiday disruption**
→ Safety first. Verify weather/warning/closure/operator status separately; city/county and sector determine answer. Never infer transport/trash/clinic/bank status from holiday or weather alone.
```

**Rationale:** These are high-frequency needs where "which site?" is insufficient.

**Verification:** Scenario section exists; each playbook has ask → sequence → route shape.

**If this fails:** Add only top 4 playbooks: moving, official notice, bill/fine, apartment problem.

---

### Step 5: Fill Missing Daily-Life Rows

**Objective:** Add missing but common routes without expanding into stale details.
**Confidence:** Medium
**Depends on:** Step 4

**Files:**
- `SKILL.md`

**Changes:**

Add concise rows to existing domains:

Government/Identity:
- Registered mail / official notice interpretation → issuing agency + postmark/receipt date; search `行政處分 訴願 期限` only as legal-process route, not advice.
- ROC/Minguo date and Taiwan address parsing → convert carefully; verify date context before deadline advice.

Healthcare:
- Medical records/certificate copy → hospital medical records counter; search `[hospital] 病歷 申請 診斷證明`.
- Hospital bill/payment dispute → hospital billing counter/patient service; NHI dispute route if coverage issue.
- Pharmacy/OTC/refill question → pharmacist/prescribing clinic; TFDA for import/safety.

Tax/Work/Money:
- Freelancer/self-employed admin → eTax + local tax bureau + NHI/BLI category routing; verify with current official pages.
- Debt/collection calls → bank/lender first; suspected scam 165; legal aid/consumer/financial dispute route depending on source.

Transport:
- Lost item on public transport → operator lost-and-found first; taxi receipt/fleet/city transport bureau.
- Airport/flight disruption → airline/airport first; travel insurance/credit card insurer as secondary.

Consumer/Digital:
- Registered letter pickup / missed delivery notice → Chunghwa Post tracking/local post office; bring matching ID.
- Account locked/OTP inaccessible after phone loss → carrier + bank/service official recovery; fraud triage first.

Life Events/Social Welfare:
- Homeless/immediate shelter/food need → 1957/local social welfare; danger/medical 119/110.
- Same-sex marriage/family documents → 戶政事務所 + receiving agency; foreign documents may need authentication.
- Adoption/foster care → local social welfare bureau; legal aid/lawyer for contested/private cases.

**Rationale:** These are common "what can happen?" needs and fit routing-index scope.

**Verification:** New rows are route-only; no unverified amounts/deadlines.

**If this fails:** Keep additions limited to scenario playbooks and defer row expansion.

---

### Step 6: Tighten What Skill Does Not Cover

**Objective:** Keep boundaries clear after expansion.
**Confidence:** High
**Depends on:** Steps 3-5

**Files:**
- `SKILL.md`

**Changes:**

Revise `## What This Skill Does NOT Cover`:

```markdown
- Recommendation databases: restaurants, shops, gyms, neighborhoods, repair providers. Use maps/web search; this routing index supplies official constraints, complaint routes, safety, accessibility, and transport checks.
- Specific legal advice: route to legal aid/lawyer; this routing index can structure process questions, evidence, deadlines to verify.
- Medical diagnosis/treatment choice: route to clinic/hospital/pharmacist; this routing index can help find services, records, billing, emergency routing.
- Live news/policy/current prices: web-search/official verification required.
- Form completion with legal consequences: help interpret fields and identify agency guidance, but avoid inventing answers.
```

**Rationale:** Expansion into action workflows increases risk of overreach; boundaries must be explicit.

**Verification:** Section remains short and clear.

**If this fails:** Restore original section and add only form-completion warning.

---

### Step 7: Update README

**Objective:** Human-facing docs match routing-index behavior and avoid product-brand framing.
**Confidence:** High
**Depends on:** SKILL changes

**Files:**
- `README.md`

**Changes:**

Update opening:

```markdown
`taiwan-daily-life` is a AI agent routing index for daily-life questions in Taiwan: official source, office, hotline, portal, Chinese search term, and practical next-step artifact.
```

Add examples:

- "What should I bring?"
- "What does this notice/bill mean?"
- "Draft a Chinese message to my landlord/school/clinic."
- "What is open/running today?"
- "What evidence should I preserve before escalating?"

Update maintenance rule:

```markdown
Keep scenario playbooks sequence-focused and non-stale. Do not encode exact fees/deadlines unless verified against current official sources.
```

**Rationale:** README should tell maintainers to preserve compact playbook style without tying the artifact to a particular AI product.

**Verification:** README mentions routing + action artifacts and does not describe itself as a Codex or AI-brand-specific skill.

**If this fails:** Leave README unchanged; runtime behavior lives in `SKILL.md`.

---

## Verification Plan

### Automated Checks

- [ ] `rg -n "Agent Output Policy|Status Variables|Source Truth Levels|Scenario Playbooks" SKILL.md`
- [ ] `rg -n "NT\\$|[0-9]+元|\\d+ days|\\d+天|罰鍰|費用" SKILL.md` to review newly added exact figures; expected: no unverified new figures.
- [ ] `rg -n "Codex|OpenAI|ChatGPT|Claude|Gemini|Copilot|AI-brand" SKILL.md README.md` returns no product-brand framing except unavoidable filesystem/tooling context if any.
- [ ] `rg -n "provenance/update note|Last updated" SKILL.md` confirms note policy changed.

### Manual Verification

- [ ] Read `Answering Workflow` top-to-bottom; confirm no conflict between routing-index purpose and agent artifacts.
- [ ] Check scenario playbooks for compactness and no stale facts.
- [ ] Check all added rows route to an owner/source, not generic advice.
- [ ] Test mental prompts:
  - "I moved to Banqiao; what do I need to update?"
  - "I got a registered letter from tax office."
  - "My landlord won't return deposit."
  - "My ARC number fails on a bank site."
  - "My phone was stolen and bank OTP is on it."

### Acceptance Criteria Validation

| Criterion | How to Verify | Expected Result |
|-----------|---------------|-----------------|
| Routing-index preserved | Read new sections | They point to source/sequence, not encyclopedia content. |
| Agent deliverables added | Search workflow | Checklist/script/evidence/deadline/status outputs named. |
| Scenario playbooks added | Search section | 8 high-frequency scenarios present. |
| Status variables added | Search section | Compact relevant-only checklist present. |
| Repetition reduced | Search caveats | Recommendation caveat centralized or reduced. |
| README updated | Read README | New scope, maintenance guidance, and provider-neutral framing present. |

---

## Rollback Plan

Per-step rollback: revert each added section or row group.

Full rollback:

1. Restore `SKILL.md` from pre-execution version.
2. Restore `README.md` from pre-execution version.
3. Keep this plan as record unless user requests removal.

---

## Notes

### Risks

- **Bloat:** Scenario playbooks could make skill too long. Mitigation: compact bullets; no city tables.
- **Overreach:** Agents may interpret notices as legal advice. Mitigation: explicit route/verify/evidence framing.
- **Staleness:** Added examples could encode policy facts. Mitigation: no exact numbers/deadlines unless verified.
- **Noise:** Provenance note requirement currently forces meta text in every answer. Mitigation: revise to conditional note.

### Open Questions

- [ ] Should this folder be initialized/imported into a Git repo so projex lifecycle can commit plans/execution?
- [ ] Should the on-disk filename `SKILL.md` remain for compatibility while public docs use provider-neutral terms?
