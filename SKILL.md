---
name: the-ads-loop
description: Use this when the founder is about to put money into Meta ads, or already has money running. They say "is my ads gate open", "write my ads money card", "build my ad launch", "go", "pull my ads read for this week", or "continue the ads loop". It decides whether ads are the right lane, turns the founder's own price into the most a lead may cost, builds one campaign paused in their own ad account, and reads it once a week.
---

# The Ads Loop

One purpose: run the ads lane. Is this the right lane at all, the most a lead may cost, one
campaign built paused in their own account, and one read a week.

**Your first message on a fresh run carries this line, verbatim:** This skill is a base. Once you
have done it your way, tell your squad "update the skill to do it like this."

**You never spend.** Everything you create is created paused. You never call
`ads_activate_entity` without the founder's word in that same turn, and you never write a budget
number they did not say, with one exception: the daily number already on
`squad/ads-money-card.md` is what THE BUILD builds with. The account spending limit is typed by
their hand and you never touch it.

**2 files rank above anything you write.** `squad/business.md`, the offer document, carries the
price. `squad/ads-money-card.md` carries the lead ceiling and the kill line, built out of that
price. No offer document, no price, no ceiling, no ads: point at the Winning Offer (g4 or g5) and
stop. You never write `squad/business.md` and you never write `squad/pipeline.md`. **And you
never quote somebody else's cost per lead:** every number here comes off their own price or
Meta's own arithmetic (`references/the-numbers.md`).

`.claude/squad-roots.md` is the per-repo instance file every member-run skill reads first
(founder name, product word, the `pipeline` path, the `ads gate` row), and its values win over
the `squad/` paths below, which are worked examples. A row reading "(none yet)" is an unanswered
field, not an override. Legacy repos carry
`.claude/spine-roots.md`: read that when no squad-roots.md exists, write squad-roots.md when
neither does. `<date>` is always `YYYY-MM-DD`.

## The modes

| Mode | The founder says | What comes back |
|---|---|---|
| gate | "is my ads gate open", `/the-ads-loop gate` | one word, and the row |
| card | "write my ads money card", `/the-ads-loop card` | the ceiling, and the card |
| launch | "build my ad launch", `/the-ads-loop launch`, then "go" | one campaign paused |
| read | "pull my ads read for this week", `/the-ads-loop read` | the status, 2 numbers, one row |

## The outputs, and resuming

- `.claude/squad-roots.md`: the `ads gate` row. Nothing else in it touched.
- `squad/ads-money-card.md`: the 2 divisions, the lead ceiling, the daily number, the payback
  answer, the kill line. Edited in place when the price moves, never rebuilt.
- `squad/ads-launch-<date>.md`: `## THE MINE`, `## THE CONCEPTS`, `## THE BUILD`, `## THE AD`,
  `## THE OVERNIGHT RULE`, `## THE SPENDING LIMIT`, the launch card, the `launched <date>` stamp.
  One a week.
- `squad/ads/<date>/ad-N.mp4`: the clip for concept N, downloaded the same day.
- `squad/ads-log.md`: one row per week.

Nothing else gets written. Never `squad/business.md`, never `squad/pipeline.md`, never an
experiment, never a calendar event, never a second card.

**Resuming** ("continue the ads loop") reads those outputs, never a session's memory, and
continues at the first thing missing: no `ads gate` row, a row reading `shut` (nothing downstream
runs), no money card, a card with no kill line (that gate only), no launch file, a launch file
missing a section, a live campaign with no log row for the week that ended. Never rebuild a
campaign that already has ids on disk, and never regrade a week whose row is written. A budget
typed once is not a budget typed today, and neither is a `go`.

## THE ACCOUNT, first, every mode

Open the 3 files next to `SKILL.md` (`references/the-numbers.md`, `references/the-account.md`,
`references/what-runs-without-you.md`). Any missing: stop and ask for the whole folder again.

Then `ads_get_ad_accounts`, and read `is_ads_mcp_enabled` and `is_queryable` on EVERY account it
returns.

- No ad account at all: they make one in Ads Manager and ask again.
- Accounts back, none with both flags true: print `not_queryable_reason` in their own language
  and stop.
- One usable: that is the account. More than one: print the list with both flags, and check the
  account they name at the gate against it.
- No connector: print the click path from `references/the-account.md` (Claude app, Settings,
  Connectors, Add custom connector, `https://mcp.facebook.com/ads`, the Business login) and stop.

**An empty result set is never a number.** The token expires about every 60 days. Say
"re-authorise the Meta connector and run this again." Never report an empty read as zero leads,
zero spend, or a quiet week.

Verify a field before you ask for it (`ads_get_field_context`).
`cost_per_result` and `results` never at `ad_account` level, campaign or below.
`learning_stage_info` and `delivery_sub_status` at ad set only, never filtered or sorted on, read
per ad set and compared by you.

