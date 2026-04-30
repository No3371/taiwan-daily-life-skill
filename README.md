# Taiwan Daily Life Routing Index

`taiwan-daily-life` is an agent routing index for daily-life questions in Taiwan: official source, office, hotline, portal, Chinese search term, and practical next-step artifact.

The instruction set is designed as a navigation index and action playbook, not an encyclopedia. It helps an agent answer questions like:

- How do I handle household registration, ARC/APRC, NHI, taxes, or work permits in Taiwan?
- Which hotline or agency handles fraud, labor disputes, housing problems, consumer complaints, or domestic violence?
- Where should I check typhoon closures, earthquakes, public transport disruptions, or government office calendars?
- What Chinese keyword should I search for a local Taiwan service?
- What should I bring?
- What does this notice/bill mean?
- Draft a Chinese message to my landlord/school/clinic.
- What is open/running today?
- What evidence should I preserve before escalating?

## Files

- `SKILL.md` - operating playbook, emergency-first rules, cross-domain routing, and domain reference lookup map.
- `references/` - detailed routing references by domain. This is where domain source routes, hotlines, portals, search terms, and edge-case notes live.
- `README.md` - human-facing overview and maintenance notes.

## Core Use

Use this routing index when a user asks about living in Taiwan, including:

- government paperwork and identity systems
- healthcare, NHI, public health, pregnancy, and mental health routing
- housing, utilities, garbage, neighborhood services, and tenant disputes
- banking, fraud, insurance, taxes, and payments
- schools, childcare, elder care, disability services, and social welfare
- work, labor rights, employment services, and workplace disputes
- transport, vehicles, weather, earthquakes, typhoons, holidays, and closures
- legal process, mediation, police reports, personal safety, and civil defense

The expected output is practical routing plus useful action artifacts: who to contact, what official site to check, what detail the user must provide, what Chinese term to search, what to bring, what to say, what to preserve, and what to verify as current.

## Maintenance Rules

Keep `SKILL.md` concise but operational: universal answer behavior, need-pattern/action playbooks, cross-domain rules, emergency immediate-action numbers, and complete lookup cues.

When adding or moving domain reference content, update both the target `references/*.md` file and the `SKILL.md` lookup row so agents can find it.

Detailed domain route corrections belong in the relevant reference file; mirror only enough cue text in `SKILL.md` for lookup.

Keep scenario playbooks sequence-focused and non-stale. Do not encode exact fees/deadlines unless verified against current official sources.

Before adding exact numbers, deadlines, fees, fines, fares, subsidy thresholds, eligibility rules, or hotline hours, verify them against current official sources. Taiwan government pages and hotlines change, and stale details can cause real-world harm.

For high-risk admin claims and advisory hotlines, keep a source anchor near the route in `references/*.md`: exact official URL, what claim it supports, and a last-checked date when the page does not expose a clear update date. Avoid generic homepages as proof for immigration, NHI, tax, labor, housing, medicine import, emergency, or scam-adjacent claims.

Link-check convention for tracked routing docs:

```powershell
$files = git ls-files README.md SKILL.md "references/*.md"
$urls = $files | ForEach-Object {
  Select-String -Path $_ -Pattern 'https?://[^\s\)\]\>;"]+' -AllMatches |
    ForEach-Object { $_.Matches.Value.TrimEnd('.', ',', ';', ':') }
} | Sort-Object -Unique
$urls | ForEach-Object {
  $url = $_
  try { $r = Invoke-WebRequest -Uri $url -Method Head -MaximumRedirection 5 -TimeoutSec 20; "{0} {1}" -f [int]$r.StatusCode, $url }
  catch { try { $r = Invoke-WebRequest -Uri $url -Method Get -MaximumRedirection 5 -TimeoutSec 20; "{0} {1}" -f [int]$r.StatusCode, $url } catch { "FAIL $url :: $($_.Exception.Message)" } }
}
```

Record any known-bad or JS-only URLs with last-checked date and manual verification note near the affected reference row.

Prefer official sources:

- central government agencies
- city/county governments
- public utilities and transport operators
- hospitals, schools, banks, and insurers for their own services

Use blogs, forums, maps, and comparison articles only for practical color. Label those results as non-authoritative.

## High-Risk Areas

Be especially careful with:

- emergency and safety routing
- immigration and ARC/APRC rules
- NHI enrollment and premiums
- tax filing and residency rules
- labor law, wage claims, and workplace harassment
- housing disputes and rental electricity rules
- disaster closures and transport disruptions
- mental health, domestic violence, stalking, and police/legal routes

For emergencies, give the immediate action first. Do not make the user read background context before seeing `110`, `119`, `113`, `165`, or other urgent routing.


