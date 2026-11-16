# TAB Mortgage Calculator

> **Internal only.** This calculator uses TAB's internal Mortgage Rate Card. Keep this repository private and do not publish it with GitHub Pages or share it outside TAB.

A single-page calculator for indicative TAB Mortgage quotes on buy-to-let, commercial and mixed-use term loans. It shows the standard **Mortgage** and **Mortgage Pro** side by side.

## Using it

Open `index.html` in any modern browser. There is no build step, and nothing to install.

- **Property:** buy-to-let, commercial or mixed use. Mixed use is priced on the buy-to-let or commercial grid, depending on which has the larger floor area.
- **Inputs:** property type, location, value, monthly rent, term (3, 4 or 5 years) and number of properties.
- **Rate loadings:** Core Flex adjustments from the rate card. They add up, and the total is capped at +3.00%. Specialist property types set their Tier 1 or Tier 2 loading automatically, and it is counted once.
- **ESG discounts:** each one reduces the exit fee.

## How it calculates

- **Pay rate** = LTV band margin + Core Flex loading + Bank of England base rate.
- **Maximum loan:** the highest loan, in £1,000 steps from maximum LTV, that passes the rent test. Rent must cover interest at the stress rate by the required ICR.
  - **Mortgage:** stress rate = pay rate + 1%.
  - **Mortgage Pro:** stress rate = pay rate − 2% prepaid interest + 1%.
- **Net advance** = gross loan − arrangement, admin and valuation fees, and Pro's prepaid interest.
- Payments are interest only.

## Settings

The **Settings** button lets you change every rate, loading, fee and limit. Changes are saved in that browser only, and **Reset to rate card** restores the defaults.

To change the defaults for everyone, edit the `CONFIG` object near the top of the `<script>` in `index.html`.

## Sources and assumptions

| What | Source |
|---|---|
| Margins, Core Flex loadings, specialist tiers, 65% specialist LTV cap, £2.5m Pricing Committee referral | TAB internal Mortgage Rate Card |
| Base rate 4.00% | Bank of England, decision of 5 November 2026 |
| ICR 1.25× at pay rate + 1%, 2% arrangement and exit fees, admin and valuation fees, Mortgage Pro 2% prepaid interest, £4m credit referral | Carried over from the earlier TAB loan calculator. **Not on the rate card — confirm before relying on them.** |

## Disclaimer

Illustrative only. This is not a mortgage offer, an agreement in principle or financial advice. Every case is subject to valuation, underwriting and credit approval. Rates track base rate, so payments can go up as well as down. TAB loans are unregulated, and any property used as security is at risk of repossession if payments are not kept up.