## THE GATE

Trigger: "is my ads gate open". This entry sends most people away. **Ask 2 things, in one
message:** the monthly number they can put into this lane without touching rent, and which
account it leaves.

**The money door:** their number against `squad/business.md`'s price. Money they can lose this
month and still sleep, or the gate is shut.

**The event door**, with the working shown. An ad set needs roughly 50 of the thing you ask Meta
to count (a form fill, for a service founder) inside a week before it leaves what Meta calls the
learning phase. Monthly over 30 is the daily, times 7 the weekly, and weekly over 50 is what one
of them has to cost. $3,000 a month is $100 a day, $700 a week, so $14. The closest published
range is $30 to $70 by trade, 2 to 5 times above it, with no sample size and no method.

> At $100 a day the only thing you may ask Meta to count is one that costs $14 or less. Raise the
> budget to cost times 50 divided by 7, or go run outreach, which answers the same question for free.

The waiting: with no Meta setup they wait about 2 weeks (business verification and the
2026-04-01 billing change), so start verification and billing today
(`references/the-account.md` section 4).

**Then one word, open or shut, the reason in one line**, and the row into
`.claude/squad-roots.md`:

```
| ads gate | open · savings, $3,000/mo · 2026-09-03 |
```

`shut` ends the run: no card, no launch, nothing on disk. Say what would open it (a higher price,
a cheaper thing to count, or money that is not rent) and send them back to outreach.

## THE MONEY CARD

Trigger: "write my ads money card". The gate row must read `open`; it does not, say so and stop.

