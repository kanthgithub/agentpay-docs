LOOM SCRIPT — agentpay-v1-demo.mp4 (~6 min)

[0:00–0:30]  HOOK
   • "Hi, I'm Lakshmi. AI agents are starting to make payments.
      Today I'll show you why AgentPay is the only one of these
      where the agent literally cannot drain your wallet —
      because the chain enforces the limit, not a server."

[0:30–1:30]  COLD INSTALL
   • Terminal: `npx @agentpay/agentpayd init`
   • Daemon creates keystore at ~/.agentpay/
   • Show: tree ~/.agentpay/   →  master.enc, sessions/, policies/
   • Voice-over: "My laptop is the only place this key exists.
      Not AgentPay's backend. Not your phone. Not a custodian."

[1:30–2:30]  ENABLE A SESSION KEY
   • CLI: `agentpayd policy create --merchant example.dev \
            --cap-weekly 50 --token USDC`
   • Daemon shows the JWS PolicyWindow + the preview UserOp
   • Confirm with passphrase prompt
   • UserOp lands on Etherspot bundler (Base mainnet)
   • Show Etherscan link: enableSessionKey()
   • Voice-over: "That's Etherspot's audited
      ERC20SessionKeyValidator at 0x1417… on Base mainnet,
      Shieldify-audited May 2024."

[2:30–4:00]  AGENT MAKES A PAYMENT (the magic)
   • Open Cursor, ask in chat:
        "buy me 1 hour of compute on example.dev"
   • Cursor calls daemon over stdio MCP
   • Daemon signs child JWS silently under the parent
   • UserOp goes through Etherspot bundler
   • Show Etherscan: USDC moved to merchant wallet
   • Show terminal: signed JWS receipt printed
   • Voice-over: "Notice — no prompt. Parent envelope
      already pre-authorised this merchant."

[4:00–5:00]  THE MOAT
   • "Now let me try to break it."
   • Modify the agent: spend 5× the cap to a DIFFERENT merchant
   • Daemon refuses to sign — show the revert message
   • "Even if my daemon were compromised, watch this:"
   • Manually sign a malicious UserOp with the session key,
     send to bundler
   • On-chain: validator REJECTS, UserOp reverts
   • Show Etherscan revert with reason: "merchant not authorised"
   • Voice-over: "AgentPay can't pay anyone you didn't authorise.
      Even if our backend AND our daemon are both compromised."

[5:00–5:30]  ARCHITECTURE SLIDE (one static image)
   • 3-layer enforcement diagram (already in the docs)
   • "Etherspot's validator IS Layer 3.
      That's the partnership we're proposing today."

[5:30–6:00]  OUTRO
   • Repo: github.com/<you>/agentpay
   • "I'm solo. Building this in 6 weeks.
      I'd love to chat about a case study + a priority
      Discord channel. Reply or grab time on cal.com/<you>."