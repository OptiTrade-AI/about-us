# 📊 OptiTrade AI
## Master Core Options Trading Strategies

---

## 📈 Strategy Comparison Matrix

| Strategy | Market Outlook | Risk Level | Profit Potential | Best For |
|----------|---------------|------------|------------------|----------|
| Cash-Secured Put | Bullish-Neutral | ⚠️ Medium | 💰 Limited | Income + Acquisition |
| Covered Call | Neutral-Bullish | ⚠️ Medium | 💰 Limited | Income Generation |
| Bull Put Spread | Bullish-Neutral | ✅ Low | 💰 Limited | Defined Risk Bullish |
| Bull Call Spread | Bullish | ✅ Low | 💰 Limited | Directional with Cap |
| Bear Call Spread | Bearish-Neutral | ✅ Low | 💰 Limited | Defined Risk Bearish |
| Bear Put Spread | Bearish | ✅ Low | 💰 Limited | Directional with Cap |
| Long Straddle | High Volatility | ⚠️⚠️ High | 💰💰 Unlimited | Earnings/Events |
| Long Strangle | Very High Vol | ⚠️⚠️ High | 💰💰 Unlimited | Big Moves Expected |
| Iron Condor | Range-Bound | ✅ Low | 💰 Limited | Theta Harvesting |
| Butterfly Spread | Neutral | ✅ Low | 💰 Limited | Precision Play |
| Calendar Spread | Neutral | ✅ Low | 💰 Moderate | Volatility + Theta |

---

## Cash-Secured Puts 🎯

### Strategy Overview
Sell a put option while holding enough cash to purchase the underlying stock if assigned. Conservative income strategy for stocks you want to own at a discount.

**Market Outlook:** Bullish to Neutral | Best when IV is high

### 📊 Profit/Loss Diagram
```
Profit/Loss
    ^
    |         ████████████████████████  Max Profit: $200 (Premium)
$200|        █
    |       █
    |      █
  $0|-----█--------------------------------> Stock Price
    |    █ $43 (Breakeven)
    |   █
    |  █
-$XX| █                                    Max Loss: Strike - Premium
    |█
    +-----|-----|-----|-----|-----|-----|
         $40   $43   $45   $48   $50   $52
              (BE) (Strike)
```

### 📋 Key Metrics

| Metric | Value |
|--------|-------|
| Maximum Profit | Premium Received |
| Maximum Loss | Strike - Premium |
| Breakeven | Strike - Premium |
| Cash Required | Strike × 100 |

### 💼 Example Trade
```
Stock Price:    $50.00
Sell Put:       $45 Strike
Premium:        $2.00 ($200)
Cash Required:  $4,500
Breakeven:      $43.00
```

### 📈 Scenarios at Expiration

| Stock Price | Outcome | P/L |
|-------------|---------|-----|
| $50 | Put expires worthless | +$200 ✅ |
| $45 | Put expires worthless | +$200 ✅ |
| $43 | Assigned at breakeven | $0 |
| $40 | Assigned, loss | -$300 ❌ |

### ✅ Do's
- Only sell on stocks you want to own
- Choose strikes below support levels
- Target 30-45 DTE for optimal theta
- Set alerts for technical levels

### ❌ Don'ts
- Don't sell without adequate cash
- Avoid during earnings without planning
- Don't ignore assignment risk
- Avoid strikes you'd regret owning

---

## Covered Calls 📈

### Strategy Overview
Sell call options against stock you own to generate income. One of the most popular income strategies for long-term stockholders.

**Market Outlook:** Neutral to Slightly Bullish | Best in range-bound markets

### 📊 Profit/Loss Diagram
```
Profit/Loss
    ^
    |              ████████████████████  Max Profit: $650
$650|             █
    |            █
$150|███████████  Premium Collected
    |
  $0|---------------------------------------------> Stock Price
    |                                   
    |           (Own stock, downside risk)
-$XX|
    +-----|-----|-----|-----|-----|-----|
         $45   $48   $50   $55   $60   $65
                    (Cost)(Strike)
```

