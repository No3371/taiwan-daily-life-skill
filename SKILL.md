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

Last updated: 2026-04-30 23:55 +08:00 (Asia/Taipei)

## Core Principle
This skill is a **routing index**, not an encyclopedia. For each domain it tells you:
- The single best source for authoritative answers
- The specific tool, page, or hotline — not just the homepage
- What to search/look up when the source requires a query
- Edge cases that catch people off guard

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

## Domain Index

### 1. 政府、戶政與身分 Government, Household Registration & Identity

**Primary routing:**
| Question type | Go to |
|---|---|
| Household registration, National ID, household records | 戶政司: https://www.ris.gov.tw → find local 戶政事務所 |
| 戶籍謄本 / household transcript online or counter service | https://www.ris.gov.tw; search "戶籍謄本 線上申辦" or use MyData when accepted |
| ID card replacement / name change / seal registration | Local 戶政事務所; search "[city/district] 戶政事務所 身分證 補換發 / 印鑑證明" |
| Moving household registration | Local 戶政事務所; search "遷入登記 應備文件" + city/district |
| Natural person certificate / TW FidO | 內政部憑證管理中心: https://moica.nat.gov.tw; TW FidO: https://fido.moi.gov.tw |
| MyData document download/authorization | https://mydata.nat.gov.tw; verify the receiving agency accepts MyData output |
| City/county service complaints and routing | Search "[city] 1999" or "[city] 市民服務"; not every county handles 1999 the same way |
| Neighborhood-level help | 里辦公處 / 里長; useful for school district, local notices, disaster cleanup, and elderly-care referrals |
| ARC/APRC status, eligibility, application | https://www.immigration.gov.tw → "Services" → relevant category |
| ARC renewal, address change, lost ARC | NIA e-service: https://oa.immigration.gov.tw |
| Gold Card application & status | https://goldcard.nat.gov.tw (fully in English) |
| Work permit status | 勞動部 eService: https://ezworktaiwan.wda.gov.tw |
| Visa overstay / status regularization | Call NIA directly: **02-2388-9393** (not the 0800 line) |
| Foreigner/new resident daily-life consultation | NIA 外來人士在臺生活諮詢服務熱線 **1990**; overseas **886-800-001990**; verify language hours |
| Police criminal record certificate | 警政署線上申辦: https://eli.npa.gov.tw/E7WebO/; search "警察刑事紀錄證明" and verify pickup/postal eligibility |
| Document notarization / authentication | Local court notary office for notarization; BOCA: https://www.boca.gov.tw for document authentication |
| Official translation requirements | Ask the receiving agency; search "[agency] 翻譯 公證" |
| What documents any government office needs | Search "[service name] 應備文件" on the specific agency's website |
| Registered mail / official notice interpretation | Identify issuing agency, receipt/postmark date, case number, deadline, and required action; route to the issuing agency first; search "行政處分 訴願 期限" only as legal-process routing, not advice |
| ROC/Minguo date or Taiwan address parsing | Convert carefully and verify context before deadline advice; route address ambiguity to local 戶政事務所, 地政事務所, post office ZIP search, or receiving agency |
| Voting / election registration questions | 中央選舉委員會: https://www.cec.gov.tw; household registration status determines district |
| Citizen military service questions | 內政部役政署: https://www.nca.gov.tw; search "役男 兵役" + city/county |

**Key routing notes:**
- NIA's current foreigner/new-resident daily-life hotline is 1990; for case-specific ARC/immigration office questions, 02-2388-9393 routes through NIA headquarters/service staff
- "應備文件" (required documents) is the magic search term on any Taiwan government site
- "申辦須知" and "線上申辦" are the other useful search terms for official application pages
- For Taiwanese users, the fastest route is often not a national homepage but the local 戶政事務所, 區公所, 里辦公處, or city/county 1999 service.
- Natural person certificate, TW FidO, MyData, NHI Express, eTax, BLI e-services, and MVDIS are the core resident self-service portals; check whether the user's ID type can log in.
- All NIA forms downloadable at: https://www.immigration.gov.tw → 表單下載
- Local 戶政事務所 handles: National ID, household records, name changes, marriage/birth/death registration, household record copies (戶籍謄本) — find nearest via RIS 戶政機關通訊錄: https://www.ris.gov.tw/app/portal/20
- For citizens, household registration status can affect voting, school districts, tax household questions, subsidies, and military service; ask what record or benefit depends on it.

---

### 2. 健保與醫療 NHI & Healthcare

