---
name: set-up-woocommerce-chatgpt-ads-conversions-api
description: >-
  ChatGPT Ads conversion tracking for WooCommerce (WordPress) through the OpenAI Conversions API.
  Use this skill when a WooCommerce merchant advertising on ChatGPT wants their purchases tracked:
  connecting the OpenAI Conversions API or the ChatGPT Ads pixel. It sends every paid order to
  ChatGPT Ads from the server, with revenue, profit, new and returning customer and lifetime value
  events. It works through Product Metrics, so use it even when Product Metrics is never mentioned.
  Not for customer data matching or bidding: each has its own skill, as do other store platforms and
  ad channels.
license: MIT
metadata:
  author: Product Metrics
  version: "1.2.0"
  docs: https://www.productmetrics.io/docs/tracking/server-side/woocommerce-openai
---

# WooCommerce ChatGPT Ads server-side tracking (OpenAI Conversions API)

Send every paid WooCommerce order to your ChatGPT Ads pixel from the server, through the OpenAI Conversions API. Server-side sending matters because a browser pixel misses the purchases that ad blockers and browser privacy rules block, and ChatGPT Ads can only optimise on the purchases it sees.

You run the Product Metrics steps through its CLI or MCP server; the person does the steps in WooCommerce and ChatGPT Ads. Read `references/working-with-product-metrics.md` once for how to work with both.

**All conversion actions by agents are secondary**, the status Product Metrics creates its actions with. Choosing what a campaign bids or optimises on (making an action primary, or picking the Meta or ChatGPT Ads conversion) is the person's step, by every route and also when they ask: give them the exact clicks, wait until they say it is done, then read it back.

## Workflow

1. **Read where setup stands** with `productmetrics setup get-status --json` (MCP: `setup.get_status`), and skip every step that is done.
2. **Connect the store and ChatGPT Ads** if either is missing: `references/connect-woocommerce.md` and `references/connect-chatgpt-ads.md`.
3. **Follow `references/server-side-tracking.md`** step by step and confirm each **You should see** line before you move on: later steps depend on earlier ones (the consent banner decides what is sent for each order, and checks only pass once a test order has arrived).
4. **Report back** what is live now, what the person still has to do (with the exact labels from the reference), and how to check it again later.

## References

| Read | When | Docs page |
| --- | --- | --- |
| `references/server-side-tracking.md` | Server-side tracking: prerequisites, the steps, how it works on WooCommerce, troubleshooting and FAQ | https://www.productmetrics.io/docs/tracking/server-side/woocommerce-openai |
| `references/connect-woocommerce.md` | The WooCommerce store isn't connected yet, or its connection is broken | https://www.productmetrics.io/docs/platforms/woocommerce |
| `references/connect-chatgpt-ads.md` | ChatGPT Ads isn't connected yet, or you need the full list of what Product Metrics sends to it | https://www.productmetrics.io/docs/channels/openai |
| `references/working-with-product-metrics.md` | Before your first command: interface, rules, browser steps, secrets | https://www.productmetrics.io/docs/cli/for-agents |

If there is no `references/` folder next to this file (the skill was installed from the docs site), fetch the docs page in the last column instead, with `.md` appended for Markdown: it has the same steps.

## Related skills

- `set-up-woocommerce-chatgpt-ads-customer-matching`: Customer data matching for WooCommerce in ChatGPT Ads
- `set-up-woocommerce-chatgpt-ads-poas-bidding`: POAS and ROAS bidding for WooCommerce in ChatGPT Ads
- `set-up-woocommerce-chatgpt-ads-ltv-bidding`: LTV bidding for WooCommerce in ChatGPT Ads
- `set-up-woocommerce-google-ads-conversion-tracking`: Server-side tracking for WooCommerce in Google Ads
- `set-up-woocommerce-meta-conversions-api`: Server-side tracking for WooCommerce in Meta
- `check-tracking`: check every part of tracking and find a test order
- `product-metrics`: picks the right skill for any store and channel

Install: `npx skills add product-metrics/skills --skill set-up-woocommerce-chatgpt-ads-conversions-api`. Every skill: https://www.productmetrics.io/docs/agent-skills/platform-skills.
