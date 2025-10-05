# 📊 OptiTrade AI
## Master Core Options Trading Strategies

---

## Cash-Secured Puts 🎯

### Strategy Overview
Sell a put option while holding enough cash to purchase the underlying stock if assigned. Conservative income strategy for stocks you want to own at a discount.

**Market Outlook:** Bullish to Neutral | Best when IV is high

| Metric | Value |
|--------|-------|
| Maximum Profit | Premium Received |
| Maximum Loss | Strike - Premium |
| Breakeven | Strike - Premium |

### Example Trade
- **Stock Price:** $50.00
- **Sell 1 Put Strike:** $45.00
- **Premium Received:** $2.00 ($200)
- **Cash Required:** $4,500
- **Breakeven:** $43.00

**Scenarios:**
- Stock stays above $45: +$200 profit (Keep premium, no assignment)
- Stock drops to $42: -$100 loss (Own shares at $43 effective cost)

### Do's ✅
- Only sell on stocks you want to own
- Choose strikes below support levels
- Target 30-45 DTE for optimal theta

### Don'ts ❌
- Don't sell without adequate cash
- Avoid during earnings without planning
- Don't ignore assignment risk

---

## Covered Calls 📈

### Strategy Overview
Sell call options against stock you own to generate income. One of the most popular income strategies for long-term stockholders.

**Market Outlook:** Neutral to Slightly Bullish | Best in range-bound markets

| Metric | Value |
|--------|-------|
| Maximum Profit | Premium + Capital Gain |
| Maximum Loss | Stock Price - Premium |
| Breakeven | Stock Cost - Premium |

### Example Trade
- **Own 100 Shares:** $50.00
- **Sell 1 Call Strike:** $55.00
- **Premium Received:** $1.50 ($150)
- **Max Profit:** $650

**Scenarios:**
- Stock stays below $55: Keep $150 + stock (Expires worthless, repeat strategy)
- Stock rises to $60: +$650 total profit ($500 stock gain + $150 premium)

---

## Put Credit Spreads (Bull Put) 🔻

### Strategy Overview
Sell a put at higher strike, buy a put at lower strike. Defined risk bullish strategy that profits when stock stays above the sold strike.

**Market Outlook:** Bullish to Neutral | High IV preferred

| Metric | Value |
|--------|-------|
| Maximum Profit | Net Credit |
| Maximum Loss | Width - Credit |
| Breakeven | High Strike - Credit |

### Example Trade
- **Stock Price:** $50.00
- **Sell 1 Put @ $48:** +$2.00
- **Buy 1 Put @ $45:** -$0.50
- **Net Credit:** $1.50 ($150)
- **Max Loss:** $150
- **Breakeven:** $46.50

**Scenarios:**
- Stock above $48: +$150 max profit
- Stock drops to $44: -$150 max loss

---

## Call Debit Spreads (Bull Call) 🔺

### Strategy Overview
Buy a call at lower strike, sell a call at higher strike. Lower cost bullish alternative to buying calls outright with defined risk.

**Market Outlook:** Moderately Bullish | Defined risk preferred

| Metric | Value |
|--------|-------|
| Maximum Profit | Width - Debit |
| Maximum Loss | Net Debit |
| Breakeven | Low Strike + Debit |

### Example Trade
- **Stock Price:** $50.00
- **Buy 1 Call @ $50:** -$3.00
- **Sell 1 Call @ $55:** +$1.00
- **Net Debit:** $2.00 ($200)
- **Max Profit:** $300
- **Breakeven:** $52.00

---

## Call Credit Spreads (Bear Call) 🔽

### Strategy Overview
Sell a call at lower strike, buy a call at higher strike. Bearish strategy that profits when stock stays below the sold strike.

**Market Outlook:** Bearish to Neutral | High IV preferred

| Metric | Value |
|--------|-------|
| Maximum Profit | Net Credit |
| Maximum Loss | Width - Credit |
| Breakeven | Low Strike + Credit |

### Example Trade
- **Stock Price:** $50.00
- **Sell 1 Call @ $52:** +$2.00
- **Buy 1 Call @ $55:** -$0.50
- **Net Credit:** $1.50 ($150)
- **Max Loss:** $150
- **Breakeven:** $53.50

---

## Put Debit Spreads (Bear Put) 🔼

### Strategy Overview
Buy a put at higher strike, sell a put at lower strike. Bearish strategy with limited risk and lower cost than buying puts alone.

**Market Outlook:** Moderately Bearish | Defined risk preferred

| Metric | Value |
|--------|-------|
| Maximum Profit | Width - Debit |
| Maximum Loss | Net Debit |
| Breakeven | High Strike - Debit |

### Example Trade
- **Stock Price:** $50.00
- **Buy 1 Put @ $50:** -$3.00
- **Sell 1 Put @ $45:** +$1.00
- **Net Debit:** $2.00 ($200)
- **Max Profit:** $300
- **Breakeven:** $48.00

---

## Long Straddle 🎪

### Strategy Overview
Buy both a call and put at the same strike. Profits from large moves in either direction. Ideal before major events like earnings.

