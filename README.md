# The Ads Loop

This skill is a base. Once you have done it your way, tell your squad "update the skill to do it
like this."

The part of an Execution Squad that spends money, so it starts by trying to talk you out of it.
If the gate opens, it turns your price into the most a lead may cost you and builds one campaign
paused in your own ad account.

## What to bring

Your offer document at `squad/business.md`. Your pipeline at `squad/pipeline.md`, which Meta
cannot see. Then 4 numbers: what you can spend in a month without touching
rent, what delivery costs per client, how many leads to close one, and the number that
stops the spending.

## Install

Drop this whole folder, `references/` included, into `.claude/skills/` and reopen Claude Code.

One connector, added in the Claude app, not the terminal: **Settings, Connectors, Add custom
connector, `https://mcp.facebook.com/ads`**, then the Business login. Then 2 settings in its tool
list: the tool that turns things on and the tool that changes a budget go to **request approval**.

A second connector makes the ad: **Add custom connector, name it Higgsfield,
`https://mcp.higgsfield.ai/mcp`**. A paid plan is required and every clip charges credits. Or
record each ad on your phone, one take.

## Run it

- **"Is my ads gate open?"** 2 questions, then one word, open or shut, and the row lands in
  `.claude/squad-roots.md`.
- **"Write my ads money card."** 2 questions, then your ceiling, the payback answer, and the kill
  line you type. It lands at `squad/ads-money-card.md`.
- **"Build my ad launch."** You open 3 ads and say what each says, say yes to the clips, and set 2
  things by hand in Ads Manager. The campaign comes back paused, every id in
  `squad/ads-launch-<date>.md`, the clips in `squad/ads/<date>/`. Nothing runs until you say
  **"Go."**
- **"Pull my ads read for this week."** Sunday. The status, 2 numbers, cost per client, then your
  one change. It lands as one row in `squad/ads-log.md`.

Stopped halfway? Say **"continue the ads loop"** in a new window; it picks up at the first thing
missing.

## What you get

It never sends, never spends, and never turns anything on without your word in that same
message. It never writes a budget you did not say out loud. The account spending limit, the one
wall Meta enforces against everybody including this skill, is typed by your hand. It will never
quote you a cost-per-lead benchmark: your ceiling comes off your own price.

The one thing that runs without you is Meta's own rule, printed by the launch and clicked in
once: any ad that spends twice your lead ceiling with nothing to show gets turned off.

The lessons are a1 to a4 at aichrislee.com.
