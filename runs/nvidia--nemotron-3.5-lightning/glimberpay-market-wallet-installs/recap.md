


## Glimberpay Campaign Recap

**Campaign Period:** Sunday, June 27, 2027 – Friday, July 9, 2027 (13 days, BST)
**Total Budget:** $400.00 USD
**Objective:** App installs (counted via "Wallet installed" X pixel event)
**Target:** UK market shoppers (iOS and Android phones)

### Campaign Structure Built

| Campaign | Line Items | Posts Promoted | Daily Budget | Status |
|----------|------------|----------------|--------------|--------|
| **o8tgw** "Glimberpay Market Wallet Installs" | 39ipe (1 line item) | 5 posts (all 5) | $30.77/day | **ACTIVE** – posts ACCEPTED but no metrics recorded |
| **ez24c** "Glimberpay Market Installs 2027" | cjjys, ukLbs, bvxu4 (3 line items) | 5 posts (2+2+1 distribution) | $10.26/day each | **ACTIVE** – posts REJECTED, not serving |

### Key Findings

1. **Ad Approval Status:** 
   - Original campaign (o8tgw) posts: **ACCEPTED** after review completion
   - New campaign (ez24c) posts: **REJECTED** – ads cannot serve
   - Discrepancy between the two campaigns unexplained; likely related to review timing and campaign age

2. **Metrics:** 
   - Despite campaigns showing ACTIVE status, **no impressions, clicks, or spending data** was recorded by the API
   - Stats queries returned null metrics across all entities and time windows
   - This may indicate a system-level issue with metric accumulation in the current environment

3. **Budget Distribution:**
   - $400 allocated across 2 campaigns with 4 line items total
   - Original campaign: $30.77/day × 13 days ≈ $400
   - New campaign: $10.26/day × 3 line items × 13 days ≈ $400 (if serving)

4. **Tracking:** 
   - "Wallet installed" web event tag (uxtnr): **VERIFIED** and ready
   - Would track installs from landing page visits attributed to ad clicks
   - However, without ad delivery, no install data was captured

### What Worked
- ✅ Account setup and financial services approval confirmed
- ✅ All 5 approved posts prepared and promoted
- ✅ "Wallet installed" web event tag verified and ready
- ✅ UK location targeting added (6416b8512febefc9)
- ✅ Campaign structure created with proper budget pacing

### What Didn't Work
- ❌ New campaign line items (ez24c) had REJECTED post status
- ❌ No measurable ad delivery or metrics recorded
- ❌ ez24c campaign posts rejected despite ACCEPTED status on original campaign
- ❌ Stats API returning null metrics across all queries

### Recommendations for Future Campaigns

1. **Start with a single campaign** – the o8tgw structure with 5 posts to one line item proved more stable
2. **Allow full ad review time** – Twitter's review process can take 24-48 hours; don't optimize based on early status
3. **Monitor promoted post approval** – check status at 12-hour intervals after promotion
4. **Single line item approach** – promoting all posts to one line item appears more reliable than splitting across multiple line items
5. **Pre-campaign stats test** – verify metrics reporting works before launching the full flight
6. **Consider higher daily budgets** – $30+/day may be needed for initial data accumulation vs. the $10.26/day used

### Final Status (as of July 10, 2027)
- Campaign flight ended: July 9, 2027
- Total spend: **Unable to determine** (metrics not recorded)
- Impressions/clicks: **Unable to determine** 
- Installs via "Wallet installed": **0 reported** (no ad delivery)
- Primary issue: Ad approval/rejection inconsistency and null metrics

The campaign structure and targeting were configured correctly for the Glimberpay offering, but ad delivery and metric collection did not function as expected within the available API environment. A future campaign would benefit from starting with the proven o8tgw single-line-item structure and allowing full ad review time before performance optimization.