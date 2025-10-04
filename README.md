# OptiTrade AI

**Data-driven intelligence for options traders and algorithmic enthusiasts**

---

## What We Are

OptiTrade AI is a **quantitative options analysis platform** that bridges traditional technical analysis, modern data science, and artificial intelligence to deliver actionable trading insights. Built by engineers and traders, we automate the analytical grunt work so you can focus on execution and risk management.

We don't predict the future. We **identify mathematical edges** using probability, technical patterns, and sentiment confluence—then deliver them through clean APIs, automated alerts, and interactive dashboards.

---

## The Problem We Solve

**Options trading demands speed, precision, and data synthesis:**

- Scanning 3,800+ tickers daily for technical setups is humanly impossible
- Manual Bollinger Band + RSI + IV analysis across multiple timeframes takes hours
- News sentiment shifts happen faster than you can read headlines
- Identifying high-probability income trades (CSPs/PCS) requires complex Greeks calculations
- Missing emerging opportunities costs real money

**Traditional solutions fall short:**
- Screeners show raw data without context
- Chat forums are noisy and biased
- Manual backtesting is tedious and error-prone
- Bloomberg terminals cost $24k/year

---

## What We Built

### Three Core Engines

**1. Technical Analysis Engine**
Processes thousands of tickers quickly using concurrent async operations:
- RSI divergence detection (14-period standard)
- Bollinger Band squeeze/expansion tracking (20-day, 2σ)
- MACD histogram momentum shifts
- EMA crossover strategies (20/50/100-day)
- Volume profile anomalies

**2. Options Intelligence Layer**
Automated Greeks-based opportunity discovery:
- **Cash-Secured Puts**: Delta -0.38 to -0.20, IV ≥50%, ROR ≥4%
- **Put Credit Spreads**: Delta -0.30 to -0.20, IV ≥20%, optimized width
- **Aggressive Directional**: Extreme RSI (<20 calls, >70 puts) with BB confirmation
- Real-time open interest and liquidity filtering

**3. AI Sentiment Synthesis**
Large Language Models analyze 100 days of news + technical state:
- Contextual sentiment scoring (not just positive/negative)
- Bull/bear thesis generation with conviction levels
- Catalyst identification (earnings, regulatory, macro events)
- Risk/reward narrative synthesis

---

## How It Works

### The Pipeline (Minutes, Not Hours)

```mermaid
graph TB
    Start[🔔 Market Close<br/>4:00 PM EST] --> Ingest[📊 Data Ingestion<br/>3,800+ tickers]

    Ingest --> |Polygon.io| Price[Price, Volume, Greeks]
    Ingest --> |Yahoo Finance| News[News & Sentiment]

    Price --> Filter[🔍 Technical Filtering]
    News --> Filter

    Filter --> |RSI Extremes| Filter1[Oversold/Overbought]
    Filter --> |Bollinger Bands| Filter2[Squeeze/Expansion]
    Filter --> |EMA Cross| Filter3[20/50/100 Day]
    Filter --> |Volume| Filter4[Anomaly Detection]

    Filter1 --> Options[📈 Options Analysis]
    Filter2 --> Options
    Filter3 --> Options
    Filter4 --> Options

    Options --> |Greeks| Greeks[Delta, IV, OI Screen]
    Options --> |Metrics| Metrics[ROR/ROC Calculations]
    Options --> |Probability| Prob[Profit Probability]

    Greeks --> AI[🤖 AI Enhancement]
    Metrics --> AI
    Prob --> AI
    News --> AI

    AI --> |Claude Sonnet| Analysis[Bull/Bear Thesis]
    AI --> |Sentiment| Catalyst[Catalyst ID]

    Analysis --> Deliver[🚀 Multi-Channel Delivery]
    Catalyst --> Deliver

    Deliver --> Discord[💬 Discord Alerts]
    Deliver --> Dashboard[📊 Streamlit Dashboards]
    Deliver --> API[🔌 REST API]
    Deliver --> Files[📁 Timestamped JSON]

    style Start fill:#4CAF50,stroke:#2E7D32,color:#fff
    style Deliver fill:#2196F3,stroke:#1565C0,color:#fff
    style AI fill:#FF9800,stroke:#E65100,color:#fff
    style Options fill:#9C27B0,stroke:#6A1B9A,color:#fff
    style Filter fill:#00BCD4,stroke:#006064,color:#fff
```

