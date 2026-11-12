# OSINT Report: +1 (817) 217-1519

| Field | Value |
| --- | --- |
| **Case ID** | `OSINT-PN-18172171519` |
| **Target** | `18172171519` / `+1 817-217-1519` |
| **Authorization** | Stated authorized by requester |
| **Collection window** | 2026-11-12 (UTC) |
| **Classification** | Open-source / public data only |
| **Analyst** | Cursor cloud agent |

---

## 1. Executive summary

The target is a **valid United States NANP wireless number** geolocated to the **Arlington / Fort Worth–Dallas (DFW) metro**, Texas (area code **817**, overlay **682**).

**Thousand-block pooling** assigns line `1519` to block **1** (`817-217-1xxx`), originally allocated to **MetroPCS, Inc. (OCN 5562)** — not the Verizon Wireless assignment that many prefix-level directories report for `817-217` as a whole. MetroPCS is part of the **T-Mobile** family; **current serving carrier may differ if the number has been ported** (LRN/CNAM paid lookup required; not available in this free collection).

**No subscriber name, address, email, or social profile** was identified in open web indexes. Community reputation sources show **no spam/scam complaint footprint**.

**Confidence:** High for format/geo/NXX-block attribution; Low for current carrier and identity (identity unresolved).

---

## 2. Number normalization

| Format | Value |
| --- | --- |
| Digits as provided | `18172171519` |
| E.164 | `+18172171519` |
| International | `+1 817-217-1519` |
| National | `(817) 217-1519` |
| RFC3966 | `tel:+1-817-217-1519` |
| Country / region | United States (`US`) |
| Valid (libphonenumber) | **Yes** |
| Possible | **Yes** |
| libphonenumber type | `FIXED_LINE_OR_MOBILE` (US wireless not always distinguished) |
| Time zone | `America/Chicago` (Central) |

**Tooling:** Python `phonenumbers` library; PhoneInfoga v2.11.0 local scanner.

---

## 3. Geographic & numbering-plan intelligence

### 3.1 NPA (area code) 817

- **State:** Texas
- **Primary market:** Fort Worth / Arlington / surrounding communities
- **Overlay:** 682 (10-digit local dialing)
- **LATA:** 552 (Dallas, TX)
- **CBSA:** Dallas–Fort Worth–Arlington, TX (`19100`)

### 3.2 NXX (central office / prefix) 817-217

| Attribute | Value | Source |
| --- | --- | --- |
| Use type | **Wireless** | area-codes.com, AT&T prefix registry, Wirefly |
| Rate center | **Arlington, TX** | Local Calling Guide |
| County | **Tarrant** | area-codes.com / areacodebase |
| Approx. coords | **32.734, -97.1094** | area-codes.com / areacodebase |
| Associated ZIPs (rate-center context) | **76011, 76012, 76010** | area-codes.com |
| Prefix intro (reported) | **2006-11-02** | area-codes.com / Wirefly |
| Prefix-level company (A-block / summary) | Cellco Partnership dba **Verizon Wireless – TX** (OCN **6506**) | Multiple NXX summaries |

> **Caveat:** Prefix-level “carrier” fields often reflect the NXX code holder or the majority / A-block assignee. They are **not** a reliable current-carrier answer for a specific line under thousand-block pooling and number portability.

### 3.3 Thousand-block assignment (critical)

Line number **1519** → thousands digit **1** → block **`817-217-1`**.

