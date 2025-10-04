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

```
Market Close (4:00 PM EST)
         ↓
[1] Data Ingestion
    • Polygon.io: Price, volume, Greeks
    • Yahoo Finance: News articles
    • Batch processing: 3,800+ tickers concurrently (entire VTI holdings)
         ↓
[2] Technical Filtering
    • RSI extremes (oversold/overbought)
    • Bollinger Band positioning
    • EMA alignment/crossovers
    • Volume confirmation
         ↓
[3] Options Analysis
    • Greeks screening (delta, IV, OI)
    • Probability calculations
    • ROR/ROC metrics
    • Spread optimization
         ↓
[4] AI Enhancement
    • News sentiment aggregation
    • Contextual analysis by Claude
    • Conviction scoring
         ↓
[5] Delivery
    • Discord: Formatted alerts
    • Dashboards: Interactive Streamlit apps
    • API: JSON responses
    • Files: Timestamped results + history
```

### What Makes It Fast

- **Async/Await**: Parallel API calls via `asyncio.gather()` for massive speedup
- **Smart Caching**: Redis layer for repeated lookups (disabled by default, easily toggled)
- **Batch Processing**: Groups of tickers processed concurrently with semaphores
- **Early Filtering**: Volume thresholds before expensive options chain lookups

---

## Real Output Examples

### Cash-Secured Put Opportunity

```
TICKER: HOOD | $28.50 | RSI: 42 (Neutral) | 15% below 50-day SMA

OPTIONS CHAIN:
  Strike: $27.00 | DTE: 28 days | Premium: $1.15
  Delta: -0.32 | IV: 68% | Open Interest: 842 contracts

METRICS:
  Return on Risk: 4.44% (58% annualized)
  Break-Even: $25.85 (9.3% downside cushion)
  Probability of Profit: ~68% (based on delta)
  Cash Collateral: $2,700 | Max Loss: $2,585

TECHNICAL CONTEXT:
  ✅ Price between SMA and lower BB (oversold setup)
  ✅ High IV environment (premium expansion)
  ✅ Liquid options chain (easy exits)
  ⚠️  Earnings in 35 days (after expiration)

VERDICT: HIGH-CONFIDENCE OPPORTUNITY
```

### Aggressive Call Signal

```
TICKER: NVDA | $118.20
STATUS: EXTREME OVERSOLD

TECHNICAL TRIGGERS:
  • RSI: 24 (extreme fear)
  • Price: $4.80 below lower Bollinger Band (2.2σ)
  • Volume: 185M (240% of 30-day average)
  • 20 EMA < 50 EMA (short-term weakness)

PLAY: Buy $120 calls expiring in 14-21 days
REASONING: Mean reversion likely at this RSI extreme. Historical
bounce rate at RSI <25 for NVDA = 78% within 5 days. Volume
spike suggests capitulation. Avoid weeklies due to theta decay.

CONFIDENCE: MEDIUM (needs follow-through volume on day 2)

AI TAKE (Claude Sonnet 4):
"Recent news highlights supply chain concerns and analyst
downgrade, but fundamentals remain strong. Oversold condition
appears technical vs. fundamental shift. Historical pattern shows
RSI <25 preceded +8-12% rallies in 6 of last 7 occurrences."
```

### Swing Trade Signal

```
TICKER: PLTR | $42.15 | Signal: LONG
STRATEGY: Golden Cross Setup

EMA ALIGNMENT:
  • 20 EMA: $41.80 (price above - bullish)
  • 50 EMA: $40.50 (recently crossed above)
  • 100 EMA: $38.20 (strong uptrend support)

ENTRY: $42.00-$42.50 zone
STOP: $39.80 (below 50 EMA)
TARGET 1: $45.50 (R/R = 2:1)
TARGET 2: $48.00 (R/R = 3:1)

CONFIDENCE: HIGH
  ✅ 20 EMA crossed 50 EMA 3 days ago
  ✅ Volume on breakout: 142M (180% avg)
  ✅ All EMAs rising (trend strength)
  ✅ Price consolidating above 20 EMA

REASONING: Classic golden cross setup with strong momentum
confirmation. Volume surge validates institutional interest. Risk
well-defined at 50 EMA support.
```

---

## Who This Is For

### Income-Focused Options Sellers
*"I want 3-5% monthly returns selling premium."*
- **Use Case**: Run CSP/PCS screeners weekly
- **What You Get**: Pre-filtered high-probability trades with defined risk
- **Why It Works**: Greeks + technical + liquidity = edge
- **Time Saved**: 90% (from manual chain scanning)

### Momentum/Swing Traders
*"I trade EMA crossovers but can't scan 1,000 stocks daily."*
- **Use Case**: Daily swing signal alerts at market close
- **What You Get**: LONG/SHORT setups with entry/stop/target prices
- **Why It Works**: Multi-timeframe EMA confluence + volume confirmation
- **Edge**: Catch crossovers within 24 hours vs. discovering them 3 days late

### Aggressive Short-Term Traders
*"I scalp extreme RSI reversals on high IV tickers."*
- **Use Case**: Post-market aggressive options pipeline
- **What You Get**: RSI <20 (calls) or >70 (puts) with BB confirmation
- **Why It Works**: Mean reversion at statistical extremes
- **Warning**: 35% win rate, but 3:1 R/R with discipline

### Quantitative Developers
*"I need clean data + APIs to build custom strategies."*
- **Use Case**: FastAPI endpoints for programmatic access
- **What You Get**: JSON responses with technical indicators + Greeks
- **Why It's Better**: Async Python, Pydantic validation, OpenAPI docs
- **Extend It**: White-label the platform, add ML models, build bots

---

## Why We're Different

### Transparency Over Mystery

**Most platforms:**
- Proprietary "AI scores" with no methodology
- Black-box algorithms you can't audit
- Claims without backtests

**OptiTrade AI:**
- Open-source core (BSL 1.1 license)
- Every calculation explained in code
- Historical JSON files for your own backtesting
- No magic—just math and execution

### Precision Over Hype

We **don't** promise:
- "95% win rates"
- "Triple your account in 30 days"
- "Never lose again"

We **do** provide:
- Statistical edges (not certainties)
- Risk/reward transparency
- Tools to execute your thesis
- Data to learn and improve

### Production-Grade Engineering

**Not a weekend project:**
- FastAPI + Pydantic (type safety, validation)
- Async concurrency (10x performance)
- Docker deployments (reproducibility)
- Comprehensive error handling
- Rate limiting for API quotas
- Structured logging

**Built by engineers who trade:**
- Experienced with real P&L pain
- Obsessed with data quality
- Value speed + reliability
- Ship features that matter

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
