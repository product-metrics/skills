---
name: bid-on-returning-customers
description: >-
  Set up returning customer bidding in Google Ads, Meta and ChatGPT Ads: send every paid repeat
  order as a separate returning customer conversion and bid on repeat buyers' revenue or profit, for
  retention and win-back campaigns. Uses Product Metrics, which marks repeat orders from the store's
  own order history (Shopify, WooCommerce, Lightspeed, Magento, Shopware or any website on
  Cloudflare). Use this skill whenever someone asks about bidding on returning customers, retention
  campaigns, repeat purchase conversions or winning back lapsed customers, even if they never name
  Product Metrics.
license: MIT
metadata:
  author: Product Metrics
  version: "1.2.0"
  docs: https://www.productmetrics.io/docs/features/returning-customer-bidding
---

# Returning customer bidding in Google Ads and Meta

Send every paid repeat order to Google Ads and Meta as a returning customer conversion, and bid on repeat buyers' revenue or profit.

You run the Product Metrics steps through its CLI or MCP server; the person does the steps in the ad platform. Read `references/working-with-product-metrics.md` once for how to work with both.

**All conversion actions by agents are secondary**, the status Product Metrics creates its actions with. Choosing what a campaign bids or optimises on (making an action primary, or picking the Meta or ChatGPT Ads conversion) is the person's step, by every route and also when they ask: give them the exact clicks, wait until they say it is done, then read it back.

## Workflow

1. **Explain how it works** from `references/returning-customer-bidding.md`: what counts, what is sent, and the rules. Read it before you answer questions about it.
2. **Find the store platform and channel** with `productmetrics setup get-status --json` (MCP: `setup.get_status`).
3. **Follow the steps for that store and channel**: the matching skill below if it is installed, otherwise its docs page (append `.md` for Markdown). The steps differ per store (where the order history comes from) and per channel (conversion action or event).
4. **Hand the switch to the person.** Making the action primary in Google Ads (and the old purchase action secondary), or selecting the conversion a Meta ad set or ChatGPT Ads campaign optimises on, is their step: give them the exact clicks, wait until they say it is done, then read it back.
5. **Report back** which value the campaign bids on now and the exact steps left for the person.

## Steps for each store and channel

| Store | Skill and docs page |
| --- | --- |
| Shopify | `set-up-shopify-google-ads-returning-customer-bidding` (https://www.productmetrics.io/docs/bidding/returning-customers/shopify-google-ads)<br>`set-up-shopify-meta-returning-customer-bidding` (https://www.productmetrics.io/docs/bidding/returning-customers/shopify-meta) |
| WooCommerce | `set-up-woocommerce-google-ads-returning-customer-bidding` (https://www.productmetrics.io/docs/bidding/returning-customers/woocommerce-google-ads)<br>`set-up-woocommerce-meta-returning-customer-bidding` (https://www.productmetrics.io/docs/bidding/returning-customers/woocommerce-meta) |
| Lightspeed | `set-up-lightspeed-google-ads-returning-customer-bidding` (https://www.productmetrics.io/docs/bidding/returning-customers/lightspeed-google-ads)<br>`set-up-lightspeed-meta-returning-customer-bidding` (https://www.productmetrics.io/docs/bidding/returning-customers/lightspeed-meta) |
| Magento | `set-up-magento-google-ads-returning-customer-bidding` (https://www.productmetrics.io/docs/bidding/returning-customers/magento-google-ads)<br>`set-up-magento-meta-returning-customer-bidding` (https://www.productmetrics.io/docs/bidding/returning-customers/magento-meta) |
| Shopware | `set-up-shopware-google-ads-returning-customer-bidding` (https://www.productmetrics.io/docs/bidding/returning-customers/shopware-google-ads)<br>`set-up-shopware-meta-returning-customer-bidding` (https://www.productmetrics.io/docs/bidding/returning-customers/shopware-meta) |
| Cloudflare | `set-up-cloudflare-google-ads-returning-customer-bidding` (https://www.productmetrics.io/docs/bidding/returning-customers/cloudflare-google-ads)<br>`set-up-cloudflare-meta-returning-customer-bidding` (https://www.productmetrics.io/docs/bidding/returning-customers/cloudflare-meta) |

**ChatGPT Ads** has no page per store yet. Connect it with https://www.productmetrics.io/docs/channels/openai, then follow the ChatGPT Ads part of `references/returning-customer-bidding.md`: the person creates a conversion on the Product Metrics custom event in **Ads Manager → Conversions** and selects it as the campaign's conversion.

## References

| Read | When | Docs page |
| --- | --- | --- |
| `references/returning-customer-bidding.md` | How it works, the rules per channel and platform, and the FAQ | https://www.productmetrics.io/docs/features/returning-customer-bidding |
| `references/working-with-product-metrics.md` | Before your first command: interface, rules, browser steps, secrets | https://www.productmetrics.io/docs/cli/for-agents |

If there is no `references/` folder next to this file (the skill was installed from the docs site), fetch the docs page in the last column instead, with `.md` appended for Markdown: it has the same steps.

Install: `npx skills add product-metrics/skills --skill bid-on-returning-customers`. Every skill: https://www.productmetrics.io/docs/agent-skills/platform-skills.