**The price comes off `squad/business.md` and is never asked. Ask 2 things:** what delivery costs
per client (subcontractors, software, their own hours priced like an employee's), and how many
leads it takes them to close one (10 until their own closes replace it).

**Then the arithmetic, every line showing its working.**

- Gross profit: what the client pays minus what delivery costs.
- Divided by 6: the most they may spend to win one client. 6 is Chris's read, not a measured
  number, and the card says so.
- Divided by leads per close: the ceiling on one lead. A wall, never a target.
- The daily number, $100, and what it buys at that ceiling in leads a day.
- The event door against their own ceiling: the weekly budget over 50, printed beside the
  ceiling, and say which is smaller.
- The payback question, yes or no: in the first 30 days, does what a client pays cover twice what
  he cost to get and to serve? No means spend slowly.

**A ceiling nobody sells a lead for** is a price problem, not an ads problem. Print what their
price would have to be and point at the Winning Offer. Never soften the ceiling.

**Then one number, typed by the founder: the kill line.** Total money spent on ads since day 1,
with zero paying clients out of them. Not per ad. The whole account, running total. One rule
picks it: never more than the money they can lose this month and still sleep.

Then write `squad/ads-money-card.md`, one page, and say once: that check happens the moment they
type, not while they sleep.

## THE LAUNCH

Trigger: "build my ad launch". The money card must exist and carry a kill line. Everything lands
in `squad/ads-launch-<date>.md`, written as you go so a stopped run resumes.

### The 2 settings

2, not 7. In the Claude app, Settings, Connectors, Meta Ads, its tool list, set 2 tools to
**request approval**: `ads_activate_entity`, the one that turns things on, and
`ads_update_entity`, the one that changes a budget or a status. Leave the rest alone. The reads
stay always-allowed or a scheduled read stalls. Wait for their word that both are set.

### The mine

`ads_library_search` on the buyer words from `squad/business.md` and `squad/clients/*/notes.md`
where those exist, their country, `limit` 50, `ad_active_status` ACTIVE.

**Primary sort: count duplicate `ad_creative_link_title` values per `page_id`.** The same
advertiser running the same hook several times is the one honest signal in the response.
Secondary sort `ad_delivery_start_time`, printed as a real date and never as proof of money
(banned in this repo, `references/the-numbers.md` section 7).

Print the top 3 into `## THE MINE`: page name, headline, start date, `ad_snapshot_url`. Say what
came back: never the body, never the image, never spend or reach.

### The 3 links, then the concepts

"Open these 3 and tell me what each ad actually says." Then wait. One line with it: do not copy a
long-running ad's guarantee, since the ad may not promise what their own offer does not.

Then 3 concepts out of what they reported plus the closest-to-money message from
`squad/pipeline.md`. One person, one claim, in their own words. Nothing invented about the buyer,
no number that is not on the money card or in the offer document. Written into `## THE CONCEPTS`.

### The build, paused

Created paused by the tools' own default, and the build comes before the clips.

1. `ads_get_ad_account_pages`, and check `leadgen_tos_accepted`. False: print the terms URL and
   wait. The lead terms are accepted once, by their hand.
2. `ads_create_campaign`, `objective: OUTCOME_LEADS`, `campaign_daily_budget` in cents off the
   money card. The budget lives on the campaign; the connector rejects an ad-set budget under a
   campaign that has one. A campaign id already on disk means no second campaign: this
   week's ad set goes inside it.
3. `ads_create_ad_set`, `optimization_goal: LEAD_GENERATION`, `promoted_object` carrying the
   `page_id`, targeting `geo_locations` only. No interests, no invented ids. Advantage+ Audience
   is on by default and age is a suggestion, so **location is the only hard lever they still
   hold.**
4. 3 ads, one per concept, through the connector's creative tool and `ads_create_ad`.

Write every id into `## THE BUILD`: account, campaign, ad set, the 3 ads, the budget, the geo,
the objective, the optimization goal.

### The ad, made

Each concept becomes one clip, through the founder's own Higgsfield connector, on their own
credits.

**Check the connector first**, off the live tool list. Not connected: print the click path from
`references/the-account.md` section 9 (Claude app, Add custom connector, name it Higgsfield,
`https://mcp.higgsfield.ai/mcp`), and the fallback: they record the concept on their phone, one
take, and pick that file below.

**One prompt per concept**, written into `## THE AD` before anything is generated: 9:16, up to 15
seconds, their own words from the concept, one person, one claim. No guarantee, and nothing that
is not on the money card or in the offer document. The model is Seedance 2.0 unless the founder
names Veo.

**Then the gate, before generating.** One line per ad: the credit cost, read off the tool's own
response or Higgsfield's published rates, never invented, then yes or no. A paid plan is
required, every generation through a connector charges credits at standard rates, and an
unlimited plan does not cover it. Generate only the ads they said yes to.

**Download the same day**, because the link expires. Save each MP4 into
`squad/ads/<date>/ad-N.mp4`, N matching the concept, and write which ad carries which file into
`## THE AD`. It never goes on the open internet: no host, no share link.

**Then their hand.** `ads_creative_upload_media` with `upload_source: LOCAL_FILE` opens Meta's
own picker so they choose that file off their own device. Say that, then wait. **Never ask for a
link:** a share link is rejected when it needs a sign-in. No picker on their surface: leave the 3
ads paused with the creative they have, tell them to add the file by hand in Ads Manager, and
write "none" into `## THE AD`.

### The overnight rule, and the wall

2 things by their hand on one trip to Ads Manager, 5 minutes, once. Print the rule to build,
exactly:

> Rules, Create a New Rule. **Apply to:** all active ads. **Condition:** Amount spent (lifetime)
> is greater than [2 times the lead ceiling] AND Results is less than 1. **Action:** Turn off
> ads. **Schedule:** Continuously.

Fill the bracket off the money card. It is Meta's own free feature, checked every 30 to 60
minutes, day and night.

**Then the wall, same trip.** Print the kill line off the money card and ask them to type it into
the **account spending limit**, with the account's billing settings. That number in that box is
enforced by Meta against everybody, this skill included. Raise it the day a client pays out of
ads. **You print the number. You never write the setting.**

Wait for them to say both are done, then write `## THE OVERNIGHT RULE` with `set <date>` and
`## THE SPENDING LIMIT` with the number and the date.

### The launch card, and the one gate

One screen:

- spend per day, and the week's total
- the 2 kills: Meta's rule, per ad, and the kill line, whole account, running total
- what runs: one campaign, this week's ad set beside any already running, 3 ads, location only
- which finished ad set goes off with this one, when it would take the count past 3, or "none"
- the first Sunday it can be read, past 7 days and about 50 events, and the words look, do not
  touch

Then wait. 3 answers. **go** activates, in that same turn, and nothing else. **A change** is one
thing: a budget they say in that turn goes through `ads_update_entity` on
`campaign_daily_budget`, at or under the money card's daily number once the campaign is live (on
the first launch nothing has spent, so the number they say is written); a raise past it on a live
campaign is a scale and waits for the scale gate. A week's total they name is divided by 7 and
shown before it is written; then print the card again and stop here again. **kill it and mine
again**: nothing is live, so leave every id in the launch file, say what is being abandoned, and
go back to the mine.

Anything about the words in an ad is **kill it and mine again**, never a change: ad creatives are
immutable. **You never activate in the same turn as a change.**

### Go

On the word only, in that same turn. `ads_activate_entity` on the campaign, then the ad set, then
the ads, in that order, because activating a parent does not activate its children. Then, only
when the card named one, `ads_update_entity` turns off the ad set it named. Report `PUBLISHING`
as in progress, never as live. Stamp `launched <date>` into the file and close with one line:
leave it alone until that first Sunday.

## THE READ

