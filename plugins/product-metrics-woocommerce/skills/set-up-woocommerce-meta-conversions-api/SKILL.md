---
name: set-up-woocommerce-meta-conversions-api
description: >-
  Meta Conversions API (CAPI) for WooCommerce (WordPress). Use this skill when a WooCommerce
  merchant wants Meta (Facebook and Instagram) ads to see more of their purchases: setting up the
  Conversions API or a server-side pixel, or Meta reporting fewer purchases or a lower ROAS than the
  store. It sends every paid order to the Meta pixel from the server, with revenue, profit, new and
  returning customer and lifetime value events. It works through Product Metrics, so use it even
  when Product Metrics is never mentioned. Not for Advanced Matching or bidding: each has its own
  skill, as do other store platforms and ad channels.
license: MIT
metadata:
  author: Product Metrics
  version: "1.2.0"
  docs: https://www.productmetrics.io/docs/tracking/server-side/woocommerce-meta
---

# WooCommerce server-side tracking with the Meta Conversions API

Send every purchase from your WooCommerce store to Meta from the server through the Meta Conversions API, with Advanced Matching and the script served from your own domain. Server-side sending matters because a browser pixel misses the purchases that ad blockers and browser privacy rules block, and Meta can only optimise on the purchases it sees.

You run the Product Metrics steps through its CLI or MCP server; the person does the steps in WooCommerce and Meta. Read `references/working-with-product-metrics.md` once for how to work with both.

**All conversion actions by agents are secondary**, the status Product Metrics creates its actions with. Choosing what a campaign bids or optimises on (making an action primary, or picking the Meta or ChatGPT Ads conversion) is the person's step, by every route and also when they ask: give them the exact clicks, wait until they say it is done, then read it back.

## Workflow

1. **Read where setup stands** with `productmetrics setup get-status --json` (MCP: `setup.get_status`), and skip every step that is done.
2. **Connect the store and Meta** if either is missing: `references/connect-woocommerce.md` and `references/connect-meta.md`.
3. **Follow `references/server-side-tracking.md`** step by step and confirm each **You should see** line before you move on: later steps depend on earlier ones (the consent banner decides what is sent for each order, and checks only pass once a test order has arrived).
4. **Report back** what is live now, what the person still has to do (with the exact labels from the reference), and how to check it again later.

## References

| Read | When | Docs page |
| --- | --- | --- |
| `references/server-side-tracking.md` | Server-side tracking: prerequisites, the steps, how it works on WooCommerce, troubleshooting and FAQ | https://www.productmetrics.io/docs/tracking/server-side/woocommerce-meta |
| `references/connect-woocommerce.md` | The WooCommerce store isn't connected yet, or its connection is broken | https://www.productmetrics.io/docs/platforms/woocommerce |
| `references/connect-meta.md` | Meta isn't connected yet, or you need the full list of what Product Metrics sends to it | https://www.productmetrics.io/docs/channels/meta |
| `references/working-with-product-metrics.md` | Before your first command: interface, rules, browser steps, secrets | https://www.productmetrics.io/docs/cli/for-agents |

If there is no `references/` folder next to this file (the skill was installed from the docs site), fetch the docs page in the last column instead, with `.md` appended for Markdown: it has the same steps.

## Related skills

- `set-up-woocommerce-meta-advanced-matching`: Advanced Matching for WooCommerce in Meta
- `set-up-woocommerce-meta-new-customer-bidding`: New customer bidding for WooCommerce in Meta
- `set-up-woocommerce-meta-returning-customer-bidding`: Returning customer bidding for WooCommerce in Meta
- `set-up-woocommerce-meta-poas-bidding`: POAS and ROAS bidding for WooCommerce in Meta
- `set-up-woocommerce-meta-ltv-bidding`: LTV bidding for WooCommerce in Meta
- `set-up-woocommerce-google-ads-conversion-tracking`: Server-side tracking for WooCommerce in Google Ads
- `set-up-woocommerce-chatgpt-ads-conversions-api`: Server-side tracking for WooCommerce in ChatGPT Ads
- `check-tracking`: check every part of tracking and find a test order
- `product-metrics`: picks the right skill for any store and channel

Install: `npx skills add product-metrics/skills --skill set-up-woocommerce-meta-conversions-api`. Every skill: https://www.productmetrics.io/docs/agent-skills/platform-skills.