From [Local Calling Guide](https://www.localcallingguide.com/lca_prefix.php?npa=817&nxx=217) (data stamped **2026-11-01**):

| NPA-NXX | Block | Rate centre | Switch (CLLI) | OCN / Company | Eff. date |
| --- | --- | --- | --- | --- | --- |
| 817-217 | A | Arlington, TX | DLLSTXJFDMD | 6506 CELLCO / Verizon Wireless – TX | — |
| 817-217 | **0–3** | Arlington, TX | **DLLTTXID1MD** | **5562 METROPCS, INC.** | 2007-05-25 |
| 817-217 | 4–9 | Arlington, TX | DLLSTXJFDMD | 6506 CELLCO / Verizon Wireless – TX | 2007 (varies) |

**Implication for `…-1519`:** Original block assignee = **MetroPCS, Inc.** Switch CLLI `DLLTTXID1MD` is in the Dallas switch footprint. Many automated “817-217 = Verizon” lookups are **misleading for this specific line**.

---

## 4. Carrier assessment

| Layer | Finding | Confidence |
| --- | --- | --- |
| Line type (NXX use) | Wireless | High |
| Original thousand-block OCN | MetroPCS, Inc. (`5562`) | High |
| Corporate successor context | MetroPCS → T-Mobile US family | High (historical) |
| Current serving carrier (LRN) | **Unknown** — free LRN endpoints blocked (Cloudflare / API keys) | N/A |
| Portability | Possible; not proven | — |
| VoIP indicators | None at NXX/block level (wireless CO code) | Medium |

**Not obtained this run:** Twilio Lookup, FreeCarrierLookup (blocked), AbstractAPI, CNAM, HLR/LRN live query.

---

## 5. Open-web footprint & reputation

### 5.1 Exact-match web presence

Searches across formats (`817-217-1519`, `(817) 217-1519`, `8172171519`, `+18172171519`, `817.217.1519`) returned:

- NPA-NXX / area-code reference pages only
- **No** indexed news articles, business listings, documents, paste dumps, or Reddit threads naming this exact line

PhoneInfoga Google dorks were generated for social, disposable SMS, reputation, and document surfaces; **no live hit confirming a public identity** was returned via web search.

### 5.2 Community / spam reputation

| Source | Result |
| --- | --- |
| **RoboKiller** (`lookup.robokiller.com`) | User reputation **Positive**; status **Allowed**; **0 comments** |
| **Should I Answer?** | **No rating**; no user reviews; **no suspicious activity** in their DB (page generated on request / noindex) |
| **Truecaller / Sync.me** | Pages load; **caller name gated** behind sign-in — no public identity extracted |
| **800notes / WhoCallsMe / Tellows / SpamCalls** | HTTP **403** from this environment (bot protection) |
| **NoCall / CallerComplaints** | **404** for this number path |
| **Reddit / Pastebin / GitHub** exact search | **No hits** on the full number |

**Assessment:** Low public complaint signal; consistent with a non-notorious / non-telemarketing-facing line **or** a line that simply has not been reported. Absence of complaints ≠ proof of legitimacy for any specific call.

---

## 6. Negative findings (important)

The following were **not** established from open sources in this investigation:

- Subscriber legal name or CNAM display name
- Current residential / business address tied to the MSISDN
- Email, username, or social media account ownership
- Live porting history / current OCN via LRN
- Association with a specific employer or domain
- Evidence the number is a disposable SMS receive-service line

People-search aggregators (Whitepages, TruePeopleSearch, FastPeopleSearch, That’s Them) returned **403** from this host and were not used to assert identity.

---

## 7. Risk & analytic notes

1. **Spoofing:** Any NANP number can appear on Caller ID via illegal spoofing; NXX geography does not prove the caller’s physical location.
2. **Prefix vs block vs LRN:** Treat Verizon-labeled `817-217` summaries as **weak** for this MSISDN; prefer thousand-block + live LRN.
3. **Overlay 682:** Local DFW numbers may also present as 682; unrelated to this target’s assignment but relevant to regional dialing analysis.
4. **Privacy:** Report limited to public telecom metadata and community reputation; no attempt to bypass paywalls, CAPTCHAs, or authentication.

---

## 8. Recommended next steps (authorized / lawful)

If deeper investigation is authorized and appropriately scoped:

1. **LRN / current carrier** via Twilio Lookup, Telnyx, or similar (paid) API  
2. **CNAM** dip for display name (often incomplete for mobiles)  
3. **HLR / line type intelligence** for mobile vs landline confirmation  
4. Manual review of authenticated Truecaller / carrier portals **only with lawful access**  
5. Correlate with any **first-party** CRM, SMS, or call-detail records the authorizing party already controls  

---

## 9. Sources

- libphonenumber / Python `phonenumbers` (local validation)
- PhoneInfoga v2.11.0 (dork generation + local format scan)
- https://www.localcallingguide.com/lca_prefix.php?npa=817&nxx=217
- https://www.area-codes.com/exchange/exchange.asp?npa=817&nxx=217
- https://npa.areacodebase.com/node/358971
- https://www.att.com/local/area-codes/817
- https://telecomrouting.com/reference/area-codes/817/
- https://www.wirefly.com/area-codes/817
- https://lookup.robokiller.com/ (query `(817) 217-1519`)
- https://www.shouldianswer.com/phone-number/817-217-1519
- Web search sweeps (Google-indexed results via Cursor WebSearch), 2026-11-12

---

## 10. Chain of custody / artifacts

| Artifact | Path |
| --- | --- |
| This report | `osint-reports/18172171519/REPORT.md` |
| Machine-readable summary | `osint-reports/18172171519/findings.json` |
| PhoneInfoga console capture | retained in analyst workspace `/tmp/phoneinfoga_out.txt` (not committed) |

**Disclaimer:** This product is derived solely from publicly available information and passive collection. It is not a substitute for lawful process, carrier records, or a formal subscriber subpoena. Findings may become stale as numbers port and databases update.
