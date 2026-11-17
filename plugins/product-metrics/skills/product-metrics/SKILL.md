---
name: product-metrics
description: >-
  Product Metrics is a profit optimisation platform for ecommerce advertising: server-side
  conversion tracking, POAS (profit) bidding, new and returning customer and LTV bidding, product
  segmentation and campaign planning across Google Ads, Meta and ChatGPT Ads, for Shopify,
  WooCommerce, Lightspeed, Magento, Shopware and any website on Cloudflare. Use this skill for any
  Product Metrics task, and whenever someone wants server-side or ad-blocker-proof conversion
  tracking, the Meta or OpenAI Conversions API, Enhanced Conversions, Advanced Matching, bidding on
  profit or POAS, new customer acquisition, LTV bidding or Customer Match lists for an online store.
  It routes to the right skill for the store platform and ad channel.
license: MIT
metadata:
  author: Product Metrics
  version: "1.2.0"
  docs: https://www.productmetrics.io/docs/agent-skills/overview
---

# Product Metrics

**Product Metrics** (https://www.productmetrics.io) sends every paid order from an online store to Google Ads, Meta and ChatGPT Ads from the server, with its revenue, profit, new or returning customer and lifetime value, so campaigns can bid on profit instead of revenue. It also segments products by profitability and plans campaigns. Docs: https://www.productmetrics.io/docs (index for agents: https://www.productmetrics.io/docs/llms.txt).

This skill picks the right one for the job. Read `references/working-with-product-metrics.md` before your first command.

**All conversion actions by agents are secondary**, the status Product Metrics creates its actions with. Choosing what a campaign bids or optimises on (making an action primary, or picking the Meta or ChatGPT Ads conversion) is the person's step, by every route and also when they ask: give them the exact clicks, wait until they say it is done, then read it back.

## 1. Find the store platform and channel

Ask, or read it with `productmetrics setup get-status --json` (MCP: `setup.get_status`). Store platforms: Shopify, WooCommerce, Lightspeed eCom (C-Series), Magento 2 (installed by a developer), Shopware 6, and any other website through Cloudflare Tracking (sign in to Cloudflare; no plugin). A custom-built store sends orders by webhook: https://www.productmetrics.io/docs/platforms/custom-store.

## 2. Pick the skill

One skill per task, store platform and channel. Replace `<platform>` with `shopify`, `woocommerce`, `lightspeed`, `magento`, `shopware` or `cloudflare` (any website):

| Task | Google Ads | Meta | ChatGPT Ads |
| --- | --- | --- | --- |
| Server-side tracking | `set-up-<platform>-google-ads-conversion-tracking` | `set-up-<platform>-meta-conversions-api` | `set-up-<platform>-chatgpt-ads-conversions-api` |
| Enhanced Conversions | `set-up-<platform>-google-ads-enhanced-conversions` | `set-up-<platform>-meta-advanced-matching` | `set-up-<platform>-chatgpt-ads-customer-matching` |
| Customer lists | `set-up-<platform>-google-ads-customer-match` | – | – |
| New customer bidding | `set-up-<platform>-google-ads-new-customer-bidding` | `set-up-<platform>-meta-new-customer-bidding` | – |
| Returning customer bidding | `set-up-<platform>-google-ads-returning-customer-bidding` | `set-up-<platform>-meta-returning-customer-bidding` | – |
| POAS and ROAS bidding | `set-up-<platform>-google-ads-poas-bidding` | `set-up-<platform>-meta-poas-bidding` | `set-up-<platform>-chatgpt-ads-poas-bidding` |
| LTV bidding | `set-up-<platform>-google-ads-ltv-bidding` | `set-up-<platform>-meta-ltv-bidding` | `set-up-<platform>-chatgpt-ads-ltv-bidding` |

Order of work: server-side tracking first, then customer data for matching, then a bidding goal.

By task, on any store:

| Skill | Use it to |
| --- | --- |
| `set-up-tracking` | Go from nothing to tracking active: workspace, store, Google Ads, Meta, consent, costs, first purchase |
| `connect-google-ads` | Connect Google Ads and Merchant Center, or fix a broken connection |
| `check-tracking` | Check every part of tracking and find a test order (read only) |
| `bid-on-profit` | Set up and check POAS or ROAS bidding in Google Ads and Meta |
| `analyse-google-ads` | Answer "how are my campaigns doing" and "why did ROAS drop" with real figures (read only) |
| `bid-on-new-customers` | Set up new customer bidding (new customer acquisition) in Google Ads, Meta and ChatGPT Ads |
| `bid-on-returning-customers` | Set up returning customer bidding in Google Ads, Meta and ChatGPT Ads |
| `bid-on-ltv` | Set up LTV (customer lifetime value) bidding in Google Ads, Meta and ChatGPT Ads |

If the skill you need isn't installed, install it (`npx skills add product-metrics/skills --skill <name>`) or follow its docs page: every docs URL serves Markdown with `.md` appended, and https://www.productmetrics.io/docs/llms.txt lists them all.

## 3. Key facts

- **POAS** = profit ÷ ad spend; **ROAS** = revenue ÷ ad spend, written as a plain number (4.2). A **target ROAS** is a percentage (420%); on the profit value, 100% is break-even.
- All conversion actions by agents are secondary, as Product Metrics creates them. The person makes one primary in Google Ads (**Goals → Conversions**) and keeps one purchase action primary.
- Profit is sent once the additional costs are active and every cost of the order is known; a loss is sent as 0. Costs: https://www.productmetrics.io/docs/using/costs.
- Consent: Product Metrics reads the store's consent banner and sends only what the visitor allowed: https://www.productmetrics.io/docs/using/consent.
- All three channels get revenue, profit, new and returning customer and lifetime value. On ChatGPT Ads, new and returning customer bidding has no per-store skill yet: use `bid-on-new-customers` or `bid-on-returning-customers`. Customer Match lists are Google Ads only.

## MCP server

For analysis (campaign and product profit, segments, changes), connect the Product Metrics MCP server: `https://www.productmetrics.io/mcp` (https://www.productmetrics.io/docs/mcp/connect).

If there is no `references/` folder next to this file (the skill was installed from the docs site), use the docs pages linked above instead, with `.md` appended for Markdown: it has the same steps.