### 📋 Key Metrics

| Metric | Value |
|--------|-------|
| Maximum Profit | (Strike - Stock Cost) + Premium |
| Maximum Loss | Stock Price - Premium |
| Breakeven | Stock Cost - Premium |

### 💼 Example Trade
```
Own 100 Shares:  $50.00
Sell Call:       $55 Strike
Premium:         $1.50 ($150)
Max Profit:      $650
New Breakeven:   $48.50
```

### 📊 Return Analysis

| Scenario | Stock Price | Profit | Annualized Return* |
|----------|-------------|--------|-------------------|
| Optimal | $55+ | $650 | ~52% |
| Keep Premium | $50-$55 | $150 | ~12% |
| Breakeven | $48.50 | $0 | 0% |
| Loss | <$48.50 | Negative | Negative |

*Based on 30 DTE

---

## Put Credit Spreads (Bull Put) 🔻

### Strategy Overview
Sell a put at higher strike, buy a put at lower strike. Defined risk bullish strategy that profits when stock stays above the sold strike.

**Market Outlook:** Bullish to Neutral | High IV preferred

### 📊 Profit/Loss Diagram
```
Profit/Loss
    ^
    |         ████████████████████████████  Max Profit: $150
$150|        █
    |       █
    |      █
  $0|-----█----------------------------> Stock Price
    |    █ $46.50 (Breakeven)
    |   █
    |  █
-$150|██                                  Max Loss: $150
    +-----|-----|-----|-----|-----|
         $43   $45   $46.5 $48   $50
              (Buy) (BE) (Sell)
```

### 📋 Position Structure

```
         SELL PUT                BUY PUT
         ↓                       ↓
    $48 Strike (+$2.00)    $45 Strike (-$0.50)
    ═══════════════════════════════════════
    Net Credit: $1.50 ($150)
    Width: $3.00
    Max Loss: $150
    Risk/Reward: 1:1
```

### 💼 Example Trade

| Component | Strike | Premium | Action |
|-----------|--------|---------|--------|
| Short Put | $48 | +$2.00 | SELL |
| Long Put | $45 | -$0.50 | BUY |
| **Net Credit** | | **$1.50** | **$150** |

### 📈 Probability Analysis

| Metric | Value |
|--------|-------|
| Max Profit | $150 (Keep credit) |
| Max Loss | $150 (Width - Credit) |
| Breakeven | $46.50 |
| Win Rate* | ~65-70% |
| Risk/Reward | 1:1 |

*Estimated based on delta

---

## Call Debit Spreads (Bull Call) 🔺

### Strategy Overview
Buy a call at lower strike, sell a call at higher strike. Lower cost bullish alternative to buying calls outright with defined risk.

**Market Outlook:** Moderately Bullish | Defined risk preferred

### 📊 Profit/Loss Diagram
```
Profit/Loss
    ^
    |              ████████████████████  Max Profit: $300
$300|             █
    |            █
    |           █
    |          █
  $0|----█----------------------------------> Stock Price
    |   █ $52 (Breakeven)
    |  █
-$200|██                                    Max Loss: $200
    +-----|-----|-----|-----|-----|
         $48   $50   $52   $55   $58
              (Buy) (BE) (Sell)
```

### 💼 Position Structure

```
         BUY CALL               SELL CALL
         ↓                       ↓
    $50 Strike (-$3.00)    $55 Strike (+$1.00)
    ═══════════════════════════════════════
    Net Debit: $2.00 ($200)
    Width: $5.00
    Max Profit: $300
    Risk/Reward: 1.5:1
```

### 📊 Price Target Analysis

| Stock Price at Exp | P/L | Return |
|-------------------|-----|--------|
| $58+ | +$300 | +150% ✅ |
| $55 | +$300 | +150% ✅ |
| $52 | $0 | 0% |
| $50 | -$200 | -100% ❌ |
| $45 | -$200 | -100% ❌ |

