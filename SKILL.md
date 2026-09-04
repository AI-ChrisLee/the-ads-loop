---
name: the-ads-loop
description: Use this when the founder is about to put money into Meta ads, or already has money running. They say "is my ads gate open", "should I run ads", "write my ads money card", "what can a lead cost me", "build my ad launch", "go", "pull my ads read for this week", "log this week's ads decision", or "continue the ads loop" (picking a stopped run back up). It decides whether ads are the right lane at all, turns the founder's own price into the most a lead may cost, builds one campaign paused inside their own ad account, and prints two numbers and a status with one change under them. Everything it builds is paused, and the founder says the word that turns it on.
---

# The Ads Loop

Outreach spends time. Ads spend money every hour, replies or no replies. **Your work, in one
line: hold the gate shut until both doors clear, turn the founder's own price into the most a
lead may cost, build one campaign paused in their account, and print two numbers and a status
with one change under them.** The founder's part: four numbers, three links they open with
their own eyes, one video they pick off their own disk, and the word that turns it on.

**You never spend.** Every campaign, ad set and ad you create is created paused, which is the
create tools' own default. You never call `ads_activate_entity` without the founder's word in
that same turn, never on a yes they gave in an earlier run, and never on a flag in a file. You
never write a budget number they did not say out loud in that turn, and the one exception is
named here: the daily number already sitting on `squad/ads-money-card.md`, which they chose when
that card was built, is the number beat 7 builds with, onto a paused campaign that spends nothing
until the gate at beat 10. Every other budget write needs the number in that turn. The account
spending limit, which is the one wall Meta enforces against you, is set by their hand in Ads
Manager at beat 9 and you never touch it.

**Two files rank above anything you write, and neither is yours to invent.**
`squad/business.md`, the offer document, carries the price. `squad/ads-money-card.md` carries
the lead ceiling and the kill line, and it is built out of that price. No offer document means
no price, which means no ceiling, which means no ads: point at the Winning Offer and stop. You
never write `squad/business.md` and you never write `squad/pipeline.md`.

**And you never quote somebody else's cost per lead.** Nobody publishes an honest one for a
solo founder selling a service. Every number in this lane comes from the founder's own price or
from Meta's own arithmetic. `references/the-numbers.md` holds both, and the claims that are
banned outright.

This skill runs in ANY founder's repo. `.claude/squad-roots.md` is the per-repo instance file
every member-run skill reads first (founder name, product word, the `pipeline` path, and the
`ads gate` row this skill writes), and its values win over the `squad/` paths below, which are
worked examples. A row reading "(none yet)" is an unanswered field, not an override: the
worked-example path stands until this run fills it. Legacy repos carry `.claude/spine-roots.md`;
read that when no squad-roots.md exists, and write squad-roots.md when neither does. `<date>` is
always `YYYY-MM-DD`.

## The modes, and how they are called

| Mode | The founder says | Beats |
|---|---|---|
| gate | "is my ads gate open", "should I run ads", `/the-ads-loop gate` | 0, 1. Once, before any money moves |
| card | "write my ads money card", "what can a lead cost me", `/the-ads-loop card` | 0, 2. Once, and again when the price moves |
| launch | "build my ad launch", `/the-ads-loop launch`, then "go" | 0, 3 to 11 |
| read | "pull my ads read for this week", "log this week's ads decision", `/the-ads-loop read` | 0, 12 to 14. Sunday, and any morning for the kill line |

## The run map (where you run, where you STOP)

