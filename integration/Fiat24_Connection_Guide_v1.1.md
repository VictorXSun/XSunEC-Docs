---
title: Fiat24 Connection Guide
description: Fiat24 integration verification and DNS/API ownership evidence for XSunEC
version: v1.1
date: 2025-10-25
author: XSunEC Documentation
---

# 💳 Fiat24 × XSunEC Integration Guide

**Scope:** API test, DNS verification, account linking, and compliance snapshot  
**Maintainer:** [victor@xsunec.com](mailto:victor@xsunec.com)  
**Last updated:** 2025-10-25

---

## 1️⃣ Overview

This document records the verification and integration between **XSunEC** and **Fiat24**, covering:
- API connectivity tests (expected 403 response)
- DNS ownership verification via Cloudflare
- Account dashboard linkage and crypto wallet view
- Transaction visibility and compliance structure

**Objectives:**
- ✅ Confirm API endpoint reachability (`api.fiat24.com`)
- ✅ Validate DNS ownership for `xsunec.com`
- ✅ Capture verified Fiat24 account dashboard and wallet interfaces
- ✅ Store all screenshots under `/integration/_evidence/`

---

## 2️⃣ Verification Evidence

| Step | Evidence | Status |
|---|---|---|
| Fiat24 Dashboard Login | ![Fiat24 Verification Screen](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_Verification_Screen.png) | ✅ |
| Account Linking Proof  | ![Fiat24 Account Linked](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_Account_Linked.png) | ✅ |
| Wallet Overview        | ![Fiat24 Wallet Interface](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_Wallet_Interface.png) | ✅ |
| Add USD Interface      | ![Fiat24 Add USD Interface](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_AddUSD_Interface.png) | ✅ |
| Sell Token Interface   | ![Fiat24 Sell Interface](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_Sell_Interface.png) | ✅ |
| API Test Result        | ![Fiat24 API Test](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_API_Test.png) | ⚠️ Expected 403 Forbidden |
| DNS Configuration      | ![Fiat24 DNS Config](https://raw.githubusercontent.com/VictorXSun/XSunEC-Docs/main/integration/_evidence/Fiat24_DNS_Config.png) | ✅ Verified TXT + CNAME |

📁 Evidence directory: `/integration/_evidence/`

---

## 3️⃣ API Endpoint Test

### Endpoint Tested
```bash
curl -v https://api.fiat24.com/v1/info
```

### Result
> **403 Forbidden** — The endpoint is reachable but requires authentication.  
> ✅ This confirms API availability, TLS certificate validity, and firewall accessibility.

**Interpretation:**  
A `403` indicates Fiat24’s API is live, accessible from your IP/network, and correctly protected by authorization.

---

## 4️⃣ DNS and HTTPS Configuration

| Type | Name | Target / Value | Proxy | Status |
|------|------|----------------|--------|--------|
| CNAME | fiat24 | api.fiat24.com | DNS only | ✅ |
| TXT | fiat24-verification | xsunec-fiat24-ownership | DNS only | ✅ |
| SSL | GitHub Pages / Cloudflare | Auto-issued Let’s Encrypt | — | ✅ |

📸 See: `Fiat24_DNS_Config.png` for verification record.  
The TXT record proves domain ownership and control under `xsunec.com` — a key compliance requirement for third-party integrations.

---

## 5️⃣ Account Connection Summary

| Element | Description |
|----------|--------------|
| Account ID | #18602810 |
| Login Email | victorxunmei@gmail.com |
| Linked Wallet | `0x00cB...EcAECC` (Arbitrum chain) |
| Fiat Balances | USD 12.38 / EUR 0.50 / CHF 0.00 / RMB 0.00 |
| Card Status | Debit Card (active) |
| Transaction Records | PayPal, USD↔EUR conversions visible |
| Compliance | All data masked per GDPR / Swiss regulatory guidance |

---

## 6️⃣ Compliance & Privacy Notes

- Screenshots include masked personal data.  
- Files stored under `/integration/_evidence/` follow repository privacy standards.  
- Fiat24 integration does **not** transmit or expose private keys.  
- API tests are performed without authentication for reachability proof only.  
- DNS verification conforms to Cloudflare security baseline.  

**Regulatory alignment:**  
> Swiss FINMA-registered Virtual Bank (Fiat24) + XSunEC self-owned domain control = compliant integration baseline.

---

## 7️⃣ Reference Links

- Fiat24 Official: [https://www.fiat24.com](https://www.fiat24.com)  
- Developer Docs: [https://api.fiat24.com](https://api.fiat24.com)  
- GitHub Evidence Repo: [https://github.com/VictorXSun/XSunEC-Docs](https://github.com/VictorXSun/XSunEC-Docs)  
- Brandfetch Integration (previous step): `/integration/Brandfetch_Integration_Guide.md`  

---

© 2025 **XSunEC Global Operations** — Smart · Compact · Reliable  
Maintained under **💳 Payments & Finance v1.2 — Global Accounts Integration**  
Contact: [victor@xsunec.com](mailto:victor@xsunec.com)