---

## Iron Condor 🦅

### Strategy Overview
Combine bull put spread and bear call spread. Profits from low volatility when stock stays within a range. Popular income strategy.

**Market Outlook:** Neutral | Range-Bound | Low Volatility

### 📊 Profit/Loss Diagram
```
Profit/Loss
    ^
    |     
-$160|██                                  ████  Max Loss
    | █                                  █
    |  █                                █
  $0|---█████████████████████████████---> Stock Price
    |      █                      █
    |       ████████████████████  Max Profit: $140
$140|             ▓▓▓▓▓▓▓
    +-----|-----|-----|-----|-----|-----|
         $42   $43.6 $45   $50   $55  $56.4 $58
              (BE)  (Put) (Call) (BE)
                    Spread  Spread
```

### 📋 Four-Leg Structure

```
PUT SIDE                          CALL SIDE
────────────────────────────────────────────────
Buy Put:  $42  (-$0.30)          Sell Call: $55  (+$1.00)
Sell Put: $45  (+$1.00)          Buy Call:  $58  (-$0.30)
────────────────────────────────────────────────
Put Credit: $0.70                Call Credit: $0.70
────────────────────────────────────────────────
                TOTAL CREDIT: $1.40 ($140)
```

### 💼 Example Trade

| Leg | Action | Strike | Premium |
|-----|--------|--------|---------|
| 1 | BUY | $42 Put | -$0.30 |
| 2 | SELL | $45 Put | +$1.00 |
| 3 | SELL | $55 Call | +$1.00 |
| 4 | BUY | $58 Call | -$0.30 |
| | | **Net:** | **+$1.40** |

### 📈 Profit Zones

| Zone | Stock Range | Outcome | P/L |
|------|-------------|---------|-----|
| 🔴 Loss | <$42 | Put spread ITM | -$160 |
| 🟡 Partial | $42-$43.60 | Partial loss | -$160 to $0 |
| 🟢 Profit | $43.60-$56.40 | Both spreads OTM | +$140 |
| 🟡 Partial | $56.40-$58 | Partial loss | $0 to -$160 |
| 🔴 Loss | >$58 | Call spread ITM | -$160 |

### 🎯 Success Metrics

- **Probability of Profit:** ~60-70%
- **Return on Risk:** 87.5% ($140/$160)
- **Ideal Outcome:** Stock stays $45-$55

---

## Long Straddle 🎪

### Strategy Overview
Buy both a call and put at the same strike. Profits from large moves in either direction. Ideal before major events like earnings.

**Market Outlook:** Large Move Expected | Direction Uncertain

### 📊 Profit/Loss Diagram
```
Profit/Loss
    ^       
    |      █                      █
    |     █                        █
    |    █                          █      Unlimited Upside
    |   █                            █
  $0|--█------------------------------█--> Stock Price
    | █ $44 (BE)              $56 (BE) █
-$600|▼                                ▼   Max Loss
    +-----|-----|-----|-----|-----|-----|
         $40   $44   $50   $56   $60   $64
              (BE) (Strike)(BE)
```

### 💼 Position Structure

```
         ATM CALL              ATM PUT
         ↓                     ↓
    $50 Strike (-$3.00)   $50 Strike (-$3.00)
    ════════════════════════════════════════
    Total Cost: $6.00 ($600)
    Breakevens: $44 and $56
    Need: 12% move either way
```

### 📈 Earnings Example

| Stock Move | Stock Price | P/L | ROI |
|------------|-------------|-----|-----|
| +20% 🚀 | $60 | +$400 | +67% |
| +12% ✅ | $56 | $0 | 0% |
| +5% | $52.50 | -$350 | -58% |
| No move ❌ | $50 | -$600 | -100% |
| -5% | $47.50 | -$350 | -58% |
| -12% ✅ | $44 | $0 | 0% |
| -20% 🚀 | $40 | +$400 | +67% |