| Beat | What happens |
|---|---|
| 0 THE ACCOUNT | AUTO: the install check, the roots file, the two flags on every account the login returns, the field catalog. Every mode, before any question |
| 1 THE GATE | HUMAN INPUT: the monthly number and the account it leaves. Then AUTO: the two doors and the waiting, then **STOP · GATE: open or shut, one word, the reason named** |
| 2 THE MONEY CARD | HUMAN INPUT: delivery cost per client, leads per close. Then AUTO: the two divisions, the payback question, then **STOP · GATE: the kill line, typed as a number** |
| 3 THE TWO PERMISSIONS | HUMAN INPUT: two settings inside the connector, set by the founder, confirmed in words |
| 4 THE MINE | AUTO: the library search, sorted by repeated hooks per advertiser |
| 5 THE THREE LINKS | HUMAN INPUT: the founder opens three ads and says what they actually say |
| 6 THE CONCEPTS | AUTO: three ad concepts off what they reported and the message that got closest to money |
| 7 THE BUILD, PAUSED | AUTO: campaign, ad set, three ads, all created paused |
| 8 THE VIDEO | HUMAN INPUT: the picker opens, the founder chooses the file |
| 9 THE OVERNIGHT RULE, AND THE WALL | HUMAN INPUT: Meta's rule and the account spending limit, five minutes in Ads Manager, by their hand, confirmed in words |
| 10 THE LAUNCH CARD | AUTO print, then **STOP · GATE: go, change one thing, or kill it and mine again** |
| 11 GO | AUTO on the word only: campaign, then ad set, then ads, in that order |
| 12 THE READ | AUTO: the kill line first, then row zero the status, row one cost per lead, row two cost per client |
| 13 THE ONE CHANGE | **STOP · GATE: one move, named**, then AUTO: the write, and the log row |
| 14 THE SCALE GATE | AUTO: the four conditions read off the account. Scaling opens or it does not. Then the weekly task, offered once |

The beat numbers ARE the step numbers below. Never pause an automated beat to ask a small
question (batch it into the next gate); never run through a gate because the answer seems
obvious. Beats 1 and 2 happen once: a confirmed money card is never rebuilt from scratch, it is
edited when the price moves.

**Resuming.** The rule keys on the OUTPUTS, never on a session's memory. Check them in this
order and continue at the first one missing or incomplete.

| Missing or incomplete | Resume at |
|---|---|
| `.claude/squad-roots.md` carries no `ads gate` row | beat 1 |
| the row reads `shut` | beat 1, and nothing downstream runs |
| the row reads `open` and `squad/ads-money-card.md` does not exist | beat 2 |
| the card exists and carries no `kill line` number | beat 2, THE GATE ONLY: never redo the arithmetic |
| the card is complete and no `squad/ads-launch-<date>.md` exists | beat 3 |
| the newest launch file has no `## THE BUILD` block naming three ad ids | beat 7 |
| `## THE BUILD` names three ads and `## THE VIDEO` is empty | beat 8 |
| the launch file has no `## THE OVERNIGHT RULE` line reading `set <date>`, or no `## THE SPENDING LIMIT` line | beat 9, and only the half that is missing |
| the launch file carries no `launched <date>` stamp | beat 10 |
| a campaign is live and `squad/ads-log.md` has no row for the week just ended | beat 12 |
| the newest log row names a change and the account does not carry it | beat 13 |

Never rebuild a campaign that already has ids on disk. Never regrade a week whose row is
written. A budget the founder typed once is not a budget they typed today, and neither is a `go`:
a resumed run still stops at beat 10.

## The outputs (4 files, every run)

1. `squad/ads-money-card.md`: the price, the two divisions, the lead ceiling, the daily number,
   the payback answer, the kill line. Beat 2, edited in place when the price moves.
2. `squad/ads-launch-<date>.md`: the mine, the three concepts, the build with every id, the
   video, the overnight rule, the spending limit, the launch card, and the `launched <date>`
   stamp. Beats 4 to 11.
3. `squad/ads-log.md`: one row per week, the header line first when the file is new. Beat 13.
4. `.claude/squad-roots.md`: the `ads gate` row, written at beat 1. Nothing else in it touched.

Nothing else gets written. Never `squad/business.md`, never `squad/pipeline.md`, never a
creative file, never an experiment, never a calendar event, never a second card.

## Beat 0 · THE ACCOUNT

**The install check, before you spend any of the founder's input.** Three files inside THIS
skill's folder, next to `SKILL.md`, must open: `references/the-numbers.md`,
`references/the-account.md`, `references/what-runs-without-you.md`. Any missing: stop and say
the folder was downloaded without its `references/`, copy the whole skill folder in again.
Arithmetic and rule text guessed from memory are wrong quietly, which in this lane costs money.

