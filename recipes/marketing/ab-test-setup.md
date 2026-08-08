# Recipe: Two Spoons (A/B Test Setup)

> Offer the crowd two versions of the same dish and watch which spoon empties first. Not the one you
> *think* they'll like — the one they actually reach for.

## What you're cooking

You have a change you're tempted to make — a new headline, a different button, a reworked pricing page — and a
quiet worry that you're guessing. Maybe you are. An A/B test (also called a split test) settles it honestly:
show half your visitors version A, half version B, change exactly one thing, and let their behavior pick the
winner instead of the loudest opinion in the room.

This recipe turns an AI into an experimentation expert. It produces a test designed to give you a real
answer, not a comforting one: a sharp hypothesis, the single thing you're varying, the sample size you need
before you're allowed to trust the result, the metrics that tell you whether it worked and whether it did any
harm, and a plan for reading the outcome without fooling yourself.

You don't need to know statistics to use this. Paste the card into Claude Code or Codex, tell it what you want
to improve and how much traffic the page gets, and it will design the test with you and explain why each rule
is there — because the rules are what keep the test from lying to you.

## Before you start

Tell the AI to read **The Mother Stock** first — `recipes/marketing/product-marketing-context.md`, the
master positioning document — if it exists, so it already knows your product, audience, and voice and only
asks for what's missing.

Then it needs three things about *this* test: the **context** (what you're trying to improve and what change
you're considering), the **current state** (your baseline conversion rate today and how much traffic the page
gets), and the **constraints** (what tools you have, how technical the change is, and your timeline). Those
numbers decide whether the test is even runnable — a low-traffic page can wait months for an answer, and it's
better to know that before you start than after.

## The method

**Start with a hypothesis, not a hunch.** Write it in one shape: *Because [what you observed], we believe
[this change] will cause [this outcome] for [this audience]; we'll know it's true when [this metric moves].*
"The button color might help" is not a hypothesis. "Because users report they can't find the call to action,
a larger high-contrast button will lift click-through to signup by 15% for new visitors" is.

**Change one thing.** Vary a single element — a headline, a layout, a call-to-action, the amount of content —
so that when the number moves you know *what* moved it. Testing many things at once (a multivariate test)
needs far more traffic and muddies the lesson. Make the one change bold enough to actually matter; a tiny
tweak produces an effect too small to detect.

**Pick the sample size before you launch, and honor it.** This is the rule the whole method turns on. The
lower your baseline and the smaller the improvement you want to catch, the more visitors you need per version.
Rough guide, per version, at 95% confidence: a page converting at 1% needs about 97,000 visitors each to
detect a 20% lift; at 3% baseline, about 31,000; at 5%, about 18,000; at 10%, about 8,700. Detecting a smaller
lift multiplies these fast — catching a 5% lift instead of 20% can mean millions of visitors. Use a
calculator (Evan Miller's or Optimizely's) and decide the number *first*.

**Run it long enough to be real.** Even with the sample in hand, run at least one full week to capture
day-of-week variation, two business cycles for B2B, and through a payday for e-commerce. But don't let it run
past four to eight weeks — novelty wears off and outside events creep in. If the math says the test would take
over 60 days, don't run it as-is: raise the effect you're willing to detect, test earlier in the funnel where
traffic is higher, combine similar pages, or decide from qualitative evidence instead.

**Choose three tiers of metric.** One **primary** metric tied directly to the hypothesis — the one you'll call
the test on. A few **secondary** metrics that explain *why* it moved. And **guardrail** metrics that must not
get worse — support tickets, refund rate — that will stop the test if the "winner" is quietly doing damage.

**Split the traffic deliberately.** A straight 50/50 is the default. Go conservative (90/10 or 80/20) when a
bad version could cost you, or ramp up slowly for a technically risky change. Keep it consistent so a
returning visitor always sees the same version, and make sure exposure is balanced across times of day and
days of the week.

**Then leave it alone.** During the test, monitor for technical breakage and note any outside events, but do
not touch the versions, do not add traffic from a new source — and above all, do not peek at the results and
stop early because one side looks ahead. Peeking and stopping the moment you see significance is the single
most common way A/B tests produce false winners; you pre-committed to a sample size precisely so you wouldn't
be tempted.

**Read the result against a checklist.** Did it reach the planned sample size? If not, it's preliminary — full
stop. Is it statistically significant (95% confidence, meaning under a 5% chance the difference is random)?
Is the effect big enough to matter in the real world? Do the secondary metrics agree? Did any guardrail slip?
Do the segments (mobile vs. desktop, new vs. returning) tell the same story? A significant winner ships; a
significant loser teaches you why; no significant difference means you need more traffic or a bolder change;
mixed signals mean dig deeper before you decide. Document every test — hypothesis, versions with screenshots,
results, and the decision — so the next test starts smarter than this one did.

## Acceptance Criteria (how you know it worked)

- [ ] The test has a written hypothesis in the "because / we believe / will cause / for / we'll know when" form.
- [ ] Exactly one variable differs between the two versions.
- [ ] A required sample size per version is calculated *before* launch, with the days-to-run it implies.
- [ ] Primary, secondary, and guardrail metrics are each named before the test starts.
- [ ] The plan states the minimum run time (at least one full week) and a stop rule for guardrail harm.
- [ ] The result is only called "won/lost" after the sample size is reached and 95% significance is checked.

## Primary metric

The one conversion metric named in the hypothesis — the share of visitors taking the target action — read only
after the pre-committed sample size is reached and 95% statistical significance is confirmed.

## The bright lines (never cross)

- **Never call a test early.** Reaching significance before the planned sample size is a false positive waiting
  to happen. Commit to the number and wait for it.
- **Never change more than one thing at once** in a simple A/B test, or you won't know what caused the result.
- **Never touch the versions mid-test** or add a new traffic source — either one contaminates the answer.
- **Never ignore the guardrails.** A "winner" that raises refunds or support load has lost; stop it.
- **Never present an inconclusive test as a win.** No significant difference is a real, honest result — say so.

---

*Two spoons, one honest question, and the patience to let the crowd answer it. The discipline isn't in
running the test — it's in not peeking before it's done.*
