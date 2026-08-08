# Recipe: Passed Hand to Hand (Referral Programs)

> The oldest marketing there is: one person tells another, because the thing was genuinely good. This
> recipe builds the structure that makes that easy — and rewards it honestly.

## What you're cooking

The best customers you'll ever get arrive because someone they trust told them to come. That kind of
growth is cheaper, stickier, and higher-quality than anything you can buy — referred customers tend to
stay longer, spend more, and refer others in turn. The trouble is it happens by accident, in ones and
twos, and you have no way to encourage it or even see it.

This recipe designs the program that turns that accident into a repeatable loop: the right moment to ask,
the easiest possible way to share, an incentive structure that's generous without being exploitable, and
the tracking that tells you whether it's actually working. It covers customer referral programs (your
customers bringing their friends) and affiliate programs (creators and partners bringing their audiences),
and helps you tell which one you actually need.

You don't need to be a growth marketer. Paste this card into your AI (Claude Code, Codex, or similar),
tell it what you sell and who buys it, and it designs the program with you — sizing the reward against
real economics, not vibes.

## Before you start

Read **The Mother Stock** first (`recipes/marketing/product-marketing-context.md`) if it exists — it
holds your positioning, audience, and economics, so the AI shouldn't re-ask what's already written down.
Only gather what the Mother Stock doesn't cover:

- **Which program.** Customers referring friends (referral), outside creators earning commission
  (affiliate), or both? Are you B2B or B2C?
- **The economics.** What's a customer worth over their lifetime (LTV), what's your gross margin, and what
  does it currently cost you to acquire one from other channels (CAC)? These numbers set the ceiling on
  what you can afford to reward.
- **The current state.** Is there a program already? Roughly what share of customers refer anyone today?
  What incentives have you tried?
- **The product fit.** Is this something people naturally talk about? Does it get better as more of a
  person's team or friends use it (network effects)?
- **The resources.** What's your budget for rewards, and what tools are you open to using?

## The method

Everything runs on one loop: a **trigger moment** prompts a **share**, the share **converts** a new
customer, the new customer earns a **reward**, and the reward feeds the next turn. Design each stage
deliberately.

**Trigger at the peak, not at random.** Ask when the customer is happiest and most convinced — right after
their first "aha" moment, after they hit a milestone, after a great support experience, after they renew
or upgrade. Asking a lukewarm user to advocate is asking them to lie; asking a delighted one is handing
them a way to share something they already feel.

**Make sharing take one action.** Ranked by how well they actually convert: in-product sharing beats a
personalized link, which beats an email invitation, which beats a social post, which beats a referral code
(though a code is the only one that works offline). Every extra step sheds people. Aim for one click.

**Choose an incentive structure that fits.** *Single-sided* (only the referrer is rewarded) is simpler and
suits high-value products. *Double-sided* (both the referrer and the friend get something) converts better
and frames the ask as a gift rather than a transaction — the referrer isn't selling, they're giving. The
classic is Dropbox: give storage, get storage, with the reward tied directly to the product's own value.
*Tiered* rewards (3 referrals earns one thing, 10 earns another) gamify the process and turn one-time
referrers into repeat ones — this is Morning Brew's stickers-to-hoodie ladder, where the reward is itself
shareable and builds identity.

**Size the reward against real math, not guesswork.** The ceiling is `(LTV × gross margin) − target CAC` —
that's the most you can pay for a referred customer and still come out ahead. Stay under it. As rough
starting points: B2C rewards tend to run $10–50 or 10–25% of the first purchase; B2B SaaS runs $50–500 or
one to three months free; enterprise goes higher and often custom. Pick a reward *type* that fits the
product too — product credit drives usage, cash feels transactional, swag is memorable and shareable, free
months are clear but can attract freebie-seekers.

**When it underperforms, diagnose the stage.** If few customers refer, the problem is upstream — you're
asking at the wrong moment, the share is too much work, or the reward doesn't land; fix the moment and the
friction first. If people share but the referrals don't convert, the problem is downstream — the landing
experience for the invited friend is weak, or their incentive is too thin; make the referrer's endorsement
visible on arrival and strengthen the new-user reward. Common failure-to-fix pairs: low awareness → a
prominent in-app prompt; low share rate → collapse it to one click; fraud → verification and per-account
limits; one-and-done referrers → a tiered ladder.

**Measure both health and impact.** Program health: active referrers (referred someone in the last 30
days), referral conversion rate, rewards paid. Business impact: the share of new customers coming from
referrals, the CAC of a referred customer versus other channels, and the program's overall ROI —
`(revenue from referred customers − program costs) / program costs`, where costs include rewards, tools,
and your time. If you want a single north star, the *viral coefficient* (K) is invitations per user times
their conversion rate: K above 1 means each customer brings more than one new one (true viral growth);
below 1 means referrals usefully amplify your other acquisition. Most healthy programs live below 1 and
that's fine.

**Launch on a checklist, then tend it.** Before launch: set goals and metrics, design the incentive, build
or configure the tool, create the referral landing page, wire up tracking and attribution, write the fraud
rules and the terms, and test the whole flow end to end. At launch: announce to existing customers, add the
in-app prompts, update the site, and brief support. In the first 30 days: watch the funnel, find your top
referrers, gather feedback, fix friction, and nudge the people who haven't referred yet.

## Acceptance Criteria (how you know it worked)

- [ ] The program asks at a defined high-intent moment (post-aha, milestone, renewal), not at a random or
  lukewarm one.
- [ ] Sharing takes one click via the highest-converting mechanism the product can support.
- [ ] The reward is sized at or under `(LTV × gross margin) − target CAC`, with the numbers shown — not
  guessed.
- [ ] Tracking and attribution exist before launch, so you can measure referral conversion rate and CAC
  by channel from day one.
- [ ] Fraud rules (verification, per-account limits) are defined before launch, not bolted on after abuse.
- [ ] There's terms-and-conditions text and a tested end-to-end flow before a single customer sees the
  program.

## Primary metric

The share of new customers acquired through referral — the plainest measure of whether the thing is
actually being passed hand to hand.

## The bright lines (never cross)

- **Reward the referral, never buy a lie.** The customer's endorsement has to be their honest opinion. An
  incentive that pushes people to vouch for something they don't believe poisons the trust that makes
  referral worth doing at all.
- **Guard against the cobra effect.** A reward that's gameable will be gamed — you'll get fraud and
  low-quality signups optimizing for the bonus, not fit. Verify, cap, and watch for it from day one.
- **Never promise a reward you won't reliably pay.** People are staking their reputation with friends on
  your behalf. Honor every earned reward, on time, exactly as stated.
- **Stay honest in every incentive claim.** No fake "limited-time" referral bonuses, no inflated reward
  values, no terms that quietly claw back what was earned.
- **Keep the referred person's data private.** An invited friend's contact details belong to them, not to
  your list — get real consent before you market to them.

---

*The phrase this card is named for comes from this cookbook's own front door: the good things get passed
hand to hand. A referral program doesn't manufacture that — it just clears the path so the handoff is easy
and the giver is thanked. Build something worth passing on first; the structure only carries what's
already good.*