**Then, before you ask the founder anything at all:** `ads_get_ad_accounts`, and read
`is_ads_mcp_enabled` and `is_queryable` on EVERY account it hands back. Not on one account they
named, because at this point they have named none. That check costs two minutes and it stands
between them and a fortnight of waiting, so it runs first, every mode, every time.

- **Not one account has both flags true:** print `not_queryable_reason` in their own language and
  stop right there. No questions get asked, nothing downstream runs.
- **One account comes back usable:** that is the account. Say its name and carry on.
- **More than one:** print the short list, each account with its two flags, and carry on. The
  account they name at beat 1 is checked against that list before a door prints, and naming an
  unusable one stops the run the same way.

**No connector at all:** print the click path from `references/the-account.md` and stop. It is
added in the Claude app, not at the terminal, and Claude Code 2.1.46 or later picks it up.

**An empty result set is never a number.** A read that comes back with nothing means the token
may have expired, which happens about every 60 days. Say "re-authorise the Meta connector and
run this again." Never report an empty read as zero leads, zero spend, or a quiet week.

**Before any metric call:** `ads_get_field_context` on the field names you are about to ask
for. The tool surface roughly tripled between May and September, 29 tools to 97, and two of the
names changed inside five weeks, so you verify the field rather than remember it.
`cost_per_result` and `results` are never requested at `ad_account` level; campaign or below. `learning_stage_info` and
`delivery_sub_status` live at ad set only, cannot be filtered or sorted on, and are read per ad
set and compared by you.

Then say in one line what opened: the account name, `squad/business.md`, `squad/pipeline.md`,
`squad/ads-money-card.md`, and the newest launch file.

## Beat 1 · THE GATE

Trigger: "is my ads gate open", "should I run ads". The point of this beat is to send most
people away, and that is the beat working.

**Ask two things, in one message.**

1. The monthly number they can put into this lane without touching rent.
2. Which account it leaves.

Then read `squad/pipeline.md` and pull the message that got closest to money, verbatim. If the
file does not exist, say so in one line and carry on; the gate does not need it.

**Then print the two doors, both of them, before any money leaves.**

- **The money door** is their own number, against `squad/business.md`'s price. Money they can
  lose this month and still sleep, or the gate is shut. No offer document at all: say in one line
  that the money door has no price to sit against, point at G5's Winning Offer, and stop.
- **The event door** is arithmetic and it is the one nobody tells them. Turn the monthly number
  they just gave into a week first, and show the working: monthly divided by 30 is the daily,
  times 7 is the weekly. An ad set needs roughly 50 optimization events a week to leave the
  learning phase, so that weekly number divided by 50 is what one event has to cost for Meta to
  finish learning inside the week. $3,000 a month is $100 a day, $700 a week, so $14. Nothing
  published anywhere puts a service lead near $14.

Say it whole, in these words or close to them:

> At $100 a day the only event you may optimize for is one that costs $14 or less. For a service
> founder that is a form fill on Meta. Either your own numbers beat every published one, or you
> raise the budget to cost times 50 divided by 7, or you accept that this lane reads a direction
> and never an answer, and you go run outreach, which answers the same question for free.

**Then print the waiting, once, whole. All four rows, never a pointer to a file instead.**

| What waits | What it costs |
|---|---|
| The server-side switch | The two flags you read at beat 0. No waitlist, no ETA, no published rule about who gets it, and nobody can fix it |
| Business verification | 24 to 72 hours, and up to 5 to 15 business days. Documents get rejected |
| The 2026-04-01 billing change | Credit cards are out for ad accounts under a Business Portfolio, so monthly billing or a debit card, 3 to 4 business days and sometimes weeks |
| The login expiry | Meta's token runs out around every 60 days, so at least two re-authorisations inside a 180-day term, and it shows up as empty results rather than as an error |

A founder with no Meta setup spends their first two weeks waiting, and nobody tells them that
before they decide. `references/the-account.md` holds the detail behind each row.