**Primary routing:**
| Question type | Go to |
|---|---|
| NHI enrollment eligibility & process | NHIA English Enrollment: https://www.nhi.gov.tw/en/np-5-2.html; for ARC holders, use "Foreign Nationals who Reside in Taiwan with an Alien Resident Certificate (ARC)" |
| NHI enrollment or dependent transfer for citizens/residents | NHIA local service division or employer/township office; search "健保 轉入 眷屬加保 應備文件" |
| NHI premium calculation | https://www.nhi.gov.tw → 保費專區 → 保費計算 |
| Find NHI-contracted clinic, dental clinic, or hospital | https://www.nhi.gov.tw → 特約醫事機構查詢 OR NHI Express App |
| NHI card replacement | NHI Express App (健保快易通) → 補發申請 |
| NHI records / medication history / test results access | NHI Express App (健保快易通) → 健康存摺; verify what the user needs to export or show |
| What NHI covers / doesn't cover | https://www.nhi.gov.tw/en → "Benefits" |
| Hospital appointment booking | Each hospital's own app or website; search "[hospital name] 掛號" |
| After-hours clinic / urgent care | Search "[city/district] 夜間門診" or "[city] 急診"; use **119** for emergency ambulance |
| English-speaking doctors | Practical search: "英語看診" + specialty + city; verify with the clinic/hospital 服務台 and NHI contract search |
| Eye / dental care | Search "眼科" or "牙醫" + district; verify NHI contract status in NHI search |
| Medical records / diagnosis certificate copy | Hospital medical records counter or patient service; search "[hospital] 病歷 申請 診斷證明" |
| Hospital bill/payment dispute | Hospital billing counter or patient service first; if NHI coverage is disputed, route to NHIA service division/hotline |
| Pharmacy / OTC / refill question | Ask pharmacist or prescribing clinic; use TFDA for medicine import, safety, or product authorization questions |
| Pregnancy, prenatal care, child health | 衛福部國健署 HPA: https://www.hpa.gov.tw; 孕產婦關懷諮詢專線 **0800-870-870**; also ask OB/pediatric clinic and local health center |
| Vaccines / public health clinic | Local health center (衛生所/健康服務中心); search "[district] 衛生所 疫苗" |
| Communicable disease / epidemic / travel health question | 疾病管制署 Taiwan CDC: https://www.cdc.gov.tw; 防疫專線 **1922** or **0800-001922** |
| Adult preventive care / cancer screening | 衛福部國健署 HPA: https://www.hpa.gov.tw; search "成人預防保健" or "[screening type] 篩檢資格" |
| Drug coverage check | 健保用藥品項查詢: https://www.nhi.gov.tw → 藥品給付規定 |
| Bringing prescription medicine into Taiwan | TFDA: https://www.fda.gov.tw/eng → Drugs → Drug Application for Personal Use |
| Food safety / suspicious food product | TFDA 食藥署: https://www.fda.gov.tw; food safety hotline **1919** |
| NHI disputes / complaints | NHI hotline: **0800-030-598** |
| Mental health stress / suicidal thoughts | **1925** 安心專線 for crisis or strong distress; local community mental health center 社區心理衛生中心 for non-emergency support; **119/110** if immediate danger |
| Addiction / drug-use support | 毒品危害防制中心諮詢專線 **0800-770-885**; if overdose or immediate danger call **119** |

**Key routing notes:**
- NHI Express App (健保快易通) is often the fastest route for card management, records, clinic finder, and virtual NHI card; available in English
- The 6-month waiting period has exceptions for employed ARC holders, specific foreign-professional/dependent categories, and foreign newborns; Gold Card or spouse status alone is not enough to summarize eligibility — verify current rules at https://www.nhi.gov.tw/en → Enrollment
- Co-pay amounts change; always verify current figures at the NHI site rather than citing from memory
- For mental health: search "身心科" or "精神科" + district; NHI covers outpatient psychiatry
- For psychiatric emergency, self-harm risk, violence risk, severe confusion, overdose, or inability to stay safe, route to **119/110** first; do not treat 1925 as ambulance dispatch.
- For non-suicidal but persistent mental-health distress, route to local 社區心理衛生中心, 身心科/精神科 clinic, school counseling, workplace EAP, or 1925 depending on urgency.
- Pharmacies are 藥局; prescription refills depend on the doctor's prescription type, so route medication-specific answers to the prescribing clinic or pharmacist
- For pregnancy, vaccines, and child health, local health centers matter as much as hospitals; ask the user's district/city before giving a route.
- For Taiwanese residents, routine health questions often route through 健康存摺, local 衛生所/健康服務中心, and HPA screening eligibility pages before a hospital is needed.

---

### 3. 稅務 Taxation

**Primary routing:**
| Question type | Go to |
|---|---|
| Filing annual income tax | https://www.etax.nat.gov.tw (EN available; guided filing in May) |
| Tax residency rules (183-day) | eTax alien individual income tax: https://www.etax.nat.gov.tw/etwmain/alien-tax-service/alien-individual-income-tax; verify filing-year instructions |
| Withholding tax for non-residents | eTax alien individual income tax / National Taxation Bureau pages; search "外僑所得稅 扣繳 非居住者" |
| Gold Card tax incentive details | https://goldcard.nat.gov.tw → "Tax Incentives" |
| Tax ID / reporting ID for foreigners | Usually the NIA-issued 統一證號 on ARC/APRC or unified ID basic-data sheet; no separate tax ID for most ARC holders, but verify legacy/no-ARC cases |
| Household/dependent deductions and income lookup | https://www.etax.nat.gov.tw; search "綜合所得稅 扶養親屬" or "所得及扣除額資料查詢" |
| Business tax / VAT (if self-employed) | https://www.etax.nat.gov.tw → 營業稅 |
| Local taxes: house tax, land value tax, vehicle license tax | Local taxation bureau; search "[city/county] 地方稅務局 房屋稅 / 地價稅 / 使用牌照稅" |
| Vehicle fuel fee | Motor Vehicles Office / MVDIS: https://www.mvdis.gov.tw; search "燃料使用費 查詢" |
| Find local taxation bureau | https://www.mof.gov.tw → 所屬機關 → find by region |
| Tax hotline (EN available in May) | **0800-000-321** |
| Uniform invoice lottery / e-invoice carrier | 財政部電子發票整合服務平台: https://www.einvoice.nat.gov.tw |
| Tax payment at convenience store | eTax payment barcode or printed bill → ibon/FamiPort/OK mart/Life-ET depending on bill |

**Key routing notes:**
- eTax portal guided filing (報稅精靈) walks through the process step by step; most foreigners can use it without a tax agent
- The key question that changes everything: were you in Taiwan ≥183 days last calendar year? This determines resident vs. non-resident treatment
- Salary deduction (薪資所得特別扣除額) and basic deduction (免稅額) amounts change annually — always pull current figures from eTax, not cached sources
- If the user asks about invoices, distinguish tax invoices for businesses from consumer 統一發票 lottery/e-invoice carrier questions
- For Taiwanese household tax questions, clarify whether the issue is national income tax, local property/land tax, vehicle tax, or inheritance/gift tax; different bureaus handle them.

---

### 4. 租屋、水電與鄰里 Housing, Utilities & Neighborhood

