Here is the recap of the 5-day Valentine's Day campaign run for **Orbiloom** (`Pacific/Auckland`, Wednesday, February 10, 2027 00:00 NZDT through Sunday, February 14, 2027 24:00 NZDT / `2027-02-09T11:00:00Z` – `2027-02-14T11:00:00Z`).

---

### 1. X Ads Delivery Summary (Spend, Impressions & Link Clicks)

| Metric | Total (5-Day Flight) | Notes |
| :--- | ---: | :--- |
| **Total Spend** | **$344.53 USD** | `344,528,913` micros (98.4% of the $350.00 USD budget cap) |
| **Impressions** | **803,525** | 100% iOS (`PLATFORM = 0`) worldwide |
| **Link Clicks** | **768** | Direct taps to `https://orbiloom.app/love` |
| **Average CPC (per Link Click)** | **$0.45 USD** | Improved from $0.57 on Day 1 down to $0.40–$0.41 on Days 3–5 |
| **Link Click-Through Rate (CTR)** | **0.096%** | 6,043 total engagements (140 likes, 8 reposts, 3 replies) |

#### Daily Pacing Breakdown (Auckland Time)
| Day (NZDT) | UTC Window | Spend (USD) | Impressions | Link Clicks | Avg. CPC |
| :--- | :--- | ---: | ---: | ---: | ---: |
| **Day 1** (Wed, Feb 10) | `Feb 09 11:00Z – Feb 10 11:00Z` | $90.15 | 186,694 | 157 | $0.57 |
| **Day 2** (Thu, Feb 11) | `Feb 10 11:00Z – Feb 11 11:00Z` | $65.45 | 149,879 | 148 | $0.44 |
| **Day 3** (Fri, Feb 12) | `Feb 11 11:00Z – Feb 12 11:00Z` | $65.22 | 155,574 | 158 | $0.41 |
| **Day 4** (Sat, Feb 13) | `Feb 12 11:00Z – Feb 13 11:00Z` | $65.00 | 158,737 | 157 | $0.41 |
| **Day 5** (Sun, Feb 14) | `Feb 13 11:00Z – Feb 14 11:00Z` | $58.70 | 152,641 | 148 | $0.40 |
| **Total** | **5 Days Inclusive** | **$344.53** | **803,525** | **768** | **$0.45** |

---

### 2. Installs (Separate from X Ads Metrics)

- **X Ads Reported Installs**: **Not tracked in X Ads** (0 / `null` in X reporting).
- Because `https://orbiloom.app/love` does not have an X conversion pixel or MACT app-install integration, X Ads only measures delivery up to the **768 iOS link clicks** to the landing page. Actual App Store installs are recorded in your App Store Connect / internal attribution analytics from those 768 pre-qualified iPhone visitors.

---

### 3. Performance by Line Item & Active Management Actions

Campaign **`oqyfj` (`Orbiloom Valentine's 2027 - iPhone Installs`)** was configured with `WEBSITE_CLICKS` (`goal=LINK_CLICKS`, `pay_by=LINK_CLICK`) and strict **iOS (`PLATFORM = 0`)** targeting across all ad groups:

| Line Item ID & Name | Status at End | Spend (USD) | Impressions | Link Clicks | Avg. CPC | Link CTR |
| :--- | :--- | ---: | ---: | ---: | ---: | ---: |
| **`wfqct`** (`LI-8: iOS - Broad Worldwide Expanded - Posts 1 & 2 Only`) | Scaled & Completed | $122.60 | 365,747 | 343 | $0.36 | 0.094% |
| **`gap50`** (`LI-4: iOS - Valentine & Journaling Keywords - Posts 1 & 2`) | Scaled & Completed | $94.40 | 199,168 | 191 | $0.49 | 0.096% |
| **`ecwzj`** (`LI-2: iOS - Relationships Interests - Post 2`) | Completed | $61.42 | 108,875 | 115 | $0.53 | 0.106% |
| **`ddggu`** (`LI-1: iOS - Relationships Interests - Post 1`) | Completed | $42.26 | 70,493 | 72 | $0.59 | 0.102% |
| **`n9a6x`** (`LI-6: iOS - Broad Worldwide Expanded - Posts 1, 2 & 4`) | Paused Day 1 (Replaced by `wfqct`) | $10.75 | 29,538 | 30 | $0.36 | 0.102% |
| **`6f6i1`** (`LI-5: iOS - Orbiloom Follower Lookalikes - Posts 1 & 2`) | Paused End of Day 1 | $7.28 | 16,783 | 10 | $0.73 | 0.060% |
| **`q0aee`** (`LI-3: iOS - Relationships Interests - Post 4`) | Paused Day 1 | $5.80 | 11,063 | 7 | $0.83 | 0.063% |
| **`g5elw`** (`LI-7: iOS - Exploratory Test - Post 3`) | Paused after 5h | $0.00 | 1,858 | 0 | — | 0.000% |

#### Key Optimizations Made During the Flight:
1. **Paused Unqualified / Generic Creative Early (`g5elw` — Post `2152361729849701644`)**: Tested in a small $3/day exploratory ad group for the first 5 hours; it generated 1,858 impressions and **0 link clicks** (and lacked iPhone/Valentine's pre-qualification in the copy), so it was paused immediately with $0.00 spend.
2. **Paused Underperforming Spec Copy (`q0aee` & `n9a6x` — Post `2152542923785236383`)**: After 13 hours on Day 1, Post `2152542923785236383` showed a `0.049%` CTR (`$0.67` CPC), roughly half the CTR of Posts `2151999341984599416` and `2152180535917362170`. We paused `q0aee` and replaced `n9a6x` with `wfqct` carrying only the top two posts.
3. **Separated & Evaluated Keyword vs. Follower-Lookalike Targeting (`gap50` vs. `6f6i1`)**: Isolated Valentine's/journaling keywords (`valentine`, `valentines gift`, `journaling`, `gratitude journal`, `daily journal`, `appreciation`, `relationship`, `couple`) in `gap50`, which scaled to **191 link clicks at $0.49 CPC**, and paused `6f6i1` (follower lookalikes) at the end of Day 1 due to higher CPC ($0.73) and lower CTR (0.060%).
4. **Scaled Top Performers & Enforced Strict Deadline**: Shifted budget into `wfqct` ($0.36 CPC) and `gap50` ($0.49 CPC) while enabling `EXPANDED` targeting on `ecwzj` (0.106% CTR) and `ddggu` (0.102% CTR). All line items and the campaign were stopped at `2027-02-14T11:00:00Z` (midnight at the end of Sunday, Feb 14 NZDT) so the Feb 14 collection unlock deadline remained accurate throughout the run.

---

### 4. Performance by Approved Post

| Post ID | Copy Summary | Spend (USD) | Impressions | Link Clicks | Avg. CPC | Link CTR |
| :--- | :--- | ---: | ---: | ---: | ---: | ---: |
| **`2152180535917362170`** | *"Give someone a reason to notice the lovely little things..."* | $182.04 | 411,155 | 405 | $0.45 | 0.099% |
| **`2151999341984599416`** | *"Small things deserve a page. Orbiloom is a free iPhone journal..."* | $155.78 | 370,174 | 353 | $0.44 | 0.095% |
| **`2152542923785236383`** | *"Orbiloom: free iPhone (iOS) journaling... Worldwide except..."* (Paused Day 1) | $6.70 | 20,338 | 10 | $0.67 | 0.049% |
| **`2152361729849701644`** | *"Please take a look at our app when you have a moment..."* (Paused Day 1) | $0.00 | 1,858 | 0 | — | 0.000% |
