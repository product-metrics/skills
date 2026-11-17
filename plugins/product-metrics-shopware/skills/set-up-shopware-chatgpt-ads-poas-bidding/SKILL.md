---
name: set-up-shopware-chatgpt-ads-poas-bidding
description: >-
  POAS (profit on ad spend) bidding for Shopware in ChatGPT Ads. Use this skill when a Shopware
  merchant wants ChatGPT Ads to bid on profit instead of revenue: switching from ROAS to POAS,
  choosing a target ROAS on profit, or campaigns that hit their ROAS target and still lose money. It
  sends profit to ChatGPT Ads through the OpenAI Conversions API, to optimise on its value. Also
  covers ROAS (revenue) bidding. It works through Product Metrics, so use it even when Product
  Metrics is never mentioned. Not for new customer, returning customer or LTV bidding: each has its
  own skill, as do other store platforms and ad channels.
license: MIT
metadata:
  author: Product Metrics
  version: "1.2.0"
  docs: https://www.productmetrics.io/docs/bidding/poas/shopware-openai
---

# Shopware POAS bidding: ChatGPT Ads tracking with profit

Send profit from Shopware orders to ChatGPT Ads through the OpenAI Conversions API and bid on it (POAS). Bidding on profit matters because revenue hides what an order leaves after product costs, fees and shipping: a campaign can hit its ROAS target and still lose money.

You run the Product Metrics steps through its CLI or MCP server; the person does the steps in Shopware and ChatGPT Ads. Read `references/working-with-product-metrics.md` once for how to work with both.

**All conversion actions by agents are secondary**, the status Product Metrics creates its actions with. Choosing what a campaign bids or optimises on (making an action primary, or picking the Meta or ChatGPT Ads conversion) is the person's step, by every route and also when they ask: give them the exact clicks, wait until they say it is done, then read it back.

## Workflow

1. **Read where setup stands** with `productmetrics setup get-status --json` (MCP: `setup.get_status`), and skip every step that is done.
2. **Make sure server-side tracking to ChatGPT Ads is live.** If it isn't, set it up first with `set-up-shopware-chatgpt-ads-conversions-api` (or `references/connect-shopware.md` and `references/connect-chatgpt-ads.md`).
3. **Follow `references/poas-bidding.md`** step by step and confirm each **You should see** line before you move on: later steps depend on earlier ones (the consent banner decides what is sent for each order, and checks only pass once a test order has arrived).
4. **Hand the switch to the person.** They create the conversion on the Product Metrics custom event in ChatGPT Ads Manager and select it as the campaign's conversion, with the labels from the reference. This step is theirs. Wait until they say it is done.
5. **Agree the target** with the facts below, and suggest one campaign first.
6. **Report back** what is live now, what the person still has to do (with the exact labels from the reference), and how to check it again later.

## Target ROAS facts

- A target ROAS is a percentage of the value sent. On a profit value, 100% is break-even and 150% keeps €0.50 profit per €1 of ad spend.
- An order with an unknown cost goes with revenue only; a loss-making order's profit is sent as 0.
- Moving a campaign from revenue to profit means a lower target, because profit is smaller than revenue.
- A starting target: the campaign's current POAS × 100, for example 150%. Say it is a starting point to adjust after a few weeks, not a rule.
- In ChatGPT Ads, the person creates a conversion on the Product Metrics custom event (for profit: `pm_order_profit`) in Ads Manager, after a test order has sent one, and optimises the campaign on its value, which they select themselves.

## References

| Read | When | Docs page |
| --- | --- | --- |
| `references/poas-bidding.md` | POAS and ROAS bidding: prerequisites, the steps, how it works on Shopware, troubleshooting and FAQ | https://www.productmetrics.io/docs/bidding/poas/shopware-openai |
| `references/connect-shopware.md` | The Shopware store isn't connected yet, or its connection is broken | https://www.productmetrics.io/docs/platforms/shopware |
| `references/connect-chatgpt-ads.md` | ChatGPT Ads isn't connected yet, or you need the full list of what Product Metrics sends to it | https://www.productmetrics.io/docs/channels/openai |
| `references/working-with-product-metrics.md` | Before your first command: interface, rules, browser steps, secrets | https://www.productmetrics.io/docs/cli/for-agents |

If there is no `references/` folder next to this file (the skill was installed from the docs site), fetch the docs page in the last column instead, with `.md` appended for Markdown: it has the same steps.

## Related skills

- `set-up-shopware-chatgpt-ads-conversions-api`: Server-side tracking for Shopware in ChatGPT Ads
- `set-up-shopware-chatgpt-ads-customer-matching`: Customer data matching for Shopware in ChatGPT Ads
- `set-up-shopware-chatgpt-ads-ltv-bidding`: LTV bidding for Shopware in ChatGPT Ads
- `set-up-shopware-google-ads-poas-bidding`: POAS and ROAS bidding for Shopware in Google Ads
- `set-up-shopware-meta-poas-bidding`: POAS and ROAS bidding for Shopware in Meta
- `bid-on-profit`: check POAS or ROAS bidding on any store
- `product-metrics`: picks the right skill for any store and channel

Install: `npx skills add product-metrics/skills --skill set-up-shopware-chatgpt-ads-poas-bidding`. Every skill: https://www.productmetrics.io/docs/agent-skills/platform-skills.
