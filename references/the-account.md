# The account: the connector, the permissions, and the waiting

Everything a founder has to have true before an ad can exist, and the 4 things nobody
discloses to them.

## 1. The connector

The Meta Ads connector is a **custom connector**, added in the Claude app and not at the
terminal.

> Claude, Settings, Connectors, Add custom connector, `https://mcp.facebook.com/ads`, then the
> Business OAuth. No developer app, no review queue.

Claude Code 2.1.46 or later picks up connectors added at claude.ai automatically, which is the
same path G6 uses for Google Calendar. Add it in the app rather than with `claude mcp add`: the
OAuth browser sometimes fails to open at the terminal, which our own audit logged.

**The plan question is answered, so stop treating it as open.** Custom connectors are available
on every plan, free users limited to one at a time, Pro and Max with no limit. Claude Code
already needs a paid seat, which G2 establishes. **No extra subscription beyond the one G2
already asks for.**

## 2. The two account flags, read before anything else

`ads_get_ad_accounts` returns `is_ads_mcp_enabled` and `is_queryable`. Either false and the tool
itself says do not use that account. There is no waitlist, no ETA and no published eligibility
rule, and nobody can fix it: not the member, not us. Print `not_queryable_reason` and stop.

Two minutes here instead of two weeks of building against an account that cannot answer.

## 3. The two permissions the founder sets, and the seven they do not

**Set these two, inside the Meta Ads connector's settings in Claude, to request approval:**

| Job | Tool | Setting |
|---|---|---|
| Turning anything on | `ads_activate_entity` | request approval, never always-allow |
| Changing a budget or a status | `ads_update_entity` | request approval |
| Everything that only reads | the read tools | always allowed, so a scheduled read never stalls |

Create tools are left alone on purpose: they make paused objects, so a create is not a spend.

**Meta's own Business Settings panel is an FAQ line, not a step.** Business Settings,
Integrations, Ads MCP Server shows seven actions (edit or set any budget, create campaigns,
create ad sets, create ads, edit targeting, edit creative, edit status), all on by default. The
practitioner who documented it says himself he does not know whether switching one off blocks
anything, Meta's own MCP overview page documents none of it, and nobody has tested a build with
one off. So: it exists, go look if you want, this run does not ask you to touch it. Switching off
"edit or set any budget" would break the launch, since a campaign budget is a budget.

The strongest practitioner source on this connector lands on our buyer directly, and it is worth
quoting rather than hiding: if you are new to ads, letting an AI connector run them for you will
not make you a master, and the better use is daily updates and segment reports. That is the
read-only half of what this skill does.

## 4. The waiting nobody discloses

| Blocker | What it costs |
|---|---|
| The server-side switch | `is_ads_mcp_enabled` / `is_queryable`. No waitlist, no ETA, unfixable from our side |
| Business verification | 24 to 72 hours, and up to 5 to 15 business days. Documents get rejected |
| The 2026-04-01 billing change | Credit cards removed for ad accounts under a Business Portfolio. Monthly billing or debit, 3 to 4 business days and sometimes weeks |
| Token expiry | Meta long-lived user tokens expire around 60 days, so at least two silent re-auths inside a 180-day term |

**A founder with no existing Meta setup spends their first two weeks waiting.** Say it at the
gate, in their language, before they decide.

**The expiry symptom is the dangerous one.** It has been reported as **empty results rather than
a clear error**. An empty read is therefore never printed as zero leads or a quiet week. It is
printed as "re-authorise the Meta connector and run this again."

## 5. The wall that actually holds

The **account spending limit**, set by the founder's own hand in Ads Manager, with the account's
billing settings. Meta enforces it and no agent can exceed it. It is the only hard safety claim
in this lane, and it only exists once the founder types a number into it, which is why beat 9
asks for it on the same trip as the overnight rule and prints the kill line as the number. This
skill never writes it. Changing it is rate limited to 10 times a day (error 17, subcode 1885172).

Ad set budget changes are limited to **4 per hour** (error 613, subcode 1487632). A rejected
budget write is reported, never retried.

## 6. What the fields will and will not do

Verify with `ads_get_field_context` before each metric call. The tool surface roughly tripled
between May and September and names changed inside it, so the catalog is read, never recalled.

| Field | Levels | Filterable | Sortable |
|---|---|---|---|
| `amount_spent` (alias `spend`) | account, campaign, adset, ad | yes | yes |
| `impressions` | all four | yes | yes |
| `results` | all four | yes | yes |
| `cost_per_result` | campaign, adset, ad | yes | yes |
| `lead` (alias `leads`) | all four | yes | yes |
| `cost_per_lead` | all four | yes | yes |
| `3_second_video_plays` | account, campaign, adset. **No ad level** | yes | yes |
| `cost_per_video_view` | all four. Display name: "cost per 3-second video play" | yes | yes |
| `delivery_sub_status` | **adset only** | yes | no |
| `learning_stage_info` | **adset only** | **no** | **no** |

`cost_per_result` and `results` are never requested at account level. `learning_stage_info` and
`delivery_sub_status` are read per ad set and compared inside the skill; neither can be pushed
into a filter.

`delivery_sub_status` enum: `LEARNING` ("exploring the best way to deliver your ad set when you
either create a new ad or ad set or make a significant edit") and `FAIL` (the Delivery column
reading "Learning limited"). `learning_stage_info` carries the status, the conversions, the
**last significant edit time**, the exit reason and the attribution windows.

## 7. Three defaults that decide how the build is written

- **The budget lives on the campaign.** The connector recommends campaign budget and
  **pre-validates it**: an ad-set budget under a campaign that carries one is rejected outright.
- **Advantage+ Audience is on by default**, and with it age is treated as a suggestion rather
  than a cap. **Location is the only hard lever the founder still holds.** For someone serving
  one city, that is the whole targeting lesson in one sentence.
- **Placement exclusions are being removed**, replaced by value rules with a bid decrease capped
  at 90 percent, two criteria per rule, ten rules per set. No rollout date announced. Nothing
  here touches placements; this exists so a founder reading a 2025 tutorial does not hunt for a
  checkbox that is gone.

## 8. The result event

Optimize for `LEAD_GENERATION` with an **on-Meta instant form**. It is the cheapest honest event,
which is the only kind $100 a day has a chance with, and it reports natively with no pixel and no
custom conversion.

A custom conversion (a booked call, a qualified lead) **may not report through this connector**,
and `ads_get_customconversions` carries no metrics fields at all. A founder who optimizes for
something the read cannot see has built a campaign nobody can grade.

The Page's lead terms must be accepted once, by hand: `ads_create_ad_set` needs
`leadgen_tos_accepted` true for a LEAD_GENERATION goal. Check it with
`ads_get_ad_account_pages` before building and stop with the terms URL when it is false.

**Embedded booking inside instant forms is real and no run may depend on it.** It came from one
scheduling vendor's own announcement, not Meta's; only two schedulers are live and cal.com, which
G6 teaches, is not one of them; and global availability is expected October 2026 at the earliest.
FAQ line, never a workflow step.
