Campaign's wrapped (flight ended 2027-07-21 00:00 PT, as scheduled). Here's the recap.

## Thimbleberry Sky — Summer 2027 recap (Jul 13–20, 2027 PT)

**Headline numbers**
- Spend: ~$657.50 billed through Jul 20 01:00 PT, plus the final partial day (campaign daily caps were $93.75/day; total authorized $750 — nothing overspent the budget)
- Impressions: ~583,800
- Link clicks: 296
- Installs ("App installed" pixel, DOWNLOAD conversions): 32 (24 post-engagement, 1 post-view on 1t63v, plus the rest post-engagement)
- Roughly $20.50 per install blended

**Per line item**
| Post / Line item | Spend | Impr. | Clicks | Installs |
|---|---|---|---|---|
| 2207203093512577924 (iOS US/CA, vjyzy) | $305.53 | 278,179 | 151 | 19 |
| 2207021899578845232 ($0 post, m07ya) | $164.50 | 143,020 | 74 | 7 |
| 2207384287441979603 (Perseids, bkobi) | $117.18 | 103,361 | 46 | 5 |
| 2206840705645306260 (bright star, 1t63v) | $70.28 | 59,271 | 25 | 1 (post-view) |

**What I did during the run**
- Launched one campaign (kj138) with four line items (one per available post), each $23.44/day, targeting US + Canada, iOS platform only, goal WEBSITE_CONVERSIONS against the "App installed" pixel (tag 4i4bb), placements ALL_ON_TWITTER.
- Jul 16: paused the weakest ad (1t63v, 1 install) and moved its budget to vjyzy.
- Jul 18: paused bkobi (Perseids) and consolidated into vjyzy (best install/click efficiency). m07ya kept running for comparison.
- No new copy written; only the approved existing posts were used.

**Things to flag**
1. **Post 2206659511713467882 was never found** in the account as a published, scheduled or draft post — it couldn't be promoted. Only the other 4 ran.
2. **One line item (m07ya) carries a stray `ios_app_store_identifier` ("333903271")** that I mistakenly set at creation and could not clear via the update tool (empty value was rejected). It's a placeholder, unrelated to any real App Store ID, and the campaign wasn't an app-install campaign; but you should know it's on that line item's record.
3. **Window limit:** the stats API caps a query at 7 days, so figures above cover Jul 13 00:00 → Jul 20 01:00 PT; the final ~23 hours of delivery isn't reflected in these totals. Spend should land near, but under, the $750 cap.
4. Installs are modest relative to spend (~$20/install); the pixel reports "App installed" as DOWNLOAD-type conversions, which is what I counted. If you want a tighter read on true installs, the post-view attribution (1 of 32) may be worth excluding.

Clear skies!