# CS2 Sim

[![cs2-sim MCP connector](https://glama.ai/mcp/connectors/io.github.GeminiGeorge22/cs2-sim/badges/score.svg)](https://glama.ai/mcp/connectors/io.github.GeminiGeorge22/cs2-sim)

CS2 Sim is a **Counter-Strike 2 economy simulator** you add to Claude, ChatGPT, Cursor, or VS Code. Ask: How much money after this loss? Should we buy, force, or eco? Simulate the rest of the half.

Operated by **FMF Tools**.

- Live site: https://cs2-sim.fmf-x402.workers.dev/
- MCP endpoint (Streamable HTTP): https://cs2-sim.fmf-x402.workers.dev/mcp
- Install page: https://cs2-sim.fmf-x402.workers.dev/install
- Tools and prices: https://cs2-sim.fmf-x402.workers.dev/docs

No account is required. `tools/list`, money rules, and next-round money are free. Paid sims are charged per successful call through MPP on Tempo or x402 on Base (USDC). Bad input is refused and is not charged.

## Install

MCP server URL: `https://cs2-sim.fmf-x402.workers.dev/mcp`

### Claude Desktop

Settings → Connectors → Add custom connector → URL: `https://cs2-sim.fmf-x402.workers.dev/mcp`

Or add this to `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "cs2-sim": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://cs2-sim.fmf-x402.workers.dev/mcp"]
    }
  }
}
```

### Claude Code

```bash
claude mcp add --transport http cs2-sim https://cs2-sim.fmf-x402.workers.dev/mcp
```

### Cursor

`~/.cursor/mcp.json` (or `.cursor/mcp.json` in a project):

```json
{
  "mcpServers": {
    "cs2-sim": {
      "url": "https://cs2-sim.fmf-x402.workers.dev/mcp"
    }
  }
}
```

### VS Code (Copilot agent mode)

```bash
code --add-mcp '{"name":"cs2-sim","type":"http","url":"https://cs2-sim.fmf-x402.workers.dev/mcp"}'
```

### ChatGPT

Settings → Apps & Connectors → Advanced settings → turn on Developer mode → Create connector. Name: CS2 Sim. MCP server URL: `https://cs2-sim.fmf-x402.workers.dev/mcp`. Authentication: none.

## Tools

| MCP tool | Price |
|---|---|
| cs2_money_rules | free |
| cs2_next_round_money | free |
| cs2_buy_decision | $0.001 |
| cs2_economy_sim | $0.003 |

## Licence and fan notice

This repository is MIT licensed. CS2 Sim is an unofficial fan tool, not affiliated with or endorsed by Valve. Counter-Strike is a trademark of Valve Corporation. Economy rules are public Competitive/Premier game facts. Free tools stay free. Paid tools sell only our own computation.

Contact: fmf-tools@agentmail.to
