# Product Metrics for Shopify

Shopify: server-side conversion tracking, Enhanced Conversions and Advanced Matching, Customer Match lists, and POAS, new customer, returning customer and LTV bidding in Google Ads, Meta (Conversions API) and ChatGPT Ads (OpenAI Conversions API), with Product Metrics. 17 skills, one per setup task and ad channel.

The skills follow the [Agent Skills](https://agentskills.io) format. Each one is a short `SKILL.md` with the workflow, plus a `references/` folder with the full steps for every goal, store and channel, generated from the [Product Metrics docs](https://www.productmetrics.io/docs).

## Skills

| Skill | What it does |
| --- | --- |
| `set-up-shopify-google-ads-conversion-tracking` | Server-side Google Ads conversion tracking for Shopify. |
| `set-up-shopify-meta-conversions-api` | Meta Conversions API (CAPI) for Shopify. |
| `set-up-shopify-chatgpt-ads-conversions-api` | ChatGPT Ads conversion tracking for Shopify through the OpenAI Conversions API. |
| `set-up-shopify-google-ads-enhanced-conversions` | Google Ads Enhanced Conversions for Shopify. |
| `set-up-shopify-meta-advanced-matching` | Meta Advanced Matching for Shopify. |
| `set-up-shopify-chatgpt-ads-customer-matching` | Customer data matching for ChatGPT Ads on Shopify. |
| `set-up-shopify-google-ads-customer-match` | Google Ads Customer Match lists for Shopify. |
| `set-up-shopify-google-ads-new-customer-bidding` | New customer bidding (new customer acquisition) for Shopify in Google Ads. |
| `set-up-shopify-meta-new-customer-bidding` | New customer bidding (new customer acquisition) for Shopify in Meta. |
| `set-up-shopify-google-ads-returning-customer-bidding` | Returning customer bidding for Shopify in Google Ads. |
| `set-up-shopify-meta-returning-customer-bidding` | Returning customer bidding for Shopify in Meta. |
| `set-up-shopify-google-ads-poas-bidding` | POAS (profit on ad spend) bidding for Shopify in Google Ads. |
| `set-up-shopify-meta-poas-bidding` | POAS (profit on ad spend) bidding for Shopify in Meta. |
| `set-up-shopify-chatgpt-ads-poas-bidding` | POAS (profit on ad spend) bidding for Shopify in ChatGPT Ads. |
| `set-up-shopify-google-ads-ltv-bidding` | LTV (customer lifetime value) bidding for Shopify in Google Ads. |
| `set-up-shopify-meta-ltv-bidding` | LTV (customer lifetime value) bidding for Shopify in Meta. |
| `set-up-shopify-chatgpt-ads-ltv-bidding` | LTV (customer lifetime value) bidding for Shopify in ChatGPT Ads. |

## Install

- **Claude Code:** `/plugin install product-metrics-shopify --marketplace product-metrics/skills`
- **Any agent with the skills CLI:** `npx skills add product-metrics/skills`, then pick the skills.
- **Cursor and Codex:** add https://github.com/product-metrics/skills as a plugin marketplace and install `product-metrics-shopify`.

The agent signs in to Product Metrics through the MCP server or the [`productmetrics` CLI](https://www.productmetrics.io/docs/cli/overview); you approve browser steps yourself. A Product Metrics account is needed: https://www.productmetrics.io.

**What it runs and sends.** No hooks, scripts or telemetry. The plugin adds the Product Metrics MCP server (`https://www.productmetrics.io/mcp`, remote, OAuth sign-in): when the agent calls it, it reads and changes your own Product Metrics account (stores, tracking setup, Google Ads, Meta and ChatGPT Ads connections, reports). The skills may also tell the agent to run the `productmetrics` CLI if you have it installed, and to fetch public pages from https://www.productmetrics.io/docs. Steps in your store admin or ad platform are always handed to you. Privacy: https://www.productmetrics.io/privacy. Terms: https://www.productmetrics.io/terms. Support: https://www.productmetrics.io/contact.

## Licence

[MIT](LICENSE)
