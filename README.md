# cross margin vs isolated margin: How to Choose the Right Risk Model for Crypto Margin Trading

When comparing **cross margin vs isolated margin**, the real question is not which mode can produce higher returns. Both modes use leverage, and leverage magnifies losses as quickly as it magnifies gains.

The practical question is simpler:

> Do you want one position to use shared account collateral, or do you want to cap the margin assigned to that position?

On OKX, **cross margin** can use available margin across eligible positions, which may keep a trade open longer. **Isolated margin** separates the margin assigned to one position, so a liquidation generally does not consume unrelated funds in the account. The trade-off is straightforward: cross margin gives the position more room, while isolated margin gives you a clearer maximum loss boundary.

This guide explains the difference, liquidation mechanics, fees, common mistakes, and how to decide which mode better fits a specific trading setup on OKX.

## Cross Margin vs Isolated Margin: The Short Answer

| Comparison | Cross margin | Isolated margin |
| --- | --- | --- |
| Collateral | Shared across eligible positions or the relevant margin account | Assigned to a specific position |
| Liquidation buffer | Usually larger because more available balance may support the position | Usually smaller because only allocated margin supports the position |
| Loss containment | Weaker; losses may affect other funds or positions | Stronger; unrelated account funds are generally not used to cover that position |
| Position management | Convenient for several related positions | Easier to budget and monitor per trade |
| Main danger | One losing position can consume funds intended for other trades | The position can be liquidated sooner |
| Best suited to | Hedged portfolios, active traders, and strategies that intentionally share collateral | Defined-risk trades, experiments, and traders who want strict position-level limits |

The important word in the cross-margin column is **eligible**. Cross margin does not always mean every asset in every part of your account is automatically available. The result depends on account mode, collateral settings, instrument, margin currency, and regional product rules.

On OKX, the trading interface lets you select the margin mode before placing an order. The option appears next to the leverage control in supported products.

## What Is Cross Margin?

With cross margin, the platform uses a shared pool of available margin to support one or more positions. If one trade has an unrealized loss, other available collateral may help keep it open. Profitable positions can also contribute to overall account equity, depending on the account mode and product.

That shared structure creates two opposite effects:

- A position may have more room before liquidation.
- The loss from that position may spread beyond the margin initially associated with it.

OKX describes cross margin as a mode in which the entire margin balance is shared among open positions. Its calculation rules also distinguish between different account and position configurations, including one-way mode, hedge mode, multi-currency margin, and different contract types.

### A simplified cross-margin example

Assume a trader has:

- $1,000 in available margin
- A $2,000 leveraged position
- No other positions
- No trading fees, funding fees, or maintenance-margin changes in the example

If the position loses $100, the remaining account equity is approximately $900 before other adjustments. The position is not limited to a separate $100 or $200 “position wallet”; the broader available balance helps support it.

That can be useful when the trade is part of a planned portfolio. It can also be uncomfortable when the trade was supposed to risk only a small portion of the account.

Cross margin is therefore less about “lower risk” and more about **shared risk management**. A lower probability of immediate liquidation does not mean a lower maximum loss. If account equity keeps falling, more of the shared balance can eventually be consumed.

## What Is Isolated Margin?

With isolated margin, the margin assigned to a position is separated from the rest of the account. If that position is liquidated, funds outside the isolated position are generally not used to cover its loss. OKX states that only the margin allocated to that position is at risk in isolated mode.

This makes isolated margin useful when the trader wants to answer a specific question before opening a position:

> How much money am I willing to put at risk on this trade?

The answer is not always identical to the exact liquidation loss. Trading fees, funding fees, maintenance margin, market movement, and platform mechanics can affect the final result. Still, isolated mode gives the trader a much clearer boundary than cross mode.

### A simplified isolated-margin example

Assume:

- $1,000 in the account
- $100 assigned to an isolated position
- $900 left outside that position

If the isolated position is liquidated, the loss is generally confined to the margin allocated to that position, subject to fees and the product’s liquidation rules. The remaining $900 is not automatically pulled in to rescue the trade.

This is why isolated margin is often easier to use for:

- A single directional trade
- A new strategy
- A high-volatility token
- A small experimental position
- A trade with a predefined maximum allocation
- Separating one strategy from the rest of a portfolio

The drawback is that the liquidation price may be closer. A position with a small isolated margin buffer has less room to absorb an adverse move.

## The Main Difference: Liquidation Exposure

Liquidation is where the difference between cross and isolated margin becomes financially meaningful.

In isolated mode, the system assesses the position using the margin attached to that position. If the position’s margin balance falls below the required maintenance level, the position can be partially or fully liquidated according to the relevant rules.

