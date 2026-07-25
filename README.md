# <img src="https://kamino-dex.com/favicon.svg" width="28" alt="Kamino logo"> Kamino — #1 Exchange Protocol on Solana

[![Live on Solana](https://img.shields.io/badge/Network-Solana%20Mainnet-9945FF?style=flat-square&logo=solana)](https://kamino-dex.com)
[![TVL](https://img.shields.io/badge/TVL-$2.1B+-00D1FF?style=flat-square)](https://kamino-dex.com)
[![Fees](https://img.shields.io/badge/Platform%20Fees-0%25-00E676?style=flat-square)](https://kamino-dex.com)
[![Audited](https://img.shields.io/badge/Audits-OtterSec%20·%20Offside%20Labs%20·%20Sec3-green?style=flat-square)](#security--audits)
[![License](https://img.shields.io/badge/License-BSL%201.1-blue?style=flat-square)](#license)
[![Twitter](https://img.shields.io/badge/Twitter-@KaminoFinance-1DA1F2?style=flat-square&logo=twitter)](https://twitter.com/KaminoFinance)
[![Discord](https://img.shields.io/badge/Discord-Join%20Community-5865F2?style=flat-square&logo=discord)](https://discord.gg/kamino)

> **Swap, Earn, Borrow & Multiply — all in one protocol.**
>
> Kamino is the leading protocol on Solana, combining token swapping with zero platform fees, the largest lending market, automated liquidity vaults, and one-click leveraged strategies. Sub-400ms execution. Active Simulation. Best price routing across 5+ sources.

**🌐 [kamino-dex.com](https://kamino-dex.com)** · **📖 [Documentation](https://docs.kamino-dex.com)** · **🐛 [Report Bug](https://github.com/kamino-finance/kamino-dex/issues)** · **💬 [Discord](https://discord.gg/kamino)**

---

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Architecture](#architecture)
- [Protocol Products](#protocol-products)
  - [Kamino Swap](#kamino-swap)
  - [Kamino Lend](#kamino-lend)
  - [Kamino Multiply](#kamino-multiply)
  - [Kamino Liquidity Vaults](#kamino-liquidity-vaults)
- [Active Simulation](#active-simulation)
- [Supported Tokens](#supported-tokens)
- [KMNO Token](#kmno-token)
- [Security & Audits](#security--audits)
- [Getting Started](#getting-started)
- [SDK & API](#sdk--api)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [Community](#community)
- [License](#license)

---

## Overview

Kamino is a unified protocol deployed on Solana Mainnet that integrates four core products into a single non-custodial platform:

| Product | Description | Status |
|---------|-------------|--------|
| **Kamino Swap** | Zero-fee token exchange with Active Simulation and Meta Swap routing | ✅ Live |
| **Kamino Lend** | Solana's largest lending market — supply, earn, and borrow across isolated markets | ✅ Live |
| **Kamino Multiply** | One-click amplified positions with up to 5× exposure | ✅ Live |
| **Kamino Liquidity** | Automated concentrated vaults with auto-rebalancing and compounding | ✅ Live |

**Why Kamino?**

- **$2.1B+ TVL** — the most trusted protocol on Solana
- **0% platform fees** — only standard Solana network fees (~$0.00025)
- **Sub-400ms execution** — powered by Solana's parallel processing
- **Active Simulation** — every swap pre-validated before submission
- **5+ aggregated routes** — Jupiter, DFlow, Autobahn, Raydium, Fluxbeam
- **3 independent audits** — OtterSec, Offside Labs, Sec3
- **Zero security incidents** — since launch

→ **Try it now at [kamino-dex.com](https://kamino-dex.com)**

---

## Key Features

### ⚡ Active Simulation Engine
Every swap is simulated in real-time before execution. Routes are validated, pricing is confirmed, and failed transactions are eliminated — before any fees are spent. This is unique to Kamino and not available on any other Solana protocol.

### 🔀 Meta Swap Routing
Kamino's aggregation engine queries 5+ major routing sources simultaneously (Jupiter, DFlow, Autobahn, Raydium, Fluxbeam) to find the optimal execution path for every trade at any size.

### 🏦 Isolated Lending Markets
Kamino Lend uses isolated markets architecture where each pool operates independently. Risk in one market doesn't cascade into others, providing institutional-grade protection for all participants.

### 📈 One-Click Multiply
Amplify your position with automated looping strategies. Kamino handles borrowing, swapping, and collateral management in a single transaction with partial-liquidation protection.

### 💧 Auto-Rebalancing Vaults
Concentrated liquidity positions managed automatically. Kamino monitors price movements, rebalances when positions drift out of range, and compounds fees — delivering up to 10× more efficient capital usage.

### 🗳️ On-Chain Governance
KMNO holders vote on protocol parameters, fee tiers, emission allocations, and upgrades. No single entity controls Kamino — the community governs.

---

## Architecture

```
┌─────────────────────────────────────────────────────┐
│                    KAMINO PROTOCOL                   │
│                  kamino-dex.com                       │
├─────────────┬──────────┬───────────┬────────────────┤
│  Kamino     │  Kamino  │  Kamino   │    Kamino      │
│  Swap       │  Lend    │ Multiply  │   Liquidity    │
├─────────────┴──────────┴───────────┴────────────────┤
│              Active Simulation Engine                │
├─────────────────────────────────────────────────────┤
│    Meta Swap Router (5+ aggregated sources)          │
│    Jupiter · DFlow · Autobahn · Raydium · Fluxbeam   │
├─────────────────────────────────────────────────────┤
│           Solana Runtime (400ms blocks)               │
└─────────────────────────────────────────────────────┘
```

### Core Components

```
kamino-dex/
├── programs/
│   ├── kamino-swap/          # Swap program with Active Simulation
│   ├── kamino-lend/          # Lending market (K-Lend) core logic
│   ├── kamino-multiply/      # Leveraged position management
│   └── kamino-liquidity/     # Automated concentrated vault engine
├── sdk/
│   ├── typescript/           # TypeScript SDK for integration
│   └── python/               # Python SDK for analytics
├── app/
│   └── web/                  # Frontend application (kamino-dex.com)
├── tests/
│   ├── unit/                 # Unit tests for all programs
│   ├── integration/          # Cross-program integration tests
│   └── simulation/           # Active Simulation test suite
└── docs/                     # Protocol documentation
```

---

## Protocol Products

### Kamino Swap

Kamino Swap is an intents-based exchange platform offering the best price execution for any token swap on Solana.

**How it works:**

1. User submits a swap intent (token pair + amount)
2. Active Simulation validates all available routes off-chain
3. Meta Swap Router selects the optimal execution path across 5+ sources
4. Transaction is submitted to Solana with guaranteed pricing
5. Swap confirms in <400ms with zero platform fees

**Swap Features:**
- Zero platform fees on all swaps
- Active Simulation pre-validation
- Meta Swap aggregation (Jupiter, DFlow, Autobahn, Raydium, Fluxbeam)
- Limit orders via Pyth Express Relay
- Customizable slippage tolerance
- Support for 400+ tokens

→ **Swap now at [kamino-dex.com](https://kamino-dex.com)**

### Kamino Lend

The largest lending market on Solana with $2.1B+ TVL.

**Supply** assets (SOL, USDC, USDT, wBTC, wETH, and more) to earn dynamic interest rates. **Borrow** against your collateral across isolated markets with transparent risk parameters.

**Lending Features:**
- Isolated markets architecture — independent risk per pool
- Dynamic interest rates based on utilization
- Support for tokenized equities as collateral
- Real-time health factor monitoring
- Partial liquidation protection

### Kamino Multiply

One-click leveraged strategies with up to 5× amplification.

```
User deposits SOL
  → Kamino borrows USDC against SOL
    → Swaps USDC back to SOL
      → Deposits SOL as additional collateral
        → Repeats until target leverage reached

All in a single transaction. Automated. Non-custodial.
```

**Multiply Features:**
- Up to 5× amplified exposure
- Single-transaction execution
- Partial-liquidation design
- Clear liquidation threshold dashboard
- Popular strategies: Long SOL, Loop JLP, Hedge positions

### Kamino Liquidity Vaults

Automated concentrated positions with auto-rebalancing and auto-compounding.

| Vault | TVL | APR | 24h Volume |
|-------|-----|-----|------------|
| SOL / USDC | $284M | 24.8% | $42M |
| SOL / USDT | $118M | 31.4% | $18M |
| wBTC / SOL | $76M | 18.2% | $9M |

**Vault Features:**
- Concentrated positions for up to 10× capital efficiency
- Automatic rebalancing when price moves out of range
- Auto-compounding of earned fees
- No manual management required
- KMNO rewards on top of fee earnings

→ **View all vaults at [kamino-dex.com](https://kamino-dex.com)**

---

## Active Simulation

Active Simulation is Kamino's proprietary mechanism that pre-validates every swap before execution. It is the core innovation that separates Kamino from all other Solana exchange protocols.

```
Traditional Swap Flow:
  User → Submit Tx → Network → ❌ Failed (lost gas)
                              → ❌ Wrong price (slippage)
                              → ✅ Success (sometimes)

Kamino Active Simulation Flow:
  User → Simulate Off-Chain → Validate Route → Confirm Price
       → ✅ Submit only verified transactions
       → Zero failed swaps. Accurate pricing. Every time.
```

**Why it matters:**
- Eliminates failed transactions entirely
- Guarantees quoted price accuracy
- Removes inaccurate routes before submission
- Maintains reliability during network congestion
- Zero additional cost to the user

---

## Supported Tokens

Kamino supports **400+ tokens** across the Solana ecosystem. Key supported assets:

| Token | Ticker | Swap | Lend/Borrow | Liquidity Vaults |
|-------|--------|------|-------------|------------------|
| Solana | SOL | ✅ | ✅ | ✅ |
| USD Coin | USDC | ✅ | ✅ | ✅ |
| Tether | USDT | ✅ | ✅ | ✅ |
| Wrapped Bitcoin | wBTC | ✅ | ✅ | ✅ |
| Wrapped Ether | wETH | ✅ | ✅ | ✅ |
| Jupiter | JUP | ✅ | ✅ | — |
| Bonk | BONK | ✅ | — | — |
| Pyth | PYTH | ✅ | ✅ | — |
| dogwifhat | WIF | ✅ | — | — |
| Raydium | RAY | ✅ | — | — |
| Orca | ORCA | ✅ | — | — |
| Kamino | KMNO | ✅ | — | — |

Any liquid token on Solana is accessible through Kamino's Meta Swap aggregation.

---

## KMNO Token

**KMNO** is Kamino's governance token, giving holders direct control over the protocol's evolution.

**Governance Rights:**
- Vote on market configurations and risk parameters
- Influence fee tier structures
- Direct emission allocations across pools
- Approve or reject protocol upgrades

**How to Earn KMNO:**
- Active protocol participation (swapping, lending, borrowing)
- Liquidity provision in Kamino vaults
- Community contributions and protocol engagement

**Token Details:**
| Property | Value |
|----------|-------|
| Ticker | KMNO |
| Network | Solana |
| Type | Governance |
| Supply Model | Governed by community |
| Exchange | Available on [kamino-dex.com](https://kamino-dex.com) |

---

## Security & Audits

Kamino is built with institutional-grade security. Every component has been independently audited and continuously monitored.

### Audit History

| Firm | Scope | Status |
|------|-------|--------|
| **OtterSec** | Lend, Liquidity, Core | ✅ Passed |
| **Offside Labs** | Lend, Multiply | ✅ Passed |
| **Sec3** | Full protocol surface | ✅ Passed |

### Security Principles

- **Non-custodial** — Kamino never holds user funds. All operations execute via audited on-chain programs.
- **Open-source** — All contracts are publicly available on GitHub for review and verification.
- **Governance-controlled** — Protocol changes require KMNO holder consensus with timelock delays.
- **Isolated risk** — Each lending market operates independently, preventing risk cascade.
- **Partial liquidation** — Multiply positions use partial-liquidation design to protect against cascading losses.

### Track Record

```
Total Value Locked:    $2.1B+
Security Incidents:    0
Audits Completed:      3
Uptime:                99.99%
```

---

## Getting Started

### Prerequisites

- A Solana-compatible wallet (Phantom, Solflare, Backpack, or Ledger)
- SOL for network fees (~$0.00025 per transaction)

### Quick Start

1. **Visit** [kamino-dex.com](https://kamino-dex.com)
2. **Connect** your wallet (top-right corner)
3. **Choose** your product:
   - **Swap** → Exchange tokens with zero fees and Active Simulation
   - **Earn** → Supply assets to Kamino Lend for interest
   - **Borrow** → Take loans against your collateral
   - **Multiply** → Amplify your exposure up to 5×
   - **Liquidity** → Deposit into automated concentrated vaults
4. **Confirm** the transaction in your wallet
5. **Done** — Sub-400ms finality on Solana

### For Developers

```bash
# Clone the repository
git clone https://github.com/kamino-finance/kamino-dex.git
cd kamino-dex

# Install dependencies
yarn install

# Build programs
anchor build

# Run tests
anchor test

# Deploy to devnet
anchor deploy --provider.cluster devnet
```

---

## SDK & API

### TypeScript SDK

```bash
npm install @kamino-finance/sdk
```

```typescript
import { KaminoSwap } from '@kamino-finance/sdk';

const kamino = new KaminoSwap({
  connection: solanaConnection,
  wallet: userWallet,
});

// Get best swap route with Active Simulation
const route = await kamino.getRoute({
  inputMint: USDC_MINT,
  outputMint: SOL_MINT,
  amount: 1000_000_000, // 1000 USDC
  slippage: 0.5,
});

// Execute swap
const tx = await kamino.swap(route);
console.log(`Swap confirmed: ${tx.signature}`);
```

### Python SDK

```bash
pip install kamino-sdk
```

```python
from kamino import KaminoClient

client = KaminoClient(rpc_url="https://api.mainnet-beta.solana.com")

# Fetch lending market data
markets = client.get_lending_markets()
for market in markets:
    print(f"{market.name}: TVL ${market.tvl:,.0f}, APR {market.apr:.1f}%")
```

### REST API

```bash
# Get swap quote
curl https://api.kamino-dex.com/v1/quote \
  -d inputMint=USDC \
  -d outputMint=SOL \
  -d amount=1000000000

# Get lending market stats
curl https://api.kamino-dex.com/v1/lend/markets

# Get vault performance
curl https://api.kamino-dex.com/v1/vaults
```

Full API documentation: [docs.kamino-dex.com/api](https://docs.kamino-dex.com/api)

---

## Deployment

### Mainnet Program IDs

| Program | Address |
|---------|---------|
| Kamino Swap | `KSwp...` |
| Kamino Lend | `KLnd...` |
| Kamino Multiply | `KMul...` |
| Kamino Liquidity | `KLiq...` |

### Build from Source

```bash
# Install Solana CLI
sh -c "$(curl -sSfL https://release.solana.com/v1.18.0/install)"

# Install Anchor
cargo install --git https://github.com/coral-xyz/anchor anchor-cli

# Build all programs
anchor build

# Run full test suite
anchor test -- --features test

# Verify deployed program
anchor verify <PROGRAM_ID>
```

---

## Contributing

Kamino is open-source and welcomes contributions from the community.

### How to Contribute

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/improvement`)
3. **Commit** your changes (`git commit -m 'Add new feature'`)
4. **Push** to the branch (`git push origin feature/improvement`)
5. **Open** a Pull Request

### Development Guidelines

- Write tests for all new functionality
- Follow Rust formatting standards (`cargo fmt`)
- Run clippy before submitting (`cargo clippy`)
- Update documentation for any public API changes
- Add comments explaining complex logic

### Bug Reports

Found a vulnerability? Please report it responsibly:
- **Security issues** → security@kamino-dex.com (do not open public issues)
- **Bugs** → [GitHub Issues](https://github.com/kamino-finance/kamino-dex/issues)
- **Feature requests** → [GitHub Discussions](https://github.com/kamino-finance/kamino-dex/discussions)

---

## Community

Join the Kamino community:

| Platform | Link |
|----------|------|
| 🌐 Website | [kamino-dex.com](https://kamino-dex.com) |
| 🐦 Twitter | [@KaminoFinance](https://twitter.com/KaminoFinance) |
| 💬 Discord | [discord.gg/kamino](https://discord.gg/kamino) |
| 📱 Telegram | [t.me/kamino_finance](https://t.me/kamino_finance) |
| 🗳️ Governance | [gov.kamino.finance](https://gov.kamino.finance) |
| 📖 Documentation | [docs.kamino-dex.com](https://docs.kamino-dex.com) |
| 🐙 GitHub | [github.com/kamino-finance](https://github.com/kamino-finance) |

---

## License

Kamino Protocol is licensed under the [Business Source License 1.1](LICENSE).

Core protocol code is source-available. The license converts to a fully open-source license after the change date specified in the license file. See [LICENSE](LICENSE) for full terms.

---

<p align="center">
  <strong>Kamino — The protocol Solana was built for.</strong><br>
  <a href="https://kamino-dex.com">kamino-dex.com</a>
</p>
