---
name: set-up-lightspeed-google-ads-ltv-bidding
description: >-
  LTV (customer lifetime value) bidding for Lightspeed in Google Ads. Use this skill when a
  Lightspeed merchant wants Google Ads to value customers by what they spend over time: LTV or CLV
  bidding, or value-based bidding for repeat buyers. With every paid order it sends the customer's
  lifetime revenue and profit, so the campaign bids on customers who come back. It works through
  Product Metrics, so use it even when Product Metrics is never mentioned. Not for POAS, new
  customer or returning customer bidding: each has its own skill, as do other store platforms and ad
  channels.
license: MIT
metadata:
  author: Product Metrics
  version: "1.2.0"
  docs: https://www.productmetrics.io/docs/bidding/ltv/lightspeed-google-ads
---

# Lightspeed lifetime value (LTV) bidding in Google Ads

Send each customer's lifetime revenue and profit from Lightspeed to Google Ads and bid on it with a target ROAS. It matters because a first order understates customers who come back; lifetime value lets the campaign pay more for the customers worth more.

You run the Product Metrics steps through its CLI or MCP server; the person does the steps in Lightspeed and Google Ads. Read `references/working-with-product-metrics.md` once for how to work with both.

**All conversion actions by agents are secondary**, the status Product Metrics creates its actions with. Choosing what a campaign bids or optimises on (making an action primary, or picking the Meta or ChatGPT Ads conversion) is the person's step, by every route and also when they ask: give them the exact clicks, wait until they say it is done, then read it back.

## Workflow

1. **Read where setup stands** with `productmetrics setup get-status --json` (MCP: `setup.get_status`), and skip every step that is done.
2. **Make sure server-side tracking to Google Ads is live.** If it isn't, set it up first with `set-up-lightspeed-google-ads-conversion-tracking` (or `references/connect-lightspeed.md` and `references/connect-google-ads.md`).
3. **Follow `references/ltv-bidding.md`** step by step and confirm each **You should see** line before you move on: later steps depend on earlier ones (the consent banner decides what is sent for each order, and checks only pass once a test order has arrived).
4. **Hand the switch to the person.** They make the action they bid on primary and the old purchase action secondary in Google Ads (**Goals → Conversions**, or a campaign-specific goal), with the labels from the reference. This step is theirs. Wait until they say it is done, then read it back with `productmetrics google-ads get-conversion-actions --property-id <property_id> --json` (`goal_status`).
5. **Agree the target** with the facts below, and suggest one campaign first: switching the value resets what Google Ads learned about conversion value.
6. **Report back** what is live now, what the person still has to do (with the exact labels from the reference), and how to check it again later.

## Target ROAS facts

- A target ROAS is a percentage of the value sent. On a profit value, 100% is break-even and 150% keeps €0.50 profit per €1 of ad spend.
- An order with an unknown cost goes with revenue only; a loss-making order's profit is sent as 0.
- Set the target on what a customer is worth over time; don't copy the purchase action's target, because each LTV conversion carries what that order adds to the customer's lifetime value.
- In Google Ads, the person keeps **one** purchase action primary: the Product Metrics action they bid on. They set the old purchase action to secondary (or use a campaign-specific goal), so every purchase is counted once. Product Metrics creates its actions as secondary, as every conversion action by an agent is.

## References

| Read | When | Docs page |
| --- | --- | --- |
| `references/ltv-bidding.md` | LTV bidding: prerequisites, the steps, how it works on Lightspeed, troubleshooting and FAQ | https://www.productmetrics.io/docs/bidding/ltv/lightspeed-google-ads |
| `references/connect-lightspeed.md` | The Lightspeed store isn't connected yet, or its connection is broken | https://www.productmetrics.io/docs/platforms/lightspeed |
| `references/connect-google-ads.md` | Google Ads isn't connected yet, or you need the full list of what Product Metrics sends to it | https://www.productmetrics.io/docs/channels/google-ads |
| `references/working-with-product-metrics.md` | Before your first command: interface, rules, browser steps, secrets | https://www.productmetrics.io/docs/cli/for-agents |

If there is no `references/` folder next to this file (the skill was installed from the docs site), fetch the docs page in the last column instead, with `.md` appended for Markdown: it has the same steps.

## Related skills

- `set-up-lightspeed-google-ads-conversion-tracking`: Server-side tracking for Lightspeed in Google Ads
- `set-up-lightspeed-google-ads-enhanced-conversions`: Enhanced Conversions for Lightspeed in Google Ads
- `set-up-lightspeed-google-ads-customer-match`: Customer Match lists for Lightspeed in Google Ads
- `set-up-lightspeed-google-ads-new-customer-bidding`: New customer bidding for Lightspeed in Google Ads
- `set-up-lightspeed-google-ads-returning-customer-bidding`: Returning customer bidding for Lightspeed in Google Ads
- `set-up-lightspeed-google-ads-poas-bidding`: POAS and ROAS bidding for Lightspeed in Google Ads
- `set-up-lightspeed-meta-ltv-bidding`: LTV bidding for Lightspeed in Meta
- `set-up-lightspeed-chatgpt-ads-ltv-bidding`: LTV bidding for Lightspeed in ChatGPT Ads
- `bid-on-profit`: check POAS or ROAS bidding on any store
- `product-metrics`: picks the right skill for any store and channel

Install: `npx skills add product-metrics/skills --skill set-up-lightspeed-google-ads-ltv-bidding`. Every skill: https://www.productmetrics.io/docs/agent-skills/platform-skills.
