---
name: taiwan-daily-life
description: >
  台灣生活導航 — A precise information index for agents helping people navigate daily life in Taiwan.
  Use this skill when a user asks ANY question about living in Taiwan: government paperwork
  (戶政, 身分證, 自然人憑證/TW FidO, ARC, NHI, taxes), healthcare, housing and rentals, utilities,
  neighborhood/city services, banking, insurance, schools, childcare, elder care, disability
  support, work and labor rights, weather, earthquakes, typhoons, holidays, stop-work/school
  announcements, transportation, telecom, errands, mail, garbage/recycling, consumer disputes,
  legal process, emergency situations, or anything phrased as "how do I do X in Taiwan",
  "我在台灣怎麼…", or "這在台灣要找哪個單位".
  This skill tells the agent WHERE to find authoritative answers and WHAT to look for —
  so the agent spends zero time searching aimlessly and goes straight to the right source.
  Trigger for both Taiwanese residents and foreign expats/newcomers.
---

# 台灣生活導航 — Taiwan Daily Life Navigation Index

Last updated: 2026-05-01 00:37 +08:00 (Asia/Taipei)

## Core Principle
This skill is a **routing index**, not an encyclopedia. Use this file as the operating playbook and domain lookup map. Detailed source routes, URLs, hotlines, search terms, and edge cases live in the relevant `references/*.md` file.

Assume the user may be Taiwanese, a long-term resident, or a newcomer. Do not frame answers as
"for foreigners" unless visa/nationality status is actually relevant. Many Taiwanese users know
roughly what exists but want an agent to quickly identify the right office, Chinese search term,
online portal, hotline, or evidence to prepare.

Do not reproduce this entire file to the user. Read it, route correctly, then answer.

---

## Language Policy
Respond in the user's main language. If the user mixes English and Chinese, answer in the language that best carries the explanation and include exact Chinese service names/search terms they can use locally. Always include both Chinese name and English when citing official bodies (e.g. 健保署 NHIA).

---

## Answering Workflow
- First classify urgency: emergency, deadline/penalty risk, rights/dispute, routine errand, or recommendation.
- If urgent or safety-related, give the phone number/action first, then explain.
- Include provenance/update note only for audits, meta questions about this routing index, or when freshness/currentness affects confidence. For emergencies, never delay life-safety action with metadata.
- If the answer depends on city/county, district, visa type, age, employer status, school level, property address, or calendar year, ask for that missing detail or state the assumption.
- Do not assume the user is foreign. Ask or infer whether the user has household registration, ARC/APRC, NHI, employment insurance, student status, vehicle/property ownership, or dependent family members only when it changes the route.
- For fees, eligibility, fines, schedules, tax figures, NHI amounts, transport fares, and policy deadlines, verify current details by web search before giving exact numbers.
- For weather, earthquakes, typhoons, holidays, closures, transport disruptions, and service outages, verify current official status and give the timestamp/source; do not answer from memory.
- Prefer official government, operator, school, hospital, bank, or utility sources. Use blogs/forums only for practical color, and label them as non-authoritative.
- Give the user the local keyword to search in Chinese; Taiwan services are often easier to find with the exact Chinese phrase.
- For recommendation/comparison questions without a single official source (restaurants, doctors with a specific language, banks with English apps, ISPs, schools, repair shops), use maps/web search or official provider sites and label the result as non-authoritative/practical rather than government-confirmed.

## Agent Output Policy
- Prefer actionable artifacts when the user's need is concrete: bring-this checklist, Chinese call/LINE script, form/search terms, evidence packet, deadline plan, current-status check, or step sequence.
- For confusing documents/notices/bills, parse what it is, identify sender/authority, extract deadline/amount/location/action, then route to official verification.
- For recurring admin tasks, give sequence first, then offices/links, then what to prepare.
- If online flow fails, provide counter-service fallback and the exact phrase to ask for.

## Source Truth Levels
- Official truth: law, eligibility, deadlines, fees, fines, permits, agency jurisdiction. Use government/operator primary sources.
- Operational truth: open today, branch practice, appointment slots, train/bus status, hospital clinic hours. Verify with the office/operator/institution that owns the service.
- Practical truth: recommendations, English friendliness, app quality, neighborhood convenience, repair-shop quality. Use maps/web/provider sites; label as non-authoritative.

---

## Common User Need Patterns
- "I just moved / arrived": ARC address change, NHI enrollment, SIM, bank account, rent utilities, garbage schedule, local clinic, EasyCard/YouBike, digital ID.
- "I live here and need the right office": 戶籍遷入/遷出, 戶籍謄本, 印鑑證明, 身分證補換發, 自然人憑證/TW FidO, 1999, 區公所, 里辦公處.
- "Something went wrong": lost ARC/passport/NHI card, scam transfer, landlord deposit, unpaid wages, traffic ticket, medical bill, apartment leak, typhoon closure.
- "Is it operating/open today?": typhoon stop-work/school, national holiday, make-up workday, bank/post office/stock market closure, school closure, transport disruption, government system outage.
- "I need a document": 戶籍謄本, police criminal record, tax certificate, income statement, translation/notarization, school enrollment proof, lease template.
- "I need to book or pay": hospital appointment, train ticket, tax/utility/government bill, parking/traffic fine, parcel pickup, convenience-store printing.
- "I need rights/protection": labor complaint, consumer dispute, housing mediation, domestic violence, legal aid, telecom/bank complaint.
- "Life stage / care": pregnancy, birth registration, childcare, elder care, disability support, caregiver issues, funeral/death paperwork.
- "Family/property/benefit admin": school district, childcare subsidy, rent subsidy, elderly or disability benefits, inheritance paperwork, land/building transcript, vehicle tax/fines, labor insurance/pension records.
- "Daily practical life": trash/recycling, parcel delivery, medicine import, mobile payments, e-invoice lottery, pet registration, driving license, scooter/car accident, insurance claim.

