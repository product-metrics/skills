---
name: set-up-cloudflare-meta-returning-customer-bidding
description: >-
  Returning customer bidding for any website on Cloudflare (Cloudflare Tracking, no store plugin) in
  Meta. Use this skill when a merchant with a website on Cloudflare wants retention or win-back
  campaigns in Meta that value repeat orders. It sends every paid repeat order as a returning
  customer conversion, with its revenue or profit, to bid on. It works through Product Metrics, so
  use it even when Product Metrics is never mentioned. Not for new customer, POAS or LTV bidding:
  each has its own skill, as do other store platforms and ad channels.
license: MIT
metadata:
  author: Product Metrics
  version: "1.2.0"
  docs: https://www.productmetrics.io/docs/bidding/returning-customers/cloudflare-meta
---

# Returning customer bidding in Meta on any website with Cloudflare

Send repeat orders from your website to Meta as PMReturningCustomer through the Meta Conversions API with Advanced Matching, and optimise a campaign on a custom conversion. It matters because a retention campaign should value repeat orders, and only those.

You run the Product Metrics steps through its CLI or MCP server; the person does the steps in Cloudflare and Meta. Read `references/working-with-product-metrics.md` once for how to work with both.

**All conversion actions by agents are secondary**, the status Product Metrics creates its actions with. Choosing what a campaign bids or optimises on (making an action primary, or picking the Meta or ChatGPT Ads conversion) is the person's step, by every route and also when they ask: give them the exact clicks, wait until they say it is done, then read it back.

## Workflow

1. **Read where setup stands** with `productmetrics setup get-status --json` (MCP: `setup.get_status`), and skip every step that is done.
2. **Make sure server-side tracking to Meta is live.** If it isn't, set it up first with `set-up-cloudflare-meta-conversions-api` (or `references/connect-cloudflare.md` and `references/connect-meta.md`).
3. **Follow `references/returning-customer-bidding.md`** step by step and confirm each **You should see** line before you move on: later steps depend on earlier ones (the consent banner decides what is sent for each order, and checks only pass once a test order has arrived).
4. **Hand the switch to the person.** They create the custom conversion in Meta Events Manager and select it as the ad set's optimisation event, with the labels from the reference. This step is theirs. Wait until they say it is done.
5. **Agree the target** with the facts below, and suggest one campaign first.
6. **Report back** what is live now, what the person still has to do (with the exact labels from the reference), and how to check it again later.

## Target ROAS facts

- A target ROAS is a percentage of the value sent. On a profit value, 100% is break-even and 150% keeps €0.50 profit per €1 of ad spend.
- An order with an unknown cost goes with revenue only; a loss-making order's profit is sent as 0.
- Usually only the campaign that serves returning customers bids on this value; the others keep their current goal.
- In Meta, the person optimises on a custom conversion built on the Product Metrics event for this goal (for profit: `PMOrderProfit` with the rule `pm_purpose` equals `ORDER_PROFIT`), which they select themselves. An event only appears in Meta's selector after Meta has received one, so a test order comes first.

## References

| Read | When | Docs page |
| --- | --- | --- |
| `references/returning-customer-bidding.md` | Returning customer bidding: prerequisites, the steps, how it works on any website on Cloudflare, troubleshooting and FAQ | https://www.productmetrics.io/docs/bidding/returning-customers/cloudflare-meta |
| `references/connect-cloudflare.md` | The website isn't connected yet, or its connection is broken | https://www.productmetrics.io/docs/platforms/cloudflare |
| `references/connect-meta.md` | Meta isn't connected yet, or you need the full list of what Product Metrics sends to it | https://www.productmetrics.io/docs/channels/meta |
| `references/working-with-product-metrics.md` | Before your first command: interface, rules, browser steps, secrets | https://www.productmetrics.io/docs/cli/for-agents |

If there is no `references/` folder next to this file (the skill was installed from the docs site), fetch the docs page in the last column instead, with `.md` appended for Markdown: it has the same steps.

## Related skills

- `set-up-cloudflare-meta-conversions-api`: Server-side tracking for any website on Cloudflare in Meta
- `set-up-cloudflare-meta-advanced-matching`: Advanced Matching for any website on Cloudflare in Meta
- `set-up-cloudflare-meta-new-customer-bidding`: New customer bidding for any website on Cloudflare in Meta
- `set-up-cloudflare-meta-poas-bidding`: POAS and ROAS bidding for any website on Cloudflare in Meta
- `set-up-cloudflare-meta-ltv-bidding`: LTV bidding for any website on Cloudflare in Meta
- `set-up-cloudflare-google-ads-returning-customer-bidding`: Returning customer bidding for any website on Cloudflare in Google Ads
- `bid-on-profit`: check POAS or ROAS bidding on any store
- `product-metrics`: picks the right skill for any store and channel

Install: `npx skills add product-metrics/skills --skill set-up-cloudflare-meta-returning-customer-bidding`. Every skill: https://www.productmetrics.io/docs/agent-skills/platform-skills.