**STOP · GATE.** One word, open or shut, with the reason named in one line. Then write the row
into `.claude/squad-roots.md`:

```
| ads gate | open · savings, $3,000/mo · 2026-09-03 |
```

`shut` is a finished, useful answer, and it ends the run: no card, no launch, nothing else on
disk. Say what would open it (a higher price, a cheaper event, or money that is not rent) and
send them back to outreach.

## Beat 2 · THE MONEY CARD

Trigger: "write my ads money card", "what can a lead cost me". The gate row must read `open`.

**The price comes off `squad/business.md` and is never asked.** Ask two things:

1. What delivery costs per client: subcontractors, software, and their own hours priced like an
   employee's.
2. How many leads it takes them to close one. Default 10 until their own closes replace it.

**Then the arithmetic, and every line of it shows its working.**

- Gross profit per client: what the client pays minus what delivery costs.
- Divided by 6: the most they may spend to win one client. Six is Chris's read, not a measured
  number, and it is written on the card as his read. The 3 to 1 everybody quotes came out of
  software, where the product ships itself and nobody does the work.
- Divided by leads per close: the ceiling on one lead. A wall, never a target.
- The daily number, $100, and what it buys at that ceiling in leads per day.
- **The event door again, now against their own ceiling.** Weekly budget divided by 50 is the
  event cost that clears learning. Print their ceiling next to it and say which is smaller. A
  ceiling above $14 does not make the arithmetic go away; it means their price is carrying them.
- The payback question, answered yes or no: in the first 30 days, does what a client pays cover
  twice what he cost to get and to serve? No means spend slowly.

**A ceiling nobody sells a lead for** is a price problem, not an ads problem. Say it in one
line, print what their price would have to be, and point at the Winning Offer. Never soften the
ceiling to make the lane work.

**STOP · GATE.** One number, typed by the founder: the kill line. Total money spent on ads since
day one with zero paying clients out of them. Not per ad, the whole account, running total. One
rule picks it: never more than the money they can lose this month and still sleep. They write it
down now because they will not be calm on the day it gets hit.

Then write `squad/ads-money-card.md`, one page, the numbers where the eye lands. Say in one
line: the kill-line check runs the moment they type, on any morning, not while they sleep.

## LAUNCH · beats 3 to 11

Trigger: "build my ad launch". The money card must exist and carry a kill line. Everything here
lands in one file, `squad/ads-launch-<date>.md`, written as you go so a stopped run resumes.

### Beat 3 · THE TWO PERMISSIONS

HUMAN INPUT, and it is two settings, not seven. In Claude, open the Meta Ads connector's
settings and its tool list, then set two tools to **request approval**:

- the one that turns things on (`ads_activate_entity`)
- the one that changes a budget or a status (`ads_update_entity`)

Leave everything else alone. One line of why: the create tools make paused objects, so a create
is not a spend, and the read tools have to stay always-allowed or a scheduled read stalls on
every call.

Meta's own Business Settings panel is an FAQ line and not a step. It exists, all seven actions
are on by default, and nobody has tested what a build does with one switched off, so this run
does not ask anyone to touch it. Wait for the founder to say the two settings are set.

### Beat 4 · THE MINE

AUTO. `ads_library_search` on the buyer words from `squad/business.md` and from
`squad/clients/*/notes.md` where those exist, the founder's country, `limit` 50,
`ad_active_status` ACTIVE.

**Primary sort: count duplicate `ad_creative_link_title` values per `page_id`.** The same
advertiser running the same hook several times is the one honest signal in the response.
Secondary sort: `ad_delivery_start_time`, printed as a real date and **never described as proof
that an ad is making money.** That claim is banned in this repo and the ban is in
`references/the-numbers.md`.

Print the top three: page name, headline, start date, `ad_snapshot_url`, and write them into
`## THE MINE`. Say plainly what came back, because a founder who expected ad copy will think the
run broke: the library returns a headline and a link, never the body, never the image, never
spend or reach. The tool also needs at least one active ad account and refuses bulk extraction,
50 per call.

### Beat 5 · THE THREE LINKS

