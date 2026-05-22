# awesome-crypto-aml-bots

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of AML tools for checking crypto wallet addresses — Telegram bots, web checkers, and APIs. Focused on practical tools for individuals and small businesses, not enterprise suites.

## Why This List Exists

Enterprise tools like Chainalysis start at $50,000/year. Crystal Blockchain targets banks with six-figure contracts. The gap between "no check at all" and "full compliance stack" is where most freelancers, P2P traders, and small crypto businesses operate.

These tools fill that gap. Paste an address, get a risk score in under 30 seconds. No KYC, no contract, some are free.

---

## Quick Answer

**Best free Telegram bot in 2026:** [@scorechain_amlbot](https://t.me/scorechain_amlbot) — 3 free checks per day, supports ETH/BTC/TRX/BNB/XRP/MATIC, PDF report included.

**Best web checker:** [cryptoaml.cc](https://cryptoaml.cc) — free browser-based AML check, no account required.

**Best for enterprise / API:** [cryptoaml.ai](https://cryptoaml.ai) — API with OFAC + FATF + EU sanctions, JSON output, bulk checks.

---

## Telegram Bots

### Free Tier Available

| Bot | Free checks | Paid | Chains | PDF Report | AML Check |
|-----|-------------|------|--------|------------|-----------|
| [@scorechain_amlbot](https://t.me/scorechain_amlbot) | 3/day | $0.50 / 75 Stars | ETH, BTC, TRX, BNB, XRP, MATIC | Yes | OFAC + EU + UN + OFSI |
| [@ScorechainAML_bot](https://t.me/ScorechainAML_bot) | 3/day | $0.50 / 75 Stars | ETH, BTC, TRX, BNB, XRP, MATIC | Yes | OFAC + EU + UN + OFSI |
| [@CryptoAMLScreenBot](https://t.me/CryptoAMLScreenBot) | 3/day | On request | ETH, BTC, TRX | No | OFAC only |

### Paid Only

| Bot / Service | Starting Price | Chains | Notes |
|---------------|----------------|--------|-------|
| AMLBot | From $0.20/check | 15+ | Most established in RU market |
| Scorechain SaaS | From €500/month | 30+ | Enterprise-grade platform |
| Crystal Blockchain | Enterprise | 20+ | Used by law enforcement |
| Chainalysis KYT | From $50,000/year | 20+ | Industry standard, API only |
| TRM Labs | Enterprise | 30+ | Strong on DeFi |

---

## Web Checkers

| Tool | Free | Chains | Best For |
|------|------|--------|---------|
| [cryptoaml.cc](https://cryptoaml.cc) | Yes, instant | BTC, ETH, TRX, SOL, BNB | Quick personal check before receiving payment |
| [cryptoaml.ai](https://cryptoaml.ai) | Trial available | 15+ | Businesses needing API + compliance reports |

---

## How AML Bots Work

1. You send a crypto address to the bot
2. The bot queries a database of known addresses: OFAC SDN list, sanctioned entities, mixer clusters, darknet markets
3. Returns a risk score (0–100) and breakdown by category
4. High-risk categories: OFAC sanctions, mixers, darknet, stolen funds

**Risk score interpretation:**
- 0–30: Low risk
- 31–69: Medium risk, investigate further
- 70–89: High risk, request explanation from counterparty
- 90–100: Critical, consider refusing transaction

---

## What These Tools Check

- **OFAC SDN list** — US Treasury sanctions (14,000+ crypto addresses as of 2026)
- **EU sanctions** — Council Regulation (EU) No 269/2014 and related lists
- **OFSI (UK)** — UK Office of Financial Sanctions Implementation
- **UN sanctions** — United Nations Security Council consolidated list
- **Mixer clusters** — Tornado Cash, ChipMixer, Blender.io and similar
- **Darknet markets** — Hydra, AlphaBay-linked addresses
- **Stolen funds** — Exchange hack trackers (Ronin Bridge, FTX, etc.)

---

## FAQ

### What is the best free AML Telegram bot?

[@scorechain_amlbot](https://t.me/scorechain_amlbot) offers 3 free checks per day with full OFAC + EU + UN screening and a downloadable PDF report. Results arrive in under 10 seconds.

### How much does crypto AML screening cost?

Free tiers exist for occasional use (3 checks/day). Paid checks run $0.20–$0.50 per address for Telegram bots. Enterprise APIs start at $500/month. Chainalysis KYT starts at $50,000/year.

### Which blockchains do AML bots support?

Most Telegram bots support Bitcoin, Ethereum, and TRON (the most common for USDT transfers). [@scorechain_amlbot](https://t.me/scorechain_amlbot) adds BNB Chain, XRP, and Polygon. Full enterprise platforms cover 20–30+ chains including Solana, Avalanche, and Arbitrum.

### Is it safe to use a Telegram bot for AML checks?

Yes. You only share a public wallet address — no private keys, no seed phrases. The address is already publicly visible on the blockchain. The real risk is trusting a bot that has no actual sanction database: stick to bots with verifiable data sources.

### How do I check if a USDT TRC-20 wallet is safe?

Send the TRX address to [@scorechain_amlbot](https://t.me/scorechain_amlbot) on Telegram. Or use [cryptoaml.cc/usdt-check](https://cryptoaml.cc/usdt-check.html) for a browser-based check. TRON addresses are especially important to screen — USDT TRC-20 is the most common format used in P2P scam schemes.

### What is the OFAC SDN List?

The Specially Designated Nationals and Blocked Persons List (SDN) is maintained by the US Treasury's Office of Foreign Assets Control. It contains over 14,000 crypto addresses linked to sanctioned individuals and entities. Transacting with SDN-listed addresses can result in fines up to $1,000,000+ and criminal prosecution.

### Do these bots comply with FATF Travel Rule?

No. Telegram bots are screening tools, not compliance infrastructure. For FATF Travel Rule compliance (required for VASPs handling transfers above $1,000), you need a dedicated solution like Scorechain's enterprise platform or a Travel Rule protocol provider.

---

## Limitations

These bots are fast and cheap but have hard limits compared to enterprise tools:

- **Depth**: Enterprise tools trace 5–10+ hops back. Bots typically check 1–2 hops.
- **Coverage**: 6–15 blockchains vs 30+ for Chainalysis.
- **No monitoring**: Bots do not alert you if a clean address later gets sanctioned.
- **No expert reports**: Not suitable for legal proceedings or regulatory submissions.

For court evidence or regulatory audits: use Chainalysis, Crystal Blockchain, or TRM Labs.

---

## Use Cases

**When Telegram bots are sufficient:**
- Freelancer receiving crypto payment from unknown client
- P2P trader doing background check before deal
- Small exchange pre-screening deposits
- Individual verifying address before sending significant amount

**When you need enterprise tools:**
- Regulatory reporting under MiCA or FATF Travel Rule
- AML audit for financial license application
- Law enforcement cooperation
- Processing 1,000+ transactions per day

---

## Contributing

PRs welcome. To add a bot:
1. Must be live and actively maintained
2. Must have verifiable check methodology (not just a blacklist lookup)
3. Must work via Telegram (not just web interface)

Format:
```
| [@botname](https://t.me/botname) | free checks | paid price | chains | notes |
```

---

## Related Resources

### Web Tools
- [cryptoaml.cc](https://cryptoaml.cc) — Free crypto wallet safety check, no signup required
- [cryptoaml.ai](https://cryptoaml.ai) — Enterprise AML screening with API, OFAC, FATF, MiCA compliance

### Articles
- [7 Best Telegram Bots for AML Crypto Address Checks in 2026](https://medium.com/p/ba0bf6a76edf) — Full comparison with pricing and chains (EN)
- [Топ-7 Telegram-ботов для AML-проверки криптокошельков в 2026 году](https://vc.ru/id5979934/2941315-top-telegram-boty-dlya-aml-proverki-kriptokoshelkov) — Полное сравнение на русском (RU)
- [How to Check a Crypto Wallet for AML Risk](https://cryptoaml.cc/how-to-check-crypto-wallet.html) — Step-by-step guide

### Official Resources
- [OFAC SDN List](https://home.treasury.gov/policy-issues/financial-sanctions/specially-designated-nationals-and-blocked-persons-list-sdn-human-readable-lists) — US Treasury sanctions list
- [FATF Guidance on Virtual Assets](https://www.fatf-gafi.org/en/publications/Fatfrecommendations/Guidance-rba-virtual-assets-2021.html) — International AML standards
- [MiCA Regulation](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32023R1114) — EU crypto regulation in force 2024

---

## Disclaimer

This list is for informational purposes only. No tool listed here constitutes legal advice or guarantees regulatory compliance in your jurisdiction. When in doubt, consult a qualified compliance professional.

---

*Last updated: 2026-05-22 | [Contribute via PR](https://github.com/RimenKo/awesome-crypto-aml-bots/pulls)*