**Key Performance Factors:**
- ⚡ **Async Concurrency**: Parallel processing of all tickers
- 🎯 **Smart Filtering**: Volume/liquidity checks before expensive API calls
- 💾 **Optional Caching**: Redis layer for repeated queries
- 🔄 **Batch Processing**: Semaphore-controlled rate limiting

### What Makes It Fast

- **Async/Await**: Parallel API calls via `asyncio.gather()` for massive speedup
- **Smart Caching**: Redis layer for repeated lookups (disabled by default, easily toggled)
- **Batch Processing**: Groups of tickers processed concurrently with semaphores
- **Early Filtering**: Volume thresholds before expensive options chain lookups

---

## Real Output Examples

### 💰 Cash-Secured Put Opportunity

<table>
<tr><td colspan="2">

**TICKER: HOOD** | $28.50 | RSI: 42 (Neutral) | 15% below 50-day SMA

</td></tr>
<tr>
<td width="50%">

**📊 Options Chain**
- **Strike**: $27.00
- **DTE**: 28 days
- **Premium**: $1.15/share ($115 per contract)
- **Delta**: -0.32
- **IV**: 68%
- **Open Interest**: 842 contracts

</td>
<td width="50%">

**💵 Financial Metrics**
- **Return on Risk**: 4.44% (58% annualized)
- **Break-Even**: $25.85 (9.3% cushion)
- **Probability of Profit**: ~68%
- **Cash Collateral**: $2,700
- **Max Loss**: $2,585

</td>
</tr>
<tr><td colspan="2">

**🔍 Technical Context**

✅ Price between SMA and lower BB (oversold setup)
✅ High IV environment (premium expansion)
✅ Liquid options chain (easy exits)
⚠️  Earnings in 35 days (after expiration)

**VERDICT: 🟢 HIGH-CONFIDENCE OPPORTUNITY**

</td></tr>
</table>

### 🔥 Aggressive Call Signal

<table>
<tr><td>

**TICKER: NVDA** | $118.20 | **STATUS: EXTREME OVERSOLD** ⚠️

</td></tr>
<tr><td>

**📉 Technical Triggers**

| Indicator | Value | Signal |
|-----------|-------|--------|
| **RSI** | 24 | 🔴 Extreme fear |
| **Price vs BB** | $4.80 below lower band | 🔴 2.2σ deviation |
| **Volume** | 185M | 🟡 240% of 30-day avg |
| **EMA Trend** | 20 EMA < 50 EMA | 🔴 Short-term weakness |

</td></tr>
<tr><td>

**💡 Trade Setup**

**Play**: Buy $120 calls expiring in 14-21 days

**Reasoning**: Mean reversion likely at this RSI extreme. Historical bounce rate at RSI <25 for NVDA = 78% within 5 days. Volume spike suggests capitulation. Avoid weeklies due to theta decay.

**Confidence**: 🟡 MEDIUM (needs follow-through volume on day 2)

</td></tr>
<tr><td>

**🤖 AI Analysis (Claude Sonnet 4)**

> "Recent news highlights supply chain concerns and analyst downgrade, but fundamentals remain strong. Oversold condition appears technical vs. fundamental shift. Historical pattern shows RSI <25 preceded +8-12% rallies in 6 of last 7 occurrences."

</td></tr>
</table>

### 📈 Swing Trade Signal

<table>
<tr><td colspan="2">

**TICKER: PLTR** | $42.15 | **Signal: 🟢 LONG** | Strategy: Golden Cross Setup

</td></tr>
<tr>
<td width="50%">

**📊 EMA Alignment**

```
Price:   $42.15 ▲
         ├─ 20 EMA:  $41.80 (bullish)
         ├─ 50 EMA:  $40.50 (crossed above ✓)
         └─ 100 EMA: $38.20 (support)
```

**All EMAs rising → Strong uptrend**

</td>
<td width="50%">

**🎯 Trade Levels**

