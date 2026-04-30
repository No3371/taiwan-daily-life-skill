# Taiwan Daily Life Skill

`taiwan-daily-life` is a Codex skill for routing questions about daily life in Taiwan to the right official source, office, hotline, portal, or Chinese search term.

The skill is designed as a navigation index, not an encyclopedia. It helps an agent answer questions like:

- How do I handle household registration, ARC/APRC, NHI, taxes, or work permits in Taiwan?
- Which hotline or agency handles fraud, labor disputes, housing problems, consumer complaints, or domestic violence?
- Where should I check typhoon closures, earthquakes, public transport disruptions, or government office calendars?
- What Chinese keyword should I search for a local Taiwan service?

## Files

- `SKILL.md` - the actual Codex skill loaded by agents. This is the source of truth.
- `README.md` - human-facing overview and maintenance notes.

## Core Use

Use this skill when a user asks about living in Taiwan, including:

- government paperwork and identity systems
- healthcare, NHI, public health, pregnancy, and mental health routing
- housing, utilities, garbage, neighborhood services, and tenant disputes
- banking, fraud, insurance, taxes, and payments
- schools, childcare, elder care, disability services, and social welfare
- work, labor rights, employment services, and workplace disputes
- transport, vehicles, weather, earthquakes, typhoons, holidays, and closures
- legal process, mediation, police reports, personal safety, and civil defense

The expected output is practical routing: who to contact, what official site to check, what detail the user must provide, and what Chinese term to search.

## Maintenance Rules

Keep `SKILL.md` concise and route-focused.

Before adding exact numbers, deadlines, fees, fines, fares, subsidy thresholds, eligibility rules, or hotline hours, verify them against current official sources. Taiwan government pages and hotlines change, and stale details can cause real-world harm.

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