### ⚡ Key Considerations

- **Implied Volatility:** Buy when IV is low, before event
- **Time Decay:** Theta works against you (-$30-40/day)
- **Volatility Crush:** IV drop post-earnings can hurt
- **Break-even:** Needs significant move (typically 10-15%)

---

## Long Butterfly Spread 🦋

### Strategy Overview
Buy one lower strike, sell two middle strikes, buy one higher strike. Low-cost strategy that profits from minimal movement.

**Market Outlook:** Neutral | Expect Stock Near Middle Strike

### 📊 Profit/Loss Diagram
```
Profit/Loss
    ^
    |           ╱▔▔▔╲
    |          ╱     ╲
$350|         ╱       ╲           Max Profit at $50
    |        ╱         ╲
    |       ╱           ╲
  $0|------╱-------------╲---------> Stock Price
    |     ╱               ╲
    |    ╱                 ╲
-$150|───╱───────────────────╲───
    +-----|-----|-----|-----|-----|
         $45  $46.5  $50  $53.5  $55
         (Buy) (BE) (Sell)(BE) (Buy)
```

### 📋 Three-Strike Structure

```
LOWER WING        BODY          UPPER WING
    ↓              ↓                ↓
Buy 1 @ $45    Sell 2 @ $50    Buy 1 @ $55
  (-$6.00)      (+$6.00)         (-$1.50)
═══════════════════════════════════════════
         Net Debit: $1.50 ($150)
         Max Profit: $350 (at $50)
         Risk/Reward: 2.33:1
```

### 💼 Example Trade Analysis

| Component | Quantity | Strike | Cost |
|-----------|----------|--------|------|
| Long Call | +1 | $45 | -$6.00 |
| Short Calls | -2 | $50 | +$6.00 |
| Long Call | +1 | $55 | -$1.50 |
| **Net** | | | **-$1.50** |

### 📈 Expiration Outcomes

| Stock Price | P/L | Comments |
|-------------|-----|----------|
| $45 or below | -$150 | Max loss |
| $46.50 | $0 | Lower breakeven |
| $48 | +$200 | In profit zone |
| $50 | +$350 | 🎯 Max profit |
| $52 | +$200 | In profit zone |
| $53.50 | $0 | Upper breakeven |
| $55+ | -$150 | Max loss |

### 🎯 Ideal Conditions

- **Low Volatility:** IV contraction helps
- **Tight Range:** Stock stays near $50
- **Time Decay:** Benefits from theta
- **Precision Play:** Best for experienced traders

---

## Calendar Spread (Time Spread) 📅

### Strategy Overview
Sell near-term option and buy longer-term option at the same strike. Profits from time decay differential and volatility changes.

**Market Outlook:** Neutral Short-Term | Expect Stock Near Strike | IV to Rise

### 📊 Profit/Loss Profile
```
Profit/Loss (At Front Expiration)
    ^
    |        ╱▔▔▔▔▔╲
    |       ╱       ╲        Max profit if stock at $50
$250|      ╱         ╲       and IV increases
    |     ╱           ╲
    |    ╱             ╲
  $0|───╱───────────────╲──────> Stock Price
    |  ╱                 ╲
-$150|─╱───────────────────╲─
    +-----|-----|-----|-----|-----|
         $45   $48   $50   $52   $55
                    (Strike)
```

### 📋 Time Spread Structure

```
FRONT MONTH (Sell)        BACK MONTH (Buy)
        ↓                         ↓
   30 DTE @ $50              60 DTE @ $50
   Sell Call: +$2.00         Buy Call: -$3.50
   ══════════════════════════════════════════
           Net Debit: $1.50 ($150)
         Max Loss: $150 (debit paid)
         Max Profit: $200-$400 (varies)
```

### 💼 Example Trade Timeline

