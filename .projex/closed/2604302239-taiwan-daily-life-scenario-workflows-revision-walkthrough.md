# Walkthrough: Taiwan Daily Life Routing Index Scenario Workflow Revision

> **Execution Date:** 2026-04-30
> **Completed By:** Agent
> **Source Plan:** 2604302239-taiwan-daily-life-scenario-workflows-revision-plan.md
> **Duration:** ~5 minutes execution, plus close documentation
> **Result:** Success

---

## Summary

`taiwan-daily-life` was revised from a source-routing index into a routing index plus compact action playbook. `SKILL.md` now tells agents what useful artifacts to produce, how to classify source truth, what status variables to ask for, and how to handle common daily-life scenarios. `README.md` now describes the artifact in provider-neutral terms.

---

## Objectives Completion

| Objective | Status | Notes |
|-----------|--------|-------|
| Preserve routing-index purpose | Complete | New sections add action sequencing without converting the file into policy encyclopedia. |
| Add concrete agent deliverables | Complete | `Agent Output Policy` added in `SKILL.md`. |
| Add scenario playbooks | Complete | Eight high-frequency daily-life scenarios added. |
| Add status-variable checklist | Complete | `Status Variables To Check Only When Relevant` added. |
| Reduce repeated recommendation caveats | Complete | Repeated `Non-authoritative practical search` wording replaced with centralized source-truth levels and shorter practical-search rows. |
| Update README scope | Complete | README now says routing index + practical next-step artifact. |
| Remove AI-brand framing | Complete | Product-brand search returned no matches in `SKILL.md`/`README.md`. |
| Avoid unverified new exact figures/deadlines | Complete | Added-line scan found no new exact fee/deadline-like claims. |

---

## Execution Detail

### Step 0: Initialize Execution

**Planned:** Execute projex plan after Git lifecycle blocker resolved.

**Actual:** Retry found a Git repo present but empty. Existing `README.md`, `SKILL.md`, and plan were committed as baseline, precheck passed, plan moved to `In Progress`, execution branch `projex/2604302239-taiwan-daily-life-scenario-workflows-revision` was created.

**Deviation:** Yes. Plan originally recorded "not in Git repo"; retry found repo state changed/present but uncommitted. Baseline commit resolved precheck.

**Files Changed (Actual):**
| File | Change Type | Planned? | Details |
|------|-------------|----------|---------|
| `.projex/2604302239-taiwan-daily-life-scenario-workflows-revision-log.md` | Created | No | Execution log created per execute workflow. |
| `.projex/2604302239-taiwan-daily-life-scenario-workflows-revision-plan.md` | Modified | Yes | Status/progress fields updated during execution. |

**Verification:** Execute precheck output: `PRE-CHECK PASSED`; working tree clean before execution work.

**Issues:** Initial retry precheck warned plan was not committed and working tree had untracked files. Resolved by baseline commit.

---

### Steps 1-6: Revise Routing Workflow And SKILL Content

**Planned:** Update workflow, status variables, source-truth model, scenario playbooks, missing daily-life rows, and boundaries.

**Actual:** `SKILL.md` was updated:

- Line 45: mandatory per-answer note replaced with conditional provenance/update note.
- Lines 54-64: `Agent Output Policy` and `Source Truth Levels` added.
- Lines 79-112: status variables and scenario playbooks added.
- Lines 139-140: official notice and ROC/Minguo/address parsing rows added.
- Lines 172-174: medical records, hospital bill dispute, pharmacy/refill rows added.
- Lines 255, 277, 309: repeated practical-search wording shortened for ISP, bank app, and school-option rows.
- Line 288: debt/collection call route added.
- Line 347: freelancer/self-employed admin route added.
- Lines 377, 379: lost-item and flight-disruption transport routes added.
- Line 404: phone-loss/OTP recovery route added.
- Line 424: registered letter pickup route added.
- Lines 449, 451: same-sex family documents and adoption/foster care rows added.
- Line 479: homeless/shelter/food need row added.
- Lines 685-689: boundary section rewritten around recommendation databases, legal advice, medical treatment choice, live current data, and high-consequence form completion.

