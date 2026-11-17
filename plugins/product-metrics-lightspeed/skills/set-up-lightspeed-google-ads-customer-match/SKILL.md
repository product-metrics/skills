---
name: set-up-lightspeed-google-ads-customer-match
description: >-
  Google Ads Customer Match lists for Lightspeed. Use this skill when a Lightspeed merchant wants
  audiences built from their customers: excluding existing customers from new customer campaigns,
  winning back lapsed customers, or telling Performance Max who their best customers are. It creates
  six Customer Match lists, from first-time buyers to lapsed and high-value customers, and updates
  them after every paid order. It works through Product Metrics, so use it even when Product Metrics
  is never mentioned. Not for conversion tracking or bidding: each has its own skill, as do other
  store platforms and ad channels.
license: MIT
metadata:
  author: Product Metrics
  version: "1.2.0"
  docs: https://www.productmetrics.io/docs/tracking/customer-lists/lightspeed-google-ads
---

# Lightspeed Customer Match lists in Google Ads

Create six Customer Match lists in Google Ads and keep them filled from Lightspeed, from first-time buyers to lapsed customers. Lists that update after every order matter because Google Ads' new customer settings and exclusions are only as good as its list of who already bought.

You run the Product Metrics steps through its CLI or MCP server; the person does the steps in Lightspeed and Google Ads. Read `references/working-with-product-metrics.md` once for how to work with both.

**All conversion actions by agents are secondary**, the status Product Metrics creates its actions with. Choosing what a campaign bids or optimises on (making an action primary, or picking the Meta or ChatGPT Ads conversion) is the person's step, by every route and also when they ask: give them the exact clicks, wait until they say it is done, then read it back.

## Workflow

1. **Read where setup stands** with `productmetrics setup get-status --json` (MCP: `setup.get_status`), and skip every step that is done.
2. **Make sure server-side tracking to Google Ads is live.** If it isn't, set it up first with `set-up-lightspeed-google-ads-conversion-tracking` (or `references/connect-lightspeed.md` and `references/connect-google-ads.md`).
3. **Follow `references/customer-match-lists.md`** step by step and confirm each **You should see** line before you move on: later steps depend on earlier ones (the consent banner decides what is sent for each order, and checks only pass once a test order has arrived).
4. **Report back** what is live now, what the person still has to do (with the exact labels from the reference), and how to check it again later.

## References

| Read | When | Docs page |
| --- | --- | --- |
| `references/customer-match-lists.md` | Customer Match lists: prerequisites, the steps, how it works on Lightspeed, troubleshooting and FAQ | https://www.productmetrics.io/docs/tracking/customer-lists/lightspeed-google-ads |
| `references/connect-lightspeed.md` | The Lightspeed store isn't connected yet, or its connection is broken | https://www.productmetrics.io/docs/platforms/lightspeed |
| `references/connect-google-ads.md` | Google Ads isn't connected yet, or you need the full list of what Product Metrics sends to it | https://www.productmetrics.io/docs/channels/google-ads |
| `references/working-with-product-metrics.md` | Before your first command: interface, rules, browser steps, secrets | https://www.productmetrics.io/docs/cli/for-agents |

If there is no `references/` folder next to this file (the skill was installed from the docs site), fetch the docs page in the last column instead, with `.md` appended for Markdown: it has the same steps.

## Related skills

- `set-up-lightspeed-google-ads-conversion-tracking`: Server-side tracking for Lightspeed in Google Ads
- `set-up-lightspeed-google-ads-enhanced-conversions`: Enhanced Conversions for Lightspeed in Google Ads
- `set-up-lightspeed-google-ads-new-customer-bidding`: New customer bidding for Lightspeed in Google Ads
- `set-up-lightspeed-google-ads-returning-customer-bidding`: Returning customer bidding for Lightspeed in Google Ads
- `set-up-lightspeed-google-ads-poas-bidding`: POAS and ROAS bidding for Lightspeed in Google Ads
- `set-up-lightspeed-google-ads-ltv-bidding`: LTV bidding for Lightspeed in Google Ads
- `check-tracking`: check every part of tracking and find a test order
- `product-metrics`: picks the right skill for any store and channel

Install: `npx skills add product-metrics/skills --skill set-up-lightspeed-google-ads-customer-match`. Every skill: https://www.productmetrics.io/docs/agent-skills/platform-skills.