**Market Outlook:** Large Move Expected | Direction Uncertain

| Metric | Value |
|--------|-------|
| Maximum Profit | Unlimited (both sides) |
| Maximum Loss | Total Premium Paid |
| Breakevens | Strike ± Premium |

### Example Trade
- **Stock Price:** $50.00
- **Buy 1 Call @ $50:** -$3.00
- **Buy 1 Put @ $50:** -$3.00
- **Total Cost:** $6.00 ($600)
- **Breakevens:** $44 & $56

**Scenarios:**
- Stock jumps to $60: +$400 profit
- Stock stays at $50: -$600 max loss
- Stock drops to $40: +$400 profit

---

## Long Strangle 🎭

### Strategy Overview
Buy an OTM call and OTM put. Lower cost than straddle but requires larger move to profit. Great for volatile events.

**Market Outlook:** Very Large Move Expected | Direction Uncertain

| Metric | Value |
|--------|-------|
| Maximum Profit | Unlimited (both sides) |
| Maximum Loss | Total Premium Paid |
| Breakevens | Strikes ± Premium |

### Example Trade
- **Stock Price:** $50.00
- **Buy 1 Call @ $55:** -$1.50
- **Buy 1 Put @ $45:** -$1.50
- **Total Cost:** $3.00 ($300)
- **Breakevens:** $42 & $58

---

## Iron Condor 🦅

### Strategy Overview
Combine bull put spread and bear call spread. Profits from low volatility when stock stays within a range. Popular income strategy.

**Market Outlook:** Neutral | Range-Bound | Low Volatility

| Metric | Value |
|--------|-------|
| Maximum Profit | Net Credit |
| Maximum Loss | Width - Credit |
| Breakevens | Short Strikes ± Credit |

### Example Trade
- **Stock Price:** $50.00
- **Sell 1 Put @ $45:** +$1.00
- **Buy 1 Put @ $42:** -$0.30
- **Sell 1 Call @ $55:** +$1.00
- **Buy 1 Call @ $58:** -$0.30
- **Net Credit:** $1.40 ($140)
- **Max Loss:** $160
- **Breakevens:** $43.60 & $56.40

---

## Long Butterfly Spread 🦋

### Strategy Overview
Buy one lower strike, sell two middle strikes, buy one higher strike. Low-cost strategy that profits from minimal movement.

**Market Outlook:** Neutral | Expect Stock Near Middle Strike

| Metric | Value |
|--------|-------|
| Maximum Profit | Width - Net Debit |
| Maximum Loss | Net Debit |
| Breakevens | Around Middle Strike |

### Example Trade (Call Butterfly)
- **Stock Price:** $50.00
- **Buy 1 Call @ $45:** -$6.00
- **Sell 2 Calls @ $50:** +$6.00
- **Buy 1 Call @ $55:** -$1.50
- **Net Debit:** $1.50 ($150)
- **Max Profit:** $350 (at $50)
- **Breakevens:** $46.50 & $53.50

---

## Broken Wing Butterfly 🦇

### Strategy Overview
Asymmetric butterfly with one wing wider than the other. Can be structured for credit with skewed risk profile based on directional bias.

**Market Outlook:** Slightly Directional | Neutral Near Short Strikes

### Example Trade (Bullish BWB)
- **Stock Price:** $50.00
- **Buy 1 Call @ $48:** -$4.00
- **Sell 2 Calls @ $50:** +$6.00
- **Buy 1 Call @ $54:** -$1.00
- **Net Credit:** $1.00 ($100)
- **Lower Wing Width:** $2
- **Upper Wing Width:** $4
- **Max Profit:** $300 (at $50)
- **Max Loss:** $300 (above $54)

**Scenarios:**
- Stock at $50: +$300 max profit
- Stock below $48: +$100 profit (risk-free zone)
- Stock above $54: -$300 max loss

---

## Calendar Spread (Time Spread) 📐

### Strategy Overview
Sell near-term option and buy longer-term option at the same strike. Profits from time decay differential and volatility changes.

**Market Outlook:** Neutral Short-Term | Expect Stock Near Strike | IV to Rise

| Metric | Value |
|--------|-------|
| Maximum Profit | Varies (At Strike) |
| Maximum Loss | Net Debit |
| Best Case | Stock at Strike, Front Exp |

### Example Trade
- **Stock Price:** $50.00
- **Sell 1 Call @ $50 (30 DTE):** +$2.00
- **Buy 1 Call @ $50 (60 DTE):** -$3.50
- **Net Debit:** $1.50 ($150)
- **Max Loss:** $150
- **Potential Profit:** $200-$400

### Key Benefits 💡
- Profits from time decay differential
- Benefits from rising implied volatility
- Can be rolled indefinitely

### Watch Out For ⚠️
- Large moves reduce profitability
- IV crush can hurt back-month option
- Best when stock stays near strike

---

## ⚠️ Risk Disclaimer

Options trading involves substantial risk and is not suitable for all investors. Past performance does not guarantee future results. Always understand the risks and potential losses before entering any options position.

---

*OptiTrade AI - Intelligent Options Trading Made Simple*