**Deviation:** Steps 1-6 were committed as one cohesive `SKILL.md` content revision rather than separate commits. Outcome unchanged; execution log records why.

**Files Changed (Actual):**
| File | Change Type | Planned? | Details |
|------|-------------|----------|---------|
| `SKILL.md` | Modified | Yes | Routing workflow, action policy, playbooks, rows, and boundaries updated. |
| `.projex/2604302239-taiwan-daily-life-scenario-workflows-revision-log.md` | Modified | Workflow-required | Step results logged. |

**Verification:** `rg -n "Agent Output Policy|Include provenance/update note only|Status Variables|Source Truth Levels|Scenario Playbooks|Registered mail / official notice|Medical records|Debt / collection|Freelancer|Lost item on public transport|Registered letter pickup|Homeless|What This Skill Does NOT Cover|Non-authoritative practical search" SKILL.md` found all new required sections/rows and no remaining `Non-authoritative practical search` phrase.

**Issues:** None after baseline commit.

---

### Step 7: Update README Provider-Neutral Scope

**Planned:** Update README to describe routing + action artifacts without product-brand framing.

**Actual:** `README.md` was updated:

- Line 1: title changed from "Taiwan Daily Life Skill" to "Taiwan Daily Life Routing Index".
- Line 3: opening changed from "Codex skill" to "agent routing index".
- Line 5: description changed to "instruction set" and "action playbook".
- Lines 11-15: examples added for bring checklist, notice/bill interpretation, Chinese message drafting, current operating status, and evidence preservation.
- Line 18: `SKILL.md` description changed to provider-neutral routing-index instruction set.
- Line 24: "Use this skill" changed to "Use this routing index".
- Line 35: expected output expanded to practical routing plus action artifacts.
- Lines 39-41: maintenance rules now emphasize route-focused, sequence-focused, non-stale playbooks.

**Deviation:** None.

**Files Changed (Actual):**
| File | Change Type | Planned? | Details |
|------|-------------|----------|---------|
| `README.md` | Modified | Yes | Provider-neutral framing and action-artifact scope added. |
| `.projex/2604302239-taiwan-daily-life-scenario-workflows-revision-log.md` | Modified | Workflow-required | Step results logged. |

**Verification:** README search for brand names returned no product-brand matches and found routing/action-playbook evidence.

**Issues:** None.

---

### Verification And Completion

**Planned:** Run automated checks, manual review, status update.

**Actual:** Verification passed:

- Required sections found in `SKILL.md`.
- Product-brand query returned no matches in `SKILL.md`/`README.md`.
- Added-line scan for exact fee/deadline-like claims found no matches.
- Manual diff review confirmed additions remained route/action oriented.
- Plan marked `Complete`.

**Deviation:** Plan blocker was updated from active blocker to resolved during execution retry.

**Files Changed (Actual):**
| File | Change Type | Planned? | Details |
|------|-------------|----------|---------|
| `.projex/2604302239-taiwan-daily-life-scenario-workflows-revision-plan.md` | Modified | Workflow-required | Status set `Complete`, blocker updated to resolved, open Git lifecycle question checked. |
| `.projex/2604302239-taiwan-daily-life-scenario-workflows-revision-log.md` | Modified | Workflow-required | Verification and completion recorded. |

**Verification:** `git status --short` clean before close request.

**Issues:** None.

---

## Complete Change Log

> **Derived from:** `git diff --stat master..HEAD`

### Files Created

| File | Purpose | Lines | In Plan? |
|------|---------|-------|----------|
| `.projex/2604302239-taiwan-daily-life-scenario-workflows-revision-log.md` | Execution trace and verification record | 58 | Workflow-required |

### Files Modified

| File | Changes | Lines Affected | In Plan? |
|------|---------|----------------|----------|
| `SKILL.md` | Added output policy, source-truth levels, status variables, scenario playbooks, new daily-life rows, tighter scope boundaries | 45, 54-64, 79-112, 139-140, 172-174, 255, 277, 288, 309, 347, 377, 379, 404, 424, 449, 451, 479, 685-689 | Yes |
| `README.md` | Provider-neutral routing-index framing, action-artifact examples, maintenance guidance | 1, 3, 5, 11-18, 24, 35, 39-41 | Yes |
| `.projex/2604302239-taiwan-daily-life-scenario-workflows-revision-plan.md` | Status and blocker updates | Header, dependencies, open questions | Workflow-required |