## Status Variables To Check Only When Relevant
- Location: city/county, district, address, school district, route/station.
- Identity/admin: household registration, National ID, ARC/APRC, passport, NHI, natural person certificate/TW FidO.
- Life context: age, student/employer/self-employed status, dependent family, disability/care status, renter/owner/vehicle owner.
- Urgency: immediate danger, deadline, penalty/fine, service outage, travel date, appointment date.
- Evidence: notice/bill/photo, sender, case number, amount, due date, screenshots, LINE/email, receipts, contract.

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

---

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
| NHI enrollment, clinic/hospital routing, NHI card, health records, pharmacy, pregnancy, vaccines, CDC, TFDA, food safety, mental health, addiction | `references/nhi-healthcare.md` |
| Income tax, 183-day residency, withholding, tax ID, deductions, business tax, property/vehicle local taxes, fuel fee, e-invoice | `references/taxation.md` |
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
| Emergency/safety, police, fire, ambulance, 112, DV/child/sexual assault, fraud crisis, self-harm/suicide crisis, migrant/foreign-worker urgent support | `references/emergency-safety.md` |

## Cross-Domain Routing Rules

**"I need to pay a government fee / fine / bill"**
→ Many common bills, fees, and fines can be paid through convenience-store kiosks when the bill barcode/payment channel supports it. Verify the bill's instructions, amount limit, deadline, and supported channel before sending the user to ibon/FamiPort/OK mart/Life-ET.

**"I need to print / scan a document"**
→ ibon or FamiPort kiosk at any 7-Eleven or FamilyMart, post office, or local print shop 影印店. Verify current price before quoting.

**"I need to throw something away"**
→ For item-specific handling, check 回收大百科: https://recycle.rethinktw.org. For local pickup rules, ask city/district; regular garbage, recycling, food scraps, bulky waste, and designated bag rules are local. Search "[city/district] 垃圾車 時刻表" or "[city] 大型廢棄物 清運".

**"I need a form but don't know the Chinese term"**
→ Search the agency site with: 應備文件, 申辦須知, 表單下載, 線上申辦, 常見問答.

**"I can't find the right government office"**
→ Ask the city/county and issue type. Try city/county 1999 or public-service portal, 區公所/鄉鎮市公所, 里辦公處/里長, or the main government portal https://www.taiwan.gov.tw → "Contact Us" → routes to correct agency.

**"I'm Taiwanese / already resident, don't explain visas"**
→ Route by resident systems: 戶政事務所, 區公所, 里辦公處, city/county 1999, MyData, 自然人憑證/TW FidO, 健保快易通, eTax, 勞保局 e化服務, 監理服務網, 地政事務所. Only mention ARC/NIA if nationality or immigration status changes the answer.

**"A website rejects my ARC / ID / phone number"**
→ Ask exact ID type and format, try uppercase/no spaces, confirm the phone/account name matches official records, then call the agency or use counter service.

**"Is this information still current?"**
→ For fees, premiums, tax brackets, subsidy thresholds, immigration rules, labor figures, transport fares, schedules, and deadlines: always web search to verify. Do not cite figures from this skill as current without checking.

**"Is tomorrow/today a day off, or is school/work canceled?"**
→ Ask city/county and sector. Check DGPA office calendar for planned government office days, DGPA natural-disaster closure page plus local government for stop-work/school, Ministry of Labor for private-sector labor holiday rules, and the relevant school/bank/post office/stock market/operator calendar for sector-specific closures.

**"Was that earthquake serious / is there a warning?"**
→ If there is injury, fire, gas smell, damaged building, trapped people, tsunami/coastal warning, or road danger, give **119**/**110** first. For facts, use CWA Seismological Center and report local intensity, magnitude, epicenter, time, and tsunami status with source timestamp.

**"Will transport/trash/clinics/government offices run during a typhoon or holiday?"**
→ Verify separately with the operator or local agency. Weather warnings, stop-work/school announcements, transport service status, garbage collection, clinic hours, bank hours, and school decisions are related but not interchangeable.

**"Someone is taking advantage of me (employer, landlord, scammer)"**
→ Migrant/foreign-worker labor rights: **1955** | Other labor disputes: local labor bureau / Ministry of Labor route | Landlord: **1950** or district 調解委員會 | Scam: **165** | Physical danger: **110**

**"Something is wrong in my apartment/building"**
→ Preserve dated evidence, notify landlord/building manager in writing, check lease/building rules, then route to mediation, consumer protection, city building office, or emergency services depending on danger.

**"The user only wants a recommendation"**
→ Use maps/web search for restaurants, attractions, gyms, shops, and neighborhoods. This skill can still help with official constraints: permits, opening hours from official sites, accessibility, transport operators, and safety alerts.

---

## What This Skill Does NOT Cover
- Recommendation databases: restaurants, shops, gyms, neighborhoods, repair providers. Use maps/web search; this routing index supplies official constraints, complaint routes, safety, accessibility, and transport checks.
- Specific legal advice: route to legal aid/lawyer; this routing index can structure process questions, evidence, deadlines to verify.
- Medical diagnosis/treatment choice: route to clinic/hospital/pharmacist; this routing index can help find services, records, billing, emergency routing.
- Live news/policy/current prices: web-search/official verification required.
- Form completion with legal consequences: help interpret fields and identify agency guidance, but avoid inventing answers.
