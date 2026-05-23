# Moat & Main — How the Numbers Work

This calculator compares **renting and investing** vs **buying and building equity** over time. Adjust the sliders to model your situation, then compare wealth at any year from 1 to 30.

All numbers can be shown in **nominal** (actual dollars) or **real** (inflation-adjusted) terms.

---

## Key terms (plain English)

**Unrecoverable costs** — Money you never get back. For owners: mortgage **interest**, property tax, insurance, maintenance, PMI, and HOA. For renters: rent. Mortgage **principal** is not unrecoverable — it builds equity.

**Owner premium** — If owning costs $2,500/month (unrecoverable) and rent is $2,000/month, the premium is $500. That $500 is what the renter can invest each month.

**Extra rent** — If rent exceeds the owner's unrecoverable costs, the renter pays more monthly. The calculator subtracts that difference from the renter's investment portfolio.

**Transaction frictions** — One-time costs: closing costs when you buy, real estate commission when you sell. The renter keeps the buyer's upfront cash (down payment + closing costs) and invests it. The owner pays closing costs, which reduces starting net wealth.

**Break-even year** — The first year when the owner's net equity (nominal) exceeds the renter's investment portfolio (nominal). We interpolate between yearly snapshots for a precise estimate.

**Nominal** — Numbers with inflation included (what you see in your account).

**Real** — Numbers divided by `(1 + inflation)^years` to show today's purchasing power.

---

## What the calculator does step by step

### 1. Monthly unrecoverable cost of owning

We add up:

- Mortgage **interest** (remaining loan balance × rate ÷ 12)
- Property tax (home price × tax rate ÷ 12)
- Insurance (annual ÷ 12)
- Maintenance (home price × maintenance % ÷ 12, reduced by your DIY percentage)
- **PMI** (when down payment is below 20% and loan-to-value is above 78%)
- **HOA fees** (monthly dollar amount)

Then we subtract:

- Your **lifestyle benefit** (optional emotional value you assign to owning)
- **Tax savings** (if enabled): `(interest + property tax) × marginal tax rate`

We do **not** include mortgage principal here — principal builds equity on the owner side.

### 2. Monthly cash flow between renter and owner

```
cash flow difference = owner unrecoverable cost − monthly rent
```

- If **positive**: the renter invests that amount each month (in addition to the upfront lump sum).
- If **negative**: rent is higher than owning's unrecoverable cost — the renter withdraws that amount from their portfolio each month.
- Portfolio cannot go below $0.

### 3. Renter's starting investment

**Lump sum** = down payment + buyer closing costs (cash the renter keeps instead of buying).

Both the lump sum and any monthly surplus are compounded at your chosen annual return (default 9% for SPY), applied monthly.

### 4. Owner's net equity

At any year *N*:

```
home value     = purchase price × (1 + appreciation)^N
net equity     = home value − remaining mortgage − selling commission (optional)
```

At year 0, net equity = down payment − closing costs (before any appreciation or selling).

Mortgage amortization uses standard fixed-rate P&I over 15 or 30 years.

### 5. Growth rates

- **Rent** grows at your **rent growth %** each year (separate from general inflation).
- **Insurance and HOA** grow at the general **inflation %** each year.
- **Home value** grows at your **appreciation %** each year.

### 6. PMI

When your down payment is below 20%, PMI is charged as a % of the remaining loan balance per year (default 0.5%). PMI drops to $0 once loan-to-value reaches 78%.

### 7. Tax deduction (optional)

**Marginal tax rate** is your top tax bracket — the rate you pay on your last dollar of income (e.g. 22% federal, or combined federal + state).

When the deduction checkbox is enabled:

```
monthly tax savings = (mortgage interest + property tax) × marginal tax rate
```

This reduces owner unrecoverable costs each month. Example: $1,500/mo interest + $400/mo tax at 22% → **$418/mo** in estimated savings.

We do not model the standard deduction, SALT caps, or AMT — use this as a rough sensitivity toggle.

### 8. Monthly cost snapshot by year

The **Monthly costs** panel uses the same comparison year as the wealth results — one slider controls both. Values reflect that year's home value, loan balance, rent after growth, and whether PMI still applies.

Hover the **i** icons for a plain-English explanation of each line.

### 9. Break-even (nominal)

We compare **owner net equity** vs **renter portfolio** at each year-end snapshot. Break-even is when owner net equity first exceeds the renter portfolio, with linear interpolation between years.

Toggle **Include selling commission** to see equity after a hypothetical sale (commission deducted from home value).

### 10. Shareable links

Every slider change updates the URL query string. Use **Copy share link** to send your exact scenario to someone else — they'll land on the same inputs when they open the link.

---

## Example with default numbers (National Median)

- Home price: $430,000, down 20% → loan $344,000
- Closing costs: 3% → $12,900
- Monthly owner unrecoverable cost (Year 1): ~$2,100 (interest + tax + insurance + maintenance − lifestyle)
- Monthly rent: $2,300
- Renter pays **extra** ~$200/month vs owning's unrecoverable costs (withdrawn from portfolio)
- Renter lump sum invested: $98,900 (down payment + closing costs)
- SPY return: 9% nominal, inflation: 2.5%, rent growth: 2.5%, home appreciation: 3%

Results depend on your full set of inputs — use the live calculator to explore scenarios.

> The renter's portfolio is liquid cash. The owner's net equity is tied to the house. Choose based on your life stage, mobility needs, and risk tolerance.

---

## What we still simplify

This model does **not** include:

- Capital gains tax on home sale or investments
- Standard deduction vs itemizing tradeoffs
- SALT deduction caps
- FHA vs conventional PMI differences beyond a single rate slider
- Refinancing or moving before the comparison horizon

---

## Disclaimer

All numbers are estimates for educational purposes. This is not financial, tax, or legal advice. Consult qualified professionals before making housing decisions.
