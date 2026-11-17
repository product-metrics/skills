# Product Metrics agent skills

Agent Skills that set up **server-side conversion tracking** and **profit (POAS) bidding** for online stores in **Google Ads**, **Meta** and **ChatGPT Ads**, with [Product Metrics](https://www.productmetrics.io). One skill for every setup task, store platform and ad channel: server-side tracking, Enhanced Conversions and Advanced Matching, Customer Match lists, and POAS, new customer, returning customer and LTV bidding, for Shopify, WooCommerce, Lightspeed, Magento, Shopware and any website on Cloudflare.

The skills follow the [Agent Skills](https://agentskills.io) format and work in Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI and other agents that read `SKILL.md` files. Each is a short `SKILL.md` with the workflow and a `references/` folder with the full steps, generated from the [Product Metrics docs](https://www.productmetrics.io/docs) so every step matches the docs page it links to.

## Install

```bash
# pick from every skill
npx skills add product-metrics/skills

# one skill
npx skills add product-metrics/skills --skill set-up-shopify-meta-conversions-api
```

As a plugin, one per store platform. Each plugin also connects the [Product Metrics MCP server](https://www.productmetrics.io/docs/mcp/overview).

| Store | Claude Code |
| --- | --- |
| Any store | `/plugin install product-metrics --marketplace product-metrics/skills` |
| Shopify | `/plugin install product-metrics-shopify --marketplace product-metrics/skills` |
| WooCommerce | `/plugin install product-metrics-woocommerce --marketplace product-metrics/skills` |
| Lightspeed | `/plugin install product-metrics-lightspeed --marketplace product-metrics/skills` |
| Magento | `/plugin install product-metrics-magento --marketplace product-metrics/skills` |
| Shopware | `/plugin install product-metrics-shopware --marketplace product-metrics/skills` |
| Any website (Cloudflare) | `/plugin install product-metrics-cloudflare --marketplace product-metrics/skills` |

On Claude Code before 2.1.275, add the marketplace first: `claude plugin marketplace add product-metrics/skills`, then `claude plugin install product-metrics-shopify@product-metrics`. Cursor and Codex read the same repository as a plugin marketplace (`.cursor-plugin/marketplace.json`, `.agents/plugins/marketplace.json`); Gemini CLI installs it as an extension: `gemini extensions install https://github.com/product-metrics/skills`.

## Skills by store platform

Names follow `set-up-<platform>-<channel>-<task>`. Start with server-side tracking, add customer data for matching, then pick a bidding goal.

### Shopify

Plugin `product-metrics-shopify`:

| Skill | What it sets up |
| --- | --- |
| [`set-up-shopify-google-ads-conversion-tracking`](plugins/product-metrics-shopify/skills/set-up-shopify-google-ads-conversion-tracking/SKILL.md) | Server-side Google Ads conversion tracking for Shopify |
| [`set-up-shopify-meta-conversions-api`](plugins/product-metrics-shopify/skills/set-up-shopify-meta-conversions-api/SKILL.md) | Meta Conversions API (CAPI) for Shopify |
| [`set-up-shopify-chatgpt-ads-conversions-api`](plugins/product-metrics-shopify/skills/set-up-shopify-chatgpt-ads-conversions-api/SKILL.md) | ChatGPT Ads conversion tracking for Shopify through the OpenAI Conversions API |
| [`set-up-shopify-google-ads-enhanced-conversions`](plugins/product-metrics-shopify/skills/set-up-shopify-google-ads-enhanced-conversions/SKILL.md) | Google Ads Enhanced Conversions for Shopify |
| [`set-up-shopify-meta-advanced-matching`](plugins/product-metrics-shopify/skills/set-up-shopify-meta-advanced-matching/SKILL.md) | Meta Advanced Matching for Shopify |
| [`set-up-shopify-chatgpt-ads-customer-matching`](plugins/product-metrics-shopify/skills/set-up-shopify-chatgpt-ads-customer-matching/SKILL.md) | Customer data matching for ChatGPT Ads on Shopify |
| [`set-up-shopify-google-ads-customer-match`](plugins/product-metrics-shopify/skills/set-up-shopify-google-ads-customer-match/SKILL.md) | Google Ads Customer Match lists for Shopify |
| [`set-up-shopify-google-ads-new-customer-bidding`](plugins/product-metrics-shopify/skills/set-up-shopify-google-ads-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Shopify in Google Ads |
| [`set-up-shopify-meta-new-customer-bidding`](plugins/product-metrics-shopify/skills/set-up-shopify-meta-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Shopify in Meta |
| [`set-up-shopify-google-ads-returning-customer-bidding`](plugins/product-metrics-shopify/skills/set-up-shopify-google-ads-returning-customer-bidding/SKILL.md) | Returning customer bidding for Shopify in Google Ads |
| [`set-up-shopify-meta-returning-customer-bidding`](plugins/product-metrics-shopify/skills/set-up-shopify-meta-returning-customer-bidding/SKILL.md) | Returning customer bidding for Shopify in Meta |
| [`set-up-shopify-google-ads-poas-bidding`](plugins/product-metrics-shopify/skills/set-up-shopify-google-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Shopify in Google Ads |
| [`set-up-shopify-meta-poas-bidding`](plugins/product-metrics-shopify/skills/set-up-shopify-meta-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Shopify in Meta |
| [`set-up-shopify-chatgpt-ads-poas-bidding`](plugins/product-metrics-shopify/skills/set-up-shopify-chatgpt-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Shopify in ChatGPT Ads |
| [`set-up-shopify-google-ads-ltv-bidding`](plugins/product-metrics-shopify/skills/set-up-shopify-google-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Shopify in Google Ads |
| [`set-up-shopify-meta-ltv-bidding`](plugins/product-metrics-shopify/skills/set-up-shopify-meta-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Shopify in Meta |
| [`set-up-shopify-chatgpt-ads-ltv-bidding`](plugins/product-metrics-shopify/skills/set-up-shopify-chatgpt-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Shopify in ChatGPT Ads |

### WooCommerce

Plugin `product-metrics-woocommerce`:

| Skill | What it sets up |
| --- | --- |
| [`set-up-woocommerce-google-ads-conversion-tracking`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-google-ads-conversion-tracking/SKILL.md) | Server-side Google Ads conversion tracking for WooCommerce (WordPress) |
| [`set-up-woocommerce-meta-conversions-api`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-meta-conversions-api/SKILL.md) | Meta Conversions API (CAPI) for WooCommerce (WordPress) |
| [`set-up-woocommerce-chatgpt-ads-conversions-api`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-chatgpt-ads-conversions-api/SKILL.md) | ChatGPT Ads conversion tracking for WooCommerce (WordPress) through the OpenAI Conversions API |
| [`set-up-woocommerce-google-ads-enhanced-conversions`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-google-ads-enhanced-conversions/SKILL.md) | Google Ads Enhanced Conversions for WooCommerce (WordPress) |
| [`set-up-woocommerce-meta-advanced-matching`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-meta-advanced-matching/SKILL.md) | Meta Advanced Matching for WooCommerce (WordPress) |
| [`set-up-woocommerce-chatgpt-ads-customer-matching`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-chatgpt-ads-customer-matching/SKILL.md) | Customer data matching for ChatGPT Ads on WooCommerce (WordPress) |
| [`set-up-woocommerce-google-ads-customer-match`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-google-ads-customer-match/SKILL.md) | Google Ads Customer Match lists for WooCommerce (WordPress) |
| [`set-up-woocommerce-google-ads-new-customer-bidding`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-google-ads-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for WooCommerce (WordPress) in Google Ads |
| [`set-up-woocommerce-meta-new-customer-bidding`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-meta-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for WooCommerce (WordPress) in Meta |
| [`set-up-woocommerce-google-ads-returning-customer-bidding`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-google-ads-returning-customer-bidding/SKILL.md) | Returning customer bidding for WooCommerce (WordPress) in Google Ads |
| [`set-up-woocommerce-meta-returning-customer-bidding`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-meta-returning-customer-bidding/SKILL.md) | Returning customer bidding for WooCommerce (WordPress) in Meta |
| [`set-up-woocommerce-google-ads-poas-bidding`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-google-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for WooCommerce (WordPress) in Google Ads |
| [`set-up-woocommerce-meta-poas-bidding`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-meta-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for WooCommerce (WordPress) in Meta |
| [`set-up-woocommerce-chatgpt-ads-poas-bidding`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-chatgpt-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for WooCommerce (WordPress) in ChatGPT Ads |
| [`set-up-woocommerce-google-ads-ltv-bidding`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-google-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for WooCommerce (WordPress) in Google Ads |
| [`set-up-woocommerce-meta-ltv-bidding`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-meta-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for WooCommerce (WordPress) in Meta |
| [`set-up-woocommerce-chatgpt-ads-ltv-bidding`](plugins/product-metrics-woocommerce/skills/set-up-woocommerce-chatgpt-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for WooCommerce (WordPress) in ChatGPT Ads |

### Lightspeed

Plugin `product-metrics-lightspeed`:

| Skill | What it sets up |
| --- | --- |
| [`set-up-lightspeed-google-ads-conversion-tracking`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-google-ads-conversion-tracking/SKILL.md) | Server-side Google Ads conversion tracking for Lightspeed |
| [`set-up-lightspeed-meta-conversions-api`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-meta-conversions-api/SKILL.md) | Meta Conversions API (CAPI) for Lightspeed |
| [`set-up-lightspeed-chatgpt-ads-conversions-api`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-chatgpt-ads-conversions-api/SKILL.md) | ChatGPT Ads conversion tracking for Lightspeed through the OpenAI Conversions API |
| [`set-up-lightspeed-google-ads-enhanced-conversions`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-google-ads-enhanced-conversions/SKILL.md) | Google Ads Enhanced Conversions for Lightspeed |
| [`set-up-lightspeed-meta-advanced-matching`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-meta-advanced-matching/SKILL.md) | Meta Advanced Matching for Lightspeed |
| [`set-up-lightspeed-chatgpt-ads-customer-matching`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-chatgpt-ads-customer-matching/SKILL.md) | Customer data matching for ChatGPT Ads on Lightspeed |
| [`set-up-lightspeed-google-ads-customer-match`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-google-ads-customer-match/SKILL.md) | Google Ads Customer Match lists for Lightspeed |
| [`set-up-lightspeed-google-ads-new-customer-bidding`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-google-ads-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Lightspeed in Google Ads |
| [`set-up-lightspeed-meta-new-customer-bidding`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-meta-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Lightspeed in Meta |
| [`set-up-lightspeed-google-ads-returning-customer-bidding`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-google-ads-returning-customer-bidding/SKILL.md) | Returning customer bidding for Lightspeed in Google Ads |
| [`set-up-lightspeed-meta-returning-customer-bidding`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-meta-returning-customer-bidding/SKILL.md) | Returning customer bidding for Lightspeed in Meta |
| [`set-up-lightspeed-google-ads-poas-bidding`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-google-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Lightspeed in Google Ads |
| [`set-up-lightspeed-meta-poas-bidding`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-meta-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Lightspeed in Meta |
| [`set-up-lightspeed-chatgpt-ads-poas-bidding`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-chatgpt-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Lightspeed in ChatGPT Ads |
| [`set-up-lightspeed-google-ads-ltv-bidding`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-google-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Lightspeed in Google Ads |
| [`set-up-lightspeed-meta-ltv-bidding`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-meta-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Lightspeed in Meta |
| [`set-up-lightspeed-chatgpt-ads-ltv-bidding`](plugins/product-metrics-lightspeed/skills/set-up-lightspeed-chatgpt-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Lightspeed in ChatGPT Ads |

### Magento

Plugin `product-metrics-magento`:

| Skill | What it sets up |
| --- | --- |
| [`set-up-magento-google-ads-conversion-tracking`](plugins/product-metrics-magento/skills/set-up-magento-google-ads-conversion-tracking/SKILL.md) | Server-side Google Ads conversion tracking for Magento (Adobe Commerce) |
| [`set-up-magento-meta-conversions-api`](plugins/product-metrics-magento/skills/set-up-magento-meta-conversions-api/SKILL.md) | Meta Conversions API (CAPI) for Magento (Adobe Commerce) |
| [`set-up-magento-chatgpt-ads-conversions-api`](plugins/product-metrics-magento/skills/set-up-magento-chatgpt-ads-conversions-api/SKILL.md) | ChatGPT Ads conversion tracking for Magento (Adobe Commerce) through the OpenAI Conversions API |
| [`set-up-magento-google-ads-enhanced-conversions`](plugins/product-metrics-magento/skills/set-up-magento-google-ads-enhanced-conversions/SKILL.md) | Google Ads Enhanced Conversions for Magento (Adobe Commerce) |
| [`set-up-magento-meta-advanced-matching`](plugins/product-metrics-magento/skills/set-up-magento-meta-advanced-matching/SKILL.md) | Meta Advanced Matching for Magento (Adobe Commerce) |
| [`set-up-magento-chatgpt-ads-customer-matching`](plugins/product-metrics-magento/skills/set-up-magento-chatgpt-ads-customer-matching/SKILL.md) | Customer data matching for ChatGPT Ads on Magento (Adobe Commerce) |
| [`set-up-magento-google-ads-customer-match`](plugins/product-metrics-magento/skills/set-up-magento-google-ads-customer-match/SKILL.md) | Google Ads Customer Match lists for Magento (Adobe Commerce) |
| [`set-up-magento-google-ads-new-customer-bidding`](plugins/product-metrics-magento/skills/set-up-magento-google-ads-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Magento (Adobe Commerce) in Google Ads |
| [`set-up-magento-meta-new-customer-bidding`](plugins/product-metrics-magento/skills/set-up-magento-meta-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Magento (Adobe Commerce) in Meta |
| [`set-up-magento-google-ads-returning-customer-bidding`](plugins/product-metrics-magento/skills/set-up-magento-google-ads-returning-customer-bidding/SKILL.md) | Returning customer bidding for Magento (Adobe Commerce) in Google Ads |
| [`set-up-magento-meta-returning-customer-bidding`](plugins/product-metrics-magento/skills/set-up-magento-meta-returning-customer-bidding/SKILL.md) | Returning customer bidding for Magento (Adobe Commerce) in Meta |
| [`set-up-magento-google-ads-poas-bidding`](plugins/product-metrics-magento/skills/set-up-magento-google-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Magento (Adobe Commerce) in Google Ads |
| [`set-up-magento-meta-poas-bidding`](plugins/product-metrics-magento/skills/set-up-magento-meta-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Magento (Adobe Commerce) in Meta |
| [`set-up-magento-chatgpt-ads-poas-bidding`](plugins/product-metrics-magento/skills/set-up-magento-chatgpt-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Magento (Adobe Commerce) in ChatGPT Ads |
| [`set-up-magento-google-ads-ltv-bidding`](plugins/product-metrics-magento/skills/set-up-magento-google-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Magento (Adobe Commerce) in Google Ads |
| [`set-up-magento-meta-ltv-bidding`](plugins/product-metrics-magento/skills/set-up-magento-meta-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Magento (Adobe Commerce) in Meta |
| [`set-up-magento-chatgpt-ads-ltv-bidding`](plugins/product-metrics-magento/skills/set-up-magento-chatgpt-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Magento (Adobe Commerce) in ChatGPT Ads |

### Shopware

Plugin `product-metrics-shopware`:

| Skill | What it sets up |
| --- | --- |
| [`set-up-shopware-google-ads-conversion-tracking`](plugins/product-metrics-shopware/skills/set-up-shopware-google-ads-conversion-tracking/SKILL.md) | Server-side Google Ads conversion tracking for Shopware |
| [`set-up-shopware-meta-conversions-api`](plugins/product-metrics-shopware/skills/set-up-shopware-meta-conversions-api/SKILL.md) | Meta Conversions API (CAPI) for Shopware |
| [`set-up-shopware-chatgpt-ads-conversions-api`](plugins/product-metrics-shopware/skills/set-up-shopware-chatgpt-ads-conversions-api/SKILL.md) | ChatGPT Ads conversion tracking for Shopware through the OpenAI Conversions API |
| [`set-up-shopware-google-ads-enhanced-conversions`](plugins/product-metrics-shopware/skills/set-up-shopware-google-ads-enhanced-conversions/SKILL.md) | Google Ads Enhanced Conversions for Shopware |
| [`set-up-shopware-meta-advanced-matching`](plugins/product-metrics-shopware/skills/set-up-shopware-meta-advanced-matching/SKILL.md) | Meta Advanced Matching for Shopware |
| [`set-up-shopware-chatgpt-ads-customer-matching`](plugins/product-metrics-shopware/skills/set-up-shopware-chatgpt-ads-customer-matching/SKILL.md) | Customer data matching for ChatGPT Ads on Shopware |
| [`set-up-shopware-google-ads-customer-match`](plugins/product-metrics-shopware/skills/set-up-shopware-google-ads-customer-match/SKILL.md) | Google Ads Customer Match lists for Shopware |
| [`set-up-shopware-google-ads-new-customer-bidding`](plugins/product-metrics-shopware/skills/set-up-shopware-google-ads-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Shopware in Google Ads |
| [`set-up-shopware-meta-new-customer-bidding`](plugins/product-metrics-shopware/skills/set-up-shopware-meta-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for Shopware in Meta |
| [`set-up-shopware-google-ads-returning-customer-bidding`](plugins/product-metrics-shopware/skills/set-up-shopware-google-ads-returning-customer-bidding/SKILL.md) | Returning customer bidding for Shopware in Google Ads |
| [`set-up-shopware-meta-returning-customer-bidding`](plugins/product-metrics-shopware/skills/set-up-shopware-meta-returning-customer-bidding/SKILL.md) | Returning customer bidding for Shopware in Meta |
| [`set-up-shopware-google-ads-poas-bidding`](plugins/product-metrics-shopware/skills/set-up-shopware-google-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Shopware in Google Ads |
| [`set-up-shopware-meta-poas-bidding`](plugins/product-metrics-shopware/skills/set-up-shopware-meta-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Shopware in Meta |
| [`set-up-shopware-chatgpt-ads-poas-bidding`](plugins/product-metrics-shopware/skills/set-up-shopware-chatgpt-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for Shopware in ChatGPT Ads |
| [`set-up-shopware-google-ads-ltv-bidding`](plugins/product-metrics-shopware/skills/set-up-shopware-google-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Shopware in Google Ads |
| [`set-up-shopware-meta-ltv-bidding`](plugins/product-metrics-shopware/skills/set-up-shopware-meta-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Shopware in Meta |
| [`set-up-shopware-chatgpt-ads-ltv-bidding`](plugins/product-metrics-shopware/skills/set-up-shopware-chatgpt-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for Shopware in ChatGPT Ads |

### Any website (Cloudflare)

Plugin `product-metrics-cloudflare`:

| Skill | What it sets up |
| --- | --- |
| [`set-up-cloudflare-google-ads-conversion-tracking`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-google-ads-conversion-tracking/SKILL.md) | Server-side Google Ads conversion tracking for any website on Cloudflare (Cloudflare Tracking, no store plugin) |
| [`set-up-cloudflare-meta-conversions-api`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-meta-conversions-api/SKILL.md) | Meta Conversions API (CAPI) for any website on Cloudflare (Cloudflare Tracking, no store plugin) |
| [`set-up-cloudflare-chatgpt-ads-conversions-api`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-chatgpt-ads-conversions-api/SKILL.md) | ChatGPT Ads conversion tracking for any website on Cloudflare (Cloudflare Tracking, no store plugin) through the OpenAI Conversions API |
| [`set-up-cloudflare-google-ads-enhanced-conversions`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-google-ads-enhanced-conversions/SKILL.md) | Google Ads Enhanced Conversions for any website on Cloudflare (Cloudflare Tracking, no store plugin) |
| [`set-up-cloudflare-meta-advanced-matching`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-meta-advanced-matching/SKILL.md) | Meta Advanced Matching for any website on Cloudflare (Cloudflare Tracking, no store plugin) |
| [`set-up-cloudflare-chatgpt-ads-customer-matching`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-chatgpt-ads-customer-matching/SKILL.md) | Customer data matching for ChatGPT Ads on any website on Cloudflare (Cloudflare Tracking, no store plugin) |
| [`set-up-cloudflare-google-ads-customer-match`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-google-ads-customer-match/SKILL.md) | Google Ads Customer Match lists for any website on Cloudflare (Cloudflare Tracking, no store plugin) |
| [`set-up-cloudflare-google-ads-new-customer-bidding`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-google-ads-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Google Ads |
| [`set-up-cloudflare-meta-new-customer-bidding`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-meta-new-customer-bidding/SKILL.md) | New customer bidding (new customer acquisition) for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Meta |
| [`set-up-cloudflare-google-ads-returning-customer-bidding`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-google-ads-returning-customer-bidding/SKILL.md) | Returning customer bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Google Ads |
| [`set-up-cloudflare-meta-returning-customer-bidding`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-meta-returning-customer-bidding/SKILL.md) | Returning customer bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Meta |
| [`set-up-cloudflare-google-ads-poas-bidding`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-google-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Google Ads |
| [`set-up-cloudflare-meta-poas-bidding`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-meta-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Meta |
| [`set-up-cloudflare-chatgpt-ads-poas-bidding`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-chatgpt-ads-poas-bidding/SKILL.md) | POAS (profit on ad spend) bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in ChatGPT Ads |
| [`set-up-cloudflare-google-ads-ltv-bidding`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-google-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Google Ads |
| [`set-up-cloudflare-meta-ltv-bidding`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-meta-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in Meta |
| [`set-up-cloudflare-chatgpt-ads-ltv-bidding`](plugins/product-metrics-cloudflare/skills/set-up-cloudflare-chatgpt-ads-ltv-bidding/SKILL.md) | LTV (customer lifetime value) bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in ChatGPT Ads |

## Skills for any store

In the `product-metrics` plugin:

| Skill | What it does |
| --- | --- |
| [`analyse-google-ads`](plugins/product-metrics/skills/analyse-google-ads/SKILL.md) | Analyse a store's Google Ads performance through the Product Metrics MCP server. |
| [`bid-on-ltv`](plugins/product-metrics/skills/bid-on-ltv/SKILL.md) | Set up LTV bidding: send each customer's lifetime revenue and profit to Google Ads, Meta and ChatGPT Ads with every paid order, and bid on customer lifetime value instead of the first order. |
| [`bid-on-new-customers`](plugins/product-metrics/skills/bid-on-new-customers/SKILL.md) | Set up new customer bidding (new customer acquisition) in Google Ads, Meta and ChatGPT Ads: send each customer's first paid order as a separate new customer conversion and bid on it, so campaigns win new buyers instead of people who would buy anyway. |
| [`bid-on-profit`](plugins/product-metrics/skills/bid-on-profit/SKILL.md) | Set up and check POAS (profit on ad spend) or ROAS bidding with Product Metrics in Google Ads and Meta: confirm the profit conversion actions exist, additional costs are active, the right action is primary, and the target ROAS fits the value sent. |
| [`bid-on-returning-customers`](plugins/product-metrics/skills/bid-on-returning-customers/SKILL.md) | Set up returning customer bidding in Google Ads, Meta and ChatGPT Ads: send every paid repeat order as a separate returning customer conversion and bid on repeat buyers' revenue or profit, for retention and win-back campaigns. |
| [`check-tracking`](plugins/product-metrics/skills/check-tracking/SKILL.md) | Check that Product Metrics conversion tracking works for a store, with the productmetrics CLI or the Product Metrics MCP server: store connection active, store linked to the property, Google Ads conversion actions present, Enhanced Conversions accepted, Meta Conversions API destination connected, and the latest purchase received. |
| [`connect-google-ads`](plugins/product-metrics/skills/connect-google-ads/SKILL.md) | Connect a Google Ads account and its Merchant Center to Product Metrics with the productmetrics CLI or the Product Metrics MCP server (search and execute tools). |
| [`product-metrics`](plugins/product-metrics/skills/product-metrics/SKILL.md) | Product Metrics is a profit optimisation platform for ecommerce advertising: server-side conversion tracking, POAS (profit) bidding, new and returning customer and LTV bidding, product segmentation and campaign planning across Google Ads, Meta and ChatGPT Ads, for Shopify, WooCommerce, Lightspeed, Magento, Shopware and any website on Cloudflare. |
| [`set-up-tracking`](plugins/product-metrics/skills/set-up-tracking/SKILL.md) | Set up Product Metrics server-side conversion tracking end to end for a store owner, with the productmetrics CLI or the Product Metrics MCP server (search and execute tools): sign in, create or pick the workspace, connect the store (Shopify, WooCommerce, Shopware, Lightspeed, Magento or any website through Cloudflare Tracking), connect Google Ads and Meta, create the conversion actions, set consent and additional costs, and confirm the first purchase arrives. |

Start with `product-metrics` if you are not sure which skill fits: it routes to the right one for the store platform, channel and goal.

## What the plugins run and send

**What it runs and sends.** No hooks, scripts or telemetry. The plugin adds the Product Metrics MCP server (`https://www.productmetrics.io/mcp`, remote, OAuth sign-in): when the agent calls it, it reads and changes your own Product Metrics account (stores, tracking setup, Google Ads, Meta and ChatGPT Ads connections, reports). The skills may also tell the agent to run the `productmetrics` CLI if you have it installed, and to fetch public pages from https://www.productmetrics.io/docs. Steps in your store admin or ad platform are always handed to you. Privacy: https://www.productmetrics.io/privacy. Terms: https://www.productmetrics.io/terms. Support: https://www.productmetrics.io/contact.

## Docs

- [Agent skills](https://www.productmetrics.io/docs/agent-skills/overview), [skills by platform and channel](https://www.productmetrics.io/docs/agent-skills/platform-skills) and [install options](https://www.productmetrics.io/docs/agent-skills/install)
- [Tracking and bidding guides](https://www.productmetrics.io/docs/platforms/overview) for each store platform
- [MCP server](https://www.productmetrics.io/docs/mcp/overview) and [CLI](https://www.productmetrics.io/docs/cli/overview)

## Contributing

This repository is generated from the Product Metrics docs. Report a wrong step as an issue; pull requests to the skill files are overwritten by the next sync.

## Licence

[MIT](LICENSE)
