<div align="center">
  <h1>💬 ChatBank</h1>
  <p><strong>Decentralized social chat built on Lens Protocol.</strong></p>
  <p>Own your conversations. Own your followers. Own your data.</p>
  <p>
    <a href="https://chatbank.fun">chatbank.fun</a> ·
    <a href="mailto:support@chatbank.fun">Support</a> ·
    <a href="mailto:legal@chatbank.fun">Legal</a>
  </p>
  <br />
  <img alt="brand color" src="https://img.shields.io/badge/brand-%238B5CF6-8B5CF6?style=for-the-badge" />
  <img alt="lens" src="https://img.shields.io/badge/built_on-Lens_Protocol-00501E?style=for-the-badge" />
  <img alt="stack" src="https://img.shields.io/badge/stack-React_·_TypeScript_·_Wagmi-blue?style=for-the-badge" />
</div>

---

## What is ChatBank

ChatBank is a fully self-custodial chat app built on the **Lens Protocol**. Your posts, your followers, and your social graph live on-chain — not on our servers. Wallet in, conversation owned.

- 🔐 **Self-custodial** — wallet-native, no central account, no email login required
- 🌐 **Open social graph** — your follows port to any Lens-compatible app
- ⚡ **Real-time chat** — DMs, group rooms, threaded replies
- 🪙 **Treasury-backed** — `CHATBANK_TREASURY` funds rewards and creator payouts
- 🎨 **Beautiful** — violet (`#8B5CF6`) brutalist UI, dark by default

## Architecture

```
┌──────────────────────────────────────────────────────────┐
│  React + TypeScript front-end                            │
│  ↓                                                       │
│  Wagmi / Viem · WalletConnect / Reown                    │
│  ↓                                                       │
│  Lens Protocol contracts  ←→  CHATBANK_APP / TREASURY    │
│  ↓                                                       │
│  Storage: IPFS · Arweave · Lens Storage Node             │
└──────────────────────────────────────────────────────────┘
```

## Tech stack

| Layer | Choice |
|---|---|
| Framework | React + Vite |
| Language | TypeScript (strict) |
| Wallet | Wagmi + Viem |
| Connector | WalletConnect / Reown AppKit |
| Social layer | Lens Protocol v3 |
| Styling | Tailwind CSS · violet `#8B5CF6` accent |
| Forms | react-hook-form + zod |
| State | TanStack Query + Zustand |
| Testing | Vitest + Playwright (Chromium e2e) |
| Lint | Biome (666+ files clean) |
| Package mgr | pnpm |

## Quickstart

```bash
git clone https://github.com/vilrapanhe/chatbank.git
cd chatbank
pnpm install
cp .env.example .env  # fill in WALLETCONNECT_PROJECT_ID
pnpm dev              # boots in ~1.4s
```

Server starts at `http://localhost:5173`.

### Scripts

| Command | What it does |
|---|---|
| `pnpm dev` | Vite dev server |
| `pnpm build` | Production bundle |
| `pnpm typecheck` | tsc --noEmit |
| `pnpm biome:check` | Biome lint + format check |
| `pnpm test` | Vitest unit |
| `pnpm test:e2e` | Playwright Chromium e2e |

## Environment

Required env vars (`.env`):

```bash
VITE_WALLETCONNECT_PROJECT_ID=...      # from https://cloud.reown.com
VITE_CHATBANK_APP_ADDRESS=0x...        # your deployed Lens App address
VITE_CHATBANK_TREASURY=0x...           # treasury multisig
VITE_LENS_API_URL=https://api-v2.lens.dev
VITE_STATIC_CDN=https://static.chatbank.fun
```

## Project structure

```
src/
├── components/        Reusable UI primitives
├── pages/             Route-level views (home, support, privacy, terms)
├── data/contracts.ts  CHATBANK_APP, CHATBANK_TREASURY addresses
├── lib/               Hooks, helpers, lens client
├── types/             chatbank.d.ts  (formerly hey.d.ts)
└── styles/            Tailwind layers + violet palette
tests/
└── e2e/               Playwright suites (rebrand.spec.ts etc.)
```

## Legal

- [Support](https://chatbank.fun/support)
- [Privacy](https://chatbank.fun/privacy)
- [Terms](https://chatbank.fun/terms)
- [Community Guidelines](https://chatbank.fun/guidelines)
- [Copyright Policy](https://chatbank.fun/copyright)

Reach: `legal@chatbank.fun` · `support@chatbank.fun`

## Roadmap

- [x] Full rebrand off upstream fork
- [x] Lens v3 integration
- [x] WalletConnect / Reown
- [x] Playwright e2e (9/9 passing)
- [ ] Deploy `CHATBANK_APP` to Lens mainnet
- [ ] Public CDN at `static.chatbank.fun`
- [ ] Independent legal review of ToS / Privacy
- [ ] Token-gated rooms
- [ ] Mobile (Expo)

## Contributing

PRs welcome. Run `pnpm typecheck && pnpm biome:check && pnpm test:e2e` before opening.

## License

AGPL-3.0 — open and copyleft, like the social web should be.

---

<div align="center">
  <sub>built on Lens · self-custodial · <a href="https://chatbank.fun">chatbank.fun</a></sub>
</div>