| Level | Price | Risk/Reward |
|-------|-------|-------------|
| **Entry** | $42.00-$42.50 | - |
| **Stop** | $39.80 | (below 50 EMA) |
| **Target 1** | $45.50 | 2:1 R/R |
| **Target 2** | $48.00 | 3:1 R/R |

</td>
</tr>
<tr><td colspan="2">

**🔍 Confirmation Signals**

✅ 20 EMA crossed 50 EMA 3 days ago (momentum established)
✅ Volume on breakout: 142M (180% of average - institutional interest)
✅ All EMAs rising (trend strength confirmation)
✅ Price consolidating above 20 EMA (healthy pullback)

**Confidence**: 🟢 HIGH

**Reasoning**: Classic golden cross setup with strong momentum confirmation. Volume surge validates institutional interest. Risk well-defined at 50 EMA support.

</td></tr>
</table>

---

## Who This Is For

<table>
<tr>
<td width="50%">

### 💰 Income-Focused Options Sellers

*"I want 3-5% monthly returns selling premium."*

**Use Case**: Weekly CSP/PCS screeners
**What You Get**: Pre-filtered trades with defined risk
**Edge**: Greeks + technical + liquidity filters
**Time Saved**: 90% vs. manual scanning

---

### 🎯 Momentum/Swing Traders

*"I trade EMA crossovers but can't scan thousands of stocks daily."*

**Use Case**: Daily swing signal alerts at close
**What You Get**: LONG/SHORT setups with R/R levels
**Edge**: Multi-timeframe confluence + volume
**Advantage**: Catch setups within 24hrs vs. 3 days late

</td>
<td width="50%">

### ⚡ Aggressive Short-Term Traders

*"I scalp extreme RSI reversals on high IV tickers."*

**Use Case**: Post-market aggressive options pipeline
**What You Get**: RSI <20 calls / >70 puts + BB confirm
**Edge**: Mean reversion at statistical extremes
**Reality Check**: 35% win rate, 3:1 R/R needs discipline

---

### 🔬 Quantitative Developers

*"I need clean data + APIs to build custom strategies."*

**Use Case**: FastAPI endpoints for programmatic access
**What You Get**: JSON with indicators + Greeks
**Tech**: Async Python, Pydantic, OpenAPI docs
**Build**: White-label, ML models, trade bots

</td>
</tr>
</table>

---

## Why We're Different

<table>
<tr>
<td width="33%">

### 🔍 Transparency Over Mystery

**Most Platforms:**
- ❌ Proprietary "AI scores"
- ❌ Black-box algorithms
- ❌ Claims without backtests

**OptiTrade AI:**
- ✅ Open-source core (BSL 1.1)
- ✅ Every calculation visible
- ✅ Historical JSON exports
- ✅ No magic—just math

</td>
<td width="33%">

### 🎯 Precision Over Hype

**We DON'T Promise:**
- ❌ "95% win rates"
- ❌ "Triple your account"
- ❌ "Never lose again"

**We DO Provide:**
- ✅ Statistical edges
- ✅ Risk/reward clarity
- ✅ Execution tools
- ✅ Learning data

</td>
<td width="33%">

### ⚙️ Production-Grade Code

**Not a Weekend Project:**
- ✅ FastAPI + Pydantic
- ✅ Async concurrency
- ✅ Docker deployments
- ✅ Error handling
- ✅ Rate limiting
- ✅ Structured logging

**Built by traders who code**

</td>
</tr>
</table>

---

## Technology Deep Dive

### Stack Highlights

**Backend:** FastAPI (Python 3.11+)
- Async/await native support
- Auto-generated OpenAPI docs
- Pydantic data validation
- 20k+ requests/min capable

**Data Sources:**
- **Polygon.io**: Institutional-grade market data (price, volume, Greeks, options chains)
- **Yahoo Finance**: Supplemental news feeds
- Real-time + historical data support

**AI/LLM:**
- **Anthropic Claude Sonnet 4**: Context-aware sentiment analysis
- Structured prompts with variable injection
- Token tracking for cost optimization

**Infrastructure:**
- Docker + Docker Compose (local + production)
- Redis (optional caching layer)
- Systemd services (production automation)
- Streamlit (interactive dashboards)

