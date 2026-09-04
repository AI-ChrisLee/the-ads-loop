# The numbers, and the claims that are banned

Every figure in this lane comes from the founder's own price or from Meta's own arithmetic.
Nothing here is a benchmark somebody published, because for this buyer nobody published an
honest one.

## 1. The learning phase, which is the whole story

An ad set needs roughly **50 optimization events a week** to leave the learning phase. Below
that, Meta cannot tell signal from noise and the ad set sits in Learning Limited.

**Grade it out loud when it matters.** Meta's own page on the learning phase returns a title and
no body to every fetcher we have, so nobody on this side has read it. What is verified is that
the 50 per 7 days threshold is still the standard across dated 2026 sources with no reported
change, and that `delivery_sub_status` and `learning_stage_info` exist in the live field catalog
exactly as the rule describes. Say "Meta's own page could not be read" rather than pretending it
was.

The arithmetic that follows is arithmetic, not opinion.

**daily budget = target cost per result × 50 ÷ 7**

| Your event costs | Daily budget it needs | Per month |
|---|---|---|
| $5 | $36 | $1,071 |
| $10 | $71 | $2,143 |
| **$14** | **$100** | **$3,000** |
| $20 | $143 | $4,286 |
| $30 | $214 | $6,429 |
| $50 | $357 | $10,714 |

Read the other way, which is how a founder lives it. **What $100 a day, $700 a week, buys:**

| Cost per result | Events in the week | Share of the 50 |
|---|---|---|
| $5 | 140 | 280% |
| $10 | 70 | 140% |
| $14 | 50 | **100%** |
| $20 | 35 | 70% |
| $30 | 23 | 47% |
| $50 | 14 | 28% |

## 2. The event door, said whole

Print this at the gate, before the money leaves, and again on the money card against the
founder's own ceiling.

> At $100 a day the only event you may optimize for is one that costs $14 or less. For a service
> founder that is a form fill on Meta, and nothing published anywhere puts a service lead near
> $14. So either your own numbers beat the published ones, or you raise the budget to
> cost × 50 ÷ 7, or you accept that this lane reads a direction and never an answer, and you go
> run outreach, which answers the same question for free.

**$100 a day is a floor, not a promise, and the number does not move.** What moves is the
sentence next to it. Publishing a $6,000 floor would kill the lane for the founder we sell to,
and the budget was never the problem. The event is.

## 3. Cost per lead: the sentence that replaces the table

There is no benchmark table in this skill and there is not going to be one. The 2026 page I found
for this vertical prints two different numbers for the same trade on the same page, one of them a
projection, and discloses no sample size, no account count and no method.

The honest line:

> Nobody publishes an honest cost per lead for a solo founder selling a service. Every published
> number I found for this buyer is weak, and the closest thing to a range, $30 to $70 depending
> on the trade, sits two to five times above the $14 that $100 a day can pay for.

The ceiling comes off the founder's own price. The floor comes off Meta's own arithmetic.
Neither depends on a number a blog made up.

## 4. The two divisions

- Gross profit per client = what the client pays minus what delivery costs.
- **÷ 6** = the most that may be spent to win one client. Six is **Chris's read, stated as his
  read**, never as a measured figure. The 3 to 1 everyone quotes came out of software, where the
  product ships itself and nobody does the work. A business with people in it needs about 6 to 1,
  9 if the founder delivers every hour.
- **÷ leads per close** (default 10) = the ceiling on one lead. A wall, never a target. A real
  cost per lead sitting on the ceiling means breaking even, which is a slower way to lose.
- The payback question: in the first 30 days, does what a client pays cover twice what he cost
  to get and to serve? No means spend slowly.

## 5. Hook rate, and the threshold that never existed

Hook rate is **not a row with a target.** It is one diagnostic line inside the kill branch,
because at three ads on one ad set it changes no decision that cost per lead has not already
made, except one fork: all three ads produced nothing, and the founder cannot tell whether
nobody stopped or nobody converted after stopping.

Read at ad level as `amount_spent ÷ cost_per_video_view ÷ impressions`. The field catalog's own
display name for `cost_per_video_view` is "cost per 3-second video play," so this is the same
metric, derived. It is built on a two-decimal currency figure, so treat it as about ±10 percent
and never defend a decimal with it. `3_second_video_plays` does not exist at ad level; do not
ask for it there.

Where the average advertiser landed in the first half of 2026, off 88,329 sales-objective Meta
video ads over 1,000 impressions, $122 million of spend:

| | Hook rate |
|---|---|
| Cross-industry average | **25.44%** |
| **Services** | **23.86%** |
| Best of 14 industries (Toys and Games) | 28.79% |
| Lowest of 14 (Animals and Pet Supplies) | 21.32% |

**That source publishes no performance tiers.** The "under 30 percent means the creative is
broken" rule that used to ship here was invented, and it condemned all 14 industry averages
including the best one. Compare to 23.86 percent as a reference point and say the words "where
the average advertiser landed," never "pass mark." The sample is sales-objective video and our
founder runs lead-objective, so it transfers as a direction, not a threshold.

The fork it settles, and the only one:

- Below the baseline: the first three seconds are the problem, change the hook.
- At or above it with no leads: people stopped and did not convert, so the problem is the form
  or the offer, which is G5 and G6, not a new ad.

## 6. Naming a winner

No run names a winner unless the two **Wilson 95 percent intervals do not overlap.** When they
overlap, print both intervals in words and say the week cannot separate them. Never a decimal,
never "ad 2 is winning by 30 percent."

At $100 a day across three ads the weekly lead counts are single digits, so they always overlap.
The losing ad is named a different way, and it is not a comparison: **twice what a lead may cost
you, spent, with nothing to show.** That is a threshold on one ad's own numbers.

## 7. Banned outright

| Claim | Why |
|---|---|
| "An ad running 90+ days is an ad making money" | The library returns no performance signal at all. Ruled overselling certainty in our own 2026-08-23 audit and it stays ruled |
| Any published cost-per-lead benchmark, in any lesson or any run | See section 3 |
| A hook-rate pass mark of any number | See section 5 |
| A kill rule built on cost per lead | Undefined on an ad with zero leads, which is the ad it is hunting. Build it on spend |
| "Three second plays at ad level" | The field does not exist there |
| "Your squad reads the winners and writes the creative" | The library returns a headline and a link. A human opens three pages and looks |
| "The numbers get read every day" or "A/B tests run on their own" | Neither is true at this volume, and the read happens when the founder types |
| "Growing while you sleep," said about our half | The overnight half is Meta's own Automated Rules engine, free and first party. Say so |