In cross mode, the system evaluates the wider shared margin balance. This may allow the position to survive a price move that would liquidate an isolated position with the same notional size. However, the survival comes from using more available collateral, not from removing the loss.

OKX’s published rules state that cross-margin calculations can use account-level adjusted equity, while isolated calculations use the margin balance and profit or loss of the isolated position.

A useful way to remember it:

- **Isolated margin moves liquidation closer but limits the pool at risk.**
- **Cross margin may move liquidation farther away but exposes more account equity.**

Neither statement guarantees a specific liquidation price. The actual number depends on leverage, position size, mark price, maintenance-margin tier, fees, liabilities, collateral discounts, and other platform rules.

## Which Mode Is Safer?

For most traders, isolated margin is easier to control because the position-level risk is visible. That does not make it automatically safe. High leverage can still liquidate an isolated position quickly.

Cross margin may reduce the chance of liquidation for a particular position because more collateral can support it. But that benefit can create a larger account-level loss if the market continues moving against the position. OKX specifically warns that losses from one cross-margin position may affect other funds in the account.

A practical distinction:

### Choose isolated margin when:

- You want a fixed budget for each trade.
- You are testing a new asset or strategy.
- You are trading a highly volatile market.
- You do not want one position to consume funds reserved for other positions.
- You are still learning how liquidation prices move.
- You prefer to add margin manually rather than share the whole account.

### Consider cross margin when:

- You intentionally manage several positions as one portfolio.
- You are running a hedge where positions offset each other.
- You understand how shared collateral changes liquidation risk.
- You actively monitor account equity and maintenance margin.
- You have a clear rule for the maximum account-level loss.
- You need capital efficiency across related positions.

The last point matters. Cross margin should be a deliberate portfolio tool, not simply the default button left unchanged on the order panel.

## Cross Margin vs Isolated Margin for Hedging

Cross margin can make sense when positions are designed to offset each other. For example, a trader may hold a long position in one instrument and a short position in a correlated instrument. If the positions are part of one risk model, shared collateral may be useful.

But correlation is not a guarantee. Two assets that usually move together can diverge sharply during market stress. A hedge can weaken, fail, or introduce a different source of risk.

Isolated margin provides cleaner separation between the two positions. That can be useful when the trader wants to prevent a loss in one leg from automatically supporting or damaging the other.

The choice depends on whether the positions are managed as:

- **One combined portfolio risk**, which may support cross margin; or
- **Separate trade ideas**, which usually favors isolated margin.

Do not assume that two positions are hedged merely because one is long and the other is short. The contract size, asset, leverage, funding rate, basis, and liquidation mechanics all matter.

## Margin Mode Does Not Remove Borrowing Costs

Margin mode is only one part of the cost structure.

For spot and margin trading, borrowed funds can create liabilities and interest charges. OKX explains that margin trading involves borrowing assets from the market loan pool, and the amount available depends on user level, the asset’s position tier, and pool limits.

For derivatives, traders also need to account for:

- Trading fees
- Funding fees on perpetual contracts
- Liquidation fees
- Slippage
- Spread
- Interest or borrowing costs where applicable

A position can be directionally correct and still perform worse than expected after fees. OKX states that futures trading fees are calculated on the position size, not merely on the margin deposited. A $20,000 position opened with $2,000 margin is charged based on the $20,000 position value under the applicable fee formula.

This is especially important when using high leverage. Leverage reduces the margin required for a given position, but it does not reduce the notional size used to calculate many trading costs.

## Current OKX Fee Tiers to Check Before Trading

OKX’s published U.S. fee framework lists one Regular tier and nine VIP tiers. The exact rate available to an account can depend on region, product, trading pair group, asset balance, and 30-day trading volume. OKX also directs users to check the fee rate shown in their logged-in account and order panel because displayed rates may differ by account.

The table below reproduces the current publicly listed U.S. framework that was available for verification. It is a fee-tier comparison, not a list of margin products. The **Group 1, Group 2, and Group 3** columns refer to OKX’s published spot-market fee groups.