| Event | Action | Time Value | Position Value |
|-------|--------|------------|----------------|
| Entry | Open spread | Front: $2.00<br>Back: $3.50 | -$150 |
| Week 2 | Front decays | Front: $1.20<br>Back: $3.10 | -$10 |
| Week 4 | Front expires | Front: $0.00<br>Back: $2.80 | +$130 |
| Roll | Sell new front | Front: $2.20<br>Back: $2.80 | Repeat |

### 📈 Profit Scenarios

| Scenario | Outcome | P/L Range |
|----------|---------|-----------|
| Stock at $50, IV rises | 🎯 Best case | +$200 to +$400 |
| Stock at $50, IV flat | ✅ Good | +$50 to +$150 |
| Stock moves away | ⚠️ Reduced | -$50 to +$50 |
| Large move + IV drop | ❌ Worst | -$150 (max) |

### 💡 Key Benefits

- ✅ Profits from time decay differential
- ✅ Benefits from rising implied volatility  
- ✅ Can be rolled monthly for income
- ✅ Lower directional risk than spreads
- ✅ Vega positive (long volatility)

### ⚠️ Risks to Watch

- ❌ Large price moves reduce profit
- ❌ IV crush hurts back-month option
- ❌ Requires active management
- ❌ Best when stock stays near strike
- ❌ Complex position to adjust

---

## 🎯 Strategy Selection Flowchart

```
                    What's Your Outlook?
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
    BULLISH           NEUTRAL            BEARISH
        │                  │                  │
        ▼                  ▼                  ▼
  Want to own?      High/Low Vol?      Want defined risk?
        │                  │                  │
    ┌───┴───┐          ┌───┴───┐          ┌───┴───┐
   Yes     No       High    Low        Yes      No
    │       │         │       │          │        │
    ▼       ▼         ▼       ▼          ▼        ▼
Cash-Sec  Bull    Straddle  Iron    Bear Put   Short
  Put    Call      Strangle Condor  Spread    Stock
        Spread              Calendar
                           Butterfly
```

---

## 📊 Risk/Reward Comparison

| Strategy | Max Risk | Max Reward | R:R Ratio | Probability |
|----------|----------|------------|-----------|-------------|
| Cash-Secured Put | High | Limited | 1:5 - 1:10 | 60-70% |
| Covered Call | High | Limited | 1:5 - 1:10 | 60-70% |
| Credit Spreads | Defined | Limited | 1:1 - 1:3 | 60-75% |
| Debit Spreads | Defined | Limited | 1.5:1 - 2:1 | 40-50% |
| Iron Condor | Defined | Limited | 0.5:1 - 1:1 | 60-70% |
| Butterfly | Low | High | 2:1 - 4:1 | 30-40% |
| Calendar | Low | Moderate | 1:1 - 3:1 | 50-60% |
| Straddle/Strangle | High | Unlimited | 1:3+ | 30-40% |

---

## 🔑 Key Metrics Glossary

| Term | Definition | Importance |
|------|------------|------------|
| **DTE** | Days To Expiration | Affects time decay rate |
| **IV** | Implied Volatility | Higher = more expensive options |
| **Delta** | Price sensitivity | How much option moves with stock |
| **Theta** | Time decay | Daily $ loss from time passing |
| **Vega** | Volatility sensitivity | Gain/loss from IV changes |
| **Gamma** | Delta acceleration | How fast delta changes |
| **OTM** | Out of The Money | Strike unfavorable vs stock price |
| **ITM** | In The Money | Strike favorable vs stock price |
| **ATM** | At The Money | Strike = stock price |

---

## ⚠️ Risk Disclaimer

**Options trading involves substantial risk and is not suitable for all investors.** 

- Past performance does not guarantee future results
- You can lose your entire investment
- Understand assignment risk and early exercise
- Know your broker's margin requirements
- Always have an exit plan before entering
- Consider tax implications of options trades
- Start small and scale up with experience

---
*OptiTrade AI - Intelligent Options Trading Made Simple* 🚀