Trigger: "pull my ads read for this week", on a Sunday, and any morning for the kill line alone.
This read runs before `/bip sunday`.

### Measure

**First, always, the kill line:** `amount_spent` at `date_preset: maximum` against the card's
number, with the paying clients out of this channel from `squad/pipeline.md` under it. Crossed
with no client behind it and that is the only thing on the screen. This check happens the moment
they type, not while they sleep.

Then 2 calls for the week. Ad set: `amount_spent`, `impressions`, `lead`, `cost_per_lead`,
`results`, `cost_per_result`, `delivery_sub_status`, `learning_stage_info`. Ad: `amount_spent`,
`impressions`, `lead`, `cost_per_lead`, `cost_per_video_view`, `effective_status`.

**Row zero, the status, first: it decides what the rows under it mean.** One line per
live ad set. An ad set is read only once it is past 7 days and about 50 events; under either it
prints "still learning, N of about 50, held" off `learning_stage_info` and `delivery_sub_status`.
If `last_significant_edit_time` falls inside the window, name the day that reset the clock. An ad
Meta's rule turned off this week is hygiene, never the week's change.

**Rows one and two are computed on the FINISHED ad sets only.**

**Row one, cost per lead**, against the money card's ceiling. Scale, hold, or kill. On a kill
only, the hook rate at ad level: `amount_spent` divided by `cost_per_video_view` divided by
`impressions`, and call it approximate. Below about 24
percent the first 3 seconds are the problem and the hook changes; at or above it with no leads,
the leak is the form or the offer, which is g4 or g5, and g6. The 24 is the average services
advertiser in early 2026, never a pass mark.

**Row two, leads:** the plain count off the finished ad sets.

**Then the channel line, cost per client:** `amount_spent` divided by the clients who actually
paid, from `squad/pipeline.md`, never from Meta. No client yet prints as "no client yet" with the
spend behind it, never as a division by zero.

Print all of it every week. The change comes off the FIRST row that misses.

**Never name a winning ad off a week of leads.** A winner is named only when the 2 honest ranges
do not overlap (`references/the-numbers.md` section 6). Asked which ad won, print both ranges in
words and say the week cannot separate them.

### Improve, the one change

One line from the founder: one change, named, or a hold. Never 2 changes. Most weeks read
holding, and that is the loop working. Make that one change and nothing else: a kill, or a budget
raise once the scale gate has printed open.

**A change opens a new ad set and never edits a running one.** Creatives are immutable, a new ad
into a live ad set is an edit, and an edit sends that ad set back to day 1 of learning. Meta
splits the campaign's daily number across every live ad set, so 2 or 3 live is the ceiling at
$100 a day, and the weakest FINISHED ad set goes off through `ads_update_entity` on its status
before a new one opens past that.

Monday's "build my ad launch" runs again into a new launch file, building the ad set and its 3
ads inside the campaign already on disk. **A budget number moves only if they said it in that
turn.** Meta allows 4 ad-set budget changes an hour, and a rejected budget write is never
retried, it is reported.

Then append one row to `squad/ads-log.md`, header line first when the file is new:

```
week ending | status | spend | leads | cost per lead vs ceiling | cost per client | improve
2026-09-07 | out of learning | $700 | 16 | $43.75 vs $26 | none yet | new hook, new ad set
```

### The scale gate, and the weekly task

Scaling is a budget raise past the card's daily number, or a second campaign. A new ad set inside
the one campaign is the week's change, not a scale. All 4 true or the answer is no, and you name
which one failed.

| # | Condition | Where it is read |
|---|---|---|
| 1 | The oldest running ad set finished the week Meta spends learning | `delivery_sub_status` not `LEARNING`, `learning_stage_info.status` shows it exited |
| 2 | No big change across the window | `learning_stage_info.last_significant_edit_time` older than the 2 weeks |
| 3 | Cost per lead at or under the ceiling, 2 full weeks | `cost_per_lead` on 2 `time_range` calls |
| 4 | At least one client paid, out of this channel | `squad/pipeline.md` |

At $100 a day with an expensive lead, an ad set may never clear 50 a week. That is the gate
working.

**The weekly task is offered once**, gated on 3 by-hand runs of this read and the founder saying
in one line what they changed last time. Then, from `references/what-runs-without-you.md`: Claude
Desktop, Code tab, Routines, New routine, **Local**, weekly, Run now once and always-allow each
read so it never stalls. One task per founder. It only ever reads, and it fires when the lid
opens.

## Rules

- Never send, never spend, and never activate or write a budget without the founder's word in
  that turn (the money card's own daily number excepted).
- Every number comes off `squad/business.md`, the money card, or the account. Never a published
  cost-per-lead table.
- Never build an experiment. At this budget a split test is noise.
- Never drive Ads Manager with a browser tool. Meta's terms forbid automated access.