| OKX tier | Qualification by assets or 30-day volume | Group 1 maker / taker | Group 2 maker / taker | Group 3 maker / taker | Access |
| --- | ---: | ---: | ---: | ---: | --- |
| Regular | $0–$100,000 | 0.200% / 0.350% | 0.200% / 0.350% | 0.200% / 0.350% | [ Open OKX with the invitation route](https://okx.com/join/CASH20) |
| VIP 1 | $100,001–$250,000 | 0.100% / 0.200% | 0.100% / 0.200% | 0.100% / 0.200% | [ View the OKX trading account](https://okx.com/join/CASH20) |
| VIP 2 | $250,001–$500,000 | 0.075% / 0.150% | 0.075% / 0.150% | 0.075% / 0.150% | [ Check OKX eligibility](https://okx.com/join/CASH20) |
| VIP 3 | $500,001–$1,000,000 | 0.060% / 0.125% | 0.060% / 0.125% | 0.060% / 0.125% | [ Start with OKX](https://okx.com/join/CASH20) |
| VIP 4 | $1,000,001–$2,500,000 | 0.050% / 0.100% | 0.050% / 0.100% | 0.050% / 0.100% | [ Review the OKX fee tier](https://okx.com/join/CASH20) |
| VIP 5 | $2,500,001–$5,000,000 | 0.045% / 0.080% | 0.045% / 0.080% | 0.045% / 0.080% | [ Access OKX trading](https://okx.com/join/CASH20) |
| VIP 6 | $5,000,001–$10,000,000 | 0.040% / 0.070% | 0.040% / 0.070% | 0.040% / 0.070% | [ Check the available OKX rates](https://okx.com/join/CASH20) |
| VIP 7 | No asset requirement shown; $50,000,001–$75,000,000 volume | -0.0020% / 0.0250% | -0.0050% / 0.0350% | -0.0100% / 0.0400% | [ Open the OKX VIP route](https://okx.com/join/CASH20) |
| VIP 8 | No asset requirement shown; $75,000,001–$125,000,000 volume | -0.0050% / 0.0200% | -0.0100% / 0.0300% | -0.0150% / 0.0350% | [ Check OKX VIP access](https://okx.com/join/CASH20) |
| VIP 9 | No asset requirement shown; $125,000,001+ volume | -0.0075% / 0.0175% | -0.0100% / 0.0250% | -0.0200% / 0.0300% | [ Enter OKX through the invitation link](https://okx.com/join/CASH20) |

OKX notes that fee groups and rates may be reviewed periodically. The rate visible in the order placement panel is the useful number to check before submitting an order.

For the supplied invitation link, the code is **CASH20**, advertised with a **20% commission rebate**. Check the terms shown during registration because referral benefits, regional availability, and eligibility can change.

## How to Choose Between Cross and Isolated Margin on OKX

Before opening a position, use this sequence:

1. **Define the maximum amount you are willing to lose.**
   If the answer is a fixed dollar amount for one position, isolated margin is usually easier to structure.

2. **Decide whether the position belongs to a portfolio or stands alone.**
   A portfolio hedge may justify shared collateral. A standalone directional trade may not.

3. **Check the notional value, not only the margin.**
   Trading fees and price exposure are based on the position size. A small margin deposit can control a much larger position.

4. **Review the estimated liquidation price.**
   Treat it as a risk indicator, not a stop-loss. A liquidation event is controlled by the platform’s risk engine and may execute differently from a manually placed exit.

5. **Account for funding, interest, and fees.**
   A position that stays open for a long time can accumulate costs even if the price has not moved dramatically.

6. **Confirm the mode immediately before placing the order.**
   OKX lets users choose between isolated and cross modes in the trading interface for supported products. A quick check can prevent a position from being opened under the wrong risk model.

## Common Mistakes

### Treating cross margin as a stop-loss

Cross margin can provide a larger liquidation buffer, but it does not limit the loss to the original margin. If the position continues losing, shared collateral can be consumed.

### Assuming isolated margin guarantees the exact planned loss

Isolated margin limits the position’s assigned collateral, but fees, funding, price gaps, and liquidation execution can affect the final result. A stop-loss and isolated margin serve different purposes.

### Comparing leverage instead of position size

Two traders can use the same leverage but have very different risk because their position sizes and account balances differ. Start with the dollar value of the position and the amount allocated as margin.

### Ignoring the mark price

Liquidation systems generally rely on risk calculations and mark-price mechanics rather than simply the last traded price. OKX’s liquidation and maintenance-margin rules are product-specific, so the liquidation estimate should be reviewed before entry.

### Leaving cross mode enabled by habit

Cross margin can be appropriate for a planned strategy. It is a poor default when the trader has not decided how much of the account may be exposed.

## Final Verdict

For most users comparing **cross margin vs isolated margin**, isolated margin is the easier starting point because it separates one position’s collateral from the rest of the account. It is especially useful when the trade has a clearly defined allocation or when the asset is volatile.

Cross margin is more suitable when positions are intentionally managed together and the trader understands that a larger liquidation buffer can come from exposing more account equity. It can improve capital efficiency, but it also makes risk less compartmentalized.

A practical rule is:

> Use isolated margin when your priority is controlling the maximum collateral assigned to one trade. Use cross margin only when shared collateral is part of a deliberate portfolio plan.

Before trading on OKX, confirm the available product in your region, the selected margin mode, the current fee shown in the order panel, the estimated liquidation price, and any borrowing or funding costs. [👉 Check the current OKX trading setup with the invitation code](https://okx.com/join/CASH20)