HUMAN INPUT, and it is 30 minutes of the founder's own eyes, once. "Open these three and tell me
what the ad actually says." Then wait. One line with it: do not copy a long-running ad's
guarantee. Their own offer does not carry one, and the ad may not promise what the offer does not.

### Beat 6 · THE CONCEPTS

AUTO. Three ad concepts, built out of what they just reported plus the message from
`squad/pipeline.md` that got closest to money. One person, one claim, in the founder's own
words. Nothing invented about the buyer, no number that is not on the money card or in the offer
document. Written into `## THE CONCEPTS`.

### Beat 7 · THE BUILD, PAUSED

AUTO, and everything here is created paused by the tools' own default.

1. `ads_get_ad_account_pages` first, and check `leadgen_tos_accepted`. False: stop, print the
   terms URL, and say the Page's lead terms are accepted once, by hand, before an ad set can
   exist.
2. `ads_create_campaign`, `objective: OUTCOME_LEADS`, `campaign_daily_budget` in cents. One line
   saying why the budget lives on the campaign: the connector defaults to campaign budget and
   rejects an ad-set budget under a campaign that has one.
3. `ads_create_ad_set`, `optimization_goal: LEAD_GENERATION`, `promoted_object` carrying the
   `page_id`, targeting `geo_locations` only. No interests, no invented ids. Say the one line
   that matters: Advantage+ Audience is on by default, age is treated as a suggestion, and
   **location is the only hard lever they still hold.**
4. Three ads, one per concept, through the connector's creative tool and `ads_create_ad`. Check
   the tool names in the live tool list rather than trusting a name written here; two changed in
   five weeks.

Write every id into `## THE BUILD` as you go: account, campaign, ad set, the three ads, the
budget, the geo, the objective, the optimization goal.

### Beat 8 · THE VIDEO

HUMAN INPUT, and the founder's hand is in this step no matter what.
`ads_creative_upload_media` with `upload_source: LOCAL_FILE` opens Meta's own picker so they
choose the file off their own device. Say that, then wait. JPEG, PNG, GIF, MP4 and MOV.

**Never ask for a link.** A Drive, Dropbox or Canva share link is rejected when it needs a
sign-in or hands back a page instead of the file, and asking a founder to make a video public on
the open internet is a thing this repo does not do. Never ask them to host anything.

No picker appears on their surface: say so plainly, leave the three ads paused with the creative
they have, and tell them to add the video to those ads by hand in Ads Manager. Do not invent a
second path. Write which ad carries which file into `## THE VIDEO`, or write "none" there.

### Beat 9 · THE OVERNIGHT RULE, AND THE WALL

HUMAN INPUT, two things by their hand on one trip to Ads Manager, five minutes, once. Print the
rule to create, exactly:

> Rules, Create a New Rule. **Apply to:** all active ads. **Condition:** Amount spent (lifetime)
> is greater than [2 times the lead ceiling] AND Results is less than 1. **Action:** Turn off
> ads. **Schedule:** Continuously.

Fill the bracket off the money card. Then say why it lives there and whose it is: the connector
publishes no rules tool, Meta checks every 30 to 60 minutes including while they sleep, and this
is **Meta's own free feature, not ours.** A member who checks will find that out in a minute, so
they hear it from us first.

Say why it is built on spend and not on cost per lead: cost per lead is spend divided by leads,
so on an ad with zero leads it has no value at all, and a rule built on it would never fire on
exactly the ads it is hunting. Twice what a lead may cost you, spent, with nothing to show.

**Then the wall, same trip.** Print the kill line off the money card and ask them to type it into
the **account spending limit** on this ad account, which sits with the account's billing settings
in Ads Manager. Say what it buys them: a kill line on a card is a promise they make to
themselves, and the same number in that box is enforced by Meta against everybody, this skill
included. It is a lifetime total for the account, so delivery stops when it is reached, and it
can be raised up to ten times a day, which is what they do the day a client pays out of this
channel. You print the number. You never write the setting.

Wait for the founder to say both are done, then write `## THE OVERNIGHT RULE` with `set <date>`
and `## THE SPENDING LIMIT` with the number and the date.

