# Product Metrics

Product Metrics is a profit optimisation platform for ecommerce advertising: one app for server-side tracking, profit bidding, product segmentation and campaign planning across Google Ads, Meta and ChatGPT Ads. It sends each order’s profit, new or returning status and lifetime value to the ad platforms, so merchants can bid on POAS, new customers and LTV. Machine learning segments every product into custom labels for Shopping and Performance Max, and the campaign plan sets out the ideal campaign structure for those segments. A dashboard shows profit, customers, stock and returns.

Use the skills to connect your store and ad channels, check tracking, set up bidding, analyse products and campaigns, tune segmentation and product rules, and check stock and returns through the Product Metrics MCP server or CLI. Store integrations: Shopify, WooCommerce, Lightspeed, Magento, Shopware and any website on Cloudflare. Ad channels: Google Ads, Meta (Conversions API) and ChatGPT Ads (OpenAI Conversions API).

This plugin holds every Product Metrics skill (116) and connects the [Product Metrics MCP server](https://www.productmetrics.io/docs/mcp/overview). The skills follow the [Agent Skills](https://agentskills.io) format. Each one is a short `SKILL.md` with the workflow and the rules, plus a `references/` folder with the full steps for its goal, store and channel, generated from the [Product Metrics docs](https://www.productmetrics.io/docs).

## Install

The `product-metrics` plugin holds every skill and connects the [Product Metrics MCP server](https://www.productmetrics.io/docs/mcp/overview).

### Claude Code

1. Add the marketplace: `claude plugin marketplace add product-metrics/skills`
2. Install the plugin: `claude plugin install product-metrics@product-metrics`
3. Sign in to the MCP server: run `claude`, type `/mcp`, select the `product-metrics` server, choose **Authenticate** and sign in in the browser.

### Cursor

1. Add https://github.com/product-metrics/skills as a plugin marketplace (it reads `.cursor-plugin/marketplace.json`).
2. Install the `product-metrics` plugin.

### Codex

1. Add the marketplace: `codex plugin marketplace add product-metrics/skills`
2. Run `/plugins`, select **Product Metrics** and install it.

### Gemini CLI

1. Install the extension: `gemini extensions install https://github.com/product-metrics/skills`

### Kiro

[![Add to Kiro](https://kiro.dev/images/add-to-kiro.svg)](https://kiro.dev/launch/mcp/add?name=product-metrics&config=%7B%22url%22%3A%22https%3A%2F%2Fwww.productmetrics.io%2Fmcp%22%2C%22disabled%22%3Afalse%2C%22autoApprove%22%3A%5B%5D%7D)

Add the remote MCP server, then sign in through OAuth.

### Any agent with the skills CLI

1. Add the skills: `npx skills add product-metrics/skills`, then pick the ones you need (`--skill <name>` adds one).

### Without installing

Every skill is also served as an MCP resource, `skill://<name>`, by the open docs MCP server at `https://www.productmetrics.io/docs/api/mcp` (no sign-in), next to its `search_docs` and `read_page` tools. An agent connected to that server can read the skills without the plugin.

Connect your Product Metrics account to use the plugin, or create one through the plugin when you sign in. The agent connects through the MCP server or the [`productmetrics` CLI](https://www.productmetrics.io/docs/cli/overview).

**What it runs and sends.** No hooks, scripts or telemetry. The plugin adds the Product Metrics MCP server (`https://www.productmetrics.io/mcp`, remote, OAuth sign-in): when the agent calls it, it reads and changes your own Product Metrics account (stores, tracking setup, Google Ads, Meta and ChatGPT Ads connections, reports). The skills may also tell the agent to run the `productmetrics` CLI if you have it installed, and to fetch public pages from https://www.productmetrics.io/docs. Privacy: https://www.productmetrics.io/privacy. Terms: https://www.productmetrics.io/terms. Support: https://www.productmetrics.io/contact.

## Skills by store platform

All 116 skills are in the `product-metrics` plugin. Names follow `set-up-<platform>-<channel>-<task>`. Start with server-side tracking, add customer data for matching, then pick a bidding goal.

### Shopify

| Skill | What it sets up |
| --- | --- |
| [`set-up-shopify-google-ads-conversion-tracking`](skills/set-up-shopify-google-ads-conversion-tracking/SKILL.md) | Server-side Google Ads conversion tracking for Shopify |
| [`set-up-shopify-meta-conversions-api`](skills/set-up-shopify-meta-conversions-api/SKILL.md) | Meta Conversions API (CAPI) for Shopify |
| [`set-up-shopify-chatgpt-ads-conversions-api`](skills/set-up-shopify-chatgpt-ads-conversions-api/SKILL.md) | ChatGPT Ads conversion tracking for Shopify through the OpenAI Conversions API |
| [`set-up-shopify-google-ads-enhanced-conversions`](skills/set-up-shopify-google-ads-enhanced-conversions/SKILL.md) | Google Ads Enhanced Conversions for Shopify |
| [`set-up-shopify-meta-advanced-matching`](skills/set-up-shopify-meta-advanced-matching/SKILL.md) | Meta Advanced Matching for Shopify |
| [`set-up-shopify-chatgpt-ads-customer-matching`](skills/set-up-shopify-chatgpt-ads-customer-matching/SKILL.md) | Customer data matching for ChatGPT Ads on Shopify |
| [`set-up-shopify-google-ads-customer-match`](skills/set-up-shopify-google-ads-customer-match/SKILL.md) | Google Ads Customer Match lists for Shopify |
| [`set-up-shopify-google-ads-new-customer-bidding`](skills/set-up-shopify-google-ads-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Shopify in Google Ads |
| [`set-up-shopify-meta-new-customer-bidding`](skills/set-up-shopify-meta-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Shopify in Meta |
| [`set-up-shopify-google-ads-returning-customer-bidding`](skills/set-up-shopify-google-ads-returning-customer-bidding/SKILL.md) | Returning customer bidding for Shopify in Google Ads |
| [`set-up-shopify-meta-returning-customer-bidding`](skills/set-up-shopify-meta-returning-customer-bidding/SKILL.md) | Returning customer bidding for Shopify in Meta |
| [`set-up-shopify-google-ads-poas-bidding`](skills/set-up-shopify-google-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Shopify in Google Ads |
| [`set-up-shopify-meta-poas-bidding`](skills/set-up-shopify-meta-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Shopify in Meta |
| [`set-up-shopify-chatgpt-ads-poas-bidding`](skills/set-up-shopify-chatgpt-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Shopify in ChatGPT Ads |
| [`set-up-shopify-google-ads-ltv-bidding`](skills/set-up-shopify-google-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Shopify in Google Ads |
| [`set-up-shopify-meta-ltv-bidding`](skills/set-up-shopify-meta-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Shopify in Meta |
| [`set-up-shopify-chatgpt-ads-ltv-bidding`](skills/set-up-shopify-chatgpt-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Shopify in ChatGPT Ads |

### WooCommerce

| Skill | What it sets up |
| --- | --- |
| [`set-up-woocommerce-google-ads-conversion-tracking`](skills/set-up-woocommerce-google-ads-conversion-tracking/SKILL.md) | Server-side Google Ads conversion tracking for WooCommerce (WordPress) |
| [`set-up-woocommerce-meta-conversions-api`](skills/set-up-woocommerce-meta-conversions-api/SKILL.md) | Meta Conversions API (CAPI) for WooCommerce (WordPress) |
| [`set-up-woocommerce-chatgpt-ads-conversions-api`](skills/set-up-woocommerce-chatgpt-ads-conversions-api/SKILL.md) | ChatGPT Ads conversion tracking for WooCommerce (WordPress) through the OpenAI Conversions API |
| [`set-up-woocommerce-google-ads-enhanced-conversions`](skills/set-up-woocommerce-google-ads-enhanced-conversions/SKILL.md) | Google Ads Enhanced Conversions for WooCommerce (WordPress) |
| [`set-up-woocommerce-meta-advanced-matching`](skills/set-up-woocommerce-meta-advanced-matching/SKILL.md) | Meta Advanced Matching for WooCommerce (WordPress) |
| [`set-up-woocommerce-chatgpt-ads-customer-matching`](skills/set-up-woocommerce-chatgpt-ads-customer-matching/SKILL.md) | Customer data matching for ChatGPT Ads on WooCommerce (WordPress) |
| [`set-up-woocommerce-google-ads-customer-match`](skills/set-up-woocommerce-google-ads-customer-match/SKILL.md) | Google Ads Customer Match lists for WooCommerce (WordPress) |
| [`set-up-woocommerce-google-ads-new-customer-bidding`](skills/set-up-woocommerce-google-ads-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for WooCommerce (WordPress) in Google Ads |
| [`set-up-woocommerce-meta-new-customer-bidding`](skills/set-up-woocommerce-meta-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for WooCommerce (WordPress) in Meta |
| [`set-up-woocommerce-google-ads-returning-customer-bidding`](skills/set-up-woocommerce-google-ads-returning-customer-bidding/SKILL.md) | Returning customer bidding for WooCommerce (WordPress) in Google Ads |
| [`set-up-woocommerce-meta-returning-customer-bidding`](skills/set-up-woocommerce-meta-returning-customer-bidding/SKILL.md) | Returning customer bidding for WooCommerce (WordPress) in Meta |
| [`set-up-woocommerce-google-ads-poas-bidding`](skills/set-up-woocommerce-google-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for WooCommerce (WordPress) in Google Ads |
| [`set-up-woocommerce-meta-poas-bidding`](skills/set-up-woocommerce-meta-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for WooCommerce (WordPress) in Meta |
| [`set-up-woocommerce-chatgpt-ads-poas-bidding`](skills/set-up-woocommerce-chatgpt-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for WooCommerce (WordPress) in ChatGPT Ads |
| [`set-up-woocommerce-google-ads-ltv-bidding`](skills/set-up-woocommerce-google-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for WooCommerce (WordPress) in Google Ads |
| [`set-up-woocommerce-meta-ltv-bidding`](skills/set-up-woocommerce-meta-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for WooCommerce (WordPress) in Meta |
| [`set-up-woocommerce-chatgpt-ads-ltv-bidding`](skills/set-up-woocommerce-chatgpt-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for WooCommerce (WordPress) in ChatGPT Ads |

### Lightspeed

| Skill | What it sets up |
| --- | --- |
| [`set-up-lightspeed-google-ads-conversion-tracking`](skills/set-up-lightspeed-google-ads-conversion-tracking/SKILL.md) | Server-side Google Ads conversion tracking for Lightspeed |
| [`set-up-lightspeed-meta-conversions-api`](skills/set-up-lightspeed-meta-conversions-api/SKILL.md) | Meta Conversions API (CAPI) for Lightspeed |
| [`set-up-lightspeed-chatgpt-ads-conversions-api`](skills/set-up-lightspeed-chatgpt-ads-conversions-api/SKILL.md) | ChatGPT Ads conversion tracking for Lightspeed through the OpenAI Conversions API |
| [`set-up-lightspeed-google-ads-enhanced-conversions`](skills/set-up-lightspeed-google-ads-enhanced-conversions/SKILL.md) | Google Ads Enhanced Conversions for Lightspeed |
| [`set-up-lightspeed-meta-advanced-matching`](skills/set-up-lightspeed-meta-advanced-matching/SKILL.md) | Meta Advanced Matching for Lightspeed |
| [`set-up-lightspeed-chatgpt-ads-customer-matching`](skills/set-up-lightspeed-chatgpt-ads-customer-matching/SKILL.md) | Customer data matching for ChatGPT Ads on Lightspeed |
| [`set-up-lightspeed-google-ads-customer-match`](skills/set-up-lightspeed-google-ads-customer-match/SKILL.md) | Google Ads Customer Match lists for Lightspeed |
| [`set-up-lightspeed-google-ads-new-customer-bidding`](skills/set-up-lightspeed-google-ads-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Lightspeed in Google Ads |
| [`set-up-lightspeed-meta-new-customer-bidding`](skills/set-up-lightspeed-meta-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Lightspeed in Meta |
| [`set-up-lightspeed-google-ads-returning-customer-bidding`](skills/set-up-lightspeed-google-ads-returning-customer-bidding/SKILL.md) | Returning customer bidding for Lightspeed in Google Ads |
| [`set-up-lightspeed-meta-returning-customer-bidding`](skills/set-up-lightspeed-meta-returning-customer-bidding/SKILL.md) | Returning customer bidding for Lightspeed in Meta |
| [`set-up-lightspeed-google-ads-poas-bidding`](skills/set-up-lightspeed-google-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Lightspeed in Google Ads |
| [`set-up-lightspeed-meta-poas-bidding`](skills/set-up-lightspeed-meta-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Lightspeed in Meta |
| [`set-up-lightspeed-chatgpt-ads-poas-bidding`](skills/set-up-lightspeed-chatgpt-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Lightspeed in ChatGPT Ads |
| [`set-up-lightspeed-google-ads-ltv-bidding`](skills/set-up-lightspeed-google-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Lightspeed in Google Ads |
| [`set-up-lightspeed-meta-ltv-bidding`](skills/set-up-lightspeed-meta-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Lightspeed in Meta |
| [`set-up-lightspeed-chatgpt-ads-ltv-bidding`](skills/set-up-lightspeed-chatgpt-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Lightspeed in ChatGPT Ads |

### Magento

| Skill | What it sets up |
| --- | --- |
| [`set-up-magento-google-ads-conversion-tracking`](skills/set-up-magento-google-ads-conversion-tracking/SKILL.md) | Server-side Google Ads conversion tracking for Magento (Adobe Commerce) |
| [`set-up-magento-meta-conversions-api`](skills/set-up-magento-meta-conversions-api/SKILL.md) | Meta Conversions API (CAPI) for Magento (Adobe Commerce) |
| [`set-up-magento-chatgpt-ads-conversions-api`](skills/set-up-magento-chatgpt-ads-conversions-api/SKILL.md) | ChatGPT Ads conversion tracking for Magento (Adobe Commerce) through the OpenAI Conversions API |
| [`set-up-magento-google-ads-enhanced-conversions`](skills/set-up-magento-google-ads-enhanced-conversions/SKILL.md) | Google Ads Enhanced Conversions for Magento (Adobe Commerce) |
| [`set-up-magento-meta-advanced-matching`](skills/set-up-magento-meta-advanced-matching/SKILL.md) | Meta Advanced Matching for Magento (Adobe Commerce) |
| [`set-up-magento-chatgpt-ads-customer-matching`](skills/set-up-magento-chatgpt-ads-customer-matching/SKILL.md) | Customer data matching for ChatGPT Ads on Magento (Adobe Commerce) |
| [`set-up-magento-google-ads-customer-match`](skills/set-up-magento-google-ads-customer-match/SKILL.md) | Google Ads Customer Match lists for Magento (Adobe Commerce) |
| [`set-up-magento-google-ads-new-customer-bidding`](skills/set-up-magento-google-ads-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Magento (Adobe Commerce) in Google Ads |
| [`set-up-magento-meta-new-customer-bidding`](skills/set-up-magento-meta-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Magento (Adobe Commerce) in Meta |
| [`set-up-magento-google-ads-returning-customer-bidding`](skills/set-up-magento-google-ads-returning-customer-bidding/SKILL.md) | Returning customer bidding for Magento (Adobe Commerce) in Google Ads |
| [`set-up-magento-meta-returning-customer-bidding`](skills/set-up-magento-meta-returning-customer-bidding/SKILL.md) | Returning customer bidding for Magento (Adobe Commerce) in Meta |
| [`set-up-magento-google-ads-poas-bidding`](skills/set-up-magento-google-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Magento (Adobe Commerce) in Google Ads |
| [`set-up-magento-meta-poas-bidding`](skills/set-up-magento-meta-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Magento (Adobe Commerce) in Meta |
| [`set-up-magento-chatgpt-ads-poas-bidding`](skills/set-up-magento-chatgpt-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Magento (Adobe Commerce) in ChatGPT Ads |
| [`set-up-magento-google-ads-ltv-bidding`](skills/set-up-magento-google-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Magento (Adobe Commerce) in Google Ads |
| [`set-up-magento-meta-ltv-bidding`](skills/set-up-magento-meta-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Magento (Adobe Commerce) in Meta |
| [`set-up-magento-chatgpt-ads-ltv-bidding`](skills/set-up-magento-chatgpt-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Magento (Adobe Commerce) in ChatGPT Ads |

### Shopware

| Skill | What it sets up |
| --- | --- |
| [`set-up-shopware-google-ads-conversion-tracking`](skills/set-up-shopware-google-ads-conversion-tracking/SKILL.md) | Server-side Google Ads conversion tracking for Shopware |
| [`set-up-shopware-meta-conversions-api`](skills/set-up-shopware-meta-conversions-api/SKILL.md) | Meta Conversions API (CAPI) for Shopware |
| [`set-up-shopware-chatgpt-ads-conversions-api`](skills/set-up-shopware-chatgpt-ads-conversions-api/SKILL.md) | ChatGPT Ads conversion tracking for Shopware through the OpenAI Conversions API |
| [`set-up-shopware-google-ads-enhanced-conversions`](skills/set-up-shopware-google-ads-enhanced-conversions/SKILL.md) | Google Ads Enhanced Conversions for Shopware |
| [`set-up-shopware-meta-advanced-matching`](skills/set-up-shopware-meta-advanced-matching/SKILL.md) | Meta Advanced Matching for Shopware |
| [`set-up-shopware-chatgpt-ads-customer-matching`](skills/set-up-shopware-chatgpt-ads-customer-matching/SKILL.md) | Customer data matching for ChatGPT Ads on Shopware |
| [`set-up-shopware-google-ads-customer-match`](skills/set-up-shopware-google-ads-customer-match/SKILL.md) | Google Ads Customer Match lists for Shopware |
| [`set-up-shopware-google-ads-new-customer-bidding`](skills/set-up-shopware-google-ads-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Shopware in Google Ads |
| [`set-up-shopware-meta-new-customer-bidding`](skills/set-up-shopware-meta-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Shopware in Meta |
| [`set-up-shopware-google-ads-returning-customer-bidding`](skills/set-up-shopware-google-ads-returning-customer-bidding/SKILL.md) | Returning customer bidding for Shopware in Google Ads |
| [`set-up-shopware-meta-returning-customer-bidding`](skills/set-up-shopware-meta-returning-customer-bidding/SKILL.md) | Returning customer bidding for Shopware in Meta |
| [`set-up-shopware-google-ads-poas-bidding`](skills/set-up-shopware-google-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Shopware in Google Ads |
| [`set-up-shopware-meta-poas-bidding`](skills/set-up-shopware-meta-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Shopware in Meta |
| [`set-up-shopware-chatgpt-ads-poas-bidding`](skills/set-up-shopware-chatgpt-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Shopware in ChatGPT Ads |
| [`set-up-shopware-google-ads-ltv-bidding`](skills/set-up-shopware-google-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Shopware in Google Ads |
| [`set-up-shopware-meta-ltv-bidding`](skills/set-up-shopware-meta-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Shopware in Meta |
| [`set-up-shopware-chatgpt-ads-ltv-bidding`](skills/set-up-shopware-chatgpt-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Shopware in ChatGPT Ads |

### Any website (Cloudflare)

| Skill | What it sets up |
| --- | --- |
| [`set-up-cloudflare-google-ads-conversion-tracking`](skills/set-up-cloudflare-google-ads-conversion-tracking/SKILL.md) | Server-side Google Ads conversion tracking for any website on Cloudflare (Cloudflare Tracking, no store plugin) |
| [`set-up-cloudflare-meta-conversions-api`](skills/set-up-cloudflare-meta-conversions-api/SKILL.md) | Meta Conversions API (CAPI) for any website on Cloudflare (Cloudflare Tracking, no store plugin) |
| [`set-up-cloudflare-chatgpt-ads-conversions-api`](skills/set-up-cloudflare-chatgpt-ads-conversions-api/SKILL.md) | ChatGPT Ads conversion tracking for any website on Cloudflare (Cloudflare Tracking, no store plugin) through the OpenAI Conversions API |
| [`set-up-cloudflare-google-ads-enhanced-conversions`](skills/set-up-cloudflare-google-ads-enhanced-conversions/SKILL.md) | Google Ads Enhanced Conversions for any website on Cloudflare (Cloudflare Tracking, no store plugin) |
| [`set-up-cloudflare-meta-advanced-matching`](skills/set-up-cloudflare-meta-advanced-matching/SKILL.md) | Meta Advanced Matching for any website on Cloudflare (Cloudflare Tracking, no store plugin) |
| [`set-up-cloudflare-chatgpt-ads-customer-matching`](skills/set-up-cloudflare-chatgpt-ads-customer-matching/SKILL.md) | Customer data matching for ChatGPT Ads on any website on Cloudflare (Cloudflare Tracking, no store plugin) |
| [`set-up-cloudflare-google-ads-customer-match`](skills/set-up-cloudflare-google-ads-customer-match/SKILL.md) | Google Ads Customer Match lists for any website on Cloudflare (Cloudflare Tracking, no store plugin) |
| [`set-up-cloudflare-google-ads-new-customer-bidding`](skills/set-up-cloudflare-google-ads-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Google Ads |
| [`set-up-cloudflare-meta-new-customer-bidding`](skills/set-up-cloudflare-meta-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Meta |
| [`set-up-cloudflare-google-ads-returning-customer-bidding`](skills/set-up-cloudflare-google-ads-returning-customer-bidding/SKILL.md) | Returning customer bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Google Ads |
| [`set-up-cloudflare-meta-returning-customer-bidding`](skills/set-up-cloudflare-meta-returning-customer-bidding/SKILL.md) | Returning customer bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Meta |
| [`set-up-cloudflare-google-ads-poas-bidding`](skills/set-up-cloudflare-google-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Google Ads |
| [`set-up-cloudflare-meta-poas-bidding`](skills/set-up-cloudflare-meta-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Meta |
| [`set-up-cloudflare-chatgpt-ads-poas-bidding`](skills/set-up-cloudflare-chatgpt-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in ChatGPT Ads |
| [`set-up-cloudflare-google-ads-ltv-bidding`](skills/set-up-cloudflare-google-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Google Ads |
| [`set-up-cloudflare-meta-ltv-bidding`](skills/set-up-cloudflare-meta-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Meta |
| [`set-up-cloudflare-chatgpt-ads-ltv-bidding`](skills/set-up-cloudflare-chatgpt-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in ChatGPT Ads |

## Skills by task, on any store

Start with `product-metrics` if you are not sure which skill fits: it routes to the right one for the store platform, channel and goal.

| Skill | What it does |
| --- | --- |
| [`analyse-google-ads`](skills/analyse-google-ads/SKILL.md) | Analyse a store's Google Ads performance through the Product Metrics MCP server |
| [`bid-on-ltv`](skills/bid-on-ltv/SKILL.md) | Set up LTV bidding: send each customer's lifetime revenue and profit to Google Ads, Meta and ChatGPT Ads with every paid order, and bid on customer lifetime value instead of the first order |
| [`bid-on-new-customers`](skills/bid-on-new-customers/SKILL.md) | Set up new customer bidding (new customer acquisition) in Google Ads, Meta and ChatGPT Ads: send each customer's first paid order as a separate new customer conversion and bid on it, so campaigns win new buyers instead of people who would buy anyway |
| [`bid-on-profit`](skills/bid-on-profit/SKILL.md) | Set up and check POAS (profit on ad spend) or ROAS bidding with Product Metrics in Google Ads and Meta: confirm the profit conversion actions exist, additional costs are active, the right action is primary, and the target ROAS fits the value sent |
| [`bid-on-returning-customers`](skills/bid-on-returning-customers/SKILL.md) | Set up returning customer bidding in Google Ads, Meta and ChatGPT Ads: send every paid repeat order as a separate returning customer conversion and bid on repeat buyers' revenue or profit, for retention and win-back campaigns |
| [`check-campaign-structure`](skills/check-campaign-structure/SKILL.md) | Check whether Google Shopping and Performance Max campaigns are built on the Product Metrics product segments, and read the results of the campaign plan |
| [`check-product-segments`](skills/check-product-segments/SKILL.md) | Product Metrics is a profit optimisation platform for ecommerce advertising: one app for server-side tracking, profit bidding, product segmentation and campaign planning across Google Ads, Meta and ChatGPT Ads |
| [`check-stock-and-returns`](skills/check-stock-and-returns/SKILL.md) | Check stock and product returns against advertising with Product Metrics: products advertised while out of stock or about to run out, reorder dates and suggested quantities, slow movers with too much stock, Stars that will run out, and return rates per category |
| [`check-tracking`](skills/check-tracking/SKILL.md) | Check that Product Metrics conversion tracking works for a store, with the productmetrics CLI or the Product Metrics MCP server: store connection active, store linked to the property, Google Ads conversion actions present, Enhanced Conversions accepted, Meta Conversions API destination connected, and the latest purchase received |
| [`connect-google-ads`](skills/connect-google-ads/SKILL.md) | Connect a Google Ads account and its Merchant Center to Product Metrics with the productmetrics CLI or the Product Metrics MCP server (search and execute tools) |
| [`find-unprofitable-products`](skills/find-unprofitable-products/SKILL.md) | Find the products that lose money after ads, with Product Metrics: products whose POAS (profit on ad spend) is below break-even, products priced above competitors while they are advertised, and products whose results fell, each with Product Metrics' decision (push, hold, reduce or pause) |
| [`product-metrics`](skills/product-metrics/SKILL.md) | Product Metrics is a profit optimisation platform for ecommerce advertising: one app for server-side tracking, profit bidding, product segmentation and campaign planning across Google Ads, Meta and ChatGPT Ads |
| [`set-up-product-segmentation`](skills/set-up-product-segmentation/SKILL.md) | Set up and tune Product Segmentation in Product Metrics for Google Shopping and Performance Max: which Merchant Center custom label carries the segments and the category priority, the segmentation settings (date range, category column, excluded campaigns, margin or POAS, a target ROAS anchor, seasonality and competitor prices), product rules that set or lock a segment, and generating the supplemental feed |
| [`set-up-tracking`](skills/set-up-tracking/SKILL.md) | Set up Product Metrics server-side conversion tracking end to end for a store owner, with the productmetrics CLI or the Product Metrics MCP server (search and execute tools): sign in, create or pick the workspace, connect the store (Shopify, WooCommerce, Shopware, Lightspeed, Magento or any website through Cloudflare Tracking), connect Google Ads and Meta, create the conversion actions, set consent and additional costs, and confirm the first purchase arrives |

## Licence

[MIT](LICENSE)
