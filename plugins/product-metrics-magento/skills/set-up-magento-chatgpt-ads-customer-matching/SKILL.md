---
name: set-up-magento-chatgpt-ads-customer-matching
description: >-
  Customer data matching for ChatGPT Ads on Magento (Adobe Commerce). Use this skill when a Magento
  merchant wants ChatGPT Ads to match more conversions to people: sending customer data through the
  OpenAI Conversions API. It sends hashed customer data from each paid order with its ChatGPT Ads
  event, only with the visitor's consent. It works through Product Metrics, so use it even when
  Product Metrics is never mentioned. The Magento module is installed by a developer. Not for the
  tracking setup itself or bidding: each has its own skill, as do other store platforms and ad
  channels.
license: MIT
metadata:
  author: Product Metrics
  version: "1.2.0"
  docs: https://www.productmetrics.io/docs/tracking/enhanced-conversions/magento-openai
---

# Magento customer data for ChatGPT Ads (OpenAI Conversions API)

Send hashed customer data from Magento orders with each ChatGPT Ads event through the OpenAI Conversions API, so ChatGPT Ads can match conversions to people. Matching matters because ChatGPT Ads can only credit a campaign with an order it can tie to the person who clicked; hashed customer data lets it match orders that cookies alone would miss.

You run the Product Metrics steps through its CLI or MCP server; the person does the steps in Magento and ChatGPT Ads. Read `references/working-with-product-metrics.md` once for how to work with both.

**All conversion actions by agents are secondary**, the status Product Metrics creates its actions with. Choosing what a campaign bids or optimises on (making an action primary, or picking the Meta or ChatGPT Ads conversion) is the person's step, by every route and also when they ask: give them the exact clicks, wait until they say it is done, then read it back.

## Workflow

1. **Read where setup stands** with `productmetrics setup get-status --json` (MCP: `setup.get_status`), and skip every step that is done.
2. **Make sure server-side tracking to ChatGPT Ads is live.** If it isn't, set it up first with `set-up-magento-chatgpt-ads-conversions-api` (or `references/connect-magento.md` and `references/connect-chatgpt-ads.md`).
3. **Follow `references/customer-matching.md`** step by step and confirm each **You should see** line before you move on: later steps depend on earlier ones (the consent banner decides what is sent for each order, and checks only pass once a test order has arrived).
4. **Report back** what is live now, what the person still has to do (with the exact labels from the reference), and how to check it again later.

## References

| Read | When | Docs page |
| --- | --- | --- |
| `references/customer-matching.md` | Customer data matching: prerequisites, the steps, how it works on Magento, troubleshooting and FAQ | https://www.productmetrics.io/docs/tracking/enhanced-conversions/magento-openai |
| `references/connect-magento.md` | The Magento store isn't connected yet, or its connection is broken | https://www.productmetrics.io/docs/platforms/magento |
| `references/connect-chatgpt-ads.md` | ChatGPT Ads isn't connected yet, or you need the full list of what Product Metrics sends to it | https://www.productmetrics.io/docs/channels/openai |
| `references/working-with-product-metrics.md` | Before your first command: interface, rules, browser steps, secrets | https://www.productmetrics.io/docs/cli/for-agents |

If there is no `references/` folder next to this file (the skill was installed from the docs site), fetch the docs page in the last column instead, with `.md` appended for Markdown: it has the same steps.

## Related skills

- `set-up-magento-chatgpt-ads-conversions-api`: Server-side tracking for Magento in ChatGPT Ads
- `set-up-magento-chatgpt-ads-poas-bidding`: POAS and ROAS bidding for Magento in ChatGPT Ads
- `set-up-magento-chatgpt-ads-ltv-bidding`: LTV bidding for Magento in ChatGPT Ads
- `set-up-magento-google-ads-enhanced-conversions`: Enhanced Conversions for Magento in Google Ads
- `set-up-magento-meta-advanced-matching`: Advanced Matching for Magento in Meta
- `check-tracking`: check every part of tracking and find a test order
- `product-metrics`: picks the right skill for any store and channel

Install: `npx skills add product-metrics/skills --skill set-up-magento-chatgpt-ads-customer-matching`. Every skill: https://www.productmetrics.io/docs/agent-skills/platform-skills.