### Beat 10 · THE LAUNCH CARD

AUTO print, one screen:

- the proposed daily spend and the week's total
- the two kills: Meta's rule from beat 9, per ad, and the kill line off the card, whole account
- what runs: one campaign, one ad set, three ads, location only
- the date to look again, seven days out, and the words look, do not touch
- the event door restated against this campaign's actual optimization event

**STOP · GATE.** Three answers allowed, and nothing else counts as consent. Silence is not
consent, and neither is "looks good".

| The answer | What you do |
|---|---|
| **go** | beat 11, in that same turn, and nothing else |
| **change one thing** | one change, then print the card again and stop here again. A budget they say in that turn: `ads_update_entity` on `campaign_daily_budget`, on the campaign, which is paused, so nothing has spent. A week's total they name is divided by seven and the daily number is shown before it is written |
| **kill it and mine again** | nothing is live, so nothing is paused. Leave every id in the launch file, say what is being abandoned, and go back to beat 4 |

Anything about the words in an ad is **kill it and mine again**, never a change: ad creatives are
immutable, so there is no edit to make. Say that in one line rather than trying.

You never activate in the same turn as a change. The card is printed again and this gate runs
again.

### Beat 11 · GO

AUTO, on the word only, in that same turn. `ads_activate_entity` on the campaign, then the ad
set, then the ads, in that order, because activating a parent does not activate its children.
Report `PUBLISHING` as in progress, never as live. Stamp `launched <date>` into the file and
close with one line: leave it alone for seven days, every significant edit puts the ad set back
to day one of learning.

## READ · beats 12 to 14

Trigger: "pull my ads read for this week", any Sunday, and any morning for the kill line alone.
This read runs **before** `/bip sunday`, because the weekly post sums numbers this beat produces.

### Beat 12 · THE READ

AUTO. First, always, the kill line: `amount_spent` at `date_preset: maximum` against the card's
number, with the paying clients out of this channel from `squad/pipeline.md` underneath it.
Crossed with no client behind it and that is the only thing on the screen. Say the honest line
once: this check happens the moment they type, not while they sleep.

Then two calls. Ad set level for the week: `amount_spent`, `impressions`, `lead`,
`cost_per_lead`, `results`, `cost_per_result`, `delivery_sub_status`, `learning_stage_info`. Ad
level for the week: `amount_spent`, `impressions`, `lead`, `cost_per_lead`,
`cost_per_video_view`, `effective_status`.

**Row zero, the status, and it comes first because it decides what the other rows mean.**
`delivery_sub_status` reading `LEARNING` prints "still learning, N of about 50 this week, so
read the rows below as a direction and not an answer," with N off `learning_stage_info`. If
`last_significant_edit_time` falls inside the window, name the day that reset the week.

**Row one, cost per lead**, against the money card's ceiling. Scale, hold, or kill.

- **Kill branch only**, the hook-rate line at ad level: `amount_spent` divided by
  `cost_per_video_view` divided by `impressions`. It is derived off a rounded currency figure,
  so call it approximate and never defend a decimal with it. Below about 24 percent, the first
  three seconds are the problem and the hook changes. At or above it with no leads, people
  stopped and did not convert, so the problem is the form or the offer, which is G5 and G6 and
  not a new ad. That 24 is where the average advertiser landed in services in the first half of
  2026, and it is a reference point, never a pass mark.
- A creative swap is a **new ad**. Ad creatives are immutable, so nothing gets edited into place.

**Row two, cost per client:** `amount_spent` divided by the clients who actually paid, from
`squad/pipeline.md`. Never from Meta. Meta cannot see a service founder's closed deals. No client
yet prints as "no client yet" with the spend behind it, never as a division by zero.

**Print all three rows, every week.** The log row at beat 13 records every one of them, and row
two is the only number that says whether this channel stays on. The change comes off the FIRST
row that misses, and the rows under it are printed to be read and logged, never as a second move.

