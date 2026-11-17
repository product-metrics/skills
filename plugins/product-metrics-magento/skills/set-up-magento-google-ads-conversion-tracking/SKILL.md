---
name: set-up-magento-google-ads-conversion-tracking
description: >-
  Server-side Google Ads conversion tracking for Magento (Adobe Commerce). Use this skill when a
  Magento merchant wants Google Ads to see all their purchases: setting up or fixing conversion
  tracking, moving it server-side, or Google Ads counting fewer conversions than the store has
  orders because of ad blockers and browser privacy. It sends every paid order to Google Ads from
  the server as conversion actions with revenue, profit, new and returning customer and lifetime
  value. It works through Product Metrics, so use it even when Product Metrics is never mentioned.
  The Magento module is installed by a developer. Not for Enhanced Conversions, Customer Match or
  bidding: each has its own skill, as do other store platforms and ad channels.
license: MIT
metadata:
  author: Product Metrics
  version: "1.2.0"
  docs: https://www.productmetrics.io/docs/tracking/server-side/magento-google-ads
---

# Magento server-side tracking for Google Ads

Send every purchase from your Magento store view to Google Ads from the server, with the script served from your own domain. Server-side sending matters because a browser pixel misses the purchases that ad blockers and browser privacy rules block, and Google Ads can only optimise on the purchases it sees.

You run the Product Metrics steps through its CLI or MCP server; the person does the steps in Magento and Google Ads. Read `references/working-with-product-metrics.md` once for how to work with both.

**All conversion actions by agents are secondary**, the status Product Metrics creates its actions with. Choosing what a campaign bids or optimises on (making an action primary, or picking the Meta or ChatGPT Ads conversion) is the person's step, by every route and also when they ask: give them the exact clicks, wait until they say it is done, then read it back.

## Workflow

1. **Read where setup stands** with `productmetrics setup get-status --json` (MCP: `setup.get_status`), and skip every step that is done.
2. **Connect the store and Google Ads** if either is missing: `references/connect-magento.md` and `references/connect-google-ads.md`.
3. **Follow `references/server-side-tracking.md`** step by step and confirm each **You should see** line before you move on: later steps depend on earlier ones (the consent banner decides what is sent for each order, and checks only pass once a test order has arrived).
4. **Report back** what is live now, what the person still has to do (with the exact labels from the reference), and how to check it again later.

## References

| Read | When | Docs page |
| --- | --- | --- |
| `references/server-side-tracking.md` | Server-side tracking: prerequisites, the steps, how it works on Magento, troubleshooting and FAQ | https://www.productmetrics.io/docs/tracking/server-side/magento-google-ads |
| `references/connect-magento.md` | The Magento store isn't connected yet, or its connection is broken | https://www.productmetrics.io/docs/platforms/magento |
| `references/connect-google-ads.md` | Google Ads isn't connected yet, or you need the full list of what Product Metrics sends to it | https://www.productmetrics.io/docs/channels/google-ads |
| `references/working-with-product-metrics.md` | Before your first command: interface, rules, browser steps, secrets | https://www.productmetrics.io/docs/cli/for-agents |

If there is no `references/` folder next to this file (the skill was installed from the docs site), fetch the docs page in the last column instead, with `.md` appended for Markdown: it has the same steps.

## Related skills

- `set-up-magento-google-ads-enhanced-conversions`: Enhanced Conversions for Magento in Google Ads
- `set-up-magento-google-ads-customer-match`: Customer Match lists for Magento in Google Ads
- `set-up-magento-google-ads-new-customer-bidding`: New customer bidding for Magento in Google Ads
- `set-up-magento-google-ads-returning-customer-bidding`: Returning customer bidding for Magento in Google Ads
- `set-up-magento-google-ads-poas-bidding`: POAS and ROAS bidding for Magento in Google Ads
- `set-up-magento-google-ads-ltv-bidding`: LTV bidding for Magento in Google Ads
- `set-up-magento-meta-conversions-api`: Server-side tracking for Magento in Meta
- `set-up-magento-chatgpt-ads-conversions-api`: Server-side tracking for Magento in ChatGPT Ads
- `check-tracking`: check every part of tracking and find a test order
- `product-metrics`: picks the right skill for any store and channel

Install: `npx skills add product-metrics/skills --skill set-up-magento-google-ads-conversion-tracking`. Every skill: https://www.productmetrics.io/docs/agent-skills/platform-skills.
