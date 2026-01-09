<p align="center">
  <a href="README.md"><img src="https://img.shields.io/badge/English-blue?style=for-the-badge" alt="English"></a>
  <a href="README.zh-TW.md"><img src="https://img.shields.io/badge/繁體中文-red?style=for-the-badge" alt="繁體中文"></a>
</p>

<p align="center">
  <img src="assets/banner.png" alt="FinLab AI Plugin Banner" width="800">
</p>

# FinLab AI Plugin

> AI 驅動的台股量化交易技能

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai)

<p align="center">
  <img src="assets/demo.gif" alt="Demo" width="700">
</p>

## 快速安裝（任何 AI CLI）

只要告訴你的 AI 助手：

> 「請查看 https://github.com/koreal6803/finlab-claude-plugin 並幫我安裝 FinLab skill」

適用於 **Claude Code**、**ChatGPT Codex CLI**、**Gemini CLI** 及其他 AI 程式助手。

## 功能特色

- **完整數據存取** - 900+ 欄位：股價、財報、營收、估值、法人籌碼
- **策略開發** - 使用 FinLabDataFrame 方法建立因子策略
- **回測引擎** - 風險管理、停損、停利、部位控制
- **因子分析** - IC 計算、Shapley 值、中心性分析
- **機器學習** - 特徵工程與標籤生成

## 範例

### 取得法人買賣超數據

**提示：**
> 「list following TW stocks 近 5 天外資買賣超: 2330, 2317, 2454, 2881, 2308, 2382, 2882, 2412, 2303, 2344」

**結果：**

<img src="assets/demo-data.png" alt="Data Output" width="700">

### 建立並回測策略

**提示：**
> 「幫我建立一個台股月度調倉策略：從營收 YOY 正成長的股票中，篩選本益比低於 10、股價淨值比低於 1.5 的深度價值股，並確保股價在 60 日均線之上有上漲趨勢，每月選出 20 檔進行回測」

**結果：**

<img src="assets/demo-chart.png" alt="Backtest Result" width="700">

## 手動安裝

### 方式一：Claude Code

```bash
# 新增 marketplace
/plugin marketplace add koreal6803/finlab-claude-plugin

# 安裝 plugin
/plugin install finlab-plugin@finlab-plugins
```

### 方式二：ChatGPT Codex CLI

```bash
git clone https://github.com/koreal6803/finlab-claude-plugin.git
cd finlab-claude-plugin
```

然後告訴 Codex：
```
請幫我安裝此 finlab-plugin 裡的 skills
```

### 方式三：Gemini CLI

```bash
# 安裝 skill-porter
npm install -g skill-porter

# Clone 並轉換
git clone https://github.com/koreal6803/finlab-claude-plugin.git
cd finlab-claude-plugin
skill-porter convert ./finlab-plugin/skills/finlab --to gemini --output ./finlab-gemini-extension
```

然後依照 Gemini CLI 文件安裝 `finlab-gemini-extension`。

## 前置需求

取得 FinLab API Token：https://ai.finlab.tw/api_token/

```bash
export FINLAB_API_TOKEN="your_token_here"
```

## 文件說明

Plugin 包含完整參考文件：

| 文件 | 內容 |
|------|------|
| Data Reference | 900+ 欄位，80+ 資料表 |
| Backtesting Reference | sim() API、重新取樣、績效指標 |
| Factor Examples | 60+ 完整策略範例 |
| Best Practices | 模式、反模式、技巧 |
| ML Reference | 特徵工程、標籤生成 |

## 授權

MIT

## 作者

FinLab 社群
