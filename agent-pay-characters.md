


```
┌──────────────────────────────────────────────────────────────────────┐
│  ALICE'S LAPTOP (the only place that holds keys)                      │
│  ┌────────────────────────┐                                            │
│  │  agentpayd (daemon)    │ ◀── holds Alice's master keys             │
│  │  - Ed25519 master      │     (Ed25519 for signing approvals,        │
│  │  - secp256k1 master    │      secp256k1 for the on-chain wallet)    │
│  │  - HKDF salt           │                                            │
│  │  Listens on            │     Pops up the "approve?" prompt.         │
│  │  localhost:8087        │     Signs PolicyWindows + UserOps.         │
│  └────────────────────────┘                                            │
└──────────────────────────────────────────────────────────────────────┘
                  ▲   ▲
                  │   │
                  │   └─── (loopback HTTP only)
                  │
┌─────────────────┴───────────┐    ┌──────────────────────────────────┐
│  THE AGENT                  │    │  AGENTPAY BACKEND                │
│  (Claude / ChatGPT / a bot) │    │  (a cloud service we operate)    │
│                             │    │                                  │
│  - Lives wherever the AI    │    │  - Postgres of policies, users   │
│    lives (cloud or local)   │    │  - Builds UserOps                │
│  - Wants to spend money     │    │  - Talks to merchant + chain     │
│    on Alice's behalf        │    │  - HOLDS NO SIGNING KEYS         │
│  - Has zero authority       │    │                                  │
│  - Holds nothing            │    │                                  │
└─────────────────────────────┘    └──────────────────────────────────┘
                                              │       │
                                              ▼       ▼
                              ┌────────────────┐  ┌────────────────┐
                              │ MERCHANT       │  │ THE CHAIN      │
                              │ (e.g.          │  │ (Base / Ethereum) │
                              │  doordash.com) │  │ + a bundler    │
                              │                │  │   (Pimlico)    │
                              │ Just receives  │  │                │
                              │ USDC.          │  │ Checks         │
                              │ Doesn't know   │  │ signatures,    │
                              │ AgentPay       │  │ moves USDC     │
                              │ exists.        │  │                │
                              └────────────────┘  └────────────────┘
```