**Primary routing:**
| Question type | Go to |
|---|---|
| Finding rentals | Use major rental platforms and local groups; verify listing, landlord identity, and ownership before paying |
| Verifying landlord actually owns the property | 地政司 謄本查詢: https://eservices.land.moi.gov.tw — search by address; verify current fee |
| Land/building transcript for owned property | 地政司 謄本查詢: https://eservices.land.moi.gov.tw; search "土地建物謄本" |
| Cadastral map / land number / zoning clue | 地政司 or city land office; search "地籍圖資網路便民服務" and verify with local 地政事務所 |
| Residential lease mandatory/prohibited clauses and official template | 內政部: https://www.moi.gov.tw → search "住宅租賃定型化契約 應記載 不得記載"; use official template as a baseline, but focus on mandatory/prohibited terms |
| Deposit dispute / landlord refusing to return | 消費者保護 1950, or district 調解委員會 (free mediation); find at local 區公所 |
| Rental electricity overcharge | Search "住宅租賃 電費 當期每度平均電價" and verify current MOI rules; ask landlord for/authorize Taipower bill info where applicable |
| Landlord blocks rent subsidy / lease registration concern | Search "租金補貼 不得禁止" + MOI/city housing bureau; preserve lease, payment records, and landlord messages |
| Illegal sublet / short-term rental / Airbnb-style issue | Verify lease permission, building rules, and city government lodging/housing rules; unresolved disputes → district mediation or local housing/building office |
| Reporting address change (ARC) | NIA change registration; current NIA guidance says within 30 days after residential address/place-of-service change, but verify the user's category and current source: https://oa.immigration.gov.tw |
| Checking actual transaction prices in area | 實價登錄: https://lvr.land.moi.gov.tw |
| Utility setup (electricity) | 台電: https://www.taipower.com.tw → 新增用電申請 |
| Utility setup (water) | Taipei: https://www.water.gov.taipei; others: https://www.water.gov.tw |
| Power/water outage or account transfer | 台電 or water utility customer service; search "[provider] 停電" / "停水" / "過戶" |
| Natural gas setup / bill | Ask building manager or search "[city] 天然氣 公司"; provider is regional |
| Gas smell / gas leak | Call regional gas company emergency line; if danger is immediate call **119** |
| Leaks, mold, pests, noise, smoke, repairs | Document evidence; notify landlord/building manager in writing; unresolved disputes → district 調解委員會 |
| Building management fee / committee dispute | Ask 管理委員會/管理員 first; unresolved dispute → district office mediation or local building management office |
| Illegal construction / unsafe building issue | Search "[city] 違建 檢舉" or "[city] 建管處" |
| Garbage truck schedule | Search "[city/district] 垃圾車 時刻表"; Taipei DEP: https://english.dep.gov.taipei |
| How to throw away or recycle a specific item | 回收大百科: https://recycle.rethinktw.org for item-level guidance; then verify local city rules if needed |
| Bulky trash pickup | Search "[city] 大型廢棄物 清運"; usually book through city EPA/1999 |
| Internet providers comparison | Practical search: "台灣寬頻比較 [year]" plus official ISP sites; no single government source for quality comparison |
| Local nuisance / road light / pothole / drain issue | City/county 1999 or public works portal; search "[city] 1999 路燈 坑洞 水溝" |

**Key routing notes:**
- 謄本查詢 (property ownership check) is the one thing most renters don't know to do; it catches subletting scams
- 調解委員會 at the district office (區公所) is free and surprisingly effective for landlord disputes — faster than court
- 實價登錄 shows what apartments in an area actually sold/rented for — essential for price negotiation
- Land office 地政事務所 is the route for property records, land/building transcripts, cadastral questions, address/land-number confusion, and many pre-sale or ownership checks.
- Garbage, recycling, food scraps, and designated trash bags are city-specific; always ask the city/district before giving collection days
- For "how do I throw away X", use 回收大百科 first to identify recycle/trash/category handling, then route to the city EPA for collection schedule, designated bags, and bulky-item booking
- For home problems, tell users to preserve dated photos/videos, chat logs, repair quotes, receipts, and written notices before escalating.
- For tenant disputes, distinguish consumer complaint 1950, district 調解委員會 mediation, city housing/rental consultation, land office records, and emergency building/police routes; choose by danger and issue type.

---

### 5. 金融、詐騙與保險 Banking, Fraud & Insurance

**Primary routing:**
| Question type | Go to |
|---|---|
| Opening a bank account as a foreigner | Call the branch first; common routes include post office and major banks; bring ARC + passport + second ID if requested |
| Bank account changes for residents: seal, passbook, name, lost card | Issuing bank branch/service line; search "[bank] 掛失 印鑑變更 存摺遺失" |
| Which banks have English apps/web | Practical search: "[bank name] English internet banking"; verify current app/web language support with the bank |
| Mobile payment setup | LINE Pay: https://pay.line.me/tw; Taiwan Pay: https://www.taiwanpay.com.tw |
| Sending money abroad | Compare licensed remittance services and bank wire; verify fees, exchange rate, transfer limit, and recipient-country rules |
| Checking your credit score / report | 金融聯合徵信中心: https://www.jcic.org.tw → 個人信用報告申請 |
| Reporting fraud / stopping a transfer | Call the bank/card issuer immediately, call **165**, and follow police instructions; go to a police station if directed |
| Taiwan stock account / securities settlement / TDCC ePassbook | Brokerage customer service + TDCC: https://www.tdcc.com.tw; search "集保e手掌握" |
| Investment accounts / brokerage | Search "[broker name] 外資開戶" e.g. 元大, 富邦, 凱基 — each has foreigner account process |
| FSC complaint / financial dispute | 金管會: https://www.fsc.gov.tw → 申訴管道 |
| Insurance policy / claim dispute | Start with insurer complaint channel; unresolved → 金融消費評議中心: https://www.foi.org.tw |
| Vehicle compulsory insurance | Ask insurer or Motor Vehicles Office; search "強制汽車責任保險" |
| Labor insurance / pension personal record | 勞保局 e化服務: https://www.bli.gov.tw; search "個人網路申報及查詢作業" |
| Lost ATM/credit card | Call the issuing bank's 掛失 hotline immediately; then 165 if fraud is suspected |
| Debt / collection call | Verify with bank/lender first through official contact; suspected scam → **165**; disputed debt → lender complaint channel, financial dispute route, consumer protection, or legal aid depending on source |
| Mobile barcode / invoice prize payout bank account | https://www.einvoice.nat.gov.tw → 手機條碼 / 領獎設定 |

