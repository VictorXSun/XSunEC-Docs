---
title: "💳 Fiat24 × XSunEC Integration Guide (v1.2 — Global Accounts Integration)"
version: v1.2
category: payments
status: verified
date: 2025-10-25
author: XSunEC Documentation
tags: [Fiat24, Wise, Payoneer, Payments, Integration, Compliance, API]
---

# 💳 Fiat24 × XSunEC Integration Guide (v1.2 — Global Accounts Integration)

**Scope:** Full verification of Fiat24 account linkage, API accessibility, DNS ownership, and roadmap for Payoneer/Wise integrations.  
**Maintainer:** [victor@xsunec.com](mailto:victor@xsunec.com)  
**Last updated:** 2025-10-25

---

## 1️⃣ Overview

This document records the verified connection between **XSunEC** and **Fiat24**, including API reachability, DNS validation, and compliance snapshots.  
It extends version **v1.1** by introducing metadata consistency, API schema, and the **Next Steps Roadmap** toward a unified multi-channel financial system.

**Objectives:**
- ✅ Confirm API endpoint reachability (`api.fiat24.com`)
- ✅ Verify DNS ownership under `xsunec.com`
- ✅ Record live account dashboard screenshots (masked per GDPR)
- ✅ Prepare next-phase Payoneer & Wise integrations

---

## 2️⃣ Evidence Summary Table

| Step                   | Evidence                                                                                                                                          | Status                    |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- |
| Fiat24 Dashboard Login | ![Fiat24 Verification Screen](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_Verification_Screen.png) | ✅                         |
| Account Linking Proof  | ![Fiat24 Account Linked](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_Account_Linked.png)           | ✅                         |
| Wallet Overview        | ![Fiat24 Wallet Interface](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_Wallet_Interface.png)       | ✅                         |
| Add USD Interface      | ![Fiat24 Add USD Interface](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_AddUSD_Interface.png)      | ✅                         |
| Sell Token Interface   | ![Fiat24 Sell Interface](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_Sell_Interface.png)           | ✅                         |
| API Test Result        | ![Fiat24 API Test](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_API_Test.png)                       | ⚠️ Expected 403 Forbidden |
| DNS Configuration      | ![Fiat24 DNS Config](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_DNS_Config.png)                   | ✅ Verified TXT + CNAME    |

> Evidence verified on **2025-10-25** and stored under `/integration/_evidence/`.

---

## 3️⃣ API Endpoint & Response Schema

### Endpoint Tested
```bash
curl -v https://api.fiat24.com/v1/info
```

### Result
> **403 Forbidden** — Endpoint reachable, requires authorization.  
> Confirms API server availability, TLS validity, and gateway access.

### Expected Response Schema (simplified JSON)
```json
{
  "status": "error",
  "code": 403,
  "message": "Forbidden - authentication required",
  "timestamp": "2025-10-24T08:00:00Z"
}
```

---

## 4️⃣ DNS & HTTPS Validation

| Type | Name | Target / Value | Proxy | Status |
|------|------|----------------|--------|--------|
| CNAME | fiat24 | api.fiat24.com | DNS only | ✅ |
| TXT | fiat24-verification | xsunec-fiat24-ownership | DNS only | ✅ |
| SSL | GitHub Pages / Cloudflare | Auto-issued Let’s Encrypt | — | ✅ |

📸 `Fiat24_DNS_Config.png` provides verification of TXT record proof of ownership.

---

## 5️⃣ Account Dashboard Overview

| Field | Description |
|-------|-------------|
| Account ID | #18602810 |
| Login Email | v***@gmail.com (redacted) |
| Wallet | `0x00cB...EcAECC` (Arbitrum chain) |
| Fiat Balances | USD 12.38 / EUR 0.50 / CHF 0.00 / RMB 0.00 |
| Debit Card | Active |
| Transactions | PayPal and FX conversions visible |
| Compliance | GDPR-compliant, Swiss FINMA oversight |

---

## 6️⃣ Compliance & Privacy Notes

- All screenshots are masked for privacy.  
- Stored under `/integration/_evidence/` per XSunEC doc policy.  
- Fiat24 integration exposes **no private keys** or user data.  
- API requests executed anonymously for verification only.  
- DNS TXT record serves as digital ownership proof.  

> Compliance Reference: Swiss FINMA RegTech framework + GDPR Art. 25 (Data Protection by Design).

---

## 7️⃣ Integration Validation Summary

| Layer | Method | Status |
|-------|---------|--------|
| API | `curl` reachability test | ✅ Verified (403 Expected) |
| DNS | TXT & CNAME verification | ✅ Completed |
| HTTPS | Certificate check (Let’s Encrypt) | ✅ Valid |
| Dashboard | Fiat24 WebUI login | ✅ Verified |
| Evidence | Screenshots saved | ✅ Documented |

---

## 8️⃣ Next Steps & Multi-Channel Roadmap

| Phase | Integration | Objective | Target Version |
|-------|--------------|------------|----------------|
| Phase 2 | **Payoneer Connection** | Validate API endpoints, withdrawal & KYB link | v1.0-draft |
| Phase 3 | **Wise Multi-Currency Accounts** | Test multi-IBAN routing, USD/EUR transfers | v1.0-draft |
| Phase 4 | **Webhook Monitoring** | Deploy Cloudflare Worker to ping Fiat24/Wise APIs weekly | v1.0 |
| Phase 5 | **Finance Dashboard (Obsidian + GitHub Pages)** | Auto-generate compliance snapshot for all accounts | v1.1 |

**Purpose:**  
To evolve **XSunEC’s funding infrastructure** into a transparent, compliant, and automated ecosystem enabling:  
- Real-time account health visibility  
- Simplified global settlement  
- Continuous regulatory monitoring

---

## 9️⃣ Reference & Contact

- Fiat24 Official: [https://www.fiat24.com](https://www.fiat24.com)  
- Developer Docs: [https://api.fiat24.com](https://api.fiat24.com)  
- Brandfetch Integration: [Brandfetch_Integration_Guide.md](./Brandfetch_Integration_Guide.md)  
- Maintained under: **💳 Payments & Finance v1.2 — Global Accounts Integration**  
- Contact: [victor@xsunec.com](mailto:victor@xsunec.com)

---

© 2025 **XSunEC Global Operations** — Smart · Compact · Reliable
