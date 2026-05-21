# awesome-crypto-aml-bots

A curated list of Telegram bots for AML (Anti-Money Laundering) screening of crypto addresses. Updated regularly.

## Why This List Exists

Enterprise tools like Chainalysis start at $50,000/year. Crystal Blockchain targets banks and exchanges with six-figure contracts. The gap between "no check at all" and "full compliance stack" is where most freelancers, p2p traders, and small crypto businesses operate.

These Telegram bots fill that gap. Paste an address, get a risk score in under 30 seconds. No KYC, no contract, some are free.

---

## Telegram Bots

### Free Tier Available

| Bot | Free checks | Paid | Chains | PDF Report |
|-----|-------------|------|--------|------------|
| [@scorechain_amlbot](https://t.me/scorechain_amlbot) | 3/day | $0.50 / 75 Stars | ETH, BTC, TRX, BNB, XRP, MATIC | Yes |
| [@ScorechainAML_bot](https://t.me/ScorechainAML_bot) | 3/day | $0.50 / 75 Stars | ETH, BTC, TRX, BNB, XRP, MATIC | Yes |
| [@CryptoAMLScreenBot](https://t.me/CryptoAMLScreenBot) | 3/day | On request | ETH, BTC, TRX | No |

### Paid Only

| Bot / Service | Starting Price | Chains | Notes |
|---------------|----------------|--------|-------|
| AMLBot | From $0.20/check | 15+ | Most established in RU market |
| Scorechain (SaaS) | From €500/month | 30+ | Enterprise-grade platform |
| Crystal Blockchain | Enterprise | 20+ | Used by law enforcement |
| Chainalysis KYT | From $50,000/year | 20+ | Industry standard, API only |

---

## How AML Bots Work

1. You send a crypto address (ETH, BTC, TRX, etc.) to the bot
2. The bot queries a database of known addresses: OFAC SDN list, sanctioned entities, mixer clusters, darknet markets
3. Returns a **risk score** (0–100) and breakdown by category
4. High-risk categories: OFAC sanctions, mixers, darknet, stolen funds

**Risk score interpretation:**
- 0–30: Low risk
- 31–69: Medium risk, investigate further
- 70–89: High risk, request explanation from counterparty
- 90–100: Critical, consider refusing transaction

---

## What These Bots Check

- **OFAC SDN list** — US Treasury sanctions (14,000+ crypto addresses as of 2026)
- **EU sanctions** — OFAC equivalent for European jurisdictions
- **OFSI (UK)** — UK Office of Financial Sanctions Implementation
- **Mixer clusters** — Tornado Cash, ChipMixer, Blender.io and similar
- **Darknet markets** — Hydra, AlphaBay-linked addresses
- **Stolen funds** — Exchange hack trackers (Ronin Bridge, FTX, etc.)

---

## Limitations

These bots are fast and cheap but have hard limits compared to enterprise tools:

- **Depth**: Enterprise tools trace 5–10+ hops back. Bots typically check 1–2 hops.
- **Coverage**: 6–15 blockchains vs 30+ for Chainalysis.
- **No monitoring**: Bots don't alert you if a "clean" address later gets sanctioned.
- **No expert reports**: Not suitable for legal proceedings or regulatory submissions.

For court evidence or regulatory audits: Chainalysis, Crystal Blockchain, or TRM Labs.

---

## Use Cases

**When Telegram bots are sufficient:**
- Freelancer receiving crypto payment from unknown client
- P2P trader doing background check before deal
- Small exchange pre-screening deposits
- Individual verifying address before sending significant amount

**When you need enterprise tools:**
- Regulatory reporting (MiCA, FATF Travel Rule)
- AML audit for financial license
- Law enforcement cooperation
- Processing 1,000+ transactions/day

---

## Contributing

PRs welcome. To add a bot:
1. Must be live and actively maintained
2. Must have verifiable check methodology (not just blacklist lookup)
3. Must work via Telegram (not just web interface)

Format:
```
| [@botname](https://t.me/botname) | free checks | paid price | chains | notes |
```

---

## Related Resources

### Articles & Guides
- [Top 7 Telegram Bots for AML Crypto Address Checks in 2026](https://medium.com/p/ba0bf6a76edf) — Full comparison with pricing, chains, PDF reports (EN)
- [Топ-7 Telegram-ботов для AML-проверки криптокошельков в 2026 году](https://vc.ru/id5979934/2941315-top-7-telegram-botov-dlya-aml-proverki-kriptokoshelkov-v-2026-godu) — Полное сравнение на русском (RU)

### Official Resources
- [OFAC SDN List](https://home.treasury.gov/policy-issues/financial-sanctions/specially-designated-nationals-and-blocked-persons-list-sdn-human-readable-lists) — Official US Treasury sanctions list
- [Chainalysis Crypto Crime Report 2024](https://www.chainalysis.com/blog/2024-crypto-crime-report/) — Annual industry benchmark
- [FATF Guidance on Virtual Assets](https://www.fatf-gafi.org/en/publications/Fatfrecommendations/Guidance-rba-virtual-assets-2021.html) — International AML standards
- [MiCA Regulation](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32023R1114) — EU crypto regulation in force 2024

---

## Disclaimer

This list is for informational purposes. No tool in this list constitutes legal advice or guarantees compliance with AML regulations in your jurisdiction. When in doubt, consult a qualified compliance professional.

---

*Last updated: 2026-05-21 | Maintained by the community*
