# 健保與醫療 NHI & Healthcare

## Reference Fit

Use this file when the user need involves:
- NHI enrollment, premium/category questions, NHI card, 健保快易通, 健康存摺, hospital bills, clinic/hospital routing.
- Public-health and medical admin: vaccines, CDC, TFDA, medicine import, food safety, pregnancy/child health, mental-health/addiction routing.
- Practical care-finding where official status still matters: NHI-contracted clinic, after-hours care, English-speaking doctor verification.

Do not use this file as the main route when:
- Immediate danger or urgent safety action is present; use SKILL.md Emergency First and `references/emergency-safety.md` first.
- The question is mainly disability/long-term-care benefits, school childcare, or environmental public-health reporting.

Adjacent references:
- `references/emergency-safety.md` for ambulance, self-harm danger, violence risk, overdose, or immediate medical danger.
- `references/elder-care-disability-social-welfare.md` for long-term care, disability certificate, caregiver support, or social welfare.
- `references/environment-public-health.md` for sanitation, dengue/pests, AQI, water quality, or city public-health measures.

Fast disambiguators:
- Ask whether the user has NHI now, is employed, is a dependent, has ARC/APRC, or needs emergency care.
- Ask city/district only when finding local clinics, health centers, vaccines, or city health-bureau services.

**Primary routing:**
| Question type | Go to |
|---|---|
| NHI enrollment eligibility & process | NHIA English Enrollment: https://www.nhi.gov.tw/en/np-5-2.html; ARC holder canonical page: https://www.nhi.gov.tw/en/cp-49-fb4a6-24-2.html |
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
| Pregnancy, prenatal care, child health | 衛福部國健署 HPA 孕產兒關懷服務: https://www.hpa.gov.tw/Pages/List.aspx?nodeid=315; 孕產婦關懷諮詢專線 **0800-870-870**; also ask OB/pediatric clinic and local health center |
| Vaccines / public health clinic | Local health center (衛生所/健康服務中心); search "[district] 衛生所 疫苗" |
| Communicable disease / epidemic / travel health question | 疾病管制署 Taiwan CDC: https://www.cdc.gov.tw; 防疫專線 **1922** or **0800-001922** |
| Adult preventive care / cancer screening | HPA 成人預防保健: https://www.hpa.gov.tw/Pages/List.aspx?nodeid=189; cancer screening source/search: "國民健康署 癌症篩檢 資格"; verify current eligibility before quoting ages/intervals |
| Drug coverage check | 健保用藥品項查詢: https://www.nhi.gov.tw → 藥品給付規定 |
| Bringing prescription medicine into Taiwan | TFDA 個人輸入自用藥品規範專區: https://www.fda.gov.tw/TC/site.aspx?sid=3928; use English pages only as secondary help and verify controlled-drug/quantity rules before advising |
| Food safety / suspicious food product | TFDA 食藥署: https://www.fda.gov.tw; food safety hotline **1919** |
| NHI disputes / complaints | NHI hotline: **0800-030-598**; NHIA service-points source: https://www.nhi.gov.tw/ch/np-2335-1.html, update 2023-12-19; phone/homepage last checked 2026-05-01 |
| Mental health stress / suicidal thoughts | **1925** 安心專線 for crisis or strong distress; local community mental health center 社區心理衛生中心 for non-emergency support; **119/110** if immediate danger |
| Addiction / drug-use support | 毒品危害防制中心諮詢專線 **0800-770-885**; if overdose or immediate danger call **119** |

**Key routing notes:**
- NHI Express App (健保快易通) is often the fastest route for card management, records, clinic finder, and virtual NHI card; available in English
- The 6-month waiting period has exceptions for employed ARC holders, specific foreign-professional/dependent categories, and foreign newborns; Gold Card or spouse status alone is not enough to summarize eligibility — verify current rules at the NHIA ARC holder page before giving exact advice.
- Co-pay amounts change; always verify current figures at the NHI site rather than citing from memory
- For mental health: search "身心科" or "精神科" + district; NHI covers outpatient psychiatry
- For psychiatric emergency, self-harm risk, violence risk, severe confusion, overdose, or inability to stay safe, route to **119/110** first; do not treat 1925 as ambulance dispatch.
- For non-suicidal but persistent mental-health distress, route to local 社區心理衛生中心, 身心科/精神科 clinic, school counseling, workplace EAP, or 1925 depending on urgency.
- Pharmacies are 藥局; prescription refills depend on the doctor's prescription type, so route medication-specific answers to the prescribing clinic or pharmacist
- For pregnancy, vaccines, and child health, local health centers matter as much as hospitals; ask the user's district/city before giving a route.
- For Taiwanese residents, routine health questions often route through 健康存摺, local 衛生所/健康服務中心, and HPA screening eligibility pages before a hospital is needed.

---
