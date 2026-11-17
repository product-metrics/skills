# Working with Product Metrics from an agent

Product Metrics (https://www.productmetrics.io) reads each paid order from the store, works out its revenue, profit, new or returning customer and lifetime value, and sends it server-side to Google Ads, Meta and ChatGPT Ads. You drive the steps that have an API; the person does the steps that need them in a browser, their store admin or the ad platform.

## Pick the interface

Use whichever is available, in this order:

1. **The `productmetrics` CLI.** Check with `productmetrics status --json`. Read `productmetrics help agents` once. Pass `--json` to every command.
2. **The Product Metrics MCP server** (`https://www.productmetrics.io/mcp`), through its `search` and `execute` tools. `search` reads the API spec; `execute` runs `codemode.request(...)` calls. Search first; never guess a path or body.
3. **Neither:** walk the person through the app steps in the Product Metrics app (https://app.productmetrics.io), or send them to https://www.productmetrics.io/docs/cli/overview or https://www.productmetrics.io/docs/mcp/connect.

Every API operation has an id like `stores.connect`. In the CLI it is `productmetrics stores connect`; in MCP it is the operation with that `operationId`. Before a command you have not used, run `productmetrics <group> <command> --help --json` (or `search` for the operation) for its exact flags.

## Read where setup stands

```bash
productmetrics setup get-status --json
productmetrics whoami --json
```

`setup get-status` (MCP: `setup.get_status`) is the map for every step. Read `journey_stage`, `user.google_grant`, and `hub.company.next_action` / `hub.property.next_action`. Once you know the workspace and property, read it again with `--company-id <company_id> --property-id <property_id>`. Skip every step that is already done, and tell the person which ones are.

## Rules

- **All conversion actions by agents are secondary.** Every conversion action you create stays secondary, the status Product Metrics creates its actions with (`google-ads create-conversion-actions` creates them as secondary and leaves existing actions as they are). What the account bids on is the person's choice: they make the chosen action primary and the old purchase action secondary in Google Ads (**Goals → Conversions**, or a campaign-specific goal), and pick the custom conversion or event a Meta ad set or ChatGPT Ads campaign optimises on. That step is theirs by every route (the `productmetrics` CLI, the MCP server, the API, the Google Ads API or UI, a browser), also when they ask you to do it. Give them the exact clicks, wait until they say it is done, then read the state back (`productmetrics google-ads get-conversion-actions --property-id <property_id> --json` reports each action's `goal_status`). Why: the bidding choice belongs to the advertiser, and one primary purchase action keeps bidding right and counts every purchase once.
- **Discover, never guess.** Ids (`company_id`, `property_id`, installation and scope ids) come from earlier results. Never invent one.
- **Writes.** Pass `--auto-idempotency-key` (MCP: `idempotencyKey: crypto.randomUUID()`) where the command's `--help` lists it: `companies create`, `stores connect` and `tracking update-margin-policy`. On a failed write, retry with the key the error hint names, so nothing is created twice. Other writes take no key: after a failure, read to check whether the change happened before retrying.
- **Browser steps.** When a command exits with code 4 or returns `next_action: { "type": "browser", "url": … }` (MCP: an operation marked `x-browser-step` returns a URL), give the person the URL, say what they will see, wait until they say they are done, then read the state again. You cannot click through these for them. A WooCommerce or Shopware 6 store exits 4 with `next_action: { "type": "store_plugin", "expires_at": … }` instead: the person pastes the setup token into the Product Metrics plugin in their store admin before it expires.
- **Steps in the store or ad platform** (Shopify admin, WordPress, Meta Events Manager, Google Ads, ChatGPT Ads) are the person's. Give them the exact labels from the reference you are following.
- **Secrets.** Never ask for, print or store passwords, tokens or API keys, except a credential the API needs from the person: the Lightspeed API key and secret, the Meta Conversions API access token, the OpenAI Conversions API key. Pass it straight to the command and never repeat it, log it or put it in a summary.
- **Deletes** (`access: destructive`, `--yes`, MCP `confirm: true`): only when the person explicitly asks.
- **"Ask your assistant".** The docs steps sometimes tell the person to ask their assistant a question, such as whether recent orders were new or returning. That is you: answer it with the CLI or the MCP tools. For orders: `productmetrics orders list --company-id <company_id> --storefront-scope-id <scope_id> --json` (MCP: `orders.list`) lists recent orders, newest first, and `productmetrics orders get --company-id <company_id> --order-id <order_id> --storefront-scope-id <scope_id> --json` (MCP: `orders.get`) shows one order's margin and whether its customer was new or returning.

## How to talk

Write for a store owner, not a developer: short sentences, what you did, what they need to do, what comes next. ROAS is a plain number (4.2); a target ROAS is a percentage (420%). Recommend increasing or lowering priority on products, segments or campaigns; never "raise or cut bids".
