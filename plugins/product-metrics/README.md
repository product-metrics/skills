# Product Metrics

Product Metrics skills for any online store: set up and check server-side conversion tracking, bid on profit (POAS), new customers, returning customers or lifetime value in Google Ads, Meta and ChatGPT Ads, and analyse Google Ads with real figures. Includes the product-metrics skill that routes to the right setup skill, and connects the Product Metrics MCP server.

The skills follow the [Agent Skills](https://agentskills.io) format. Each one is a short `SKILL.md` with the workflow, plus a `references/` folder with the full steps for every goal, store and channel, generated from the [Product Metrics docs](https://www.productmetrics.io/docs).

## Skills

| Skill | What it does |
| --- | --- |
| `analyse-google-ads` | Analyse a store's Google Ads performance through the Product Metrics MCP server. |
| `bid-on-ltv` | Set up LTV bidding: send each customer's lifetime revenue and profit to Google Ads, Meta and ChatGPT Ads with every paid order, and bid on customer lifetime value instead of the first order. |
| `bid-on-new-customers` | Set up new customer bidding (new customer acquisition) in Google Ads, Meta and ChatGPT Ads: send each customer's first paid order as a separate new customer conversion and bid on it, so campaigns win new buyers instead of people who would buy anyway. |
| `bid-on-profit` | Set up and check POAS (profit on ad spend) or ROAS bidding with Product Metrics in Google Ads and Meta: confirm the profit conversion actions exist, additional costs are active, the right action is primary, and the target ROAS fits the value sent. |
| `bid-on-returning-customers` | Set up returning customer bidding in Google Ads, Meta and ChatGPT Ads: send every paid repeat order as a separate returning customer conversion and bid on repeat buyers' revenue or profit, for retention and win-back campaigns. |
| `check-tracking` | Check that Product Metrics conversion tracking works for a store, with the productmetrics CLI or the Product Metrics MCP server: store connection active, store linked to the property, Google Ads conversion actions present, Enhanced Conversions accepted, Meta Conversions API destination connected, and the latest purchase received. |
| `connect-google-ads` | Connect a Google Ads account and its Merchant Center to Product Metrics with the productmetrics CLI or the Product Metrics MCP server (search and execute tools). |
| `product-metrics` | Product Metrics is a profit optimisation platform for ecommerce advertising: server-side conversion tracking, POAS (profit) bidding, new and returning customer and LTV bidding, product segmentation and campaign planning across Google Ads, Meta and ChatGPT Ads, for Shopify, WooCommerce, Lightspeed, Magento, Shopware and any website on Cloudflare. |
| `set-up-tracking` | Set up Product Metrics server-side conversion tracking end to end for a store owner, with the productmetrics CLI or the Product Metrics MCP server (search and execute tools): sign in, create or pick the workspace, connect the store (Shopify, WooCommerce, Shopware, Lightspeed, Magento or any website through Cloudflare Tracking), connect Google Ads and Meta, create the conversion actions, set consent and additional costs, and confirm the first purchase arrives. |

## Install

- **Claude Code:** `/plugin install product-metrics --marketplace product-metrics/skills`
- **Any agent with the skills CLI:** `npx skills add product-metrics/skills`, then pick the skills.
- **Cursor and Codex:** add https://github.com/product-metrics/skills as a plugin marketplace and install `product-metrics`.

The agent signs in to Product Metrics through the MCP server or the [`productmetrics` CLI](https://www.productmetrics.io/docs/cli/overview); you approve browser steps yourself. A Product Metrics account is needed: https://www.productmetrics.io.

**What it runs and sends.** No hooks, scripts or telemetry. The plugin adds the Product Metrics MCP server (`https://www.productmetrics.io/mcp`, remote, OAuth sign-in): when the agent calls it, it reads and changes your own Product Metrics account (stores, tracking setup, Google Ads, Meta and ChatGPT Ads connections, reports). The skills may also tell the agent to run the `productmetrics` CLI if you have it installed, and to fetch public pages from https://www.productmetrics.io/docs. Steps in your store admin or ad platform are always handed to you. Privacy: https://www.productmetrics.io/privacy. Terms: https://www.productmetrics.io/terms. Support: https://www.productmetrics.io/contact.

## Licence

[MIT](LICENSE)
