# MacroRadar v2 — NYSE Macro Dashboard

![Status](https://img.shields.io/badge/Status-Live-brightgreen)
![Deploy](https://img.shields.io/badge/Deploy-Vercel-black?logo=vercel)
![Language](https://img.shields.io/badge/Built%20with-HTML%20%7C%20JS%20%7C%20CSS-orange)
![Data](https://img.shields.io/badge/Data-Yahoo%20Finance%20%7C%20SEC%20EDGAR-blue)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

> Real-time macro dashboard for NYSE traders. Tracks VIX, WTI, DXY, Gold, 10Y bonds and main indices (SPY, QQQ, DIA, IWM) with automatic signal generation, configurable scanner, Fed calendar, SEC 8-K live feed and correlation matrix.

🔗 **Live demo:** [macro-radar-wv9g.vercel.app](https://macro-radar-wv9g.vercel.app)

---

## 📸 Preview

![MacroRadar Dashboard](screenshot.png)

*Real-time macro dashboard — VIX gauge, NYSE indices, signal scanner, Fed calendar and SEC 8-K feed.*

---

## ✨ Features

| Feature | Detail |
|---|---|
| **VIX Fear Index** | Live price with visual gauge and 30-day history chart |
| **WTI Crude Oil** | Real-time price and % change with trend signal |
| **DXY US Dollar** | Dollar index with impact on commodities and EM |
| **Gold & 10Y Bond** | GLD ETF and TLT with daily change |
| **NYSE Indices** | SPY, QQQ, DIA, IWM — price, change, P&L |
| **BTC** | Bitcoin as risk-on/off signal |
| **Auto signals** | Bull/Bear/Neutral chips generated automatically |
| **Configurable scanner** | Custom VIX, WTI, SPY thresholds with ACTIVE/WATCH/OK status |
| **Correlation matrix** | VIX→SPY, WTI→SPY, DXY→QQQ, GLD→DXY, BTC→QQQ |
| **4 historical charts** | Today performance, VIX 30d, WTI vs SPY, 5-day cumulative return |
| **Fed calendar 2026** | All FOMC meetings with impact rating (HIGH/MED/LOW) |
| **Economic calendar** | CPI, NFP, PPI, Retail Sales, PMI with days-to-event countdown |
| **SEC 8-K live feed** | Real-time S&P 500 filings: Material Agreements, Earnings, Insider trades |
| **Live ticker bar** | Animated real-time ticker for all assets |
| **Auto-refresh** | Updates every 60 seconds automatically |

---

## 🧠 How It Works

MacroRadar pulls real-time data from Yahoo Finance API and generates automatic trading signals based on macro correlations:

```
Yahoo Finance API (free, no auth required)
        │
        ▼
  JavaScript Data Engine
  ┌─────────────────────────────────────┐
  │  Fetch: VIX, WTI, DXY, GLD, TLT   │
  │  Fetch: SPY, QQQ, DIA, IWM, BTC    │
  │  Calculate: % change, P&L           │
  │  Generate: Bull/Bear signals        │
  │  Run: Configurable scanner          │
  │  Correlate: Cross-asset matrix      │
  └─────────────────────────────────────┘
        │
        ▼
  Real-time Dashboard (HTML + CSS + JS)
  - Live ticker bar
  - Macro cards with VIX gauge
  - 4 Chart.js historical charts
  - Signal chips
  - Alert panel
  - Fed + Economic calendar
  - SEC 8-K feed
```

---

## 📊 Signal Logic

| Condition | Signal | Action |
|---|---|---|
| VIX > 25 | 🔴 BEAR | Reduce exposure, buy puts |
| VIX 20-25 | ⚠ CAUTION | Reduce position size |
| VIX < 20 | ✅ BULL | Risk-on conditions |
| WTI move > 2% | ⚠ WATCH | Review energy/transport |
| DXY > 105 | 🔴 BEAR | Negative for EM and commodities |
| QQQ vs SPY spread > 1% | ℹ INFO | Tech rotation detected |
| BTC move > 3% | ⚡ SIGNAL | Risk-on/off crypto signal |

---

## 🔧 Scanner Configuration

The signal scanner is fully configurable via the dashboard UI:

- **VIX Alert threshold** — default: 20 (range: 10-50)
- **WTI move threshold** — default: 2% (range: 0.5-10%)
- **SPY move threshold** — default: 1% (range: 0.1-5%)

Each condition shows real-time status: `ACTIVE` / `WATCH` / `OK`

---

## 📅 Fed Calendar 2026

| Date | Event | Impact |
|---|---|---|
| May 6-7 | FOMC Meeting | 🔴 HIGH |
| Jun 17-18 | FOMC + Projections | 🔴 HIGH |
| Jul 28-29 | FOMC Meeting | 🟡 MED |
| Sep 15-16 | FOMC + SEP | 🔴 HIGH |
| Nov 4-5 | FOMC Meeting | 🟡 MED |
| Dec 15-16 | FOMC + Projections | 🔴 HIGH |

---

## 🚀 Quick Start

No installation required — runs entirely in the browser.

**Option 1 — Use the live app:**
```
https://macro-radar-wv9g.vercel.app
```

**Option 2 — Run locally:**
```bash
git clone https://github.com/cris-devtrading/macro-radar
cd macro-radar
# Open index.html in your browser
```

---

## 🛠️ Tech Stack

- **HTML5 / CSS3 / Vanilla JavaScript** — zero dependencies
- **Chart.js 4.4** — historical charts
- **Yahoo Finance API** — real-time market data (free, no auth)
- **SEC EDGAR API** — 8-K filings feed
- **Vercel** — instant global deployment
- **Google Fonts** — Share Tech Mono + Rajdhani

---

## 💡 Use Cases

- **Retail traders** monitoring macro conditions before opening positions
- **Prop traders** using VIX/WTI/DXY as risk filters
- **Fintech startups** needing an embeddable macro dashboard component
- **Portfolio managers** tracking cross-asset correlations
- **Developers** learning real-time financial dashboard architecture

---

## 👤 About the Author

Built by **Cristian Chaves** — Algorithmic Trading & Fintech Developer.

Specializing in automated trading systems, broker API integrations, options analytics, and real-time financial dashboards for retail traders, prop firms, and fintech startups.

🔗 [AlgoTrader Pro — IBKR Automated Bot](https://github.com/cris-devtrading/algotrader-pro)  
🔗 [OptionsGuru — Live Options Analyzer](https://option-guru.vercel.app)  
🔗 [CCL Radar v2 — Argentine ADR/CEDEAR Monitor](https://ccl-radar.vercel.app)  
🔗 [BotSignal Latam — Telegram Signal Channel](https://botsignal.vercel.app)  
📧 Open for freelance projects — [Upwork](https://www.upwork.com/freelancers/cristianchaves) | [Fiverr](https://www.fiverr.com/cristianchaves)

---

## 📄 License

MIT — free to use, modify, and distribute with attribution.