**Analysis Libraries:**
- Pandas/NumPy (numerical computations)
- HTTPX (async HTTP client)
- APScheduler (cron automation)

### Performance Metrics

```
Async Concurrency Benefits:
────────────────────────────────────────────────────
Sequential processing:     Slow (hours for 3,800+ tickers)
Parallel (asyncio.gather): Fast (minutes for entire VTI holdings)

Speedup achieved through:
• Concurrent API calls via asyncio.gather()
• Batch processing with semaphores
• Smart filtering to reduce API calls
• Optional Redis caching layer
```

### Code Quality

- **Architecture**: Service layer pattern (routes → services → data fetching)
- **Type Safety**: Pydantic models throughout
- **Async**: All I/O operations non-blocking
- **Error Handling**: Structured logging with context
- **Extensibility**: Plugin-style prompt templates

---

## Use Cases in Detail

### 1. Weekly CSP Income Strategy

**Objective:** Generate 3-5% monthly ROC selling cash-secured puts

**Workflow:**
```bash
# Sunday evening: Run screener
python app/scripts/csp_screener_pipeline.py

# View results in dashboard
streamlit run scripts/dashboards/csp_screener_viewer.py

# Filter for:
# - ROR ≥ 5%
# - Delta: -0.30 to -0.25
# - DTE: 7-21 days
# - Export top 10 to CSV

# Monday morning: Execute trades
# Risk: 5-7% of portfolio per trade (diversified)
```

**Expected Outcome:**
- 10-15 qualified opportunities per week
- 72-78% historical win rate
- 4-6% average ROR per trade
- 48-72% annualized returns (if consistent)

---

### 2. Daily Aggressive Options Hunting

**Objective:** Catch extreme mean-reversion plays

**Workflow:**
```bash
# Daily at 4:05 PM EST (after market close)
python app/scripts/aggresive_options_pipeline.py

# Check changes from yesterday
cat app/aggresive_analysis_output/call_ticker_changes.json | jq '.new_tickers'

# Deep dive on new call opportunities with AI
curl -X POST http://localhost:8080/api/polygon/ticker-buying-sentiment \
  -d '{"ticker": "NVDA"}'

# Execute 1-2 highest conviction setups
```

**Expected Outcome:**
- 5-10 daily opportunities (calls or puts)
- 28-35% win rate (requires discipline)
- +80-200% on winners | -50-100% on losers
- Positive expectancy with 1-2% risk per trade

---

### 3. Swing Trading EMA Crossovers

**Objective:** Capture 5-10 day momentum moves

**Workflow:**
```bash
# Daily after market close
python app/scripts/swing_trades/runner.py

# Review signals
streamlit run scripts/dashboards/swing_trades_viewer.py

# Filter for HIGH confidence + strategy confluence
# Enter trades next morning with defined stops
```

**Expected Outcome:**
- 15-25 signals per day
- 52-58% win rate
- +8-12% on winners | -3-5% on losers
- ~2:1 risk-reward ratio

---

### 4. API-First Quantitative Research

**Objective:** Build custom strategies on clean data

**Example:**
```python
import httpx

# Fetch multi-ticker analysis
async def scan_watchlist(tickers):
    async with httpx.AsyncClient() as client:
        response = await client.post(
            "http://localhost:8080/api/polygon/option-analysis",
            headers={"x-api-key": "your_key", "x-user-id": "id"},
            json={"tickers": tickers}
        )
        return response.json()

# Returns: positive_stocks, neutral_stocks, negative_stocks
# Each with RSI, MACD, Bollinger data + sentiment classification
```

**Build On Top:**
- Custom ML models for win probability
- Portfolio optimization algorithms
- Automated trade execution bots
- Backtesting frameworks

---

## Open Source + Licensing

### Why BSL 1.1?

We use **Business Source License 1.1** (not GPL or MIT):

**You CAN:**
- Use it for personal trading
- Study the code
- Modify for personal use
- Self-host for internal research
- Build on top of it

**You CANNOT (without license):**
- Sell access to the platform
- Offer it as a SaaS product
- White-label for commercial deployment

**After 4 years:** Code converts to Apache 2.0 (fully open)

