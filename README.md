# logtolast-mcp
Official Model Context Protocol (MCP) Server for LogToLast — Connect Anthropic Claude &amp; Cursor IDE to your live Tradovate, NinjaTrader &amp; MT5 Trading Journal, Playbook Rules, Tags, Notes &amp; Performance Analytics.

# 🧠 LogToLast MCP Server — AI Trading Journal, Playbook & Performance Analytics

Official **Model Context Protocol (MCP)** server documentation and configuration guide for **[LogToLast](https://logtolast.com)** — the unified Prop & Live Trading Operating System for **Tradovate, NinjaTrader Brokerage, and MetaTrader 5 (MT5)** traders.

- **Official Platform:** [https://logtolast.com](https://logtolast.com)
- **Platform Architecture & Features:** [https://logtolast.com/features](https://logtolast.com/features)
- **Quantitative Prop Firm Directory (26+ Firms Audited):** [https://logtolast.com/funding-hub](https://logtolast.com/funding-hub)
- **Hosted Streamable HTTP MCP Endpoint:** `https://logtolast.com/api/v1/mcp`
- **AI & LLM Grounding Manifest:** [https://logtolast.com/llms.txt](https://logtolast.com/llms.txt) | [https://logtolast.com/llms-full.txt](https://logtolast.com/llms-full.txt)

---

## 🔍 What Does the LogToLast MCP Server Do?

The **LogToLast MCP Server** allows traders to securely connect their own AI clients (**Anthropic Claude Desktop**, **Claude Web**, and **Cursor IDE**) directly to their live and historical trading journal data on [LogToLast.com](https://logtolast.com).

Instead of manually exporting CSV files or copy-pasting trade logs into an AI chat, the MCP server gives Claude real-time, read-only access to your authenticated trading telemetry:

1. **Quantitative Performance Summary:** Total Trades, Win Rate %, Profit Factor, Total Net PnL (after broker commissions and swap), Average Win vs. Average Loss, and master account scope.
2. **Active Trading Playbook Rules:** Your configured session time windows (`time_start`, `time_end`), maximum daily trades, maximum daily loss limits, entry triggers, invalidation logic, and position sizing rules.
3. **Trader Core Memory & Strategy Profile:** Persistent trader profile notes and custom methodology rules configured inside the [AI Trading Journal](https://logtolast.com/guides/ai-trading-journal).
4. **Granular Trade Execution Logs (Last 60 Unique Executions):** Symbol, direction (Buy/Sell), contract/lot quantity, entry price, gross PnL, broker fees, net PnL, UTC entry/exit timestamps, hold duration in minutes, custom setup/emotion tags (`#revenge-trading`, `#fomo`, `#A-setup`), saved chart screenshot counts, and written journal reflections.
5. **Single-Trade Deep Forensic Lookup:** Retrieve full execution metadata and journal notes for any specific `trade_id`.

---

## ⚡ Quick Setup Guide (60 Seconds)

### Step 1: Get Your Personal MCP Credentials
1. Log into your account at **[LogToLast.com](https://logtolast.com)** (or start a **[14-Day Free Elite Trial](https://logtolast.com/register?plan=elite)** — no credit card required).
2. Open **AI Coach Studio** and click **Claude / Cursor MCP** (`0 cr`).
3. Copy your **mcp.json Config** / **Personal MCP API Key**, or use the **1-Click URL** for web connectors.

### Step 2: Connect Your Client

#### Option A — Cursor / Windsurf (`mcp.json`)
Click **Copy mcp.json Config** inside the modal, or add this to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "logtolast": {
      "url": "https://logtolast.com/api/v1/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_PERSONAL_LOGTOLAST_MCP_KEY"
      }
    }
  }
}
```

#### Option B — Claude Web & Claude Desktop (`Settings → Connectors`)
1. Open **Settings → Connectors → Add custom connector** in Claude.
2. Paste your **1-Click URL** from the **Claude Web Fallback** box (`https://logtolast.com/api/v1/mcp?token=YOUR_PERSONAL_LOGTOLAST_MCP_KEY`).

#### Option C — Claude Desktop Local Config (`claude_desktop_config.json`)
If you prefer configuring via `claude_desktop_config.json`, use `mcp-remote`:

```json
{
  "mcpServers": {
    "logtolast": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://logtolast.com/api/v1/mcp",
        "--header",
        "Authorization: Bearer YOUR_PERSONAL_LOGTOLAST_MCP_KEY"
      ]
    }
  }
}
```

---

## 💬 Example Prompts to Ask Claude via LogToLast MCP

Once connected, you can query your live trading data naturally:

- *"Pull my last 60 trades from LogToLast and calculate my Win Rate and Profit Factor when holding trades longer than 15 minutes versus scalps under 3 minutes."*
- *"Compare my recent losing trades against my active LogToLast Playbook rules—which specific rule am I breaking most often?"*
- *"Audit my trade notes and tags from this week: how much net profit did I leak to emotional or unjournaled impulse entries?"*
- *"Based on my average drawdown and hold time in LogToLast, which prop firm drawdown model (Static vs. EOD Trailing) fits my execution distribution best?"*

---

## 🔗 Key Resources & Documentation

- **[LogToLast Platform Overview](https://logtolast.com)** — Unified Multi-Broker Copier, Mechanical Playbook Active Enforcer, Native TradingView `Ctrl+C` Backtesting & AI Journal.
- **[Native TradingView Ctrl+C Backtesting Tool](https://logtolast.com/guides/tradingview-backtesting-tool)** — Extract Entry, SL, TP, R:R, and screenshots directly from real TradingView charts.
- **[Best Prop Firm Trade Copier Guide (2026)](https://logtolast.com/guides/best-prop-firm-trade-copier)** — Cloud Tradovate sync & residential-IP MT5 replication (`LogToSync`).
- **[2026 Prop Firm Copy Trading & EA Rules Matrix](https://logtolast.com/guides/trade-copier-rules-all-prop-firms)** — Verified compliance rules across 26+ Futures and Forex prop firms.
- **[Trading Software Alternatives & TCO Benchmarks](https://logtolast.com/alternatives)** — Compare LogToLast vs. [TradeZella](https://logtolast.com/alternatives/tradezella), [FX Replay](https://logtolast.com/alternatives/fxreplay), [Replikanto](https://logtolast.com/alternatives/replikanto), [Tradesyncer](https://logtolast.com/alternatives/tradesyncer), and [TradersPost](https://logtolast.com/alternatives/traderspost).
- **[Privacy Policy & GDPR / EU AI Act Compliance](https://logtolast.com/privacy-policy)** — AES-256-GCM encryption at rest and zero data selling.

---

## 📄 License
Documentation released under the MIT License. Platform powered by **LogToLast LLC** (Sheridan, Wyoming, USA).