**Key routing notes:**
- Branch practice varies; never promise a specific bank will accept a foreigner or a specific ARC type.
- JCIC credit report is what Taiwan banks check — not international credit scores; foreigners start with no history
- 165 can help trigger urgent anti-fraud handling and bank notification, but do not promise funds will be frozen or recovered; tell users to call their bank/card issuer immediately and complete any police-report steps.
- For financial disputes, preserve contracts, screenshots, transaction IDs, call times, account numbers, and written complaint responses.

---

### 6. 教育、托育與家庭 Education, Childcare & Family

**Primary routing:**
| Question type | Go to |
|---|---|
| Enrolling child in public school | Contact school directly or local 區公所教育課; bring household/ARC status + address proof |
| Finding your school district (學區) | Search "[your district/area] 學區查詢" or ask local 里辦公室 |
| Public school transfer / enrollment documents | School office + city/county education bureau; search "[city] 轉學 應備文件" |
| Bilingual/English-medium public schools | City/county education bureau first; national context: https://www.k12ea.gov.tw → 雙語教育 |
| International/private school options | Practical search: "[city] international school"; verify registration/status, school level, and admissions rules with city/county education bureau and the school |
| University application (international) | https://www.studyintaiwan.org (EN); https://www.cac.edu.tw for local entrance |
| Learning Mandarin (institutional) | Search "華語中心" + university/city; verify visa eligibility with the school and NIA/BOCA |
| Chinese proficiency test (TOCFL) | https://tocfl.edu.tw |
| Scholarships for international students | MOFA Taiwan Scholarship: https://www.mofa.gov.tw → 獎學金 |
| Daycare / preschool | City/county education or social welfare bureau; search "[city] 公托" or "[city] 幼兒園 查詢" |
| Childcare subsidy / parental leave | City social welfare bureau + Ministry of Labor/BLI for leave benefits; search "育兒津貼 托育補助 留職停薪津貼" |
| After-school care / lunch subsidy / low-income student aid | School office + city/county education bureau/social welfare bureau; search "[city] 就學補助" |
| Special education / disability support | Local education bureau + school counselor; search "[city] 特教 資源中心" |

