# What runs without you, and what does not

Read this before you promise a founder anything about overnight.

## 1. The honest paragraph

Three clocks run with the laptop shut and **not one of them is ours.** Instantly sends the batch
the founder approved. Meta delivers ads overnight, and Meta's own Automated Rule turns off an ad
that has spent twice the lead ceiling with nothing to show. YouTube publishes at the hour they
chose. Everything the squad itself does runs when the founder is at the laptop.

In this lane that means: **Meta already built the overnight part, go switch it on in five
minutes, and your squad's job is the morning it hands you.** A member who checks will find that
out in a minute, so they hear it here first.

## 2. Meta's Automated Rule, the one thing that fires while they sleep

Free, first party, in Ads Manager, set by hand once, checked every 30 to 60 minutes. There is no
rules tool on the connector at all, which is why it lives there and not here.

> **Ads Manager, Rules, Create a New Rule.**
> **Apply to:** all active ads.
> **Condition:** Amount spent (lifetime) is greater than **[2 × the lead ceiling]** AND Results
> is less than 1.
> **Action:** Turn off ads.
> **Schedule:** Continuously.

Fill the bracket off `squad/ads-money-card.md`.

**Why it is built on spend and not on cost per lead.** Cost per lead is spend divided by leads,
so on an ad with zero leads it has no value, and a rule engine fires only when every condition is
met. A null satisfies no threshold. A cost-per-lead rule would be hunting exactly the ads on
which its own field is empty, which is a rule that never fires. Two fields that are always real
numbers, spend and results, are what it stands on.

Said to a founder: twice what a lead may cost you, spent, with nothing to show.

**The skill's half of the same job**, and it runs when they type:
`ads_get_ad_entities` at ad level, filtered on `amount_spent > 2 × ceiling` AND `lead = 0`. The
naming is ours. The killing is Meta's.

## 3. The weekly task, and what it actually buys

The substrate is the **Claude Desktop scheduled task**, which is the only scheduler that can see
the member's own `squad/` files and their connectors at the same time.

> Claude Desktop, Code tab, Routines, New routine, **Local**, weekly.

Then press **Run now once**, answer the prompts, and choose always-allow for each read it asks
about. Permission mode is per task and Manual mode stalls a run until somebody approves it, so
the first run by hand is what stops every later run from hanging. A tool marked
`requiresUserInteraction` prompts on every call with no always-allow available, which is why this
task only ever reads: it never uploads, never activates and never changes a budget.

**What it does not buy: unattended time.** Tasks run only while the desktop app is running and
the computer is awake, and closing the lid puts it to sleep. There is exactly one catch-up run on
wake, for the most recently missed time, so a task set for 9am can land at 11pm. One of ours set
for 7:33am fired at 11:59am on 2026-09-03 for that reason.

**So sell it as what it is:** it makes sure the read happens on the days they would have skipped
it. Skipped-day insurance. Never "it runs while you sleep."

**One task per founder.** A task can be skipped because another was already running, so the
founder gets one, and in this lane it is the weekly read.

## 4. The direction rule, permanent, not a gate

> A routine that only reads, only drafts, or only reduces spend may be scheduled. A routine that
> sends, spends more, or publishes never runs unattended in this course.

## 5. Its only gate

Three by-hand runs of that exact read, and the founder can say in one line what they changed last
time. It cannot be passed by luck, it clears inside three weeks, and it gates a zero-risk action
in proportion to its risk.

The four conditions read off the account in beat 14 are a different gate on a different thing: they
decide whether the founder may **scale**, which is where the money risk actually sits.

## 6. What is never built

- **No cron, no launchd.** Headless Claude Code has no scheduler of its own and that is a
  developer path, not a member path.
- **No cloud routine.** It cannot see the member's disk, and the fix, pushing `squad/` to a
  hosted repo, would put real people's recorded words there to save one typed command.
- **No browser automation pointed at Ads Manager.** Meta's terms forbid automated access to its
  products. The connector is the permitted path; Selenium, Puppeteer, Playwright and browser
  tools driving a logged-in session are the forbidden one.
- **No scheduled budget changes.** Four ad-set budget changes an hour is the ceiling, a schedule
  buys nothing at this size, and it puts a paying member's ad account in the enforcement queue.
- **No experiment, scheduled or otherwise.** At this volume a split test is noise, and the tool's
  own spec requires an eligibility call first.
