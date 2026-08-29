# Florida Amendment 3 Property Tax Estimator

A single-page, self-contained calculator that shows Florida homeowners how the proposed
Amendment 3 homestead exemption increase could affect their property tax bill, comparing
2026 (current law) against 2027 and 2028 (if the amendment passes).

**Live page:** https://yourusername.github.io/amendment3-calculator/
*(update this link once GitHub Pages is enabled)*

Built and maintained by [Randy West](https://tampabayrealestate.pro), Realtor® with
Keller Williams Realty New Tampa, for clients in Hillsborough, Pinellas, Pasco, and
Hernando counties.

## What it does

Users enter three numbers pulled from their TRIM ("Truth in Millage") notice:

- Assessed value (from the Property Appraiser Value Information table)
- School millage rate (School-State + School-Local rows added together)
- Non-school millage rate (every other taxing authority row added together)

The calculator then estimates the total tax bill under three scenarios:

| Year | Non-school exemption | Notes |
|---|---|---|
| 2026 | $25,000 + up to $26,411 | Current law. Second exemption applies to assessed value between $50,000–$75,000, capped at the CPI-adjusted amount. |
| 2027 | $150,000 | Only if Amendment 3 passes with 60%+ voter approval on Nov 3, 2026. |
| 2028 | $250,000 | Same condition. |

The $25,000 school exemption never changes under the amendment — only the non-school
portion of the bill is affected. There's also a toggle for people establishing a new
Florida homestead in 2027 or later, who get a 5-year phase-in instead of the full
exemption immediately.

Assessed value is held constant across all three years so the comparison isolates the
amendment's effect, rather than mixing in normal Save Our Homes appreciation.

## Annual maintenance

A few things need a fresh look each year, ideally right after TRIM notices go out
in August:

- **The $26,411 additional homestead exemption cap** (hardcoded in the JavaScript,
  search for `26411`) is CPI-adjusted annually. Confirm the current figure against
  a real TRIM notice or the county property appraiser's site before reusing this
  page next season.
- **The $150,000 / $250,000 non-school exemption schedule** only applies if Amendment 3
  passes in November 2026. If it fails, this entire tool needs to be pulled down or
  rewritten — it currently assumes the amendment succeeds in the 2027/2028 columns.
- **Starting in 2029**, the non-school exemption is supposed to adjust with CPI. That
  logic isn't built yet since the 2029 figure isn't set. Add it once it's published.
- **Default field values** (assessed value, school/non-school millage) are illustrative
  examples based on a real Hillsborough County notice, not live data. No action needed
  unless you want to refresh them.

## Not tax advice

This tool produces educational estimates only, not a tax bill or professional advice.
It's built for general awareness, not for any individual's exact figures. That
disclaimer is also shown directly on the page itself.

## Tech notes

Plain HTML/CSS/JavaScript, no build step, no external dependencies or font requests —
this keeps it reliable when embedded via iframe on the BoldTrail/kvCore site, since
BoldTrail's custom HTML blocks sandbox inline JavaScript.