**Key routing notes:**
- For school enrollment: the 里辦公室 (neighborhood warden's office) often knows the exact local school district boundary faster than googling
- Bilingual school availability varies enormously by district — always check the specific county/city education bureau (教育局) site, not national-level info
- TOCFL level matters for university admission and some visa applications — route users to tocfl.edu.tw for official level descriptions
- For children, ask age, household/ARC status, address, current grade, language needs, and whether the child needs disability/special education support.
- Taiwanese families often need the exact city/county education bureau page, not national policy pages; local school offices and 里辦公處 can clarify school district boundaries.

---

### 7. 工作與勞權 Work & Labor Rights

**Primary routing:**
| Question type | Go to |
|---|---|
| Labor standards: wages, overtime, leave, termination | Ministry of Labor 勞動部: https://www.mol.gov.tw → 勞動條件 |
| Migrant worker support / complaints / interpretation | **1955** Labor Consultation and Complaint Hotline; WDA portal: https://fw.wda.gov.tw |
| Work permit application/status | 勞動部 eService: https://ezworktaiwan.wda.gov.tw |
| Employer withholding passport/ARC, illegal deductions, abuse | **1955** immediately; if physical danger call **110** |
| Occupational injury / workplace accident | 勞保局 BLI: https://www.bli.gov.tw; also call local labor bureau |
| Workplace safety hazard / occupational disease / violence | 職安署 OSHA or local labor inspection office; search "[city] 勞動檢查 申訴" or "職場不法侵害 申訴" |
| Workplace sexual harassment | Employer's required complaint channel first; if top person is accused, employer does not act, or result is disputed → local labor bureau; immediate danger/crime → **110** |
| Workplace bullying / harassment | Internal complaint first where safe; if employer fails to act or top person is involved → local labor bureau/labor inspection office; preserve evidence |
| Wage arrears / employer shutdown | Local labor bureau mediation/complaint; if employer closed, liquidated, or bankrupt, check BLI 積欠工資墊償基金 |
| Unemployment insurance / labor insurance | 勞保局 BLI: https://www.bli.gov.tw |
| Job search / public employment services | 台灣就業通: https://www.taiwanjobs.gov.tw; WDA/public employment service centers 就業中心/就業服務站 |
| Unemployment benefit | Public employment service agency handles unemployment recognition; BLI pays after transfer; search "失業給付 就業服務站" |
| Labor pension / National Pension questions | 勞保局 BLI: https://www.bli.gov.tw; distinguish 勞保, 勞退, 國民年金 |
| Query personal labor insurance / labor pension record | 勞保局 e化服務: https://www.bli.gov.tw; login with natural person certificate/TW FidO where supported |
| Local labor dispute mediation | Search "[city] 勞資爭議 調解" or call city/county labor bureau |
| Freelancer / self-employed admin | Route tax to eTax/local tax bureau, NHI category to NHIA/local office, labor insurance/pension to BLI where applicable; verify current official pages |

**Key routing notes:**
- Labor law answers depend on employment category: office worker, migrant worker, domestic caregiver, teacher, contractor, or self-employed.
- 1955 provides multilingual support and handles both work and daily-life issues for migrant workers; route vulnerable users there early.
- If a deadline exists (termination notice, unpaid wages, injury claim), tell the user to preserve evidence: contract, pay slips, LINE messages, schedules, photos, and bank records.
- Minimum wage, overtime formulas, leave rules, insurance contribution rates, and subsidy windows change; verify current Ministry of Labor/BLI figures before citing numbers.
- For Taiwanese workers, distinguish 勞保 (labor insurance), 就保 (employment insurance), 勞退 (labor pension), and 國民年金; users often collapse these into "勞保".
- For harassment, bullying, unpaid wages, or injury, route by evidence and forum: employer channel, local labor bureau mediation/complaint, labor inspection, BLI benefit claim, police, or 1955 for migrant-worker support.

---

### 8. 交通與車輛 Transportation & Vehicles

**Primary routing:**
| Question type | Go to |
|---|---|
| MRT/bus route planning | Google Maps, city transit app, or operator website; verify last-train/bus times on operator site |
| THSR booking / timetable | Taiwan High Speed Rail: https://www.thsrc.com.tw |
| TRA train booking / timetable | Taiwan Railway: https://www.railway.gov.tw |
| Train/MRT/bus disruption or typhoon service change | Operator website/app first; search "[operator/route] 營運異動 / 停駛 / 延誤 / 颱風" |
| EasyCard / iPASS use, lost card, refund | EasyCard: https://www.easycard.com.tw; iPASS: https://www.i-pass.com.tw |
| YouBike registration / station status | Official YouBike site/app: https://en.youbike.com.tw |
| Driver license, scooter license, vehicle inspection | Highway Bureau/Motor Vehicles Offices: https://www.thb.gov.tw |
| Traffic fines / red tickets | Motor vehicle office or https://www.mvdis.gov.tw; search "交通違規 罰鍰 查詢" |
| Vehicle tax / fuel fee / plate or ownership transfer | MVDIS + local taxation bureau; search "車輛過戶", "使用牌照稅", "燃料使用費" |
| Parking fees | City parking portal; search "[city] 停車費 查詢" |
| Towed scooter/car | Search "[city] 拖吊 查詢" or call local parking/towing office |
| Road closure / construction / disaster road condition | Local transport bureau/public works bureau, police, or Highway Bureau; search "[city/road] 道路封閉 / 交通管制 / 施工" |
| Taxi complaint / lost item | Ask receipt/fleet first; city transport bureau taxi complaint channel if unresolved |
| Lost item on public transport | Operator lost-and-found first; for taxis use receipt/fleet/time/location, then city transport bureau if needed |
| Airport transport | Verify current routes/fares with airport MRT, bus operator, TRA/THSR, or airport website |
| Airport / flight disruption | Airline and airport official notices first; travel insurance or credit-card insurer second if claims may apply |
| Traffic accident steps | Police **110** if injury/dispute; exchange IDs, insurance, photos; request accident report from police station |

**Key routing notes:**
- Do not answer transport schedules from memory; train/bus schedules, fares, and service disruptions change.
- Google Maps is useful for routing, but operator sites/apps are authoritative for disruptions, last trains, typhoon suspensions, and emergency service changes.
- Driver license exchange depends on reciprocity with the issuing country/state; route to the Motor Vehicles Office and ask the user's license jurisdiction.
- For accidents with injury, police reporting matters for insurance and later disputes even if the crash seems minor.
- For ordinary vehicle admin, MVDIS (監理服務網) is usually the resident self-service hub; local motor vehicle offices handle counter service and edge cases.

---

### 9. 通訊與數位生活 Telecom & Digital Life

**Primary routing:**
| Question type | Go to |
|---|---|
| Tourist SIM/eSIM | Airport telecom counters or official carrier sites: Chunghwa Telecom, Taiwan Mobile, Far EasTone |
| Postpaid mobile plan as resident | Carrier store; bring Taiwan ID or ARC/passport + second ID if requested |
| Telecom billing/contract dispute | Carrier customer service first; if unresolved or no reply after 15 days, 電信服務消費爭議處理中心 **0800-034-580**; NCC process: https://www.ncc.gov.tw/Chinese/content.aspx?site_content_sn=3154; NCC complaint portal: https://cabletvweb.ncc.gov.tw/pop30 |
| Cable TV / broadband complaint | Operator first; NCC complaint portal/phone if unresolved: https://cabletvweb.ncc.gov.tw/pop30; **0800-177177** (landline) or **02-4128-177** (mobile) |
| Government online identity / digital certificate | MyData: https://mydata.nat.gov.tw; natural person certificate: https://moica.nat.gov.tw |
| TW FidO / mobile natural person certificate | https://fido.moi.gov.tw; use for supported government logins and digital signing |
| Government site rejects ARC/ID number | Try exact ARC format, uppercase letters, no spaces; if still blocked, call agency or use counter service |
| Mobile number / OTP / real-name issue | Carrier store first; bring ARC/passport and ask whether number registration matches the service |
| Account locked / OTP inaccessible after phone loss | Suspend SIM/account if fraud risk, visit carrier for number recovery, then use bank/service official recovery path; call **165** if suspicious activity occurred |
| Government portal outage or maintenance | Check the service's latest news/公告; search "[service name] 系統維護 / 暫停服務 / 公告" |
| Common convenience-store digital tasks | ibon/FamiPort for printing, bill payment, ticketing, government fee payment |

**Key routing notes:**
- Telecom stores often require an ARC validity period long enough to cover the contract; prepaid is easier for short stays.
- Warn users about telecom fraud: NCC notes it will not proactively call to ask for personal data; route suspicious calls to **165**.
- For government digital services, ARC number formatting and UI language are frequent blockers; suggest the user's local household/immigration/tax office if online login fails.
- For Taiwanese citizens, ask whether they have a natural person certificate, card reader, TW FidO, or only phone-based OTP; this determines whether online service is realistic.
- When a digital service fails, ask for exact ID type, ARC issue date/format, phone carrier, browser/app, and whether the account name matches official records.
- For outages and maintenance windows, distinguish "the user's login/data issue" from "the service is temporarily unavailable"; official 公告 pages matter more than forum reports.

---

### 10. 郵件、包裹與日常採買 Mail, Parcels & Consumer Life

**Primary routing:**
| Question type | Go to |
|---|---|
| Post office tracking / postage / ZIP code | Chunghwa Post: https://www.post.gov.tw → Track & Trace / Zip Code / Postage Rates |
| Registered letter pickup / missed delivery notice | Chunghwa Post tracking or local post office first; bring matching ID and notice; verify pickup deadline/status with the post office |
| Convenience-store parcel pickup | The store chain app/kiosk; bring ID matching parcel name/phone |
| International package customs/tax | Customs Administration: https://web.customs.gov.tw; search "快遞 貨物 稅費" |
| Consumer purchase dispute / refund issue | Consumer Protection hotline **1950**; online complaint through 行政院消費者保護會 |
| Product safety / food or medicine complaint | TFDA 食藥署: https://www.fda.gov.tw; food safety hotline **1919** |
| E-invoice mobile barcode / lottery | https://www.einvoice.nat.gov.tw; official app "統一發票兌獎" |
| Printing/scanning/copying | ibon (7-Eleven), FamiPort (FamilyMart), post office, or print shop 影印店 |
| Laundry / dry cleaning dispute | Consumer Protection **1950** if shop refuses responsibility |
| Online marketplace / food delivery dispute | Platform support first; unresolved consumer dispute → **1950** and preserve order screenshots |
| Food labeling / allergen / suspicious product | TFDA or local health bureau; search "食品 標示 檢舉" + city |

**Key routing notes:**
- Parcels may be held because the recipient name, phone, or ID does not match; ask what name/phone is on the parcel notice.
- For cross-border shopping, distinguish postal packages handled by Chunghwa Post from courier packages handled by DHL/FedEx/SF/others.
- For consumer disputes, advise preserving receipts, screenshots, chat logs, product photos, and delivery labels.
- For recommendations such as shops, gyms, restaurants, and repair services, use maps/web search; this skill only routes official constraints, complaints, safety, and rights issues.

---

### 11. 家庭、寵物與生活事件 Family, Pets & Life Events

**Primary routing:**
| Question type | Go to |
|---|---|
| Marriage/divorce/birth/death registration | Local 戶政事務所 via https://www.ris.gov.tw; ask whether one party is foreign |
| Same-sex marriage / family documents | 戶政事務所 + receiving agency first; foreign documents may need translation/authentication before acceptance |
| Baby birth registration and NHI | Hospital birth documents → 戶政事務所 → NHI enrollment via employer/local office |
| Adoption / foster care | Local social welfare bureau; legal aid/lawyer for contested, private, or cross-border cases |
| Inheritance first steps after death | 戶政 death registration, tax bureau inheritance/gift tax, land office/bank/insurer as relevant; route legal disputes to legal aid/lawyer |
| Pregnancy / childbirth documents | Hospital/clinic + local 戶政事務所; foreign documents may need translation/authentication |
| Pet registration / rabies vaccine | Local animal protection office; search "[city] 寵物登記 狂犬病" |
| Importing pets to Taiwan | Bureau of Animal and Plant Health Inspection and Quarantine: https://www.aphia.gov.tw |
| Funeral / death of foreign national | Hospital/police depending on circumstance; local funeral office; contact representative office; route estate questions to legal aid/lawyer |

**Key routing notes:**
- Life-event paperwork often crosses agencies; tell users the sequence and which original documents/translations are likely needed, then route to the exact receiving office.
- For Taiwanese families, death/inheritance/admin questions usually cross 戶政事務所, National Taxation Bureau, local tax bureau, land office, banks, insurers, and court notary/legal aid; ask what asset/document is involved before routing.
- Pet import/export rules change and require timing; always verify with APHIA and airline before giving dates or quarantine steps.
- For foreign marriage/birth/death documents, ask which country issued the document because authentication requirements differ.
- For death at home, suspicious death, or accident death, police/hospital procedures come before paperwork; do not route only to 戶政.

---

### 12. 長照、身心障礙與社福 Elder Care, Disability & Social Welfare

**Primary routing:**
| Question type | Go to |
|---|---|
| Long-term care services | **1966** 長照服務專線; local long-term care management center 長期照顧管理中心 |
| Disability certificate / benefits | Local social welfare bureau; search "[city] 身心障礙證明 申請" |
| Assistive devices / home modification subsidy | Search "[city] 輔具 補助" or ask local social welfare bureau |
| Accessible transport | Search "[city] 復康巴士" and verify eligibility/reservation rules |
| Elder welfare / meal delivery / home care | Local social welfare bureau; search "[city] 老人 福利" |
| Rent subsidy / social housing / youth housing support | 內政部不動產資訊平台 and city housing bureau; search "租金補貼 社會住宅" + city/county |
| Low/middle-low income household support | Local social welfare bureau or district office; search "[city] 低收入戶 中低收入戶 申請" |
| Homeless / immediate shelter or food need | **1957** or local social welfare bureau; if danger, exposure, injury, or medical emergency use **119/110** first |
| General social welfare consultation | **1957** 福利諮詢專線; for urgent danger use **113/119/110** first |
| Caregiver stress / respite support | **1966** long-term care route; 家庭照顧者關懷專線 **0800-507-272**; local caregiver support stations |
| Dementia care support | 失智症關懷專線 **0800-474-580** and local dementia/community care resources |
| Sign-language / real-time captioning service | Local social welfare bureau; search "[city] 手語翻譯 同步聽打 申請" |
| Disability parking permit | Local social welfare bureau or motor vehicle office depending on permit/plate; search "身心障礙者專用停車位識別證 申請" |
| Accessibility barrier or service discrimination | Responsible venue/operator first; unresolved → local social welfare bureau, transport bureau, or rights complaint channel |
| Foreign caregiver / domestic caregiver issue | **1955** for migrant worker rights; local labor bureau for employment disputes |

**Key routing notes:**
- Ask age, city/county, disability certificate status, NHI/household/ARC status, living arrangement, and urgency before giving subsidy or care-service steps.
- Subsidy eligibility and service availability are local, income/status-dependent, and often tied to household registration; verify current city/county rules.
- If neglect, abuse, immediate medical danger, or domestic violence is involved, route to **113**, **119**, or **110** first.
- Accessibility routes are local and function-specific: social welfare bureau for disability certificates, sign-language/captioning, parking permits, assistive devices, and welfare; transport bureau/operator for inaccessible buses/MRT/taxis; building/public-works office for physical barrier complaints.

---

### 13. 環境與公共衛生 Environment & Public Health

**Primary routing:**
| Question type | Go to |
|---|---|
| Air quality / AQI | Ministry of Environment: https://airtw.moenv.gov.tw |
| Tap water quality / outage | Taiwan Water or Taipei Water; search provider + "水質" / "停水" |
| Dengue, pests, public sanitation | Local health bureau or EPA; search "[city] 登革熱 防治" / "環境衛生 檢舉" |
| Flu/COVID/communicable disease / travel health | CDC 疾病管制署: https://www.cdc.gov.tw; **1922** 防疫專線; local health bureau for city-specific measures |
| Heat, cold, typhoon, heavy rain alerts | CWA: https://www.cwa.gov.tw; see Weather & Closures section for closure routing |
| Noise, odor, pollution complaint | Local EPA; search "[city] 環保局 陳情" or use city 1999 where available |
| Beach/mountain/river safety | Check CWA, National Fire Agency, local scenic area, and city/county warnings before advising |

**Key routing notes:**
- Environment and public-health handling is local; ask city/county/district and whether the issue is inside a private building, public street, workplace, school, or food business.
- For immediate danger from flood, fire, landslide, gas, electrical hazard, or medical symptoms, use **119**.

---

### 14. 天氣、地震、放假與服務異動 Weather, Earthquakes, Holidays & Closures

**Primary routing:**
| Question type | Go to |
|---|---|
| Weather forecast, radar, rain, typhoon, marine/weather warnings | 中央氣象署 CWA: https://www.cwa.gov.tw; app: 天氣e點靈 |
| Earthquake report, intensity, tsunami info | CWA Seismological Center: https://scweb.cwa.gov.tw; search "地震報告" or "鄉鎮震度" |
| Immediate disaster danger: flood, landslide, fire, trapped/injured people | **119** first; then city/county disaster-prevention page if safe |
| Natural-disaster stop-work/school status | 行政院人事行政總處 DGPA: https://www.dgpa.gov.tw/typh/daily/nds.html; also verify city/county government |
| Official national office calendar / make-up workdays | DGPA 辦公日曆表: https://www.dgpa.gov.tw/informationlist?uid=41; search "行政機關辦公日曆表" + year |
| Private-sector holiday / labor day / make-up work questions | 勞動部 Ministry of Labor: https://www.mol.gov.tw; search "國定假日 出勤 補休 勞動節" |
| School calendar or closure | City/county education bureau + school announcement; search "[city] 停班停課 教育局" or "[school] 行事曆" |
| Bank, post office, stock market, or clinic open/closed | Verify with the operator/institution; official government calendar may not fully answer sector-specific closures |
| Public transport disruption due to typhoon/earthquake | Operator site/app first: THSR, TRA, MRT, bus operator, airport MRT; search "營運異動 / 停駛 / 延誤" |
| Road closure, mountain/river/beach access warning | Local government, police/fire, Highway Bureau, scenic area authority; search "[place] 封閉 / 管制 / 警戒" |
| Public-service or government-system outage | Check the service's official 公告/latest news page; search "[service] 系統維護 / 暫停服務" |

**Key routing notes:**
- Always ask for the city/county for typhoon, heavy rain, closure, school, road, and local-service questions.
- Stop-work/school announcements are per city/county and sometimes per township/village; Taipei, New Taipei, Keelung, and Taoyuan can differ.
- DGPA's disaster closure page aggregates announcements from local governments; city/county pages may have more context for local routes, schools, and trash collection.
- Do not answer "is tomorrow off?" from memory. Verify the current DGPA office calendar, current stop-work/school page, or the relevant operator/school/institution page.
- Distinguish official calendar categories: national holiday (國定假日), government office calendar (行政機關辦公日), make-up workday (補班), Labor Day (勞動節), school calendar, bank holiday, and stock-market closure.
- Weather forecast, warning, closure announcement, and actual operator service status are separate facts; cite each from the source that owns it.
- After earthquakes, give emergency actions first if there is injury, gas smell, fire, building damage, trapped people, tsunami risk, or road danger; use CWA for magnitude/intensity facts only.

---

### 15. 法律流程與調解 Legal Process & Mediation

**Primary routing:**
| Question type | Go to |
|---|---|
| Free legal aid / lawyer referral | 法律扶助基金會 LAF: https://www.laf.org.tw; **412-8518** (landline direct, mobile add **02**); press path, hours, language, and issue scope vary |
| District mediation | Local 區公所/鄉鎮市公所 調解委員會; search "[district] 調解委員會" |
| Police report / criminal complaint | Local police station or **110** if urgent |
| Stalking / harassment | **110** if in danger; local police station for report; search "跟蹤騷擾防制法 書面告誡 保護令" |
| Missing person | Local police station; no 24-hour waiting rule; bring ID, recent photo, clothing/last-seen details |
| Cybercrime / online fraud | **165** for fraud; local police station for report; preserve URLs, account IDs, screenshots, transfer records |
| Sexual harassment outside school/work | If immediate danger or assault call **110**; for protection/support call **113**; route process by setting: workplace labor bureau, school, or local government sexual-harassment complaint channel |
| Small civil claim / court filing | Judicial Yuan / local district court service center; search "[court] 訴訟輔導" |
| Protection order / domestic violence | **113** first; court/police/legal aid after safety planning |
| Restraining/protection order sequence | For DV/sexual assault use **113** + police/court; for stalking use police report/written warning then court protection-order route where applicable; verify process with police/legal aid |
| Power of attorney / will / notarization | Local court notary or licensed attorney; foreign use may require BOCA/foreign-office authentication |

**Key routing notes:**
- Do not give specific legal advice; explain process, evidence to preserve, deadlines to verify, and where to get licensed help.
- Ask whether the issue is civil, criminal, administrative, family, labor, consumer, or housing; route labor/consumer/housing to their specialized mediation channels first.
- Tell users to preserve contracts, receipts, photos, recordings where lawful, LINE/email messages, bank records, police report numbers, and official notices.
- For personal safety issues, do not make mediation the first route; use 110/113/police/legal aid before civil dispute channels.

---

### 16. 民防、警報與戰災準備 Civil Defense, Alerts & Wartime Preparedness

**Primary routing:**
| Question type | Go to |
|---|---|
| Air-raid alert / what to do during an alert | 國防部全民安全指引: https://prepare.mnd.gov.tw; follow police/civil-defense instructions |
| Air-raid shelter lookup | 警政服務 App or local police/city civil defense pages; search "[city] 防空避難設施 查詢" |
| Wan-An air-raid drill / traffic control | MND/All-out Defense Mobilization Agency + city/county police announcements; search "萬安演習" + year/city |
| Disaster shelter / relief station lookup | 消防防災 e 點通 App, city/county disaster-prevention page, or https://prepare.mnd.gov.tw |
| National alert on phone | Check official source named in the alert: CWA, MND, NFA, local government, Highway Bureau, etc.; do not rely on screenshots alone |
| Suspicious wartime/civil-defense rumor | Verify with MND, local government, police, CWA, or NFA before sharing; label social media as unverified |

**Key routing notes:**
- Civil-defense facts are highly situation-specific. Ask location, alert text, time, and whether the user is indoors, outside, driving, near coast, or in immediate danger.
- For normal mobile signal, use **110** police or **119** fire/ambulance directly. **112** is mobile-only emergency routing for weak/no own-carrier signal or no SIM, then press 0 for police or 9 for fire/ambulance.
- Presidential Alert / 國家級警報 cannot be opted out on supported devices, but delivery depends on device capability, network coverage, alert category, and target area; never promise every Taiwan SIM will receive every alert.
- During an air-raid drill or actual air-raid alert, follow police/military/civil-defense instructions and official announcements; schedules and controls vary by year and region.

---

### 17. 緊急狀況 Emergency & Safety

**Do not make users read a reference file in an emergency. Answer immediately from this section.**

### Emergency Numbers (memorize these)
| | Number |
|---|---|
| Police 警察 | **110** |
| Fire & Ambulance 消防/救護 | **119** |
| Mobile emergency routing if 110/119 cannot connect / no SIM | **112** → press 0 for police, 9 for fire/ambulance |
| Domestic Violence / Child / Sexual Assault | **113** |
| Anti-Fraud | **165** |
| Suicide Prevention | **1925** |
| Migrant / foreign worker labor rights, complaints, interpretation | **1955** |

### Advisory / Support Hotlines (verify hours before promising availability)
| | Number |
|---|---|
| Foreigner/new resident daily-life consultation | **1990**; overseas **886-800-001990** |
| Disease prevention / epidemic consultation | **1922** or **0800-001922** |
| Weather / Typhoon Info | CWA web/app first; phone weather recordings **166** Mandarin / **167** Hakka-Taiwanese-English where available; verify current CWA phone routes before quoting |
| Long-Term Care | **1966** |
| Social welfare consultation | **1957** |
| Consumer Protection | **1950** |
| Food Safety | **1919** |
| Pregnancy care consultation | **0800-870-870** |
| Drug-use/addiction consultation | **0800-770-885** |
| Family caregiver support | **0800-507-272** |

**Primary routing:**
| Question type | Go to |
|---|---|
| Real-time typhoon / earthquake alerts | CWA App: 天氣e點靈; web: https://www.cwa.gov.tw |
| Typhoon holiday / stop-work-school announcement | DGPA: https://www.dgpa.gov.tw/typh/daily/nds.html plus user's city/county government |
| Earthquake info after a quake | CWA Seismological Center: https://scweb.cwa.gov.tw; shows magnitude, epicenter, tsunami status |
| Legal aid | 法律扶助基金會 LAF: https://www.laf.org.tw; **412-8518** (landline direct, mobile add **02**); verify menu, hours, language, and issue scope |
| Your country's representative office | Search "[country] representative office Taipei" — Taiwan has unofficial offices for most countries |
| Reporting landlord/employer illegal behavior | 1999 (Taipei city issues); 110 (police); 1955 for migrant/foreign-worker labor rights; local labor bureau/MOL route for other labor disputes |
| DV / abuse resources | **113** → emergency shelter referral, protection order guidance, legal aid |
| Scam message/call but no money sent | **165** for verification; do not click links or call numbers in the message |
| Money just sent to scammer | Call bank/card issuer immediately, call **165**, preserve transfer details, and complete police report steps |
| Lost passport | Police report if stolen/lost; contact user's representative office; then NIA if ARC/visa status is affected |

**Key routing notes:**
- Typhoon stop-work/school: announced **per city/county** and sometimes narrower areas — Taipei announcing doesn't mean New Taipei has announced; always check the user's specific city
- 112 is not a replacement for 110/119 when normal signal works; it adds a voice-menu step and is mainly for mobile emergency routing.
- For language barriers, NIA 1990 provides daily-life consultation in multiple languages; in immediate danger still call 110/119 first, or 112 if mobile routing is needed.

---

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
