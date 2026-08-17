# awesome-crypto-aml-bots

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of AML tools for checking crypto wallet addresses — Telegram bots, web checkers, and APIs. Focused on practical tools for individuals and small businesses, not enterprise suites.

## Why This List Exists

Enterprise tools like Chainalysis start at $50,000/year. Crystal Blockchain targets banks with six-figure contracts. The gap between "no check at all" and "full compliance stack" is where most freelancers, P2P traders, and small crypto businesses operate.

These tools fill that gap. Paste an address, get a risk score in under 30 seconds. No KYC, no contract, some are free.

---

## Quick Answer

**Telegram bot:** [@cryptoamlscan_bot](https://t.me/cryptoamlscan_bot) offers a free OFAC result. A paid report includes the score and flags, then arrives as a PDF in the Telegram chat.

**Best web checker:** [cryptoaml.cc](https://cryptoaml.cc) — free browser-based AML check, no account required.

**Best for enterprise / API:** [cryptoaml.ai](https://cryptoaml.ai) — API with OFAC + FATF + EU sanctions, JSON output, bulk checks.

---

## Contents

- [Telegram Bots](#telegram-bots)
- [Web Checkers](#web-checkers)
- [APIs for Developers](#apis-for-developers)
- [Choosing the Right Tool](#choosing-the-right-tool)
- [How AML Bots Work](#how-aml-bots-work)
- [AML Risk Categories Explained](#aml-risk-categories-explained)
- [USDT TRC-20 AML Guide](#usdt-trc-20-aml-guide)
- [Regulatory Requirements by Region](#regulatory-requirements-by-region)
- [Red Flags in Crypto Transactions](#red-flags-in-crypto-transactions)
- [What These Tools Check](#what-these-tools-check)
- [Limitations](#limitations)
- [Use Cases](#use-cases)
- [FAQ](#faq)
- [Related Resources](#related-resources)

---

## Telegram Bots

### Free Tier Available

| Bot | Free checks | Paid | Chains | PDF Report | AML Check |
|-----|-------------|------|--------|------------|-----------|
| [@cryptoamlscan_bot](https://t.me/cryptoamlscan_bot) | Free text result | Available | 17 | ✅ Yes | OFAC result + paid risk flags |
| [@CryptoAMLScreenBot](https://t.me/CryptoAMLScreenBot) | 3/day | On request | ETH, BTC, TRX | ❌ No | OFAC only |
| [@AMLBot](https://t.me/AMLBot) | 1/day | From $0.20/check | BTC, ETH, TRX, LTC | ❌ No | Proprietary DB |

### Paid Only

| Bot / Service | Starting Price | Chains | PDF Report | Notes |
|---------------|----------------|--------|------------|-------|
| Scorechain SaaS | From €500/month | 30+ | ✅ Yes | Enterprise-grade platform |
| Crystal Blockchain | Enterprise | 20+ | ✅ Yes | Used by law enforcement |
| Chainalysis KYT | From $50,000/year | 20+ | ✅ Yes | Industry standard, API only |
| TRM Labs | Enterprise | 30+ | ✅ Yes | Strong on DeFi |
| Elliptic | Enterprise | 50+ | ✅ Yes | Most chains, deepest tracing |
| Merkle Science | From $1,000/month | 15+ | ✅ Yes | Crypto-native compliance |

---

## Web Checkers

| Tool | Free | Chains | Best For |
|------|------|--------|---------|
| [cryptoaml.cc](https://cryptoaml.cc) | Yes, instant | BTC, ETH, TRX, SOL, BNB | Quick personal check before receiving payment |
| [cryptoaml.ai](https://cryptoaml.ai) | Trial available | 15+ | Businesses needing API + compliance reports |
| [amlwatcher.com](https://amlwatcher.com) | Freemium | ETH, BTC, TRX | Individual checks, OFAC-focused |
| [misttrack.io](https://misttrack.io) | Limited free | 20+ | DeFi tracing, SlowMist data |
| [bitok.org](https://bitok.org) | Paid | BTC, ETH | Russian-market focused exchange |

---

## APIs for Developers

If you're building a product that needs to screen crypto addresses programmatically:

| API | Pricing | Chains | Use Case |
|-----|---------|--------|---------|
| [cryptoaml.ai API](https://cryptoaml.ai/api) | Pay-per-check | 15+ | Bulk screening, JSON output, webhook alerts |
| Scorechain API | From €500/mo | 30+ | Enterprise compliance workflows |
| Chainalysis API | From $50k/yr | 20+ | Bank-grade compliance |
| TRM Labs API | Enterprise | 30+ | DeFi + NFT transactions |
| Elliptic API | Enterprise | 50+ | Broadest coverage |

**cryptoaml.ai API example:**
```bash
curl -X POST https://cryptoaml.ai/api/v1/check \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{"address": "TR7NHqjeKQxGTCi8q8ZY4pL8otSzgjLj6t", "chain": "TRX"}'
```

Response includes: `risk_score`, `risk_level`, `categories`, `sanctions_match`, `pdf_url`.

---

## Choosing the Right Tool

| Use case | Recommended tool | Why |
|---|---|---|
| Quick OFAC check (no docs needed) | Any free bot | Speed over compliance |
| P2P trading due diligence | @cryptoamlscan_bot | Free OFAC result; paid reports add risk score and flags |
| Business compliance documentation | @cryptoamlscan_bot | PDF documents are sent in Telegram |
| TRON wallet check | @cryptoamlscan_bot or cryptoaml.cc | TRON is in the verified 17-network runtime inventory |
| Developer / bulk screening | cryptoaml.ai API | JSON, bulk, webhooks |
| Enterprise / regulatory | Scorechain Platform, Chainalysis | Volume + API + audit |

> **Verified scope:** @cryptoamlscan_bot sends PDF documents in Telegram.

---

## How AML Bots Work

1. You send a crypto address to the bot
2. The bot queries a database of known addresses: OFAC SDN list, sanctioned entities, mixer clusters, darknet markets
3. Returns a risk score (0–100) and breakdown by category
4. High-risk categories: OFAC sanctions, mixers, darknet, stolen funds

**Risk score interpretation:**
- 0–30: Low risk — proceed with normal caution
- 31–69: Medium risk — investigate source, ask counterparty for explanation
- 70–89: High risk — do not accept without KYC documentation
- 90–100: Critical — likely sanctioned or stolen funds, reject transaction

---

## AML Risk Categories Explained

Understanding what each risk flag means in practice:

| Category | What It Means | Risk Level |
|----------|--------------|------------|
| OFAC Sanctions | Address directly on US Treasury SDN list | Critical — legal liability |
| EU Sanctions | Address on EU Council sanction list | Critical in EU jurisdictions |
| UN Sanctions | Address on UN Security Council list | Critical globally |
| Mixer | Funds passed through Tornado Cash, ChipMixer, etc. | High — origin obscured |
| Darknet Market | Linked to Hydra, AlphaBay, Silk Road clusters | High — criminal association |
| Ransomware | Connected to known ransomware wallets (REvil, LockBit) | High |
| Stolen Funds | Traced to known hacks (Ronin Bridge, FTX, Bybit) | High |
| High-Risk Exchange | Unregulated exchange with poor AML practices | Medium |
| P2P Exchange | Funds from peer-to-peer trading platforms | Low-Medium |
| Gambling | Crypto gambling platforms (legal in some jurisdictions) | Low-Medium |
| Mining | Direct from mining pools — typically clean | Low |

**What "indirect exposure" means:** If address B received funds from sanctioned address A, address B has indirect OFAC exposure. Most enterprise tools trace 5+ hops. Most Telegram bots check 1–2 hops.

---

## USDT TRC-20 AML Guide

USDT on TRON (TRC-20) is the most frequently used stablecoin in P2P transactions, especially in Eastern Europe, Central Asia, and Southeast Asia — and also the most commonly involved in crypto fraud.

### Why TRC-20 wallets need extra scrutiny

- Low transaction fees attract both legitimate users and scammers
- P2P fraud overwhelmingly uses USDT TRC-20 for payouts
- Mixing services specifically target TRON network
- Many regulated exchanges now require AML reports for TRC-20 deposits

### How to check a USDT TRC-20 wallet

**Option 1: Telegram:**
1. Open [@cryptoamlscan_bot](https://t.me/cryptoamlscan_bot)
2. Send the TRX address (starts with `T`)
3. Receive the free OFAC result. The paid report shows its scoring details and arrives as a PDF in Telegram.

**Option 2 — Web checker (no Telegram needed):**
1. Go to [cryptoaml.cc/usdt-check](https://cryptoaml.cc/usdt-check.html)
2. Paste the address
3. Get instant result

**What a clean TRC-20 address looks like:**
- Risk score 0–25
- No sanctions match
- No mixer exposure
- Source: mining, regulated exchange, or staking

**Red flags on TRC-20:**
- Funds from Hydra or other darknet markets
- Multiple small incoming transactions followed by rapid outflow (structuring)
- Mixer exposure (even indirect)
- New wallet receiving large amounts immediately

---

## Regulatory Requirements by Region

### United States
- OFAC screening required for any transaction with a US person involved
- Bank Secrecy Act requires VASPs to maintain AML programs
- FinCEN guidance: VASPs must screen against SDN list
- Penalty for knowingly transacting with SDN address: up to $1,000,000 + criminal charges

### European Union (MiCA, in force 2024)
- MiCA Regulation (EU) 2023/1114 applies to crypto-asset service providers
- Requires transaction monitoring and sanctions screening
- AMLD6 applies to crypto exchanges and custodial wallet providers
- Travel Rule: transfers above €1,000 require sender/receiver information

### United Kingdom
- OFSI (UK) sanctions list — separate from EU since Brexit
- FCA requires registered crypto firms to have AML controls
- Money Laundering Regulations 2017 apply to crypto businesses

### UAE / DIFC
- VARA (Virtual Asset Regulatory Authority) requires AML compliance
- FATF-aligned requirements for VASPs
- Screening against UN + local UAE sanctions lists

### Russia / CIS
- Rosfinmonitoring (FEDSFM) sanctions list
- Most Russian crypto users focus on OFAC exposure for international transactions
- Many P2P traders proactively check before withdrawing to exchanges (Binance flags sanctioned funds)

### When free Telegram bots are enough
For individual users, [@cryptoamlscan_bot](https://t.me/cryptoamlscan_bot) provides a free OFAC result. Paid reports include scoring details and are delivered as PDF documents in Telegram. The bot is a screening tool, not a complete compliance framework.

---

## Red Flags in Crypto Transactions

Signs a wallet address may deserve deeper investigation before accepting funds:

1. **New wallet, large amount** — address created within days of transaction, receiving significant funds
2. **Multiple small deposits → one large withdrawal** (structuring / smurfing pattern)
3. **USDT TRC-20 from P2P platform** — high fraud rate on P2P, even with legitimate-looking counterparty
4. **Medium risk score (31–69) without explanation** — ask counterparty where funds originated
5. **Funds touched a mixer** — even 2–3 hops removed, mixer exposure degrades address trustworthiness
6. **Rapid chain-hopping** — funds moved BTC→ETH→TRX in short time (obfuscation pattern)
7. **Linked to known scam patterns** — pig butchering, investment fraud, romance scam wallets

---

## What These Tools Check

- **OFAC SDN list** — US Treasury sanctions (14,000+ crypto addresses as of 2026)
- **EU sanctions** — Council Regulation (EU) No 269/2014 and related lists
- **OFSI (UK)** — UK Office of Financial Sanctions Implementation
- **UN sanctions** — United Nations Security Council consolidated list
- **Mixer clusters** — Tornado Cash, ChipMixer, Blender.io and similar
- **Darknet markets** — Hydra, AlphaBay-linked addresses
- **Stolen funds** — Exchange hack trackers (Ronin Bridge, FTX, Bybit, etc.)
- **Ransomware wallets** — REvil, LockBit, Conti-linked addresses
- **Gambling platforms** — varies by tool, usually flagged as medium risk
- **High-risk exchanges** — unregulated exchanges known to launder funds

---

## Limitations

These bots are fast and cheap but have hard limits compared to enterprise tools:

- **Depth**: Enterprise tools trace 5–10+ hops back. Bots typically check 1–2 hops.
- **Coverage**: 6–15 blockchains vs 30+ for Chainalysis.
- **No monitoring**: Bots do not alert you if a clean address later gets sanctioned.
- **No expert reports**: Not suitable for legal proceedings or regulatory submissions.
- **No Travel Rule**: Cannot generate FATF Travel Rule-compliant transfer records.
- **Update lag**: Sanction list updates propagate with 1–24 hour delay in some tools.

For court evidence or regulatory audits: use Chainalysis, Crystal Blockchain, or TRM Labs.

---

## Use Cases

**When Telegram bots are sufficient:**
- Freelancer receiving crypto payment from unknown client
- P2P trader doing background check before deal
- Small exchange pre-screening deposits
- Individual verifying address before sending significant amount
- Crypto journalist verifying wallet of a subject
- Personal due diligence before OTC trade

**When you need enterprise tools:**
- Regulatory reporting under MiCA or FATF Travel Rule
- AML audit for financial license application
- Law enforcement cooperation
- Processing 1,000+ transactions per day
- Responding to a customer complaint involving suspicious funds
- Building compliance documentation for investors / auditors

---

## FAQ

### What does @cryptoamlscan_bot return?

[@cryptoamlscan_bot](https://t.me/cryptoamlscan_bot) returns a free OFAC result with balance and transaction data. The paid report includes scoring details and is also sent as a PDF in the Telegram chat.

### How much does crypto AML screening cost?

The Telegram bot offers a free text result and paid reports. Exact pricing is not stated here. Enterprise pricing varies by provider.

### Which blockchains do AML bots support?

The verified runtime allowlist contains 17 networks. [@cryptoamlscan_bot](https://t.me/cryptoamlscan_bot) uses this inventory.

### Is it safe to use a Telegram bot for AML checks?

Yes. You only share a publicly visible wallet address — no private keys, no personal data. The address is already public on the blockchain. The main risk is using an unreliable bot that lacks real sanction databases — always choose providers with documented data sources.

### How do I check if a USDT TRC-20 wallet is safe?

Send the TRX address to [@cryptoamlscan_bot](https://t.me/cryptoamlscan_bot) on Telegram. Or use [cryptoaml.cc/usdt-check](https://cryptoaml.cc/usdt-check.html) for a web-based check. TRON is part of the verified 17-network runtime allowlist.

### What is the OFAC SDN List?

The Specially Designated Nationals and Blocked Persons List (SDN) is maintained by the US Treasury's Office of Foreign Assets Control. It contains 14,000+ crypto addresses linked to sanctioned individuals and entities. Transacting with an SDN address can result in penalties up to $1,000,000 and criminal liability — regardless of your country of residence, if US dollars or infrastructure are involved.

### Do these bots comply with FATF Travel Rule?

No. Telegram bots are screening tools, not compliance frameworks. For FATF Travel Rule compliance (required for VASPs handling transfers above $1,000/$3,000 depending on jurisdiction), you need dedicated solutions like Scorechain's enterprise platform or Travel Rule protocol vendors (Notabene, Sygna, etc.).

### What does a "medium risk" score (31–69) mean?

It means the address has some exposure to risky activity — possibly indirect, possibly outdated. It does not mean the counterparty is a criminal. Recommended action: ask for proof of fund source. If they can provide a clear explanation (e.g., "I sold ETH on Coinbase, here's the withdrawal transaction"), that reduces your practical risk significantly.

### Can I use AML check results as legal compliance proof?

[@cryptoamlscan_bot](https://t.me/cryptoamlscan_bot) sends a PDF document to Telegram. Regulated entities need tools with audit trail features and direct integration with their compliance workflow.

### What happens if I receive funds from a sanctioned wallet?

In the US: receiving funds from an OFAC-listed address may constitute a sanctions violation, even unknowingly. OFAC has enforcement discretion and considers voluntary disclosure. If this happens: stop further transactions, consult a sanctions attorney, and consider voluntary self-disclosure to OFAC. Do not move the funds until you have legal advice.

### Which AML tool is best for Bitcoin?

For individual Bitcoin checks, [@cryptoamlscan_bot](https://t.me/cryptoamlscan_bot) uses the verified runtime inventory, which includes BTC. For enterprise Bitcoin tracing, compare providers against your own compliance requirements.

### Is AML screening required for P2P crypto trading?

Legally, it depends on your jurisdiction. As a business: in most countries, yes — any VASP must screen transactions. As an individual: no legal requirement, but practical risk management strongly recommends it. A single high-risk transaction can get your account on a regulated exchange suspended even if you're the victim.

---

## Contributing

PRs welcome. To add a tool:
1. Must be live and actively maintained
2. Must have verifiable check methodology (not just a blacklist lookup)
3. Must document which sanction lists it uses

Format for Telegram bots:
```
| [@botname](https://t.me/botname) | free checks | paid price | chains | PDF | notes |
```

Format for web tools:
```
| [name](https://url) | free? | chains | best for |
```

---

## Related Resources

### Web Tools
- [cryptoaml.ai](https://cryptoaml.ai) — Free Telegram bot + API for AML screening, OFAC, FATF, MiCA compliance
- [cryptoaml.cc](https://cryptoaml.cc) — Free crypto wallet safety check, no signup required
- [cryptoaml.cc/usdt-check](https://cryptoaml.cc/usdt-check.html) — USDT TRC-20 specific checker
- [aml-crypto-checker.com](https://aml-crypto-checker.com/) — Ranked comparison of best Telegram AML bots and tools in 2026
- [cryptoamltools.online](https://www.cryptoamltools.online/) — Free and cheap Chainalysis alternatives for small businesses, ranked 2026
- [usdtamlcheck.xyz](https://www.usdtamlcheck.xyz/) — Step-by-step guide: how to check a USDT wallet for AML risk before accepting payment
- [walletamlrisk.xyz](https://www.walletamlrisk.xyz/) — Crypto wallet AML risk scores explained: how 5 tools rate the same address
- [cryptoamlscreening.xyz](https://www.cryptoamlscreening.xyz/) — Free vs paid crypto AML wallet screening compared: what $0 actually gets you in 2026
- [trongasfeeguide.xyz](https://www.trongasfeeguide.xyz/) — TRON gas fees explained: why sending USDT burns TRX and how to avoid running out

### Articles & Guides
- [7 Best Telegram Bots for AML Crypto Checks in 2026](https://hackernoon.com/7-best-telegram-bots-aml-crypto-2026) — Full comparison: pricing, chains, PDF reports (Hackernoon)
- [7 Best Telegram Bots for AML Crypto Address Checks in 2026](https://medium.com/p/ba0bf6a76edf) — Practical guide with comparison table (Medium)
- [Top-7 Telegram Bots for AML Wallet Check in 2026](https://vc.ru/id5979934/2941315-top-telegram-boty-dlya-aml-proverki-kriptokoshelkov) — Russian-language version (vc.ru)
- [How to Check Crypto Wallet AML Risk with Telegram Bots](https://vitaliyokhrimecryptoamlchecknko.substack.com/p/how-to-check-crypto-wallet-aml-risk) — Beginner-friendly guide
- [How to Check a Crypto Wallet for AML Risk](https://cryptoaml.cc/how-to-check-crypto-wallet.html) — Step-by-step web guide

### Official Regulatory Resources
- [OFAC SDN List](https://home.treasury.gov/policy-issues/financial-sanctions/specially-designated-nationals-and-blocked-persons-list-sdn-human-readable-lists) — US Treasury sanctions list
- [FATF Guidance on Virtual Assets](https://www.fatf-gafi.org/en/publications/Fatfrecommendations/Guidance-rba-virtual-assets-2021.html) — International AML standards
- [MiCA Regulation](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32023R1114) — EU crypto regulation (in force 2024)
- [EU Consolidated Sanctions List](https://www.sanctionsmap.eu/) — EU financial sanctions database
- [OFSI (UK) Financial Sanctions](https://www.gov.uk/government/organisations/office-of-financial-sanctions-implementation) — UK sanctions list post-Brexit

### Community & Mentions
- [Twitter: Why check crypto wallets for AML?](https://x.com/1CrypTina/status/2061866427913551944) — Community perspective on AML wallet screening

---

## Disclaimer

This list is for informational purposes only. No tool listed here constitutes legal advice or guarantees regulatory compliance in your jurisdiction. When in doubt, consult a qualified compliance professional.

---

*Last updated: 2026-06-24 | [Contribute via PR](https://github.com/RimenKo/awesome-crypto-aml-bots/pulls)*
