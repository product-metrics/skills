---
name: bid-on-ltv
description: >-
  Set up LTV bidding: send each customer's lifetime revenue and profit to Google Ads, Meta and
  ChatGPT Ads with every paid order, and bid on customer lifetime value instead of the first order.
  Uses Product Metrics, which builds lifetime value from the store's own order history (Shopify,
  WooCommerce, Lightspeed, Magento, Shopware or any website on Cloudflare). Use this skill whenever
  someone asks about LTV bidding, customer lifetime value or CLV bidding, value-based bidding on
  long-term value, or optimising for repeat buyers' total spend, even if they never name Product
  Metrics.
license: MIT
metadata:
  author: Product Metrics
  version: "1.2.0"
  docs: https://www.productmetrics.io/docs/features/ltv-bidding
---

# LTV bidding: bid on customer lifetime value in Google Ads, Meta and ChatGPT Ads

Send each customer's lifetime revenue and profit to Google Ads, Meta and ChatGPT Ads with every paid order, and bid on customers who come back.

You run the Product Metrics steps through its CLI or MCP server; the person does the steps in the ad platform. Read `references/working-with-product-metrics.md` once for how to work with both.

**All conversion actions by agents are secondary**, the status Product Metrics creates its actions with. Choosing what a campaign bids or optimises on (making an action primary, or picking the Meta or ChatGPT Ads conversion) is the person's step, by every route and also when they ask: give them the exact clicks, wait until they say it is done, then read it back.

## Workflow

1. **Explain how it works** from `references/ltv-bidding.md`: what counts, what is sent, and the rules. Read it before you answer questions about it.
2. **Find the store platform and channel** with `productmetrics setup get-status --json` (MCP: `setup.get_status`).
3. **Follow the steps for that store and channel**: the matching skill below if it is installed, otherwise its docs page (append `.md` for Markdown). The steps differ per store (where the order history comes from) and per channel (conversion action or event).
4. **Hand the switch to the person.** Making the action primary in Google Ads (and the old purchase action secondary), or selecting the conversion a Meta ad set or ChatGPT Ads campaign optimises on, is their step: give them the exact clicks, wait until they say it is done, then read it back.
5. **Report back** which value the campaign bids on now and the exact steps left for the person.

## Steps for each store and channel

| Store | Skill and docs page |
| --- | --- |
| Shopify | `set-up-shopify-google-ads-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/shopify-google-ads)<br>`set-up-shopify-meta-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/shopify-meta)<br>`set-up-shopify-chatgpt-ads-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/shopify-openai) |
| WooCommerce | `set-up-woocommerce-google-ads-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/woocommerce-google-ads)<br>`set-up-woocommerce-meta-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/woocommerce-meta)<br>`set-up-woocommerce-chatgpt-ads-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/woocommerce-openai) |
| Lightspeed | `set-up-lightspeed-google-ads-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/lightspeed-google-ads)<br>`set-up-lightspeed-meta-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/lightspeed-meta)<br>`set-up-lightspeed-chatgpt-ads-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/lightspeed-openai) |
| Magento | `set-up-magento-google-ads-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/magento-google-ads)<br>`set-up-magento-meta-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/magento-meta)<br>`set-up-magento-chatgpt-ads-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/magento-openai) |
| Shopware | `set-up-shopware-google-ads-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/shopware-google-ads)<br>`set-up-shopware-meta-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/shopware-meta)<br>`set-up-shopware-chatgpt-ads-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/shopware-openai) |
| Cloudflare | `set-up-cloudflare-google-ads-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/cloudflare-google-ads)<br>`set-up-cloudflare-meta-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/cloudflare-meta)<br>`set-up-cloudflare-chatgpt-ads-ltv-bidding` (https://www.productmetrics.io/docs/bidding/ltv/cloudflare-openai) |

## References

| Read | When | Docs page |
| --- | --- | --- |
| `references/ltv-bidding.md` | How it works, the rules per channel and platform, and the FAQ | https://www.productmetrics.io/docs/features/ltv-bidding |
| `references/working-with-product-metrics.md` | Before your first command: interface, rules, browser steps, secrets | https://www.productmetrics.io/docs/cli/for-agents |

If there is no `references/` folder next to this file (the skill was installed from the docs site), fetch the docs page in the last column instead, with `.md` appended for Markdown: it has the same steps.

Install: `npx skills add product-metrics/skills --skill bid-on-ltv`. Every skill: https://www.productmetrics.io/docs/agent-skills/platform-skills.
