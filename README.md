<div align="center">

<img src="assets/jov-logo.png" alt="J0VEBOT" width="180" />

# J0VEBOT Agent Skills

**Skills for AI agents to integrate with the Jupiter ecosystem.**

[![MIT License](https://img.shields.io/badge/License-MIT-84ff00?style=flat-square)](LICENSE)
[![Jupiter](https://img.shields.io/badge/Jupiter-Integrated-84ff00?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAzMiAzMiI+PHJlY3Qgd2lkdGg9IjMyIiBoZWlnaHQ9IjMyIiByeD0iNSIgZmlsbD0iIzBhMGEwYSIvPjx0ZXh0IHg9IjE2IiB5PSIyMiIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZm9udC1mYW1pbHk9Im1vbm9zcGFjZSIgZm9udC1zaXplPSIxNCIgZm9udC13ZWlnaHQ9IjkwMCIgZmlsbD0iIzg0ZmYwMCI+Sk9WPC90ZXh0Pjwvc3ZnPg==)](https://jup.ag)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-Compatible-84ff00?style=flat-square)](https://agentskills.io)
[![Solana](https://img.shields.io/badge/Solana-$JOV-84ff00?style=flat-square)](https://jup.ag)

Skills follow the [Agent Skills](https://agentskills.io/) format.

[Install](#quick-install) · [Skills](#available-skills) · [API Coverage](#api-coverage) · [GitHub](https://github.com/J0VEBOT) · [X](https://x.com/J0VEBOT)

</div>

---

## Quick Install

```bash
npx add-skill J0VEBOT/agent-skills
```

Or install a specific skill:

```bash
npx add-skill J0VEBOT/agent-skills --skill "integrating-jupiter"
```

## Available Skills

### ⚡ integrating-jupiter

Comprehensive guidance for integrating with the **entire Jupiter Suite of APIs** — Ultra Swap, Lend, Perps, Trigger, Recurring, Tokens, Price, Portfolio, Prediction Markets, Send, Studio, Lock, and Routing.

**Use for:** endpoint selection, integration flows, error handling, and production hardening.

```bash
npx add-skill J0VEBOT/agent-skills --skill "integrating-jupiter"
```

## API Coverage

The `integrating-jupiter` skill covers every Jupiter API:

| API | Type | Description |
|-----|------|-------------|
| **Ultra Swap Order** | REST | Flagship swap with managed landing, gasless, MEV protection |
| **Ultra Swap Data** | REST | Token search, shield warnings, holdings, mint info |
| **Lend** | SDK | Deposit/withdraw for yield via `@jup-ag/lend` |
| **Perps** | On-Chain | Perpetual futures via Anchor program, up to 100x leverage |
| **Trigger** | REST | Limit orders with price conditions |
| **Recurring** | REST | DCA — scheduled swaps with configurable intervals |
| **Token** | REST | Metadata, search, verification, organic scoring |
| **Price v3** | REST | Real-time and historical pricing |
| **Portfolio** | REST | Wallet positions across DeFi protocols |
| **Prediction Markets** | REST | Binary outcome markets with JupUSD |
| **Send** | REST | Token transfers via invite links |
| **Studio** | On-Chain | Token creation with Dynamic Bonding Curves |
| **Lock** | On-Chain | Token vesting and lock program |
| **Routing (Iris)** | REST | DEX aggregation engine |
| **RFQ (JupiterZ)** | REST | Request-for-quote market maker integration |

## Quickstart Example

```typescript
import { Connection, Keypair, VersionedTransaction } from '@solana/web3.js';

const API_KEY = process.env.JUPITER_API_KEY!;  // from portal.jup.ag
const BASE = 'https://api.jup.ag';

// Get a swap order
const order = await fetch(`${BASE}/ultra/v1/order`, {
  method: 'POST',
  headers: {
    'x-api-key': API_KEY,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    inputMint: 'SOL',
    outputMint: 'USDC',
    amount: 1000000000,  // 1 SOL in lamports
    taker: wallet.publicKey.toBase58()
  })
});
```

## How It Works

1. **Install** — `npx add-skill J0VEBOT/agent-skills` adds the SKILL.md to your agent
2. **API Key** — Get one at [portal.jup.ag](https://portal.jup.ag)
3. **Configure** — Set `JUPITER_API_KEY` in your environment
4. **Execute** — Your AI agent now has full Jupiter API coverage

## Requirements

- **Jupiter API Key** — Register at [portal.jup.ag](https://portal.jup.ag) (required for REST endpoints)
- **Solana wallet** — For signing transactions
- **Node.js 18+** — For `npx add-skill`

## References

- [Jupiter](https://jup.ag) — The #1 Solana DEX aggregator
- [Jupiter Docs](https://dev.jup.ag) — Official developer documentation
- [API Portal](https://portal.jup.ag) — Get your API key
- [Rate Limits](https://dev.jup.ag/portal/rate-limit.md) — Rate limit policy
- [Status](https://status.jup.ag) — Service health
- [Agent Skills](https://agentskills.io) — Skill format specification

## $JOV

$JOV is the J0VEBOT ecosystem token on Solana. It powers agent skill fees, governance, and staking.

## Links

- 🌐 [j0vebot.com](https://j0vebot.com)
- 🐦 [@J0VEBOT on X](https://x.com/J0VEBOT)
- 💻 [GitHub](https://github.com/J0VEBOT)
- 🪐 [Jupiter](https://jup.ag)

## License

MIT — see [LICENSE](LICENSE)