### Files Deleted

None.

### Planned But Not Changed

None.

---

## Success Criteria Verification

### Criterion 1: `SKILL.md` keeps routing-index purpose

**Verification Method:** Manual diff review.

**Evidence:**
```text
New content routes to agencies, official sources, current-status checks, evidence preservation, and scenario sequences. No city tables, exact fee tables, or policy encyclopedia content added.
```

**Result:** PASS

---

### Criterion 2: Answering workflow produces concrete deliverables

**Verification Method:** Search `SKILL.md`.

**Evidence:**
```text
SKILL.md:54:## Agent Output Policy
```

**Result:** PASS

---

### Criterion 3: Scenario playbooks added

**Verification Method:** Search `SKILL.md`.

**Evidence:**
```text
SKILL.md:86:## Scenario Playbooks
```

**Result:** PASS

---

### Criterion 4: Status-variable checklist added

**Verification Method:** Search `SKILL.md`.

**Evidence:**
```text
SKILL.md:79:## Status Variables To Check Only When Relevant
```

**Result:** PASS

---

### Criterion 5: Repeated recommendation caveats reduced

**Verification Method:** Search `SKILL.md`.

**Evidence:**
```text
No remaining "Non-authoritative practical search" phrase. Central source-truth section added at SKILL.md:60.
```

**Result:** PASS

---

### Criterion 6: README reflects routing + action playbooks

**Verification Method:** Read and search README.

**Evidence:**
```text
README.md:3:`taiwan-daily-life` is an agent routing index...
README.md:35:The expected output is practical routing plus useful action artifacts...
```

**Result:** PASS

---

### Criterion 7: Product-brand framing removed

**Verification Method:** Search product-brand terms.

**Evidence:**
```text
rg -n "Codex|OpenAI|ChatGPT|Claude|Gemini|Copilot|AI-brand" SKILL.md README.md
→ no matches
```

**Result:** PASS

---

### Criterion 8: No unverified new exact figures/deadlines

**Verification Method:** Added-line scan and manual diff review.

**Evidence:**
```text
git diff master...HEAD -- SKILL.md | rg -n "^\+.*(NT\$|[0-9]+元|\d+ days|\d+天|罰鍰|費用)"
→ no matches
```

**Result:** PASS

---

### Acceptance Criteria Summary

| Criterion | Method | Result | Evidence |
|-----------|--------|--------|----------|
| Routing-index preserved | Manual diff review | Pass | Additions remain route/action oriented. |
| Agent deliverables added | `rg` | Pass | `SKILL.md:54` |
| Scenario playbooks added | `rg` | Pass | `SKILL.md:86` |
| Status variables added | `rg` | Pass | `SKILL.md:79` |
| Recommendation repetition reduced | `rg` | Pass | No `Non-authoritative practical search`; source-truth levels added. |
| README updated | Read README | Pass | README lines 1, 3, 35, 39-41. |
| Brand framing removed | `rg` | Pass | No product-brand matches in `SKILL.md`/`README.md`. |
| No new exact claims | Added-line scan | Pass | No matches in added lines. |

**Overall:** 8/8 criteria passed.

---

## Deviations From Plan

### Deviation 1: Git Blocker Resolved During Retry
- **Planned:** Execution blocked until folder was imported into Git or lifecycle waived.
- **Actual:** Retry found repo present but empty/uncommitted; baseline commit made execution valid.
- **Reason:** Repo state changed or was initialized between initial attempt and retry.
- **Impact:** Positive; normal projex lifecycle could proceed.
- **Recommendation:** For future routing-index work, initialize/commit baseline before creating execution plans.

### Deviation 2: Steps 1-6 Committed Together
- **Planned:** Step-by-step execution.
- **Actual:** Steps 1-6 were committed as one cohesive `SKILL.md` revision.
- **Reason:** All six plan steps modified a single document section set and verification applied to combined content.
- **Impact:** Low; execution log preserves step grouping and verification evidence.
- **Recommendation:** Fine for tightly coupled documentation edits; separate commits if future changes cross files or risk areas.

