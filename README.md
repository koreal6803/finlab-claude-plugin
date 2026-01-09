<p align="center">
  <a href="README.md"><img src="https://img.shields.io/badge/English-blue?style=for-the-badge" alt="English"></a>
  <a href="README.zh-TW.md"><img src="https://img.shields.io/badge/繁體中文-red?style=for-the-badge" alt="繁體中文"></a>
</p>

<p align="center">
  <img src="assets/banner.png" alt="FinLab AI Plugin Banner" width="800">
</p>

# FinLab AI Plugin

> AI-powered quantitative trading skill for Taiwan stock market (台股)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai)

<p align="center">
  <img src="assets/demo.gif" alt="Demo" width="700">
</p>

## Quick Install (Any AI CLI)

Simply tell your AI assistant:

> "Please look at https://github.com/koreal6803/finlab-claude-plugin and install the FinLab skill for me"

This works with **Claude Code**, **ChatGPT Codex CLI**, **Gemini CLI**, and other AI coding assistants.

## Features

- **Comprehensive Data Access** - 900+ data columns: prices, financials, revenue, valuations, institutional trading
- **Strategy Development** - Factor-based strategies using FinLabDataFrame methods
- **Backtesting Engine** - Risk management, stop-loss, take-profit, position sizing
- **Factor Analysis** - IC calculation, Shapley values, centrality analysis
- **Machine Learning** - Feature engineering and label generation for ML models

## Examples

### Fetch Institutional Trading Data

**Prompt:**
> "List following TW stocks 近 5 天外資買賣超: 2330, 2317, 2454, 2881, 2308, 2382, 2882, 2412, 2303, 2344"

**Result:**

<img src="assets/demo-data.png" alt="Data Output" width="700">

### Build & Backtest a Strategy

**Prompt:**
> "Build a monthly rebalancing strategy for Taiwan stocks: select stocks with positive revenue YoY growth, P/E ratio below 10, P/B ratio below 1.5 (deep value), and price above 60-day moving average (uptrend). Pick top 20 stocks monthly and backtest."

**Result:**

<img src="assets/demo-chart.png" alt="Backtest Result" width="700">

## Manual Installation

### Option 1: Claude Code

```bash
# Add marketplace
/plugin marketplace add koreal6803/finlab-claude-plugin

# Install plugin
/plugin install finlab-plugin@finlab-plugins
```

### Option 2: ChatGPT Codex CLI

```bash
git clone https://github.com/koreal6803/finlab-claude-plugin.git
cd finlab-claude-plugin
```

Then tell Codex:
```
請幫我安裝此finlab-plugin 裡的 skills
```

### Option 3: Gemini CLI

```bash
# Install skill-porter
npm install -g skill-porter

# Clone and convert
git clone https://github.com/koreal6803/finlab-claude-plugin.git
cd finlab-claude-plugin
skill-porter convert ./finlab-plugin/skills/finlab --to gemini --output ./finlab-gemini-extension
```

Then install the generated `finlab-gemini-extension` following Gemini CLI docs.

## Prerequisites

Get your FinLab API token: https://ai.finlab.tw/api_token/

```bash
export FINLAB_API_TOKEN="your_token_here"
```

## Documentation

The plugin includes comprehensive reference docs:

| Document | Content |
|----------|---------|
| Data Reference | 900+ columns across 80+ tables |
| Backtesting Reference | sim() API, resampling, metrics |
| Factor Examples | 60+ complete strategy examples |
| Best Practices | Patterns, anti-patterns, tips |
| ML Reference | Feature engineering, labels |

## License

MIT

## Author

FinLab Community