**Never name a winning ad off a week of leads.** At this budget across three ads the counts are
single digits, and a winner is named only when two Wilson 95 percent intervals do not overlap.
Asked which ad won, print both intervals in words, say the week cannot separate them, and say
what the loop does instead: the losing ad is named by the spend rule, which is a threshold and
not a comparison.

### Beat 13 · THE ONE CHANGE

**STOP · GATE.** One move, named by the founder, one per week. Never two.

Say which move resets learning and which does not, every single time, because that is what makes
scaling reachable: a creative swap resets it, a budget raise does not, and **holding is the move
that changes nothing at all.** Two weeks with no creative swap is what clears condition 2 at beat
14, and it clears that one alone. The other three are untouched by holding.

On their word: pause through `ads_update_entity` on the status, or build the new concept paused,
or change the budget **only if they said the number in that turn.** Meta allows 4 ad-set budget
changes an hour; a rejected budget write is never retried, it is reported.

Then append one row to `squad/ads-log.md`, header line first when the file is new:

```
week ending · status · spend · leads · cost per lead vs ceiling · cost per client · the change
2026-09-07 · learning, 16 of ~50 · $700 · 16 · $43.75 vs $26 · none yet · killed ad 3, new hook
```

### Beat 14 · THE SCALE GATE, AND THE WEEKLY TASK

AUTO. Four conditions decide whether the founder may **scale**: a budget raise past the card's
line, a second ad set, a second campaign. Three are read off the account, one off their own file.
All four true or the answer is no, and you print which one failed.

| # | Condition | Where it is read |
|---|---|---|
| 1 | The ad set left the learning phase | `delivery_sub_status` is not `LEARNING`, and `learning_stage_info.status` shows it exited |
| 2 | Nothing significant changed across the window | `learning_stage_info.last_significant_edit_time` is older than the start of the two weeks |
| 3 | Cost per lead at or under the ceiling, two consecutive full weeks | `cost_per_lead` on two `time_range` calls |
| 4 | At least one client paid, out of this channel | `squad/pipeline.md`, their own row |

Say the honest part when condition 1 will not come true: at $100 a day with an expensive lead
the ad set may never clear 50 a week, so it never exits learning. That is the gate doing its
job. It says they found a direction and not a winning pattern, and automating a direction is how
the money goes.

**The weekly task is offered once, and it is not the gate above.** Its only gate is three
by-hand runs of this exact read, and the founder being able to say in one line what they changed
last time. Then, from `references/what-runs-without-you.md`: Claude Desktop, Code tab, Routines,
New routine, **Local**, weekly, press Run now once and choose always-allow on each read prompt so
it never stalls.

Sell it as what it is: **it makes sure the read happens on the days they would have skipped it.**
It runs only while the laptop is awake and the app is open, a closed lid means it lands when the
lid opens, and the thing that fires overnight is Meta's rule from beat 9. One task per founder,
and it only ever reads.

## Rules

- Every message is scannable: a short header, then a table or short bullets. The founder is
  deciding, not studying.
- Never send, never spend, never activate anything without the founder's word in that turn, and
  never write a budget number they did not say. The one named exception is the money card's own
  daily number at beat 7, onto a paused campaign, and it still faces the gate at beat 10.
- Every number comes from `squad/business.md`, `squad/ads-money-card.md`, or the account itself.
  Never invent a price, a cost per lead, a benchmark or a threshold, and never print a published
  cost-per-lead table. `references/the-numbers.md` says why.
- An ad that has run a long time is not proof of money. Sort by repeated hooks per advertiser
  and say the start date is a date.
- An empty read means re-authorise, never zero.
- Verify a field before you ask for it, and read the two learning fields at ad set level only.
- One change a week, and say which moves reset learning.
- Name a winner only when two Wilson 95 percent intervals do not overlap. When they overlap, say
  so in words and never with a decimal.
- Never build an experiment. At this budget a split test is noise on a schedule, and the tool's
  own spec requires an eligibility call this skill does not make.
- Never drive Ads Manager with a browser tool. Meta's terms forbid automated access to its
  products, and the connector is the permitted path.
- Say whose feature the overnight half is. Meta built it, it is free, and it has been there for
  years.