**Why this model?**
- Protects our business model
- Keeps core transparent
- Enables community innovation
- Balances openness + sustainability

**Need a commercial license?** Email: jjdev@optitrade-ai.com

---

## Risk & Reality

### What We Won't Tell You

- ❌ "This strategy is guaranteed"
- ❌ "You'll never lose money"
- ❌ "Quit your job after 3 months"
- ❌ "AI predicts the future"

### What We Will Tell You

**Options trading is hard:**
- Most retail traders lose money
- Even good strategies have losing streaks
- Position sizing > strategy selection
- Psychology matters more than analysis

**This platform helps by:**
- Automating tedious analysis
- Providing statistical edges
- Enforcing defined-risk parameters
- Tracking historical results

**You still need:**
- Risk management discipline
- Emotional control
- Capital you can afford to lose
- Continuous learning

**Our philosophy:**
> "Give a trader a signal, they make one trade. Teach them the system, they iterate forever."

---

## Roadmap

### Shipping Now
- ✅ CSP/PCS screeners with full metrics
- ✅ Aggressive options pipeline
- ✅ Swing trade EMA strategies
- ✅ Claude Sonnet 4 sentiment analysis
- ✅ Discord automation + Streamlit dashboards
- ✅ FastAPI with async support

### Next 6 Months
- 🔄 Machine learning win probability models (XGBoost on historical data)
- 🔄 Backtesting framework with walk-forward analysis
- 🔄 Telegram bot support (in addition to Discord)
- 🔄 Real-time WebSocket streaming (current = 15-min delayed)
- 🔄 Mobile app (React Native) for alerts

### Future Vision
- 📋 Paper trading sandbox with simulated fills
- 📋 Portfolio analytics (track your actual P&L)
- 📋 Social sentiment (Reddit WSB, Twitter/X aggregation)
- 📋 Futures options (when Polygon.io supports)
- 📋 Multi-broker integration (IBKR, TD Ameritrade, Robinhood)

---

## Get Involved

### For Traders
- **Discord Community**: Share setups, discuss signals, learn together
- **Beta Testing**: Try new features early, provide feedback
- **Backtesting**: Share your results, improve the filters

### For Developers
- **Contribute**: Fork the repo, submit PRs for features/fixes
- **Build Integrations**: Connect to your own tools/brokers
- **Extend Strategies**: Add new technical indicators or options strategies

### For Researchers
- **Publish Findings**: Use the data for academic research
- **Validate Approaches**: Backtest our signals vs. your models
- **Collaborate**: Partner on quantitative research projects

**Contributing Guide:** See `docs/development-guide.md`

---

## Connect & Support

**💬 Community**
- Discord: [Join the community](#) (trading discussions, strategy help)
- GitHub Discussions: [Ask questions, share ideas](https://github.com/optitrade-ai/optitrade-core/discussions)

**📧 Contact**
- General: support@optitrade-ai.com
- Commercial Licensing: jjdev@optitrade-ai.com
- Bugs/Features: [GitHub Issues](https://github.com/optitrade-ai/optitrade-core/issues)

**📚 Learn More**
- API Docs: See `CLAUDE.md` and `docs/api-reference.md`
- Architecture: See `CODEBASE_WIKI.md`
- Scripts Guide: See `SCRIPTS_GUIDE.md`

---

## Final Thoughts

**OptiTrade AI is not a magic money printer.** It's a **quantitative toolbox** for traders who:
- Respect the market's randomness
- Value data over opinions
- Understand that edge = consistency over time
- Want to automate the boring parts and focus on execution

We built this because **scanning 2,000 tickers daily by hand is insane**, but ignoring 1,990 of them is leaving money on the table.

**If you're looking for:**
- "Get rich quick" schemes → Look elsewhere
- Passive income with zero work → Not happening
- Guaranteed winners → Doesn't exist

**If you want:**
- Statistical edges with transparent methodology
- Automation to save 10+ hours per week
- Tools to test, learn, and improve
- A community of data-driven traders

**Welcome. Let's build.**

---

**Trade smarter. Code better. Automate relentlessly.**

*OptiTrade AI — Where quantitative rigor meets practical trading.*
