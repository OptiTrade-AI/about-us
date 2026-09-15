# OptiTrade AI

> **A rules-based trading desk for options and futures.** Every weekday after the close, OptiTrade scans the market, shows you what fired, and watches every position until its rules say to exit.

---

## What It Is

OptiTrade AI runs eight trading strategies. Each one has written rules, a nightly scanner, and a tracker for open positions. It was built by an engineer and trader to answer three questions every evening:

1. **What fired today?**
2. **What do I own, and does anything need action?**
3. **Is each strategy actually working?**

The math makes the calls. AI helps you read the results, but it never picks the trade.

---

## How It Works

1. **After the close**, scanners run on the day's final prices across US stocks and 25 CME futures.
2. **Signals land on your home screen and in Discord**, each with the trade to place and the levels that matter.
3. **You decide.** Take it or pass, and note why. Place the order at the next open and record your fill.
4. **Trackers check every position nightly** and flag exits, profit targets, futures rolls, and earnings.
5. **The journal keeps score:** your P/L, each strategy's live record, and the trades you skipped.

---

## The Strategies

| Strategy | The idea | Trades |
|---|---|---|
| **Dip Harvest** | Sell a put spread when a heavily traded S&P 500 or Nasdaq-100 stock gets sharply oversold in an uptrend | Options |
| **Short Put** | Sell a put on a strong stock after a pullback. Buy it back at half the credit, or let it expire | Options |
| **Bear Harvest** | Dip Harvest for bear markets. It only switches on while SPY is below its 200-day average | Options |
| **Box Watchlist** | Buy a call when a market leader breaks out of a tight sideways range | Options |
| **Golden Cross** | Buy a strong close through resistance after the 50-day average crosses above the 200-day | Shares or calls |
| **Futures Dip** | Buy stock-index futures on sharp dips in an uptrend. Sell on the bounce | Futures |
| **Futures Pivot** | The Golden Cross breakout on 25 futures markets, long and short | Futures |
| **Futures Trend** | Buy pullbacks in futures markets that are in a clear trend | Futures |

Every strategy has a one-screen summary (what it is, when it fires, entry, exit, risk) and a full playbook.

**In live testing: Overnight Volume.** At 3:45 PM ET, it finds S&P 500 stocks trading at twice their normal volume and up on the day. They are bought at the close and sold at the next open. Every night is logged so the rule can prove itself before it gets real money.

---

## Built-In Tools

- **Home.** Tonight's signals, every open position, today's P/L, and scan health on one screen.
- **Game Plan.** One page per trading session: to-dos, a watchlist with your price levels, and notes.
- **Deep Scan.** Prices every option on a ticker with its own Black-Scholes model and scores which contracts pay unusually rich premium. An AI agent can explain why.
- **Research.** A scorecard for up to 10 tickers: trend strength, financial health from SEC filings, insider buying, short interest, and the options market's earnings bet. Claude writes a short memo that can only cite those computed numbers.
- **Journal and Analytics.** Strategy trades, your own trades, and Robinhood imports in one place, with a P/L calendar, notes on each trade, a rules checklist, and a weekly AI coach that reviews what you wrote.
- **Privacy Mode.** Press `Ctrl+Shift+H` to hide every dollar amount.

---

## Why It's Different

- **The rules don't drift.** Each scanner's core math is versioned and locked by tests. When you take a trade, its levels are frozen, so exits are judged against the plan you signed up for.
- **Backtested, then measured live.** Most rules come from backtests on real price and options history, and the scorecard puts live results next to those backtests.
- **Missing data is flagged, never guessed.** If a price, quote, or earnings date is unknown, the app says so instead of making up a number.
- **The system and you are scored separately.** Analytics keep strategy trades apart from your own, so you learn whether the system is good or you are.
- **Numbers come from code, not AI.** AI explains and summarizes, but it can't invent a figure.

---

## Who It's For

Traders who want written rules instead of tips, who sell options premium or trade index futures, and who want an honest record of what's working.

---

*Options and futures trading involves substantial risk of loss. OptiTrade provides analytical tools, not financial advice. Backtests and past performance do not guarantee future results. Position sizing and risk management are your responsibility.*

**Email**: jjdev@optitrade-ai.com