---

## Issues Encountered

### Issue 1: Initial Precheck Failed Before Retry
- **Description:** First orchestrated execution failed because `.projex` was not inside a Git repo.
- **Severity:** Medium
- **Resolution:** User requested retry; retry found Git available and baseline was committed.
- **Time Impact:** One failed execution attempt.
- **Prevention:** Create Git baseline before plan execution.

### Issue 2: Initial Retry Had Untracked Baseline Files
- **Description:** Retry precheck warned plan was not committed and working tree contained `.projex/`, `README.md`, `SKILL.md`.
- **Severity:** Low
- **Resolution:** Baseline commit created, then precheck reran successfully.
- **Time Impact:** Minimal.
- **Prevention:** Commit auxiliary plan artifacts before execution.

---

## Key Insights

### Lessons Learned

1. **Provider-neutral wording belongs in both runtime and human docs**
   - Context: User corrected "Codex skill" framing.
   - Insight: The artifact may live in a compatibility filename while public language remains platform-neutral.
   - Application: Use "routing index", "instruction set", "agent", or "assistant" unless a platform-specific contract is required.

2. **Daily-life help needs output artifacts**
   - Context: Audit found strong source routing but weak "what do I do now?" support.
   - Insight: Checklists, scripts, evidence plans, and status checks convert routing into practical help.
   - Application: Future sections should describe action artifacts, not just offices/URLs.

### Pattern Discoveries

1. **Source-truth tiers**
   - Observed in: `SKILL.md` workflow.
   - Description: Official, operational, and practical truth require different verification sources.
   - Reuse potential: Other daily-life or local-navigation indexes.

2. **Scenario-first routing**
   - Observed in: moving, notice, payment, lost document, apartment, login, care, weather scenarios.
   - Description: High-frequency situations are best handled as ask → sequence → route.
   - Reuse potential: Any civic/admin support instruction set.

### Gotchas / Pitfalls

1. **Projex execution requires Git baseline**
   - Trap: Planning can create files in a folder that is not yet execution-ready.
   - How encountered: Initial execute precheck failed.
   - Avoidance: Verify repo + committed plan before execution.

2. **Brand terms can hide in README**
   - Trap: Runtime file may be neutral while README retains platform-specific wording.
   - How encountered: Search found "Codex skill" in README before execution.
   - Avoidance: Run product-brand search across runtime docs and human docs.

### Technical Insights

- `SKILL.md` line-level changes stayed compact despite adding scenario playbooks.
- README is the right place to state maintenance guardrails for non-stale scenario playbooks.
- Execution log is enough to reconstruct the blocker resolution without adding narrative to runtime files.

---

## Recommendations

### Immediate Follow-ups

- [ ] Decide whether the compatibility filename `SKILL.md` should stay while public language remains provider-neutral.
- [ ] Run a future review after several real prompts to see whether scenario playbooks are too broad, too sparse, or correctly scoped.

### Future Considerations

- Add examples for parsing Taiwanese bills/notices only if they stay generic and avoid legal/financial advice.
- Consider a separate source-audit projex for hotline/URL freshness.

### Plan Improvements

If this plan were executed again:
- Verify Git repo and committed baseline before drafting execution-blocker language.
- Avoid exact suggested README wording like "a AI agent"; implementation correctly used cleaner wording.

---

## Related Projex Updates

### Documents To Update

| Document | Update Needed |
|----------|---------------|
| `2604302239-taiwan-daily-life-scenario-workflows-revision-plan.md` | Move to `.projex/closed/`, add completed date and walkthrough reference. |

### New Projex Suggested

| Type | Description |
|------|-------------|
| Review | Test revised routing index against real daily-life prompts after usage. |
| Audit | Verify hotline/URL freshness and remove/replace stale references. |

---

## Appendix

### Execution Log

See `2604302239-taiwan-daily-life-scenario-workflows-revision-log.md`.

### References

- Execution branch: `projex/2604302239-taiwan-daily-life-scenario-workflows-revision`
- Base branch: `master`
