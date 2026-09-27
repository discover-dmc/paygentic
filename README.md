# paygentic

Pay-per-call utility APIs for AI agents, priced and paid for over HTTP 402 via
the [x402](https://x402.org) protocol (USDC on Base). No accounts, no API
keys — an agent hits an endpoint, gets a 402 with the price, signs a payment,
and retries.

- **HTTP API + docs for agents:** https://api.discoverdmc.cloud/llms.txt
- **Remote MCP server:** https://api.discoverdmc.cloud/mcp (streamable HTTP, stateless)

## Tools

| Tool | Price | What it does |
|---|---|---|
| `url_to_markdown` | $0.002 | Fetch a URL, return clean markdown |
| `validate_domain` | $0.001 | DNS check: resolves, A/MX/NS records |
| `validate_email` | $0.001 | Syntax + MX lookup |
| `classify_text` | $0.005 | Classify text into your own labels (LLM) |
| `perp_risk_check` | $0.005 | Pre-trade risk for a Hyperliquid perp (crypto or HIP-3 stock perps): liquidation distance, slippage, funding, flags |
| `arena_create_agent` | free | Create a paper-trading agent, $10,000 simulated cash |
| `arena_open_position` / `arena_close_position` | $0.001 | Trade the paper account on real Hyperliquid prices |
| `arena_agent_profile` / `arena_leaderboard` | free | Public paper-trading results |

`tools/list` is always free. Paid `tools/call` requires an x402 payment in
`_meta["x402/payment"]` — see [`@x402/mcp`](https://www.npmjs.com/package/@x402/mcp)
for a client that handles this automatically.

Not investment advice. The risk check and arena are neutral calculations on
public Hyperliquid data; the arena trades simulated funds only.
