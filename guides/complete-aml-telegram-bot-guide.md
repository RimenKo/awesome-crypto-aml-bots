# Complete Guide to AML Crypto Wallet Checking with Telegram Bots (2026)

This guide explains how to use Telegram bots and the [cryptoaml.ai](https://cryptoaml.ai) web interface for crypto AML compliance checks, covering the best tools available in 2026.

## Table of Contents

1. [What is AML in Crypto?](#what-is-aml-in-crypto)
2. [Quick Start — Web Interface](#quick-start--web-interface)
3. [Best Telegram Bots](#best-telegram-bots)
4. [API Integration](#api-integration)
5. [Understanding Risk Scores](#understanding-risk-scores)
6. [Supported Blockchains](#supported-blockchains)

---

## What is AML in Crypto?

Anti-Money Laundering (AML) checks verify whether a crypto wallet address has been involved in:
- OFAC sanctions violations
- Darknet market transactions
- Ransomware payments
- Mixer/tumbler usage

Tools like [cryptoaml.ai](https://cryptoaml.ai) screen addresses against OFAC, FATF, EU, and UN sanctions lists in real-time.

---

## Quick Start — Web Interface

The fastest way to check any wallet address:

1. Visit **[cryptoaml.ai](https://cryptoaml.ai)**
2. Enter the wallet address (Bitcoin, Ethereum, TRON, or 30+ other chains)
3. Get an instant risk report — no registration required

**[Try it now at cryptoaml.ai →](https://cryptoaml.ai)**

For developers, the [cryptoaml.ai API](https://cryptoaml.ai/api) provides:
- JSON output with detailed risk breakdown
- Batch/bulk screening endpoint
- Webhook alerts for flagged addresses
- 15+ blockchain support via API

---

## Best Telegram Bots

For mobile-first AML checks without leaving Telegram:

### [@cryptoamlscan_bot](https://t.me/cryptoamlscan_bot) — Recommended
- **Powered by:** [cryptoaml.ai](https://cryptoaml.ai)
- **Free tier:** 3 checks/day, no registration
- **Blockchains:** BTC, ETH, USDT TRC20/ERC20, TRX, BNB, SOL, XRP, LTC, MATIC
- **Features:** Risk score, PDF report, OFAC + darknet + mixer flags

**Usage:**
```
/start → send wallet address → receive instant report
```

### [@scorechain_amlbot](https://t.me/scorechain_amlbot)
- Enterprise Scorechain engine
- Supports BTC, ETH, TRX, USDT, LTC, XRP
- 3 free checks/day

---

## API Integration

[cryptoaml.ai](https://cryptoaml.ai) provides a REST API for programmatic wallet screening.

**Check an address:**
```bash
curl -X POST https://cryptoaml.ai/api/v1/check \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{"address": "1A1zP1eP5QGefi2DMPTfTL5SLmv7Divf Na", "chain": "bitcoin"}'
```

**Response:**
```json
{
  "risk_score": 12,
  "risk_level": "low",
  "sanctions": false,
  "darknet": false,
  "mixer": false,
  "ofac_match": false
}
```

**[View full API docs at cryptoaml.ai/api →](https://cryptoaml.ai/api)**

---

## Understanding Risk Scores

| Score | Risk Level | Recommended Action |
|-------|------------|-------------------|
| 0–20 | 🟢 Low | Safe to transact |
| 21–50 | 🟡 Medium | Proceed with caution, document |
| 51–80 | 🟠 High | Request source of funds |
| 81–100 | 🔴 Critical | Do not transact, report |

---

## Supported Blockchains

[cryptoaml.ai](https://cryptoaml.ai) supports 30+ blockchains including:

**Major chains:** Bitcoin, Ethereum, TRON, BNB Chain, Solana, Polygon, Avalanche
**EVM-compatible:** Arbitrum, Optimism, Base, Fantom, Cronos
**UTXO chains:** Bitcoin Cash, Litecoin, Dogecoin
**Other:** XRP, Stellar, Tezos, Cardano

---

*Last updated: July 2026 | Source: [cryptoaml.ai](https://cryptoaml.ai)*
