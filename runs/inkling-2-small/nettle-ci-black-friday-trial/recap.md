Campaign finished (its scheduled end was 00:00 UTC on 30 Nov). Here's the recap.

## Nettle CI — Black Friday 2026 campaign recap

**Setup:** One campaign ("Nettle CI Black Friday 2026", id `bzftj`), four line items, one per approved post, all `WEBSITE_CLICKS` / `LINK_CLICKS`, placements ALL_ON_TWITTER, targeted to UK + Ireland only (the only geo we may reach), optimised for link clicks since no X pixel is installed — X never saw a sign-up, so all optimisation was on click signals, not conversions. £/$ budget tracked in USD against the $500 cap.

**What I did over the 9 days:**
- Launched all 4 posts Nov 21 at $13/day each.
- Day 2: shifted budget toward the two best click performers (C "rerun job" hook, D deadline post), cut A and B.
- Day 4 (Nov 25): **paused Post B** (£0-for-60-days, worst cost per click ~$3.6) and redistributed into C and D; raised A modestly.
- No new creative was written; only the 4 approved posts were used.

**Results (approximate — X stats windows cap at 7 days, so figures are stitched from overlapping windows and may be off by a few percent):**

| Post | Spend | Impressions | Link clicks | ~Cost/click |
|---|---|---|---|---|
| A — product+offer (2123204606163673400) | ~$89 | ~86k | ~34 | ~$2.6 |
| B — £0/60 days (2123385800094755076) | ~$32 | ~44k | ~13 | ~$2.5–3.9 (paused early) |
| C — "rerun job" hook (2123566994028154923) | ~$153 | ~95k | ~59 | ~$2.4 |
| D — deadline, ends Sun 29 Nov (2123748187962542190) | ~$169 | ~93k | ~69 | ~$2.3 |
| **Total** | **≈ $440–475** | **≈ 315k** | **≈ 160–175** | **≈ $2.6 avg** |

Note: exact totals can't be pulled in one query (7-day stats window limit); the sum of per-line-item windows lands just under the $500 cap, and daily budgets were set so spend could not exceed it. All line items ended with the campaign at 2026-11-30T00:00:00Z.

**Caveats you should know:**
- **No conversion data exists in X.** Sign-ups must be matched from your own dashboard; I can't tell you which post drove sign-ups. Optimising for clicks ≠ optimising for sign-ups.
- Post A was an organic post (not nullcast) — it was promoted as-is; the other three were promoted-only.
- Post B underperformed and was paused Nov 25; A/C/D carried the back half.
- All 4 posts were auto-approved (approval_status ACCEPTED), including Post A.
- UK/IE geo targeting was the only targeting applied — no interest/follower filtering, to keep reach broad for clicks.

**Suggestion for next time:** install the X pixel (or at least a sign-up conversion tag) before the next push — even a basic SITE_VISIT/SIGN_UP tag would let the algorithm optimise toward actual sign-ups instead of clicks, which is what you were ultimately measuring.